---
layout: post
status: publish
published: true
title: No JavaDoc in Wicket distribution
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 406
wordpress_url: http://martijndashorst.com/blog/2008/10/22/no-javadoc-in-wicket-distribution/
date: '2008-10-22 23:43:27 +0200'
date_gmt: '2008-10-22 22:43:27 +0200'
categories:
- wicket
tags: []
comments:
- id: 57330
  author: Jon
  author_email: latchkey@gmail.com
  author_url: http://lookfirst.com
  date: '2008-10-23 01:26:11 +0200'
  date_gmt: '2008-10-23 00:26:11 +0200'
  content: when are people going to realize that maven is a pile of dog poopy?
- id: 57331
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2008-10-23 08:44:18 +0200'
  date_gmt: '2008-10-23 07:44:18 +0200'
  content: when are people going to realize that Maven is here to stay and gets better
    with every release. For all its warts it actually works decently on my projects.
    What I showed here is just a bug like in any other project.
- id: 57334
  author: 'Maven: The Definitive Guide &raquo; Blog Archive &raquo; Browsing Javadoc
    for Dependencies in Eclipse: m2eclipse'
  author_email: ''
  author_url: http://blogs.sonatype.com/people/book/2008/10/23/browsing-javadoc-for-dependencies-in-eclipse-m2eclipse/
  date: '2008-10-24 05:14:53 +0200'
  date_gmt: '2008-10-24 04:14:53 +0200'
  content: "[...] threw this video together as a response to Martjin Dashorst&#8217;s
    post on why Javadoc isn&#8217;t distributed with Wicket. Given the ease with which
    you can browse Javadoc in m2eclipse, I think the days of cutting a [...]"
- id: 57335
  author: Tim O'Brien
  author_email: tobrien@sonatype.com
  author_url: http://blogs.sonatype.com/people/book/2008/10/23/browsing-javadoc-for-dependencies-in-eclipse-m2eclipse/
  date: '2008-10-24 05:16:29 +0200'
  date_gmt: '2008-10-24 04:16:29 +0200'
  content: "Martjin, I spent some hours thinking about this issue today.    Here's
    my response:\r\n\r\nhttp://blogs.sonatype.com/people/book/2008/10/23/browsing-javadoc-for-dependencies-in-eclipse-m2eclipse/"
- id: 57352
  author: Michel Schudel
  author_email: michel.schudel@gmail.com
  author_url: http://www.michelschudel.nl
  date: '2008-11-12 20:35:10 +0100'
  date_gmt: '2008-11-12 19:35:10 +0100'
  content: Yeah, I'm going crazy about this maven site-plugin site/staging/deploy
    crap, too. Way we do it is by just running "site"  and copying the module site
    directly into the parent pom's site. Seems to work fine from there.
---
<p>Until the maven site plugin is capable of actually producing a testable multi-module website, I'm putting all efforts on hold to include any docs (and JavaDocs in particular) into the Wicket distribution. I'm fed up with spending my free time figuring out the magical incantation to generate a site that runs in my browser without having to deploy it to a remote location. See <a href="http://jira.codehaus.org/browse/MSITE-366" title="[#MSITE-366] multimodule site stage doesn't work - jira.codehaus.org">MSITE-366</a> for my test case project that just won't work. If you are desperate to get them javadocs, vote for that issue. Until then: you're <a href="http://www.urbandictionary.com/define.php?term=sol" title="Urban Dictionary: sol">SOL</a>.</p>
