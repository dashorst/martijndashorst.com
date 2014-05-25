---
layout: post
status: publish
published: true
title: Atlassian Ultimate Wallboard competition comes to an end
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
excerpt: This wallboard also boasts a very clean and simple design with sexy animations.  Products
  stats, builds and issue details are complimented by local railway schedules, twitter,
  weather, and google calendars -- including birthdays and beer time!
wordpress_id: 471
wordpress_url: http://martijndashorst.com/blog/?p=471
date: '2010-12-13 23:36:08 +0100'
date_gmt: '2010-12-13 22:36:08 +0100'
categories:
- wicket
- java
- technology
tags: []
comments: []
---
<p>Last month we submitted an internal project at Topicus into an international competition hosted by <a href="http://ultimatewallboard.com/">Atlassian concerning so called Wallboards</a>. Wallboards are (agile) information radiators which show stuff like build status, sprint planning and other interesting metrics. While we didn't win the competition (congratulations Vodafone Web Team!), we are glad to have participated in this competition!</p>
<p><iframe src="http://player.vimeo.com/video/17780865?byline=0&amp;portrait=0" width="400" height="300" frameborder="0"></iframe></p>
<p>Our board was heavily inspired by the <a href="http://www.panic.com/blog/2010/03/the-panic-status-board/">Panic Status Board</a>, and we took their premise and went a bit overboard. Our dashboard (dubbed "Topicus Board") shows our project status: production server status, average request times, number of concurrent users, requests per minute, Hudson build status, number of unit tests, server uptime, deployed application versions, a list of servers with status indication (up/down), etc. Added to that we show departure times of trains of our local train station (the Topicus offices are next to the Deventer central station), SVN commits and mantis issues, Google calendar events and the local weather.</p>
<p>We built our board with Java using Apache Wicket (raise your hand if you thought we'd use something else ;-), jquery (wiquery), CSS3 and HTML5. The board animates the living daylights out of our Dell workstation (Intel embedded graphics and Linux drivers don't work too great). The code is open source (GPL) and available from <a href="https://github.com/dashorst/dashboard">https://github.com/dashorst/dashboard</a>.</p>
<p>When we started with the project Atlassian hosted a contest for the ultimate wallboard, so we figured to enter the competition, and get ourselves a nice deadline. The competition closed November 24th. And today the results finally came in. Unfortunately our wallboard didn't take the grand prize for being the ultimate wallboard, but we did manage to<a href="http://blogs.atlassian.com/news/2010/12/ultimate-wallboard-winner.html"> get a honorable mention</a>:</p>
<blockquote><p>This wallboard also boasts a very clean and simple design with sexy animations.  Products stats, builds and issue details are complimented by local railway schedules, twitter, weather, and google calendars -- including birthdays and beer time!</p></blockquote>
<p>Judge <a href="http://ultimatewallboard.com/judges#judge-807">Dick Wall</a> added:</p>
<blockquote><p>Features like tracking transport delays, the excellent two speed ticker at the bottom, and the polish of the CSS animations all stand out in this demo.</p></blockquote>
<p>We thank Atlassian for hosting this competition and hope they'll host one next year.</p>
