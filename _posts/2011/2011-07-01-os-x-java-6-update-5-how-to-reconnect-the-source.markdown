---
layout: post
status: publish
published: true
title: 'OS X Java 6 update 5: how to reconnect the source...'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 485
wordpress_url: http://martijndashorst.com/blog/?p=485
date: '2011-07-01 12:36:02 +0200'
date_gmt: '2011-07-01 11:36:02 +0200'
categories:
- wicket
tags:
- os x
- java
comments:
- id: 60698
  author: Justin Lee
  author_email: jlee@antwerkz.com
  author_url: http://antwerkz.com
  date: '2011-07-01 20:13:04 +0200'
  date_gmt: '2011-07-01 19:13:04 +0200'
  content: I can't find my way to that file anywhere on ADC.  Any tips?
- id: 60699
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2011-07-01 20:21:25 +0200'
  date_gmt: '2011-07-01 19:21:25 +0200'
  content: I just updated the post with directions.
- id: 60700
  author: Justin Lee
  author_email: jlee@antwerkz.com
  author_url: http://antwerkz.com
  date: '2011-07-01 20:28:58 +0200'
  date_gmt: '2011-07-01 19:28:58 +0200'
  content: That did it thanks.  That used to be much easier to get to.
- id: 60720
  author: Mike Swingler
  author_email: swingler@apple.com
  author_url: ''
  date: '2011-07-06 02:46:38 +0200'
  date_gmt: '2011-07-06 01:46:38 +0200'
  content: "The direct links are:\r\nJava for Mac OS X 10.6 Update 5 Developer Package:\r\n\r\n\r\nJava
    for Mac OS X 10.5 Update 10 Developer Package:\r\n\r\n\r\nYou can also just directly
    create a new JRE config in Eclipse with the src.jar and docs.jar already wired
    up to the 1.6.0_26-b03-384.jdk bundle by doing the following:\r\nEclipse &gt;
    Preferences… &gt; Java &gt; Installed JREs &gt; Search…"
---
<p>With each update of Java on OS X, Apple nukes all the things you have done to ensure a proper ability to peruse the JDK source files. Which is a pita being a Java developer. How do you get the source again in your IDE (in my case Eclipse Indigo):</p>
<ul>
<li>Download and install the javadeveloper_for_mac_os_x_10.6__10m3425.dmg from developer.apple.com (free registration required)</li>
<li>Install the client update (comes from the automatic update functionality in OS X), it doesn't matter in which order you do these two steps)</li>
</ul>
<p>Next run the following commands in a terminal:</p>
<pre>cd /System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home
sudo ln -s /Library/Java/JavaVirtualMachines/1.6.0_26-b03-384.jdk/Contents/Home/src.jar
sudo ln -s /Library/Java/JavaVirtualMachines/1.6.0_26-b03-384.jdk/Contents/Home/docs.jar</pre>
<p>Eclipse will now be able to find the sources for the Java classes.</p>
<p>If you have problems finding the OS X Java developer downloads:</p>
<ul>
<li>Go to: <a href="http://developer.apple.com/resources/">Resources</a></li>
<li>Click on "developer downloads"</li>
<li>Click on "Java" in the right side menu</li>
</ul>
<p>Apple made it impossible to provide a direct link, so you'll have to navigate the developer website yourself.</p>
<p>(updated with navigation to Java downloads)</p>
