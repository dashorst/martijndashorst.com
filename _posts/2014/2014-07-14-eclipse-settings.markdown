---
layout: post
status: publish
published: true
title: 'M2E Eclipse Settings Plugin'
author: Martijn Dashorst
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
date: '2014-07-15 01:30:00 +0100'
date_gmt: '2014-07-15 00:30:00 +0100'
---

At work (Topicus) we just [released a M2E plugin][1] for Eclipse that
enables you to manage your workspace settings for your team from your
Maven POM file.

The M2E Settings plugin allows you to specify your Eclipse settings
once, and have them delivered across your team with ease.

If you are still using the maven-eclipse-plugin to generate your
project files and use [its configuration jar setup](http://maven.apache.org/plugins/maven-eclipse-plugin/eclipse-mojo.html#additionalConfig)
you can now switch to using M2E because our plugin will maintain these
settings for you.

You could configure the maven-eclipse-plugin in your project's POM like so:

{% highlight xml %}
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-eclipse-plugin</artifactId>
    <version>2.9</version>
    <dependencies>
        <dependency>
            <groupId>com.example.settings</groupId>
            <artifactId>eclipse-settings</artifactId>
            <version>1.0</version>
        </dependency>
    </dependencies>
    <configuration>
        <additionalConfig>
            <file>
                <name>.settings/org.eclipse.jdt.core.prefs</name>
                <location>/org.eclipse.jdt.core.prefs</location>
            </file>
            <file>
                <name>.settings/org.eclipse.jdt.ui.prefs</name>
                <location>/org.eclipse.jdt.ui.prefs</location>
            </file>
			<file>[...]</file>
			<file>[...]</file>
			<file>[...]</file>
        </additionalConfig>
    </configuration>
</plugin>
{% endhighlight %}

So previously you had to manually apply the settings using the
maven-eclipse-plugin. This would copy all the configured files to their
locations, and configure Eclipse (a restart of the workspace is
typically required):

{% highlight bash %}
$ mvn eclipse:eclipse
...
$ 
{% endhighlight %}

And with the right configuration this would create, amongst other
things for each of your projects a `.settings` folder with your
configuration files:

{% highlight bash %}
$ ls -l .settings/
total 160
-rw-r--r--  1 dashorst  staff     85 Nov 29  2013 edu.umd.cs.findbugs.plugin.eclipse.prefs
-rw-r--r--  1 dashorst  staff     88 Nov 29  2013 org.eclipse.core.resources.prefs
-rw-r--r--  1 dashorst  staff    206 Nov 29  2013 org.eclipse.jdt.apt.core.prefs
-rw-r--r--  1 dashorst  staff  29892 Nov 29  2013 org.eclipse.jdt.core.prefs
-rw-r--r--  1 dashorst  staff  11754 Nov 29  2013 org.eclipse.jdt.ui.prefs
-rw-r--r--  1 dashorst  staff     86 Apr  5  2013 org.eclipse.m2e.core.prefs
-rw-r--r--  1 dashorst  staff    575 Nov  7  2013 org.eclipse.wst.common.component
-rw-r--r--  1 dashorst  staff    167 Apr 19  2013 org.eclipse.wst.common.project.facet.core.xml
-rw-r--r--  1 dashorst  staff    403 Nov 29  2013 org.eclipse.wst.validation.prefs
-rw-r--r--  1 dashorst  staff     77 Aug 25  2013 org.hibernate.eclipse.console.prefs
-rw-r--r--  1 dashorst  staff    262 Nov 29  2013 org.maven.ide.eclipse.prefs
$ 
{% endhighlight %}

Unfortunately with the advent of Eclipse 4.3 and its M2E integration,
the maven-eclipse-plugin can no longer be used. But we still want the
settings to be applied to all our projects.

In comes an Eclipse plugin that hooks up M2E and the
maven-eclipse-plugin to use the same configuration and instructs M2E to
fulfill the role of the maven-eclipse-plugin.

The *M2E Settings* plugin piggybacks on the configuration you already
had in place for the maven-eclipse-plugin. This makes it easier to
migrate your team members without forcing everyone to start using M2E.

For more information about the M2E Settings plugin, take a look at the
[project on Github][1] and try it out. It should be added to the
Eclipse Marketplace somewhere tomorrow, making it easier to find and
install.

This plugin was made possible by [Olivier
Nouguier](https://github.com/cheleb), so many thanks for his initial
work.

Go check out the [M2E Settings Plugin][1] and have fun!

[1]: https://github.com/topicusonderwijs/m2e-settings