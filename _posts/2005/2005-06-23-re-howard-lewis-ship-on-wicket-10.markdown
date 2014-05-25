---
layout: post
status: publish
published: true
title: 'Re: Howard Lewis Ship on Wicket 1.0'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 173
wordpress_url: http://martijndashorst.com/2005/06/23/re-howard-lewis-ship-on-wicket-10/
date: '2005-06-23 00:08:05 +0200'
date_gmt: '2005-06-23 00:08:05 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>Howard Lewis Ship has <a href="http://howardlewisship.com/blog/2005/06/wicket-10.html">commented</a> on the <a href="http://www.theserverside.com/news/thread.tss?thread_id=34725">release announcement of Wicket 1.0 at the serverside</a> and <a href="http://www.jroller.com/page/JonathanLocke/20050622#wicket_1_0_launched_and">Jonathan Locke responded</a> to that. Here's my addendum to those comments:</p>
<p>First I thank you, Howard, for your interest in Wicket. I hope to meet you and share a (couple of) beers at JavaOne.</p>
<blockquote><p><i>At the end of the day, it's great to see folks "gunning" for Tapestry, it's a kind of validation.</i></p></blockquote>
<p>Even though most people will state that we are 'attacking' Tapestry, the reality is different, if you ask me. Both Tapestry and Wicket are aiming at the same group: the developers currently working with Model2 frameworks. In a sense we are competing (which is only good according to many people) since we are both fishing in the same pond. We are not aiming to take over any Tapestry developer, even though I suspect there will be some that will cross over. We are hoping to lure model 2 developers and in greater quantities than Tapestry and JSF :-)</p>
<blockquote><p><i>I'm concerned that each session will get a giant serialized tree of components, something that Tapestry's structure works exceptionally hard to avoid</i></p></blockquote>
<p>With what I've come to understand of Tapestry is that in order to support page pooling, you have to use the dynamically generated properties, or reset your page at the end of the request into a virgin state. Putting this responsibility on the shoulders of the developer makes it rather complex and error prone to build applications using Tapestry development.</p>
<p>Furthermore, I read somewhere (I can't seem to find the quote) that it is very easy to slap 4GB of memory in a server, and when you've filled that up with sessions, lack of processing power and bandwidth problems have become your closest friends.</p>
<p>For failover clustering this will be a problem, but Wicket does or will (with 1.1) allow you to control maximally what enters up in your session. I think however that the main bulk of development doesn't have the requirement to do failover clustering, so I think the choice to enable quick and easy application development is correct. When the going gets tough and the session size becomes a problem Wicket allows you to tweak that.</p>
<p>I hope to meet you on JavaOne and share some insights (I'd <em>love</em> to hear more about Hivemind, as I want to use it in one of our projects).</p>
