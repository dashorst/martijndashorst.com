---
layout: post
status: publish
published: true
title: RSS - friend or foo?
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 212
wordpress_url: http://martijndashorst.com/2005/04/24/rss-friend-or-foo/
date: '2005-04-24 10:30:47 +0200'
date_gmt: '2005-04-24 10:30:47 +0200'
categories:
- wicket
tags: []
comments: []
---
<p>
I have spend all morning creating a custom XSLT stylesheet for the <a href="http://wicket.sourceforge.net">Wicket</a> project so that a RSS feed is generated each and every time the front page is created using <a href="http://maven.apache.org">maven</a>.</p>
<p>
The feed is extracted from the <a href="http://wicket.sourceforge.net/index.html#Latest_News">Latest News</a> section and transformed into a RSS-0.91 XML file. The biggest hurdle I had to overcome was the absence of getting the current date into the resulting XML file. Why oh why isn't a standard date/time facility available in XSL? I had to resort to <a href="http://xml.apache.org/xalan-j">Xalan-J</a> specific functions in order to get the current date in the feed.</p>
<p>
The only problem I now have is that the Sage RSS reader plugin for firefox doesn't show the update date when the feed is read. I hope that Sage sees when the RSS is updated, otherwise my efforts have been nought.</p>
<p>
<strong>UPDATE:</strong> Sage RSS works like a charm!</p>
