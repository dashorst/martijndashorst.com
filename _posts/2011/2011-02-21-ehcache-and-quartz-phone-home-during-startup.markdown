---
layout: post
status: publish
published: true
title: EHCache and Quartz phone home during startup
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 482
wordpress_url: http://martijndashorst.com/blog/?p=482
date: '2011-02-21 17:05:16 +0100'
date_gmt: '2011-02-21 16:05:16 +0100'
categories:
- java
- technology
- general
tags:
- ehcache
- terracotta
- open source
- trust
comments:
- id: 60196
  author: Steve
  author_email: steve@terracotta.org
  author_url: http://www.ehcache.org
  date: '2011-02-22 00:23:53 +0100'
  date_gmt: '2011-02-21 23:23:53 +0100'
  content: "Hi,\r\n\r\nI'm a bit confused about why this is so upsetting. We make
    no effort to hide the update checker It's open source so you can see what it is
    doing and it has the option to be turned off which is documented and clear. \r\n\r\nUnlike
    facebook, google, and most OS's we neither charge anything for the use of these
    awesome products nor do we make anyone look at advertisements to use them. Yet
    all of those products do heavy tracking and or update checking. \r\n\r\nWe still
    invest heavily in these products that can even be (and often are) embedded in
    our competitors products since they are Apache licensed. We don't hide them behind
    GPL or LGPL. \r\n\r\nWhile I can understand you wanting to highlight the update
    checker and tell people how to turn it off I don't see any reason to be angry
    with us or why we should feel bad?"
- id: 60197
  author: Alex Snaps
  author_email: alex.snaps@gmail.com
  author_url: ''
  date: '2011-02-22 13:12:48 +0100'
  date_gmt: '2011-02-22 12:12:48 +0100'
  content: Not much I could had that Alex didn't mention in his blog post already.
    I think though that out of fairness, you should also throw your shame at the endless
    list of open source software that people use on a daily basis that do the same
    thing. Again, all can be turned off, but is just on by default (how could it be
    otherwise?!). I really don't see anything nefarious in letting us know about your
    usage of the software as, in the end, that's what enables us to work on the product
    for your benefit as well...
- id: 60198
  author: R.J. Lorimer
  author_email: rjlorimer@realjenius.com
  author_url: http://www.realjenius.com
  date: '2011-02-22 21:36:51 +0100'
  date_gmt: '2011-02-22 20:36:51 +0100'
  content: "I had brought this up on Twitter a few months ago, and got in an interesting
    discussion with Alex Miller about it:\r\n\r\nhttp://tech.puredanger.com/2010/07/28/open-source-bargain/"
- id: 60210
  author: Philippe
  author_email: philippe.laflamme@gmail.com
  author_url: ''
  date: '2011-02-27 04:36:46 +0100'
  date_gmt: '2011-02-27 03:36:46 +0100'
  content: "+1\r\n\r\n\"a price we need to pay to use open source software\"\r\n\r\nDo
    we need to enumerate all the successful open-source software that DO NOT phone
    home? What kind of statement is that?\r\n\r\nIf Terracotta wants usage metrics
    they should use an opt-in mechanism. There are lots of examples of opt-in mechanism
    in open-source software."
- id: 60220
  author: iskorn
  author_email: igor.skornyakov@gmail.com
  author_url: ''
  date: '2011-03-01 16:01:53 +0100'
  date_gmt: '2011-03-01 15:01:53 +0100'
  content: Well, at least regarding Encache this is clearly specified in the documentation.
    I agree with Alex Miller and see nothing bad in this practice.
- id: 60367
  author: Matt Rakowki
  author_email: os@zeroio.com
  author_url: http://www.concursive.com
  date: '2011-03-30 18:24:24 +0200'
  date_gmt: '2011-03-30 17:24:24 +0200'
  content: "I recently updated both EHCache and Quartz and I was surprised to see
    the update check automatically happen today. This update check happens everywhere
    the classes are instantiated... in unit tests, in scripts, services, listeners
    and web apps.\r\n\r\nI must say it feels dirty to have to put extra code into
    all of these areas to prevent the updateCheck from happening.\r\n\r\nAs a developer,
    I appreciate being notified of updates, and thus far email and RSS feeds have
    worked just fine because I don't closely monitor INFO events on the servers.\r\n\r\nWhat
    I don't appreciate is having this happen automatically just for updating the library.
    I couldn't possibly imagine if the other 30 libraries I use each had their own
    update check.\r\n\r\nWhy is it important to notify a system administrator about
    a library that needs updating once the app is in production?\r\n\r\nThis only
    helps one organization, and that is Terracotta."
- id: 60439
  author: Simone Hask
  author_email: simonehask@live.com
  author_url: ''
  date: '2011-04-17 23:47:01 +0200'
  date_gmt: '2011-04-17 22:47:01 +0200'
  content: "You cannot totally disable the phone home feature. \r\n\r\nEven if you
    disable the phone home at startup in the Quartz properties file, if you manage
    to get an exception in a job guess what -- it phones home."
