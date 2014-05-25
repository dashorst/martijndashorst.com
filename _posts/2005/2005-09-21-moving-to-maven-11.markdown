---
layout: post
status: publish
published: true
title: Moving to Maven 1.1
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 129
wordpress_url: http://martijndashorst.com/2005/09/21/moving-to-maven-11/
date: '2005-09-21 21:43:20 +0200'
date_gmt: '2005-09-21 21:43:20 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 152
  author: Anonymous
  author_email: ''
  author_url: ''
  date: '2005-09-22 15:37:02 +0200'
  date_gmt: '2005-09-22 15:37:02 +0200'
  content: I still think the site is too low contract.  Looks perfect from a distance,
    but that text is really difficult to read!
- id: 153
  author: Anonymous
  author_email: ''
  author_url: ''
  date: '2005-09-22 15:37:35 +0200'
  date_gmt: '2005-09-22 15:37:35 +0200'
  content: Er, "too low contract"=="too low contrast".  Oops.
---
<p>
I'm moving the build of the <a href="http://wicket.sf.net">Wicket</a> to <a href="http://maven.apache.org">Maven 1.1</a>. Maven is still beta, but it seems that most quirks have been solved and it works quite well with the Wicket website.</p>
<p>In order to create the (critically acclaimed) Wicket website, I had to <a href="http://cvs.sourceforge.net/viewcvs.py/wicket/wicket/src/xdocs/site.jsl?rev=1.2&view=auto">tweak</a> the official site template provided with maven. When all open source projects just use the default template provided by maven, then all projects look the same. Yes, default project structures are a good thing, and also structured documentation, but having all sites look the same is too communistic in my opinion :-).</p>
<p>Note to self: <i>make sure other contributors move also to maven 1.1</i></p>
