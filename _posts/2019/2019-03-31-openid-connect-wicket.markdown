---
layout: post
status: draft
published: false
title: Using PAC4J OpenID Connect to authenticate in Wicket
---

At €-job we use [Topicus KeyHub](https://topicus-keyhub.com) for our Identity and Access Management (IAM). 
It guards all our servers and services. It is used as a vault for shared passwords. It is awesome.
But this post is not about Topicus KeyHub. It is about using PAC4J OIDC in an Apache Wicket application to authenticate a user.

It was something I figured was really hard, difficult and not very well integrated into Wicket.
While it is not very well integrated into Wicket, it is actually not necessary to integrate.
My final solution was about 20 lines of code to point PAC4J to the OIDC endpoint of our 
Topicus KeyHub installation and let it do the secret handshakes.

So first you need a Wicket application, easily generated from a [quick start](http://wicket.apache.org/start/quickstart.html).
Next you need to modify the POM, to add the following dependencies:

- org.apache.wicket:wicket-auth-roles
- org.pac4j:pac4j-oidc

You add them in the `dependencies` section (don't forget to add the `pac4j.version` property, the version 
at the time of writing is: 3.6.1, but you should check for the most recent version):

```xml
<dependencies>
	<dependency>
		<groupId>org.apache.wicket</groupId>
		<artifactId>wicket-core</artifactId>
    <version>${wicket.version}</version>
	</dependency>
	<dependency>
		<groupId>org.apache.wicket</groupId>
    <artifactId>wicket-auth-roles</artifactId>
		<version>${wicket.version}</version>
	</dependency>
	<dependency>
		<groupId>org.pac4j</groupId>
		<artifactId>pac4j-oidc</artifactId>
		<version>${pac4j.version}</version>
	</dependency>
  ...
```

Just because it is already 2019, you can upgrade the settings to use a modern version of 
Java (out of the box Java 8 is specified).

```xml
<plugin>
  <inherited>true</inherited>
  <groupId>org.apache.maven.plugins</groupId>
  <artifactId>maven-compiler-plugin</artifactId>
  <version>3.8.0</version>
  <configuration>
    <source>11</source>
    <target>11</target>
    <encoding>UTF-8</encoding>
    <showWarnings>true</showWarnings>
    <showDeprecation>true</showDeprecation>
  </configuration>
</plugin>
```

This is the default setup. To confirm that the application works you can 
run the `Start` class in the `src/test/java/` structure, or use the `mvn jetty:run` command.

If you get the following screenshot you're golden.

Next you need to create a page that can only be accessed after authenticating through an Open ID Connect handshake.

First create a HTML file (`SecuredPage.html`):

```html
<!DOCTYPE html>
<html>
<head><title>Secured Page</title></head>
<body>
<h1>TOP SECRET</h1>
<p>42</p>
</body>
</html>
```

And then create a Java class (`SecuredPage.java`) next to it:

```java
@AuthorizeInstantiation("ADMIN")
public class SecuredPage extends WebPage {
    public SecurePage() {
    }
}

public class ConversieApplication extends WebApplication {
  @Override
  public void init() {
    super.init();

		mountPage("secure", SecuredPage.class);
  }
}
```

The annotation `@AuthorizeInstantiation("ADMIN")` will ensure that only authorized users can access the page.
You also add a _mount_ to the page under the `/secure` path.

But for that to happen, you need to instruct Wicket to check for the annotation and check whether the user was authenticated.
You have to modify the WicketApplication for that. From the `wicket-auth-roles` project we can implement the interface `IRoleCheckingStrategy`:

```java
public class ConversieApplication extends WebApplication implements IRoleCheckingStrategy {
  @Override
  public void init() {
    super.init();

		mountPage("/secure", SecuredPage.class);

    getSecuritySettings()
      .setAuthorizationStrategy(
        new AnnotationsRoleAuthorizationStrategy(this));
  }

	@Override
	public boolean hasAnyRole(Roles roles) {
		return WebSession.get().getAttribute("oidc") != null;
	}
}
```

When you try to access the `/secure` path in our application you will get an authorization error. This is great, but
you want to authenticate against an OIDC endpoint. For this you need two things:

1. a place to do the OIDC authentication handshake with the endpoint
2. a redirect to the handshake when the user is not authenticated

Let's start with 2. For this you register a handler when a component (our SecuredPage) is instantiated without the necessary permissions:

```java
public class ConversieApplication extends WebApplication implements IRoleCheckingStrategy {

  @Override
  protected void init() {
    // ....
    getSecuritySettings().setUnauthorizedComponentInstantiationListener(
        c -> new RestartResponseAtInterceptPageException(OidcPage.class)
    );
  }
}
```
When the user is not logged in, Wicket tries to instantiate the `SecuredPage`, but is prevented from doing so and the
event handler you registered in `init()` is called.

The execption 

