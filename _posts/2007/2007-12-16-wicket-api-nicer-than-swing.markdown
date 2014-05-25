---
layout: post
status: publish
published: true
title: Wicket API nicer than Swing?
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 330
wordpress_url: http://martijndashorst.com/blog/2007/12/16/wicket-api-nicer-than-swing/
date: '2007-12-16 23:46:18 +0100'
date_gmt: '2007-12-16 21:46:18 +0100'
categories:
- wicket
tags: []
comments:
- id: 26257
  author: Ryan Sonnek
  author_email: ryan@codecrate.com
  author_url: http://ryan.codecrate.com
  date: '2007-12-17 01:57:57 +0100'
  date_gmt: '2007-12-17 00:57:57 +0100'
  content: "Thanks for the reference Martijn.  What I think is particularly compelling
    about developing with Wicket is the true \"separation of concerns\".  It's the
    \"holy grail\" of *any* development framework or API.  Keep presentation and logic/behavior
    separate.  \r\n\r\nHTML and CSS have come to rule the presentation layer, and
    Wicket does an *amazing* job of keeping logic out of the view layer.  unlike some
    other frameworks *cough* JSP *cough*...\r\n\r\nIf Swing (or some other framework)
    could get rid of Java for layout/presentation, and use Java for what it was intended
    for, behavior and logic, we'd be one step closer to great client side development
    API's."
- id: 35671
  author: John Sorat
  author_email: vsggrp@gmail.com
  author_url: ''
  date: '2008-02-05 16:11:43 +0100'
  date_gmt: '2008-02-05 15:11:43 +0100'
  content: "Have you tried Click?\r\nhttp://click.sourceforge.net/\r\n\r\nIt's incredibly
    simple than Wicket... no nested inner classes... Uses Velocity for the 'view'..."
- id: 35674
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2008-02-05 16:24:45 +0100'
  date_gmt: '2008-02-05 15:24:45 +0100'
  content: "Yes I believe you when you claim it is incredibly more simple than Wicket.
    That is why I use Wicket, because it solves my problems with state management,
    back button support, Ajax components, creating reusable components, fine-grained
    component level security, large community, scripting less templates (i.e. *NO*
    Velocity which is a BIG plus), and more.\r\n\r\nIf you can't manage inner classes,
    then yes, probably Click clicks with you."
---
<p>Not so long ago people complained about writing web applications being boring, not fun, or cumbersome. Though there is enough to complain about the Swing API (at least according to those that complain), it is generally considered to be a well thought out API.</p>
<p>
	So it is especially noteworthy when someone returns to Swing programming and longs for his web framework API. Ryan Sonnek <a href="http://www.jroller.com/wireframe/entry/still_swinging" title="code_poet : Weblog">writes</a>:</p>
<blockquote><p>I do miss Wicket quite a bit though. There are a lot of similarities between Wicket and Swing, but I think the Wicket API is much nicer.</p></blockquote>
<p>In my opinion the message here is not that Swing has a bad API, or Wicket's API is much better (this is merely the opinion of one coder), but rather that web development has come a long way, at least when you use <a href="http://wicket.apache.org/" title="Apache Wicket - Home">Wicket</a>.</p>
