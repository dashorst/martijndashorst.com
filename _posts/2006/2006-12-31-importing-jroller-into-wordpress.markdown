---
layout: post
status: publish
published: true
title: Importing JRoller into Wordpress
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 223
wordpress_url: http://martijndashorst.com/2006/12/31/importing-jroller-into-wordpress/
date: '2006-12-31 16:37:30 +0100'
date_gmt: '2006-12-31 15:37:30 +0100'
categories:
- Uncategorized
- personal
- java
- technology
- general
tags: []
comments: []
---
<p>I have moved my blog from <a href="http://jroller.com/page/dashorst">jroller.com</a> to a shared provided server (didn't want to open up my home network just yet). I didn't want another huge blogging service such as <a href="http://wordpress.com">wordpress.com</a>, rather I wanted a bit more control over what I could do with the service. I installed <a href="http://wordpress.org">Wordpress</a> as my blogging application. Having my own (part of a) server is pretty sweet, too bad it isn't Java hosted.</p>
<p>My hosting provider is <a href="http://bhosted.nl">bhosted</a>, a PHP/mysql provider in the Netherlands, and I find the service pretty decent until now. Yes, the domain registration could be smoother, but I doubt it is any worse than other providers.</p>
<p>I wanted to preserve my <a href="http://jroller.com/page/dashorst/wordpress">old blog entries</a> and migrate them to my new home. Unfortunately the wordpress installation doesn't have a connection to jroller to download all posts and import them. So I searched the <a href="http://en.wikipedia.org/wiki/Internets_(colloquialism)">internets</a> and found <a href="http://www.google.com/search?q=importing+jroller+into+wordpress">more people facing this problem</a>.</p>
<p>Finally I settled on <a href="http://zeusville.wordpress.com/2006/10/20/302/">exporting my entries using the wordpress xml format</a>, and thus preserving the comments made by other people on my blog. I then only had to go through 250+ posts to recategorize them (jroller didn't put blog entries with category 'java/wicket' on the front page).</p>
<p>I really have to thank <a href="http://zeusville.wordpress.com">Zeusville</a> for his efforts in creating the Wordpress export template for jroller.<br/></p>
