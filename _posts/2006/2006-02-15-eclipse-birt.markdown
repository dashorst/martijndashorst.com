---
layout: post
status: publish
published: true
title: Eclipse BIRT
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 94
wordpress_url: http://martijndashorst.com/2006/02/15/eclipse-birt/
date: '2006-02-15 11:22:57 +0100'
date_gmt: '2006-02-15 11:22:57 +0100'
categories:
- java
tags: []
comments:
- id: 57096
  author: Antony Stubbs
  author_email: antony.stubbs@gmail.com
  author_url: http://stubbisms.wordpress.com
  date: '2008-07-22 00:42:58 +0200'
  date_gmt: '2008-07-21 23:42:58 +0200'
  content: Have been looking at BIRT today for an old Struts app and it looks pretty
    cool. Was curious about Wicket and Birt and found your post - FYI look slike they
    have addressed a lot of your peevs you listed...
---
<p>Currently I'm figuring out whether the <a href="http://www.eclipse.org/birt/">BIRT</a> is a gift from heaven, or a one way trip to hell. At the moment, I think the roadsigns lead me into hell, instead of the start of the rainbow.</p>
<p>
My first pet peeves:</p>
<ul>
<li>the dataset editor is a modal dialog. This inhibits looking at your mappings in your Java classes, hibernate mapping files, etc. Why couldn't this be just an editor window in the usual Eclipse style of editing?</li>
<li>dragging columns in the dataset editor is no help at all. It prefixes the schema name, table name and column name on the place where the cursor is in the editor window. It doesn't add a from clause, nor does it have any intelligence on foreign key relationships.</li>
<li>the scripted dataprovider/dataset is a drag in working with Java, when you have a coding problem, it only shows up when previewing, and it doesn't provide you with a sensible error message: "The value of the property 'keyExpr' is required". I tried looking for this property in the xml definition of a valid report, but couldn't find one. How am I supposed to know where and how to set this?</li>
<li>you can only see the report working when you copy your classes into the report viewer plugin's web directory. Why isn't it possible to have it use the classpath of your current project, giving it the full capabilities of hotswap?</li>
<li>In order to have the previewer pick up changes in my Java code, I had to restart my workspace every time</li>
<li>It is very easy to have it take 100% of CPU and make your machine come down to a crawl, making you kill the Eclipse process. This problem did go away with an update of the EMF/GEF feature through the update manager.</li>
</ul>
<p>
As you can see, I am not enthousiastic about the BIRT offering. It sure doesn't feel like a 2.0 release, more like a 0.1 development snapshot.</p>
