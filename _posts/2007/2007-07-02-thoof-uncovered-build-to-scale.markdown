---
layout: post
status: publish
published: true
title: 'Thoof uncovered: Build to scale'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 278
wordpress_url: http://martijndashorst.com/blog/2007/07/02/thoof-uncovered-build-to-scale/
date: '2007-07-02 23:49:29 +0200'
date_gmt: '2007-07-02 22:49:29 +0200'
categories:
- wicket
tags: []
comments:
- id: 5308
  author: StÃ©phane
  author_email: sboisson@gmail.com
  author_url: ''
  date: '2007-07-04 16:11:58 +0200'
  date_gmt: '2007-07-04 15:11:58 +0200'
  content: Cool! We picked Wicket 1.3+iBatis 2.2 for our site too!
- id: 5338
  author: Jonathan Locke
  author_email: jonathan.locke@gmail.com
  author_url: ''
  date: '2007-07-05 05:06:14 +0200'
  date_gmt: '2007-07-05 04:06:14 +0200'
  content: Good choice!
- id: 7889
  author: Eduardo Sasso
  author_email: eduardo.sasso@gmail.com
  author_url: http://blog.context.com.br
  date: '2007-08-10 15:45:46 +0200'
  date_gmt: '2007-08-10 14:45:46 +0200'
  content: "I've been playing with wicket lately and i'm loving it... i'm also using
    the combination wicket ,ibatis + spring... \r\n\r\nwhat i really like about wicket
    is the separation of concerns, which is great compared to other frameworks...\r\n\r\nunfortunately
    what's is difficult for me is to convince my coworkers to develop our new application
    using wicket... they strongly believe that using JSF or Oracle's ADF would be
    simpler for non java gurus to develop enterprise applications...\r\n\r\nanyway,
    wicket rocks!!!"
---
<p>Scott Miller, <a href="http://thoof.com/">Thoof.com</a>'s Chief Architect <a href="http://blog.thoof.com/?p=17">writes about the architecture</a> powering <a href="http://thoof.com">Thoof</a>, and the open source products they use. Of course Wicket is one of the products they used (otherwise there would be little point in linking to the article).</p>
<p>Scott writes:</p>
<blockquote><p>[...] we wanted to create a flexible platform for the website. Not just for delivering pages, but for implementing complex functionality quickly and easily, and with performance in mind.</p></blockquote>
<p>And regarding Wicket:</p>
<blockquote><p>[wicket] allowed us to modularize components of the site, and gets a lot of the basic plumbing of logic and presentation out of the way.</p></blockquote>
<p>What is interesting in my opinion is that Wicket itself is not mentioned as a part where the focus was when tweaking the architecture, but rather the database layer. Instead of using <a href="http://www.hibernate.org/">Hibernate</a>, they opted to use <a href="http://ibatis.apache.org/">iBatis</a> instead:</p>
<blockquote><p>Unlike typical ORM frameworks like Hibernate, or even more â€œhands offâ€ systems like those employed by Rails, iBatis lets us write the SQL queries. This is more work on the front end, but gives us much greater flexibility in the long run.</p></blockquote>
<p>Scott didn't write about the specifics of the servers they run on, but claims to reach 50 requests per second. There is no mention on memory usage or the number of sessions they have on each node.</p>
<p>All in all, it seems that technology is not in the way of Thoof's success. I already like a lot of the stories posted on the service. But I suspect it still needs to grow as a community (and need some way to build that).</p>
