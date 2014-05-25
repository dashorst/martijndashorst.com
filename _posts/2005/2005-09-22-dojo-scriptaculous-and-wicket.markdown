---
layout: post
status: publish
published: true
title: Dojo, Scriptaculous and Wicket
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 128
wordpress_url: http://martijndashorst.com/2005/09/22/dojo-scriptaculous-and-wicket/
date: '2005-09-22 00:32:23 +0200'
date_gmt: '2005-09-22 00:32:23 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>Since the start of <a href="http://wicket.sf.net">Wicket</a> we only wanted the best of breed components. Now with the advent of high quality, AJAX enabled JavaScript libraries, we can provide the means of building such components. <a href="">Ryan Sonnek</a> has been actively building the first components based on <a href="http://scrip.taculo.us">scriptaculous</a>, and my employer, <a href="http://www.topicus.nl">Topicus</a> has two students building open source Ajax components for the coming 5 months. Some times the good things just fall together.</p>
<p>In the process of creating the best of breed components we feel it is important to have the basic support into the <a href="http://wicket.sf.net">Wicket core</a>, but the library specifics in their own projects on <a href="http://wicket-stuff.sf.net">Wicket Stuff</a>. This will help moving those projects faster, basing their release cycles on the release cycles of Dojo and Scriptaculous, instead of the somewhat slower release cycle of Wicket. This basically means that the Dojo and Scriptaculous support will be extracted from the Wicket core, and when you want to use such a library, you have to download a seperate jar. It is my intention and primary goal to make those projects available as soon as possible.</p>
