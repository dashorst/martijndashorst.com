---
layout: post
status: publish
published: true
title: Thoof versus digg... will thoof survive being dugg?
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 310
wordpress_url: http://martijndashorst.com/blog/2007/10/02/thoof-versus-digg-will-thoof-survive-being-dugg/
date: '2007-10-02 22:29:49 +0200'
date_gmt: '2007-10-02 21:29:49 +0200'
categories:
- wicket
tags: []
comments:
- id: 13409
  author: Ian Clarke
  author_email: ian@thoof.com
  author_url: http://thoof.com/
  date: '2007-10-02 23:52:07 +0200'
  date_gmt: '2007-10-02 22:52:07 +0200'
  content: "We had some trouble, initially because we have a queue of events being
    written to the database, and it was filling up.  We've temporarily solved that
    one by dropping events when the queue is full (the consequences of this are not
    that serious), but this is only an interim solution.\r\n\r\nWe are currently experiencing
    memory issues, possibly a leak.  We are still debugging that one using a heap
    profiler on a live webnode (but only directing a tenth of the normal traffic to
    it)."
- id: 13487
  author: Ian Clarke
  author_email: ian@thoof.com
  author_url: http://thoof.com/
  date: '2007-10-03 17:01:50 +0200'
  date_gmt: '2007-10-03 16:01:50 +0200'
  content: "Another update, for anyone that is interested!\r\n\r\nOk, so the memory
    issue was basically that we were allocating too much memory to the JVM heap, and
    not leaving enough memory for other Java-related requirements.  We've now allocating
    2 of 8GB to the JVM heap on our webnodes, and this seems to be working well.\r\n\r\nAnother
    issue is an expensive database call we were doing on new-user creation.  We took
    some quick measures to remove this (thus temporarily reducing the effectiveness
    of our recommendation algorithm), and are now working to move this workload into
    the webnodes through caching of the necessary data."
- id: 13489
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-10-03 17:21:45 +0200'
  date_gmt: '2007-10-03 16:21:45 +0200'
  content: "A JVM heap of 2 GB is the biggest that is effective, at least on sun JVM's.
    Bigger than that and your GC pauses are taking too long.\r\n\r\nIt would be nice
    to read about how you tune the JVM to handle a load, for instance what GC you
    chose, and more importantly why, what the sizes are for the different generations.\r\n\r\nA
    traffic analysis of the digg onslaught would be nice too. I guess you were fortunate
    that there wasn't a direct link to thoof.com in the main article, so that people
    had to type the link in manually.\r\n\r\nOther interesting tidbits are:\r\n -
    number of parallel sessions per vm and its memory usage\r\n - requests per second\r\n\r\nBut
    I understand if you are too busy with tweaking a system. I suspect you are monitoring
    the jconsole and look at the heartbeat of thoof. I know I did when I was monitoring
    our own application: looking at response times, number of concurrent connections
    to database, number of garbage collections, all interesting stuff if you want
    to know the status of your application."
---
<p>With the <a href="http://digg.com">Digg</a> versus <a href="http://thoof.com">Thoof</a> commercials posted to the <a href="http://digg.com/videos_comedy/Thoof_vs_Digg">digg front page</a>, it seemed like the Thoof servers have difficulty with the load. But in one hour, the servers seem like they are up, running and humming.</p>
<p>I'm wondering if this was a load test they were expecting. It would be interesting to read a <a href="http://blog.thoof.com/?p=47" title="Thoof Blog  &raquo; Blog Archive   &raquo; Thoof vs. Digg on Digg!">blog entry</a> on the effects of being dugg.</p>
