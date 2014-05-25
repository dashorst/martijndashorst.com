---
layout: post
status: publish
published: true
title: Open Source Release Scheduling
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 158
wordpress_url: http://martijndashorst.com/2005/07/07/open-source-release-scheduling/
date: '2005-07-07 23:29:22 +0200'
date_gmt: '2005-07-07 23:29:22 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 163
  author: Jesse Sightler
  author_email: jesse.sightler@gmail.com
  author_url: http://www.jroller.com/page/jsight/
  date: '2005-07-08 19:32:22 +0200'
  date_gmt: '2005-07-08 19:32:22 +0200'
  content: |-
    For framework components where everyone expects stability and consistency, I think defined schedules and carefully managed releases work best.  See also Gnome, and KDE as other examples in the free software community that have seen success with this approach.

    It's generally better to let feature commitments fluctuate a bit, and keep a steady stream of releases than to get into the "hide in a room for 3 years reinventing the world" mentality.

    And, no you are definitely not the only one who thought the whole Hibernate "Beta is the new Stable" thing was weird. :)

    Anyway, just some random thoughts...
- id: 164
  author: Andi
  author_email: ''
  author_url: http://bullgod.de/notebook/
  date: '2005-07-17 16:42:45 +0200'
  date_gmt: '2005-07-17 16:42:45 +0200'
  content: |-
    Ever considered using Jira for release planning/management? It's way more productive than the sourceforge tracker imho. You can assign bugs/feature requests to planned releases, milestones, bugfixversions and the like. Then you have a kind of in-between the "playing around" and "fix deadlines" thing. I realized that I submit more bugs and feature requests to OS projects using Jira then the really arkward sf tracker. The companies wiki (confluence if i remember right) is also way better than anything i've seen so far. They also host Jira/Wiki for free afaik. -andi

    PS: I'm not intangled with the company in any way. It's just my personal experience.
- id: 165
  author: Martijn Dashorst
  author_email: dashorst@users.sf.net
  author_url: http://www.jroller.com/page/dashorst/
  date: '2005-07-19 17:54:01 +0200'
  date_gmt: '2005-07-19 17:54:01 +0200'
  content: |-
    I have considered JIRA and although it is way more powerful than the SF.net trackers, I personally don't like the interface that much.

    I like the fact that sf.net 'integrates' much functionality, and that the trackers are very light weight.

    However, I will be proposing it to our core contributors whether they wish to move.

    It is problematic however that SF.net statistics are dependend on the tracker activity :-)
---
<p>We had a discussion over dinner concerning the <a href="http://wicket.sf.net">Wicket</a> release schedule for 1.1. Apparently there are several ways to get at a final release and we were discussing the various stages of delivering development code until the final release.</p>
<p>I'm a rather big fan of a well laid out plan, such as the <a href="http://www.eclipse.org">Eclipse</a> project <a href="http://www.eclipse.org/org/councils/PC/platform/eclipse_project_plan_3_2_2005_02_14.html">does on their roadmap</a>. Eclipse uses milestones to demarkate several stages of development, where somewhere around the 5th or 6th milestone the API gets frozen and only bugs and performance issues are resolved. The end game (from the release candidates on) is also pretty clear. Each milestone has a date attached to it, and the best part is that <a href="http://www.artima.com/lejava/articles/eclipse_culture.html">they meet the deadlines</a>!</p>
<p>My collegue however thinks that setting <em>and sticking to</em> a well laid out plan is not why he is on board of the project. He wants to play and program on a feature whenever he wants. Personally I think that working on stuff you like just for fun is not in the best interest of the project as a whole, or at least for the community. However, I <em>do</em> recognize that he does a lot of stuff in his own, free time and doesn't get a single dime for working on the project, and as such 'giving' him this freedom (i.e. not discussing it anymore ;-), <em>is</em> in the best interest of the project and community, as otherwise he won't be on board.</p>
<p>So we agreed on trying to make the 1.1 feature list stable and manageable, and create some releasing schedule that works for everyone. I also think we agreed to disagree, as we often do :-).</p>
<p>If someone is reading this stuff, what is your take on open source release scheduling? Do you prefer the Eclipse way of release scheduling (minus the deadline ;-), a more free form alpha/beta cycle, or any other release mechanism (for example 'none')? Am I the only one that found it strange that <a href="http://www.hibernate.org">Hibernate 3</a> was marked production, but was still a release candidate?</p>
