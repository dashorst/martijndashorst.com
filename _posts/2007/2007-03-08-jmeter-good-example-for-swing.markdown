---
layout: post
status: publish
published: true
title: JMeter good example for swing?
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 241
wordpress_url: http://martijndashorst.com/blog/2007/03/08/jmeter-good-example-for-swing/
date: '2007-03-08 16:48:45 +0100'
date_gmt: '2007-03-08 15:48:45 +0100'
categories:
- java
tags: []
comments:
- id: 630
  author: n8han
  author_email: nathan@technically.us
  author_url: http://technically.us/n8/
  date: '2007-03-08 17:26:31 +0100'
  date_gmt: '2007-03-08 16:26:31 +0100'
  content: That j.l. article is more about Java 6, right? But the funny thing is that
    Swing on Apple's JVM has had a "native" L&amp;F at least as accurate as Sun Java
    6's (on Windows and GNOME) for a very long time. I doubt if Apple's version 6
    runtime will be much of an improvement over previous versions, but I guess if
    I really cared I could install the beta to find out. Anyway, you make a good point
    here. Typical Java programmers (API writers and users) are sooooo far behind in
    good interfaces; having achieved a decent visual representation, they declare
    victory even though freaking keyboard bindings and the clipboard still can not
    be expected to work reliably!
- id: 635
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-03-08 22:22:45 +0100'
  date_gmt: '2007-03-08 21:22:45 +0100'
  content: Even if I select the native OS X l'n'f it just seems sort of off... and
    it is still dog slow, and still consumes hogs of memory.
---
<p>I've been using <a href="http://jakarta.apache.org/jmeter">JMeter 2.2</a> for recording and running a couple of load tests on our new server. Now a lot of people are suggesting that <a href="http://www.javalobby.org/java/forums/t91191.html">Swing is ready for the desktop</a>, at least for Linux. Well, my experience with JMeter on OS X is far from stellar:</p>
<ul>
<li>copy/paste/etc are not compatible with OS X defaults, but use the *shudder* Windows bindings</li>
<li>there is no undo</li>
<li>I can't get the data copy/pasted into other applications (textmate)</li>
<li>you never know if jmeter has saved any test script, there is no feedback, and I've lost a couple of hours worth of proxied test script generation</li>
<li>it is a true memory hog</li>
</ul>
<p>As far as I can see, JMeter is a showcase of everything people expect from a Java desktop application. There is a whole world open for new and better open source projects to build a decent load testing application.</p>
