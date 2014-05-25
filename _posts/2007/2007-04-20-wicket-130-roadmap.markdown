---
layout: post
status: publish
published: true
title: Wicket 1.3.0 roadmap
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 254
wordpress_url: http://martijndashorst.com/blog/2007/04/20/wicket-130-roadmap/
date: '2007-04-20 16:07:46 +0200'
date_gmt: '2007-04-20 15:07:46 +0200'
categories:
- wicket
tags: []
comments:
- id: 1618
  author: Peter Thomas
  author_email: peter_t3@yahoo.com
  author_url: http://ptrthomas.wordpress.com
  date: '2007-04-21 06:25:38 +0200'
  date_gmt: '2007-04-21 05:25:38 +0200'
  content: That's a really nice picture.  What did you use to create it?
- id: 1624
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-04-21 09:11:23 +0200'
  date_gmt: '2007-04-21 08:11:23 +0200'
  content: I used <a href="http://www.omnigroup.com/applications/omnigraffle/" rel="nofollow">OmniGraffle</a>
    to create it.
- id: 1633
  author: rue&#8217;s headroom &raquo; Blog Archiv &raquo; Wicket 1.3.0 roadmap
  author_email: ''
  author_url: http://www.2rue.de/cyberspace/wicket-130-roadmap/
  date: '2007-04-21 12:59:38 +0200'
  date_gmt: '2007-04-21 11:59:38 +0200'
  content: "[...] Martijn Dashorst hat in seinem Blog eine Roadmap der n&#228;chsten
    Wicket-Releases ver&#246;ffentlicht. Demnach wird die 1.2.6 an diesem Wochenende,
    die erste 1.3 beta noch diesen Monat ver&#246;ffentlicht werden. Die Inkubation
    zu einem Apache Top-Level-Projekt schreitet also erfolgreich weiter.Technorati
    Tags: java, wicket, apache [...]"
- id: 1642
  author: Matt Raible
  author_email: matt@raibledesigns.com
  author_url: http://raibledesigns.com
  date: '2007-04-21 19:33:24 +0200'
  date_gmt: '2007-04-21 18:33:24 +0200'
  content: I was hoping to learn Wicket in a day this weekend for my upcoming Comparing
    Java Web Frameworks. I'm guessing I should start with 1.2.6?  Are either of these
    releases available in a Maven repo - or can I checkout/install to get around the
    lag?
- id: 1645
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-04-21 20:18:49 +0200'
  date_gmt: '2007-04-21 19:18:49 +0200'
  content: "Matt: you can find the pointers to the code here: <a href=\"http://incubator.apache.org/wicket/getting-wicket.html\"
    rel=\"nofollow\">getting Wicket</a>. 1.2.6 is not packaged yet (you'll have to
    do that yourself), but the code in the branches/wicket-1.2.x should not change
    much.\r\n\r\nFor learning Wicket I think 1.2.6 is a good place to start."
- id: 3470
  author: Zlatan KadragiÄ‡
  author_email: aurelije@gmail.com
  author_url: ''
  date: '2007-06-03 17:09:34 +0200'
  date_gmt: '2007-06-03 16:09:34 +0200'
  content: Hi Martijn! I was looking for information about date of realize of Wicket
    1.3. Also I would like to know something more about Wicket 2.0 features and realize
    date. I am considering writing my bachelor exam on Wicket subject.
- id: 13207
  author: rue&#8217;s headroom &raquo; Blog Archiv &raquo; Wicket 1.3.0 roadmap
  author_email: ''
  author_url: http://www.2rue.de/hacking/wicket/wicket-130-roadmap/
  date: '2007-09-29 17:20:11 +0200'
  date_gmt: '2007-09-29 16:20:11 +0200'
  content: "[...] Martijn Dashorst hat in seinem Blog eine Roadmap der n&#228;chsten
    Wicket-Releases ver&#246;ffentlicht. Demnach wird die 1.2.6 an diesem Wochenende,
    die erste 1.3 beta noch diesen Monat ver&#246;ffentlicht werden. Die Inkubation
    zu einem Apache Top-Level-Projekt schreitet also erfolgreich weiter. [...]"
- id: 26532
  author: Oren
  author_email: oren@washington.edu
  author_url: http://staff.washington.edu/oren/weblog2
  date: '2007-12-19 01:31:28 +0100'
  date_gmt: '2007-12-19 00:31:28 +0100'
  content: At the risk of asking ac ompletely off-topic question - how did you get
    that 3-d glassy look on your Omni Graffle doc?
---
<p>I promised on the Wicket user list that I would devise a roadmap with some dates on when to expect releases. So here is a preliminary roadmap:</p>
<p><a href="http://www.flickr.com/photos/dashorst/466161899/" title="Photo Sharing"><img src="http://farm1.static.flickr.com/198/466161899_339852d2a3_o.png" width="550px" alt="Wicket 1.3 roadmap" /></a></p>
<p>
Some dates are not fixed, as there is an approval process to go through before we can ship it: the Apache releases tend to cause a bit more ceremony. When we have graduated you'll see that these release procedures will become more efficient: there is no extra barrier to pass once we are a top level project. We have started the processes to release both <i>Apache Wicket 1.3.0-incubating-beta</i> and <i>Wicket 1.2.6</i>. The latter will be available this weekend, the former will be submitted to the <a href="http://incubator.apache.org/guides/pmc.html">Apache Incubator PMC</a> for approval. We expect this release to become available around the end of the week after going back and forward a couple of times.</p>
<p>Note the release of wicket-x.y: we don't know (yet) how to call the version after 1.3. The vote on the development list seems to favor <strong>Apache Wicket 2.0</strong>. This is a busy weekend for me: building 2 releases. Sounds like a great way to discover if we have improved on the release procedure in the last month.</p>
