---
layout: post
status: publish
published: true
title: Writing a Wicket Article
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 184
wordpress_url: http://martijndashorst.com/2005/05/30/writing-a-wicket-article/
date: '2005-05-30 12:39:57 +0200'
date_gmt: '2005-05-30 12:39:57 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 183
  author: Herve Tchepannou
  author_email: htchepannou@sympatico.ca
  author_url: ''
  date: '2005-05-30 15:58:35 +0200'
  date_gmt: '2005-05-30 15:58:35 +0200'
  content: "I'm working in a project where I need to integrate HTML pages within my
    portletz, but I don't want to polute it with nasty JSP tags of Velocity directives.
    \nIt would have been nice for me to use wicked:id in my HTML tags.\nIs it possible
    to integrate the wicked rendering engine with a portlet container?"
- id: 184
  author: Martijn Dashorst
  author_email: dashorst@users.sf.net
  author_url: http://www.jroller.com/page/dashorst/
  date: '2005-05-30 16:34:44 +0200'
  date_gmt: '2005-05-30 16:34:44 +0200'
  content: |-
    It is not trivial to do so. One of our commiters has been actively trying to add portlet support to Wicket, but keeps complaining about the portal implementations (not the portlet spec).

    Portlet support is scheduled for 1.1, but there is no very active development happening. If you want to have support for portlets, you can vote on the sourceforge tracker (just add a I want this now comment), or even better, if you have a suggestion, become active! Just send your ideas to the mailinglist, or add them to the wiki. We are always open to suggestions.
- id: 185
  author: Les Pruszyski
  author_email: lpruszynski@gmail.com
  author_url: ''
  date: '2005-05-30 17:32:47 +0200'
  date_gmt: '2005-05-30 17:32:47 +0200'
  content: Great to know you are working on an article about Wicket. I think I appreciate
    your concerns. Maybe the best way to introduce Wicket would be to develop Jonathan
    Locke's Wicket design principles. Wicket is the best OO framework I've seen and
    it should be presented as such.
- id: 186
  author: Matt Raible
  author_email: ''
  author_url: http://raibledesigns.com
  date: '2005-05-30 18:03:48 +0200'
  date_gmt: '2005-05-30 18:03:48 +0200'
  content: If Wicket is just another component-based framework like JSF and Tapestry,
    how is it better than those two.  Why should I use Wicket over Tapestry?  Maybe
    even some code comparisons.
- id: 187
  author: Martijn Dashorst
  author_email: dashorst@users.sf.net
  author_url: http://www.jroller.com/page/dashorst
  date: '2005-05-30 22:39:27 +0200'
  date_gmt: '2005-05-30 22:39:27 +0200'
  content: |-
    I think that before I can argue that Wicket is bigger, larger, uncut than ... (insert favorite framework here), the readers need to know what Wicket is. How many people have actually heard/read about Wicket? And even more, how many have actually heard/read about component based web development?

    BTW I want the article to be out there before JavaOne, so I don't want to give away too much for the Web Framework Smackdown in which Eelco is participating. However, if someone wants to start already ... I'm game...
- id: 188
  author: Dan
  author_email: ''
  author_url: ''
  date: '2005-05-31 03:51:28 +0200'
  date_gmt: '2005-05-31 03:51:28 +0200'
  content: Don't worry about giving stuff away that you'll also use in the smackdown.  Both
    should present the best arguments...
- id: 189
  author: Jonathan Locke
  author_email: jonl@muppetlabs.com
  author_url: ''
  date: '2005-05-31 09:05:26 +0200'
  date_gmt: '2005-05-31 09:05:26 +0200'
  content: "Got this post via Google alerts today (kinda nifty thing they have there!)\n\nI
    think it's important to dispel the notion that Wicket is just Tapestry without
    XML.  I believe Wicket's component model and particularly its way of doing state
    management is subtantially different from - and I'd like to think largely better
    than - competing frameworks... even if I do hesitate to compare it in detail with
    frameworks like Tapestry or JSF (since I have insufficient knowledge about these
    frameworks to make a worthwhile comparison). \n\nAvoiding XML config files is/was
    one of the easiest goals to convey, but actually one of the least important motivations
    in designing Wicket.  What mattered most was really the quality and focus of the
    component model design itself and in particular finding a better/easier approach
    to state management that still scales.  I think it is this work that's going to
    ultimately attract attention once people really sink their teeth into it.  Unfortunately,
    it will be very hard to capture this in a \"soundbite\" (or even a 2,000 word
    article).  \n\nI think it is a problem that the quick and easy tag people are
    pinning on Wicket is \"Wicket is Tapestry without XML config files\".  This is
    easy to say but I think also inaccurate and dismissive because it omits a whole
    host of important but subtle differences and advantages which are not so easily
    conveyed.\n\nAnyway, I think it will be pretty tricky to boil down what distinguishes
    Wicket to 2,000 words or so and doubly tricky to compare it to other frameworks
    like Tapestry in that same article.  I suspect that Matt is correct that a comparison
    of implementations of an example problem would be the best approach.  Then people
    can sort of see what makes it different instead of hearing people talk about it.
    \ The risk in talking about it instead of showing it is that Wicket may end up
    getting tagged with a trivializing soundbite and a lot of people might miss out
    on something good."
---
<p>I'm in the process of writing an article concerning <a href="http://wicket.sf.net" title="Wicket">Wicket</a>. I'm wondering what the ambition should be and how to capture that in about 2000 words.</p>
<ul>
<li>focus on current MVC developers (largest population of developers)</li>
<li>focus on (b)leading edge developers (small but very vocal population)</li>
</ul>
<p>The difference in focus is the type of stuff you have to show. Current MVC developers have a different viewpoint than the (b)leading edge devs. The latter know already about component frameworks, and should be enticed to try Wicket, the current MVC developers may have heard about Component Frameworks (JSF, Tapestry), but many of them still haven't, or were afraid to really try them.</p>
<p>So my question is: What do you look for in an article about a new, <strong>cool</strong> web application framework?</p>