- id: 60701
  author: Dannes
  author_email: Dizzzz@exist-db.org
  author_url: ''
  date: '2011-07-01 21:47:34 +0200'
  date_gmt: '2011-07-01 20:47:34 +0200'
  content: The initial phone home feature actually caused problems when i ran my software
    behind à corporate firewall. Hanging thread and a nasty stack trace after a long
    time. Bweh.....
- id: 61175
  author: Erik van Oosten
  author_email: e.vanoosten@grons.nl
  author_url: http://day-to-day-stuff.blogspot.com/
  date: '2011-10-10 11:47:45 +0200'
  date_gmt: '2011-10-10 10:47:45 +0200'
  content: "Just found out that Hazelcast also calls home. It does so quite openly
    as it clearly prints a warning you're using an older version.\r\n\r\nDisable with:\r\n
    \    \r\n         false\r\n    \r\nor\r\n    -Dhazelcast.version.check.enabled=false"
- id: 61176
  author: Erik van Oosten
  author_email: e.vanoosten@grons.nl
  author_url: http://day-to-day-stuff.blogspot.com/
  date: '2011-10-10 11:48:46 +0200'
  date_gmt: '2011-10-10 10:48:46 +0200'
  content: "The XML fragment should have been:\r\n\r\n    &lt;properties&gt;\r\n         &lt;property
    name=\"hazelcast.version.check.enabled\"&gt;false&lt;/property&gt;\r\n    &lt;/properties&gt;"
- id: 61384
  author: Mark Wood
  author_email: mwood@IUPUI.Edu
  author_url: ''
  date: '2011-12-05 21:15:59 +0100'
  date_gmt: '2011-12-05 20:15:59 +0100'
  content: "o  One might not even know one is *using* EHCache or Quartz or xxx until
    one sees these log messages.  They could be buried several layers deep in dependencies.
    \ How to know that one can/should turn something off, when one doesn't even know
    it's there to *be* turned off?\r\n\r\no  Opt-in is a community norm.  You're supposed
    to expect people to be suspicious.  You're supposed to leave things like phone-home
    off by default.  You're supposed to explain what it does for the user and trust
    him to have some sympathy with the goals of people who give away useful stuff.
    \ This is probably why people get angry.\r\n\r\no  Big applications take long
    enough to start.  If various bits are phoning home when they initialize, people
    will feel that the overhead of DNS resolution and TCP handshake (not to mention
    whatever the application layer is doing) add too much startup cost, whether it's
    true or not.  And, while big app.s may run for a long time, they may *also* have
    little commandline pieces that are run very frequently but which pay the same
    overhead because they use the same core code (reusability, you know)."
---
<p>One might call EHCache (the Java caching library everybody loves) ET-Cache, since it keeps phoning home during startup. While probably just implemented as a usability feature, I find it quite nefarious, especially since Quartz (the job queuing library everybody loves) does *exactly* the same.</p>
<p>The culprit lies in <tt>net.sf.ehcache.util.UpdateChecker</tt> and <tt>org.quartz.util.UpdateChecker</tt>.</p>
<p>Information sent to Terracotta HQ include:</p>
<ul>
<li>a client ID taken from your local IP</li>
<li>os.name</li>
<li>java.vm.name</li>
<li>java.version</li>
<li>os.arch</li>
<li>QuartzVersion</li>
<li>EhCache version</li>
<li>something about source</li>
<li>uptime-secs</li>
<li>patch level from Quartz/EhCache</li>
</ul>
<p>Needless to say, this is something that should not be enabled by default, and only with a big opt-in questionnaire... This also sparks the question if the cache doesn't send *more* information home than just the update information? It is after all a product designed to send information across the network—what is one extra node more in the grand scheme of things? Has anybody audited the code for nefarious code?</p>
<p>In any case: to disable phoning home everybody should start their applications with the following command line parameters:</p>
<ul>
<li><tt>-Dnet.sf.ehcache.skipUpdateCheck=true</tt></li>
<li><tt>-Dorg.terracotta.quartz.skipUpdateCheck=true</tt></li>
</ul>
<p>Or you can configure it in your <tt>ehcache.xml</tt> according <a href="http://www.ehcache.org/documentation/configuration.html#Update_Checker">to the user manual</a>. Quartz is <a href="http://www.quartz-scheduler.org/docs/configuration/ConfigMain.html">similarly configurable in the quartz.properties</a>.</p>
<p>According to <a href="http://tech.puredanger.com/2010/07/28/open-source-bargain/">Alex Miller</a>, a former Terracotta employee, it is not evil and a price we need to pay to use open source software.</p>
<p>I disagree strongly: this undermines the premise of trustworthy open source. The download page doesn't mention the phoning home, neither does the announcement of ehcache 2.2 (last july), it is summarily mentioned in the configuration part of the manual, which you typically don't read when you just upgrade your dependency to the latest version and see that everything still works as usual. The same goes for Quartz: it was apparently added in quartz 1.7.3, but no mention of this in the release notes. Neither of the possibility to disable phoning home which was <a href="http://jira.codehaus.org/browse/GRAILSPLUGINS-2221">added in quartz 1.8</a>.</p>
<p>In my opinion, this is unacceptable behavior for any open source product, which severely undermines the trust we spent building in the last couple of years making open source a viable alternative to closed software.</p>
<p>SHAME ON YOU TERRACOTTA!</p>
