---
layout: post
status: publish
published: true
title: New Wicket Ajax capabilities in use
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 98
wordpress_url: http://martijndashorst.com/2006/02/05/new-wicket-ajax-capabilities-in-use/
date: '2006-02-05 16:49:45 +0100'
date_gmt: '2006-02-05 16:49:45 +0100'
categories:
- wicket
- java
tags: []
comments:
- id: 110
  author: Jonathan Locke
  author_email: jonl@muppetlabs.com
  author_url: ''
  date: '2006-02-05 19:18:05 +0100'
  date_gmt: '2006-02-05 19:18:05 +0100'
  content: "IMO, this:\n\n\tpublic AjaxSelfUpdatingTimerBehavior(final long millis)\n\t{\n\t\tsuper(millis);\n\t}\n\nshould
    take a Duration object, not a long.  This would turn this code:\n\ntotalTime.add(new
    AjaxSelfUpdatingTimerBehavior(60 * 1024));\n\ninto something a lot more readable:\n\ntotalTime.add(new
    AjaxSelfUpdatingTimerBehavior(Duration.ONE_MINUTE));"
- id: 111
  author: Jonathan Locke
  author_email: jonl@muppetlabs.com
  author_url: ''
  date: '2006-02-05 19:33:19 +0100'
  date_gmt: '2006-02-05 19:33:19 +0100'
  content: |-
    Using Duration would also directly enable and encourage neat time computing and parsing tricks and be more consistent with the rest of the Wicket API...

    Duration.valueOf("6.5 hours")
    Duration.minutes(7.3)
    Time startTime = Time.now()
      ...
    Duration.elapsed(startTime)

    etc...
---
<p>In the field of simplicity and ease of use, <a href="http://wicket.sf.net">Wicket</a> has a name to uphold. Until recently, our Ajax support was harder than it should have been, but with the improvements we made in Wicket 1.2 things are looking good.</p>
<p>
One of our users, <a href="http://www.talios.com">Talios</a>, has blogged about his adventures using our still fresh Ajax support. He has written a <a href="http://www.talios.com/simple_time_tracking_application.htm">simple time tracker application</a> using Wicket, Hibernate, Java 5 and Postgresql.</p>
<p>
Now this is looking promising, and I can assure you, we will have a very nice Wicket + Ajax experience when 1.2 is final!</p>
<p>
Disclaimer: Wicket 1.2 is still under development so things might change a bit in the coming weeks.</p>
