---
layout: post
status: publish
published: true
title: JQuery tabs in Wicket and issue tracking across the universe
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 264
wordpress_url: http://martijndashorst.com/blog/2007/06/04/jquery-tabs-in-wicket-and-issue-tracking-across-the-universe/
date: '2007-06-04 21:18:22 +0200'
date_gmt: '2007-06-04 20:18:22 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 3571
  author: Xavier
  author_email: xavier.hanin@gmail.com
  author_url: http://xhab.blogspot.com/
  date: '2007-06-05 07:34:40 +0200'
  date_gmt: '2007-06-05 06:34:40 +0200'
  content: "To see the tabs in action, it's nothing more than checking the jquery
    tabs plugin demo page:\r\nhttp://stilbuero.de/jquery/tabs/\r\nI've only embedded
    this component in a wicket component, so the client side demo is exactly the same
    as the wicket based one.\r\n\r\nIndeed I like wicket a lot, it makes me like web
    development again, and that's a lot :) Moreover it fits my needs very well, especially
    because it allows a very flexible page composition, where plugins can contribute
    components.\r\n\r\nFor the bug tracker in my case it was the new blog-in-5-minutes
    application (well, it was more 3 or 4 days) to check how wicket, hibernate and
    databinding can be used together to create a very simple data centric app. And
    it works very well IMO. But I didn't know bugeater, thanks for the link (jtrac
    is too flexible for me)."
- id: 3590
  author: Peter Thomas
  author_email: peter_t3@yahoo.com
  author_url: http://ptrthomas.wordpress.com
  date: '2007-06-05 13:35:14 +0200'
  date_gmt: '2007-06-05 12:35:14 +0200'
  content: "Yeah I had never heard of bugeater as well.  BTW JTrac is not really inspired
    by Trac - it started as a personal project to learn Spring and the name \"jtrack\"
    was already taken by that NASA satellite tracking applet thingy.\r\n\r\nAbout
    JTrac being too flexible for your tastes, Xavier you can be a little more subtle
    when you bash competing tools :P  But seriously, I am interested in your experiences
    with jquery - because for the moment I have chosen Yahoo! UI (but am open to switch)
    and as you said Wicket really makes it fun to componentize javascript widgets,
    page contribution, events and all."
---
<p><a href="http://xhab.blogspot.com/">Xavier Hanin</a> (of <a href="http://incubator.apache.org/ivy">Ivy</a> fame) has created a <a href="http://xhab.blogspot.com/2007/06/wicket-jquery-tab-component.html">tabbed client side JQuery/Wicket panel</a> for use in his open source continuous integration project <a href="http://xooctory.xoocode.org/">xooctory</a>. I still haven't seen the tabs in action, so I can't comment on their greatness yet.</p>
<p>What struck me most is the ease with which Xavier was able to construct the tabs, which is a feat in its own for both JQuery and Wicket.</p>
<blockquote><p>Wicket makes very easy to develop such components, and that's one of the thing I like the most about wicket. [...] My wicket implementation is about 140 lines of Java (well, 50 lines of Java and the rest of comments and imports) and 40 lines of html (most of which is used for testing only). That's all, and you don't need to be an expert in wicket to write such a component.</p>
</blockquote>
<p>Of course I also looked around on <a href="http://xoocode.org">xoocode</a> for more of Xavier's projects and he seems to like Wicket a lot, so we now have 3 issue trackers (that I know of) written using Wicket (are issue trackers the new blog-in-5-minutes applications?):</p>
<ul>
<li><a href="http://jtrac.info">jtrac</a> (Peter Thomas' <del>trac</del> Nasa inspired tracker)</li>
<li><a href="https://developer.berlios.de/projects/bugeater/">bugeater</a> (Philip Chapman/Andrew Lombardi/Ryan Gravener's issue tracker)
</li>
<li><a href="http://xoosent.xoocode.org/">xoosent</a> (Xavier's issue tracker)</li>
</ul>
<p>And other developer tools built using <a href="http://wicketframework.org">Wicket</a> are <a href="http://xooctory.xoocode.org">xooctory</a> (a continuous integration server), <a href="http://www.jfrog.org/sites/artifactory/latest/">artifactory</a> (a maven proxy). Wicket inspired is the already famous build tool called <a href="https://gosling.dev.java.net/">Gosling</a>, which has performed a reboot, but seems to get into shape pretty fast.</p>
