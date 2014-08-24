---
layout: post
status: publish
published: true
title: 'Maven Release plugin: a lesson in pain, failure and depression'
author: Martijn Dashorst
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
date: '2014-08-22 18:30:00 +0100'
---

When trying to release Wicket using the maven-release-plugin I'm often
presented with a failed build because Maven couldn't upload to Apache's
Nexus instance (remote closed the connection). Of course that
[shouldn't happen][4] but I'm [not holding my breath][5] for a solution
anytime soon.

The failed build causes me to have to restart the release from scratch.
Now folks have told me previously that I need to run

- `cd target/checkout`
- `mvn -rf module deploy`

instead of using the release plugin. However, this is not very
pragmatic when you have to provide all parameters configured in the
build script at the command line, and it goes against all my principles
of having an automated build.

So I figured to configure the maven-deploy-plugin [to retry
uploads][2], and only [upload at the end][3] so I first get test
failures and not a half filled staging repository when something goes
awry:

{% highlight xml %}
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-deploy-plugin</artifactId>
    <version>2.8.1</version>
    <configuration>
        <retryFailedDeploymentCount>10</retryFailedDeploymentCount>
        <deployAtEnd>true</deployAtEnd>
    </configuration>
</plugin>
{% endhighlight %}

Lo and behold, this doesn't work, because the Maven Deploy Plugin no
longer uploads anything during "release:perform".

So you think: no problem I just run mvn deploy from the checkout and be
done with it... Nope. Maven:

- starts building the artefacts **again** and
- testing them **again** (for the 3rd time) and
- packaging them **again** 
- and ...

How anyone can actually use this contraption effectively is beyond me.
And it appears I'm [not the only one.][1]

What now? 

[1]: http://axelfontaine.com/blog/final-nail.html
[2]: http://maven.apache.org/plugins/maven-deploy-plugin/deploy-mojo.html#retryFailedDeploymentCount
[3]: http://maven.apache.org/plugins/maven-deploy-plugin/deploy-mojo.html#deployAtEnd
[4]: https://issues.apache.org/jira/browse/INFRA-7812
[5]: https://issues.apache.org/jira/browse/INFRA-7984
