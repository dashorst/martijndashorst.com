---
layout: post
status: publish
published: true
title: Code Ronin covering the Web Framework Smackdown
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 160
wordpress_url: http://martijndashorst.com/2005/07/04/code-ronin-covering-the-web-framework-smackdown/
date: '2005-07-04 16:27:05 +0200'
date_gmt: '2005-07-04 16:27:05 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 166
  author: coderonin
  author_email: rudy@coderonin.net
  author_url: http://www.coderonin.net/
  date: '2005-07-04 15:26:27 +0200'
  date_gmt: '2005-07-04 15:26:27 +0200'
  content: |-
    Yeah, the word "different" was really inapporpriate, sorry.

    What I meant to say is that it would take time for us to learn it and adjust the "way we work", more so  than say JSF (which we can kinda use with Struts), Shale (legacy) and Tapestry (which some favour cause it is "mature").

    Still, like I said, first item of business is to rewrite our logic into POJOs, so our choice of framework will be more open. I will probably revisit Wicket at that time ;-)
- id: 167
  author: Martijn Dashorst
  author_email: dashorst@users.sf.net
  author_url: http://www.jroller.com/page/dashorst/
  date: '2005-07-04 15:53:56 +0200'
  date_gmt: '2005-07-04 15:53:56 +0200'
  content: |-
    Whether you are going to work with JSF, Tapestry or Wicket, your programming paradigm is going to shift anyway. That is the 'unlearning curve' that Howard Lewis Ship is talking about, and that is the same for each framework you mentioned (apart from WebWork, but just like you I agree with David Geary here).

    Moving your business logic into the POJO's is always a good thing, when working with either JSF, Wicket or Tapestry. But I doubt that Struts will enable you to leverage your POJO's too much.
---
<p>From the blogging search after the Smackdown, I've found the <a href="http://www.coderonin.net">Code Ronin</a> to have <a href="http://www.coderonin.net/2005/07/02/lets-get-webby-to-rumbleeeee/">blogged about it</a>, and the following quotes made me trigger:</p>
<blockquote><p><i>Out of those presented, the only ones I can see us migrating to are JSF, Tapestry, and Shale. Why not Wicket and WebWork? Well, while Wicket sounds delightful, it sounds really different, and as for WebWork, I have to agree with Craig.</i></p></blockquote>
<p>Glad to hear that Wicket sounds delightful, but considering your next statement on JSF:</p>
<blockquote><p><i>Using JSF will be easy. The biggest con is that the tags it presents are VERY GUI oriented, designed to replace HTML in the JSPs. That's great for developers, but not so great for the web integrators at my workplace who like to code their own HTML and JavaScript, thank you very much. Still, my boss spoke of visual beans two years back, and that's what JSF is.</i></p></blockquote>
<p>I <em>REALLY ENCOURAGE</em> you to take an interest in <a href="http://wicket.sf.net">Wicket</a> as we allow the web designers to design and developers develop <em>nearly</em> <strong>independently</strong>. Wicket has a pure HTML nature fulfilling your requirement to allow webdesigners to design the pages.</p>
<p>I invite you to check it out and see whether you like it. It is too early to dismiss it based on 'it sounds really different'. I attended several JSF sessions on JavaOne, sat through both 'Tapestry in Action' and 'WebWork' presentations, and I dare to say: Wicket is far more easy to <a href="http://dictionary.reference.com/search?q=grok">grok</a> than the other component based frameworks, and I might add: the current myriad of MVC frameworks.</p>
