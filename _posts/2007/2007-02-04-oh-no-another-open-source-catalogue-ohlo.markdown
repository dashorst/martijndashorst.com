---
layout: post
status: publish
published: true
title: 'Oh no... another open source catalogue: Ohlo'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 234
wordpress_url: http://martijndashorst.com/blog/2007/02/04/oh-no-another-open-source-catalogue-ohlo/
date: '2007-02-04 22:10:35 +0100'
date_gmt: '2007-02-04 20:10:35 +0100'
categories:
- wicket
- java
- technology
- general
tags: []
comments:
- id: 212
  author: epepep &raquo; Blog Archive &raquo; Ohloh
  author_email: ''
  author_url: http://per.liedman.net/?p=81
  date: '2007-02-05 20:31:11 +0100'
  date_gmt: '2007-02-05 19:31:11 +0100'
  content: "[...] Via A Wicket Diary hittade till Ohloh, en indexeringstjÃ¤nst fÃ¶r
    Ã¶ppen kÃ¤llkod. En fÃ¶rdel jÃ¤mfÃ¶rt med liknande tidigare initiativ Ã¤r att
    Ohloh fokuserar mycket pÃ¥ statistik som hÃ¤mtas ur projektens versionshanteringssystem
    (CVS, Subversion); sÃ¥vÃ¤l kodkvalitÃ© (eller iallafall mÃ¤ngden kommentarer)
    som aktivitet och storlek bedÃ¶ms. Dessutom ser det sÃ¶tt och Web 2.0-igt ut ocksÃ¥.
    [...]"
---
<p><a href="http://www.ohloh.net/projects/3958">Ohlo</a> just surfaced on my radar. Ohlo is a open source catalogue, similar to the <a href="http://codezoo.com">O'Reilly codezoo</a> effort. We have <a href="http://swik.net/">Swik</a>, <a href="http://freshmeat.net">Freshmeat</a>, etc. How many of these efforts can the internet bear?</p>
<p>Ohlo does looks like a good effort. They parse the code repositories and base some of their statistics on that. A lot of sourceforge projects will fail the test as many will be flagged as one man, inactive projects.</p>
<p>Strange thing is that for the <a href="http://maven.apache.org">maven</a> project (which is pretty heavy under development) they say that the activity is in decline. Probably the pointer to their repository was not correct.</p>
<p>Is such a catalogue any good? I think it is. I usually try to stay away from one man shows, and projects that haven't seen much development (unless the software tracker shows no bugs and the project is feature complete). This catalogue shows in a blink of an eye the status of a project and adds nice qualities to it.</p>
<p>Their summary for Wicket:</p>
<blockquote><p>+ Large, active development team<br />
+ Well-commented source code<br />
! Apache Software License may conflict with GPL</p>
</blockquote>
<p>They flag the Apache Software License as <a href="http://www.ohloh.net/projects/3958/factoids/67394">conflicting with GPL</a>. Apparently this is caused by one file in our repository trunk which is GPL licensed. The one problem I have is that they are able to discover one file with GPL code, but don't provide a link to which file that is. Anyway, I doubt this will still be a problem in the next weeks. We are removing all (L)GPL code from our code base as our effort to incubate at Apache continues. The comments in our code seem to please the Ohlo gods:</p>
<blockquote><p>Wicket is written mostly in Java. Across all Java projects on Ohloh, 35% of all source code lines are comments. For Wicket, this figure is 51%. This high number of comments puts Wicket among the highest one-third of all Java projects on Ohloh.</p>
</blockquote>
<p>They conclude this factoid with the comment that the Wicket team is a <q>[...] helpful and disciplined development team.</q></p>
<p>Read more on <a href="http://www.ohloh.net/projects/3958">Wicket at Ohlo</a>. Oh, and you can <a href="http://www.ohloh.net/projects/3958/stacks"><i>stack Wicket</i></a>, which is something like telling that it is part of your software stack.</p>
