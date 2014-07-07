---
layout: post
status: publish
published: true
title: 'Create your own Custom Eclipse Luna'
author: Martijn Dashorst
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
date: '2014-07-07 18:30:00 +0100'
date_gmt: '2014-07-07 17:30:00 +0100'
categories:
---

Ever dreamed of a lean mean Eclipse machine? So did we–and we think we
are now living the dream!

At work we have about 30-35 developers working with Eclipse. Each
developer has to download their own Eclipse bundle, and ask their
co-workers which version they should get:

 - Eclipse for Java Developers
 - Eclipse for JavaEE Developers
 - Eclipse Platform SDK

Neither of these bundles are perfectly alligned with our daily needs.

We are Java developers but use Github for our code repositories. We use
Maven (and have migrated our projects to utilize M2E). We have migrated
from Subversion to Git a while ago. The Eclipse for Java Developers is
bundled with Subversion support, Mylyn support (who uses that?) and
some other plugins we don't use. So while a good starting point it
already comes with bagage.

> Low-cost airlines motto for development environments: extra bagage
> costs more.

We are in the transition moving away from our custom monolithic
platform (tomcat/spring/hibernate/wicket/cxf) on towards a more
commonly accepted platform based on JavaEE 7, where we can skip direct
dependencies in favor of a pre-packaged, pre-integrated container.

This migration towards JavaEE would suggest that the Eclipse for JavaEE
(EJEE for short) developers would be ideal for us. But it isn't, far
from it! EJEE is slow, enables too many non-essential validations,
checks and other tripe that keeps your workspace rebuilding for the
next couple of months.

This means that folks would probably download the EJEE edition, and get
bogged down in plugins that you need to suspend (with a [low success
rate][1]), or have to go on a treasure hunt to find the right plugins.

A typical fresh and clean Eclipse installation would take about 2 hours
of work to get up and running with the proper tooling and plugins
installed. With Eclipse Luna now available, our company was looking for
a serious productivity dip while developers are installing the latest
and greatest.

## Enter yoxos

In our friday "innovation day" project we discovered [yoxos][2]: a way
to craft and distribute your own custom Eclipse builds and profiles.
This was exactly what the doctor ordered!

We were able to craft our own custom Eclipse profile with proper
initial settings (like use native polling/hooks to monitor file system
changes), nice plugins (like [qwickie][3]), and without unnecessary
baggage such as a JPA-validator that can't cope with 800 entities.

All our developers can have a working custom JavaEE Eclipse setup in
about 10 minutes. With yoxos we can distribute updates to our setup
without any issue. And best of all: our developers can still customize
their setup if they choose.

It is also possible to create custom profiles for varying projects that
need a particular plugin installed (for example an Android project).

There are some (minor) issues with yoxos though:

 - the *yoxos advanced launcher* doesn't work on ubuntu
 - yoxos doesn't have a way to provision [M2E connectors][4]
 - there is no way to add your own profile to the launcher making it
   more easy to start your custom Eclipse
 - checking out source code for your workspace from the profile doesn't
   work (as well) when using private github repositories

We'd also like to be able to provision a wildfly local server and
launch configuration using yoxos, but alas that is still something we
need to do manually.

## Summary

Yoxos is highly recommended for crafting your own custom Eclipse
distribution inside your company (or university).

Our previous setup model:

1. download a Eclipse distribution
2. start Eclipse
3. wait for eclipse "rebuild workspace" to complete
4. go to marketplace
5. select, accept and install plugins
6. restart
7. wait for eclipse "rebuild workspace" to complete
8. add update sites to eclipse to add more plugins
9. add more plugins
10. accept licenses and wait for downloads
11. restart eclipse
12. wait for eclipse "rebuild workspace" to complete
13. remember which checkmarks you need to set to make Eclipse workable
14. wait for eclipse "rebuild workspace" to complete
15. try to disable a random plugin to get rid of idiotic webservice validations
16. give up

Our new model:

1. download Yoxos launcher
2. start Yoxos launcher
3. log in
4. Download our profile
5. Launch our eclipse profile
6. Accept licenses and wait for downloads
7. Wait for eclipse "rebuild workspace" to complete
8. Start coding
9. Profit!

[1]: http://stackoverflow.com/questions/24530185/how-to-disable-apt-web-service-validation-in-eclipse-4-4-edition-for-javaee-deve
[2]: http://yoxos.eclipsesource.com
[3]: https://code.google.com/p/qwickie/
[4]: http://grumpyapache.blogspot.nl/2011/08/mess-that-is-m2e-connectors.html
