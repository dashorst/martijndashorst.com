---
layout: post
status: publish
published: true
title: Speeding up hibernate startup time using terracotta?
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 401
wordpress_url: http://martijndashorst.com/blog/2008/09/26/speeding-up-hibernate-startup-time-using-terracotta/
date: '2008-09-26 15:11:37 +0200'
date_gmt: '2008-09-26 14:11:37 +0200'
categories:
- java
tags: []
comments:
- id: 57277
  author: Konstantin
  author_email: kgignatyev@gmail.com
  author_url: ''
  date: '2008-09-26 16:54:16 +0200'
  date_gmt: '2008-09-26 15:54:16 +0200'
  content: "Just in case you did not see this:\r\nhttp://opensource.atlassian.com/projects/hibernate/browse/HHH-1258\r\n\r\nIt
    seems like many have tried but..... it is not that easy"
- id: 57278
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2008-09-26 17:04:20 +0200'
  date_gmt: '2008-09-26 16:04:20 +0200'
  content: From the issue, they didn't try keeping it running in a separate JVM using
    terracotta. I am convinced that using terracotta *will* speed up startup time
    considerably, provided that it works of course.
- id: 57279
  author: Bruno Borges
  author_email: bruno.borges@gmail.com
  author_url: http://blog.brunoborges.com.br
  date: '2008-09-26 20:06:04 +0200'
  date_gmt: '2008-09-26 19:06:04 +0200'
  content: "Martijn, you can serialize the object Configuration and from there, create
    an instance of SessionFactory.\r\n\r\nSearch within Hibernate's documentation
    website.\r\n\r\nRegards,\r\nBruno"
---
<p>
I'm in the middle of creating a conversion utility from one database to another, and I have to reinitialize my Hibernate configuration quite often. When you have a couple of hundred entities that need configuring, starting up Hibernate can take a long time. My initial thought was to <em>serialize</em> the <code>SessionFactory</code> and deserialize it upon each startup.</p>
<p>
	I didn't try this yet, but something tells me this won't work. Call it a nagging feeling. However, it should be possible to run the <code>SessionFactory</code> in a Terracotta cluster and keep that server alive, and connect my conversion utility on startup with the Terracotta cluster. This should make startup times a snap.</p>
<p>
	Mind you: this is just a thought experiment. If someone has done this before, leave a note!</p>
