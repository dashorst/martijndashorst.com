---
layout: post
status: publish
published: true
title: 'Call for developers: new Javascript datepicker development'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 47
wordpress_url: http://martijndashorst.com/2006/05/30/call-for-developers-new-javascript-datepicker-development/
date: '2006-05-30 09:55:55 +0200'
date_gmt: '2006-05-30 09:55:55 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>Igor Vaynberg, (not his <a href="http://www.vaynberg.com/joshua/">2.0 reincarnation</a>) has asked for help in <a href="http://wicketframework.org">Wicket</a>'s quest for a decent Javascript date picker that works with i18n and <a href="http://java.sun.com/j2se/1.4.2/docs/api/java/text/SimpleDateFormat.html">SimpleDateFormat</a> patterns. He writes:</p>
<blockquote><p>as you guys know weve been having a lot of trouble with the datepicker in extensions. a lot of it is from the issues of i18n and formatting in general. </p>
<p>
i started working on a replacement keeping those two items on the top of the list. the idea is to be able to define locale strings as well as a format expression that will be used for formatting and parsing and are identical to the ones used by SimpleDateFormat in java.</p>
<p>
when all is said and done it might look something like this:</p>
<p><pre>new DatePickerField(id, model, "EEEE, MMMM d yyyy")</pre>
<p>
and have localized properties like</p>
<p>
<pre>wicket.datepicker.months=January ,February... 
wicket.datepicker.shortMonths=Jan,Feb,...
etc</pre>
<p>
so the transition between java and javascript will be seamless</p>
<p>
i also want to be able to decorate any day square via ajax or another mechanism
</p></blockquote>
<p>
So if you are interested in building a killer Javascript calendar that works with existing Java idioms, give us a call.</p>
