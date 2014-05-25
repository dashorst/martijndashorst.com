---
layout: post
status: publish
published: true
title: OS X and Java developer sources
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 466
wordpress_url: http://martijndashorst.com/blog/?p=466
date: '2010-12-10 22:09:04 +0100'
date_gmt: '2010-12-10 21:09:04 +0100'
categories:
- java
- os x
tags: []
comments:
- id: 58446
  author: SteveL
  author_email: stevel@apache.org
  author_url: ''
  date: '2010-12-11 11:56:14 +0100'
  date_gmt: '2010-12-11 10:56:14 +0100'
  content: "-the java link is broken, its dynamic and as your session has expired,
    no link\r\n-you do need to fill in a survey to register. There is nowhere in that
    survey to say \"I am a java developer and intend to write x-platform applications\",
    or indeed to say that you are working on \"technology\". You have to fill in some
    check boxes that say exactly which consumer-centric product category you are working
    on.\r\n\r\nRemember: apple do technology, you, the developer, get to write consumer-centric
    apps for the mac, ipad or iphone *only*."
- id: 58586
  author: John
  author_email: johnw@gmail.com
  author_url: ''
  date: '2010-12-12 15:37:53 +0100'
  date_gmt: '2010-12-12 14:37:53 +0100'
  content: Doesn't Java 6U22 comes automatically with a system update? There seems
    to be no need to download it separately?
- id: 58593
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2010-12-12 17:47:21 +0100'
  date_gmt: '2010-12-12 16:47:21 +0100'
  content: The non-developer Java 6U22 comes with a system update, but it removes
    the JDK classes source archive, which is quite necessary as a Java developer for
    instance to look up JavaDocs or to step into when debugging. This guide allows
    you to download the <b>developer</b> tools and source files.
- id: 58594
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2010-12-12 17:49:09 +0100'
  date_gmt: '2010-12-12 16:49:09 +0100'
  content: the java link is only available when you are logged in, but it is a stable
    URL (not relative to a particular account AFAIK). In any case click on the Java
    link in the menu if the link doesn't work for you after logging in.
---
<p>With the Java 6 update 22, Apple not only set the internets on fire regarding their deprecation of Java, they also made it very hard for the core Java users on their platform to actually use the old ball and chain: developers, developers, developers.</p>
<p>It is quite hard to discover where the Apple gods decided to land the new goods, so I figured to write everything up in one blog post for posterity (and my own memory—having to go on another google hunt to do these tasks again would kill me).</p>
<p>First you need to download the developer packages from the <a href="http://connect.apple.com">connect.apple.com</a> website. This requires a free account so just register and promise your first born (as I understand it, no waving of dead chickens is necessary).</p>
<p>You can download the developer package from this location: <a href="http://connect.apple.com/cgi-bin/WebObjects/MemberSite.woa/wo/5.1.17.2.1.3.3.1.0.1.1.0.3.9.3.3.1">Apple Java downloads</a></p>
<p>Install the package and start up your favorite IDE. Now find the settings where you can tell the IDE where to find the Java sources and paste in the following for Java 6 Update 22:</p>
<p>/Library/Java/JavaVirtualMachines/1.6.0_22-b04-307.jdk/Contents/Home/src.jar</p>
<p>Navigating to that folder using Eclipse is pointless as the <tt>.jdk</tt> extension signifies a <b>package</b> and Eclipse's navigator doesn't allow "Show package contents".</p>
