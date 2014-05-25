---
layout: post
status: publish
published: true
title: Maven-eclipse-plugin woes fixed
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 432
wordpress_url: http://martijndashorst.com/blog/2009/05/29/maven-eclipse-plugin-woes-fixed/
date: '2009-05-29 09:31:15 +0200'
date_gmt: '2009-05-29 08:31:15 +0200'
categories:
- wicket
- maven
tags:
- eclipse
- maven
comments:
- id: 57607
  author: Gabriel K.
  author_email: gabriel.kastenbaum@gmail.com
  author_url: ''
  date: '2009-05-29 15:17:52 +0200'
  date_gmt: '2009-05-29 14:17:52 +0200'
  content: "I don't buy a car because the garage mechanic is a smart and pleasant
    guy...\r\n\r\n\r\nBut unfortunatly there is no real good replacement to maven.
    So I am obliged to buy This Trabant/Maven..."
- id: 57618
  author: Abel Muiño
  author_email: amuino@gmail.com
  author_url: http://ramblingabout.wordpress.com
  date: '2009-06-01 16:31:40 +0200'
  date_gmt: '2009-06-01 15:31:40 +0200'
  content: Instead of relaying on the command line for configuring your IDE, you might
    like to give <a href="http://www.eclipse.org/iam/" rel="nofollow">Eclipse IAM</a>
    a test drive.
- id: 57663
  author: Daniele
  author_email: ildella@gmail.com
  author_url: http://lazydev.ildella.net/
  date: '2009-06-08 21:34:53 +0200'
  date_gmt: '2009-06-08 20:34:53 +0200'
  content: "@Babriel: you can give buildr and gradle a try: http://lazydev.tumblr.com/tagged/tools\r\n\r\nanyway,
    great that new eclipse plugin allows to \"and adding a project link instead of
    a jar dependency.\" I really miss that feature a lot!"
---
<p>There is quite some anti-mavenism going around, about plugins suddenly not working, etc. And often this is true, case in point: maven-eclipse-plugin version 2.6 botched all projects working with Wicket by being very anal about what should live in the src/main/java directory tree (only Java files! God forbid you'd like to put web resources such as .properties (i18n for your web components), .js, .css, .html, etc next to your Java files. This version not only broke Wicket projects, but AspectJ as well.</p>
<p>Fortunately, the Maven community (more specifically Barrie Treloar and Arnaud Heritier) were helpful in finding the root cause of our pain: a conflict in merging the resources paths during the classpath generation.</p>
<p>With the latest snapshot of maven-eclipse-plugin 2.7 we now have our old build stability back, and can enjoy the new features of the maven-eclipse-plugin, such as searching your workspace for projects that are snapshot dependencies, and adding a project link instead of a jar dependency.</p>
<p>Yes, maven can sometimes be a pain, but ultimately with a great supporting and responsive community it will deliver. Many thanks to Barrie and Arnaud for being patient with us.</p>
