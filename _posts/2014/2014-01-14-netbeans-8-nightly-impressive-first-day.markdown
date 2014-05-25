---
layout: post
status: publish
published: true
title: 'Netbeans 8 nightly: impressive first day'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 554
wordpress_url: http://martijndashorst.com/blog/?p=554
date: '2014-01-14 17:20:54 +0100'
date_gmt: '2014-01-14 16:20:54 +0100'
categories:
- java
- maven
tags: []
comments:
- id: 66546
  author: Geertjan Wielenga (@GeertjanW)
  author_email: geertjan.wielenga@oracle.com
  author_url: http://blogs.oracle.com/geertjan
  date: '2014-01-14 17:39:09 +0100'
  date_gmt: '2014-01-14 16:39:09 +0100'
  content: Nice to hear. And, on behalf of the NetBeans community, we're really looking
    forward to hearing from you how we can be even better!
- id: 66547
  author: Michel Graciano
  author_email: michel.graciano@gmail.com
  author_url: http://www.michelgraciano.com.br
  date: '2014-01-14 18:06:44 +0100'
  date_gmt: '2014-01-14 17:06:44 +0100'
  content: "I am glad to hear that you have a good start. I hope you have more pleasant
    days to come. BTW, if you will sticky with NetBeans, no matter if as the only
    IDE or a choice for your team, I think you maybe want to join NetCAT team [1].
    We are early adopters which tests the IDE in our daily projects and help the NB
    team to stabilizes it before release. So, if you really are considering to use
    NetBeans, it is a great place to have one or two developers working on. I have
    been helping NetBeans for years and NetCAT has helped me to keep the IDE always
    stable ans updated in our company's projects because I have fixes really quickly
    and mostly, I can avoid regressions between versions.\r\n\r\nAn additional comment:
    I have migrated the formatting settings from Eclipse to NetBeans recently with
    more than 90% accuracy, so I think you won't have much problem with that in your
    journey.\r\n\r\nBest regards.\r\n[1] http://wiki.netbeans.org/NetCAT"
---
<p>We are busy implementing a new project that is augmented onto an existing application. We ran into some issues with Eclipse and its m2e plugin that caused us to look elsewhere–notably IntelliJ and Netbeans.</p>
<p>The old application is a monolithic, multi-module (51 in total) maven build that results in a couple of 140MB war files that are deployed into a tomcat server. It has dependencies on the whole non-JEE world: Spring, Hibernate, CXF to name a few. We have implemented our own cement between Spring, Hibernate and CXF, and use Spring only to bootstrap our services and perform the odd injection into Wicket applications. So while we have Spring on our class path, I would hesitate to call our application a 'Spring application'.</p>
<p><span style="line-height: 1.5;">The new application we are crafting </span>upon<span style="line-height: 1.5;"> this gigantic monolith will be deployed into Wildfly. We are starting to embrace JEE as our development platform because we are tired of writing the integrations between the </span>disparate<span style="line-height: 1.5;"> services ourselves. Our new application consists of many Maven modules and will provide a decoupling between our database layer and our Wicket layer through a REST api. I'll discuss that in  a later post.</span></p>
<p>One of the things we needed to solve was cache synchronisation between our old application and new application: this is achieved by transforming the non-anemic entities from the old application into anemic entities for use in our new project. A custom maven plugin  strips all non-JPA properties and methods, and generates getters and setters for the properties. The plugin retains the JPA annotations.</p>
<p>Another thing we want to use in our new application is the JPA meta-model generation. This allows us to create typesafe JPA queries, which is great going forward in our JEE architecture.</p>
<p>Trying to get all this goodness to work in Eclipse forced us to upgrade Eclipse to the latest development build 4.4M4, as anything else failed to actually do anything with this monster. We were able to get this to work sort-of, but at the cost of roughly 5 man days of downloading, installing and upgrading Eclipse.</p>
<p>When we finally got Eclipse in a circular build, we figured that other IDEs might have a better solution to our travails. I remained sceptical since my previous encounters with Netbeans and <a title="Why I don’t consider IntelliJ IDEA to be the best Java IDE" href="http://martijndashorst.com/blog/2013/11/04/intellij-not-the-best-for-me/">IntelliJ have been less than successful</a>. So one of my co-workers downloaded the latest IntelliJ Ultimate edition, and I started with Netbeans.</p>
<p>First I downloaded Netbeans 7.4, and tried to install the Wildfly plugin, but the module server went down right at the moment after I had selected the plugin to download. So I figured that I could just as well download the Netbeans 8 nightly since that has the Wildfly plugin already in its module index.</p>
<p>Long story short: I got Netbeans 8 and Wildfly integration to work with our full project setup in less than 4 hours. And everything appears to work as we expect. I am really impressed with this feat: an IDE I have never worked with for more than a couple of hours beat an IDE I have lived 10 hours a day, 5 days a week for the past 10 years with setting up this beast of a project.</p>
<p>Hat tip to the Netbeans community for this impressive result.</p>
<p>Now I'll start and actually use Netbeans in day-to-day work to see if we all should use it. I have a couple of gripes already, but I'll save that for my twitter rants, and a followup post detailing all that is wrong with Netbeans... But for now I am really happy with Netbeans and hope that it continues to impress me.</p>
