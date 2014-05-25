---
layout: post
status: publish
published: true
title: Wicket Web Beans
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 296
wordpress_url: http://martijndashorst.com/blog/2007/09/12/wicket-web-beans/
date: '2007-09-12 20:32:09 +0200'
date_gmt: '2007-09-12 19:32:09 +0200'
categories:
- wicket
tags: []
comments:
- id: 11376
  author: Wille
  author_email: wille.faler@gmail.com
  author_url: http://faler.wordpress.com
  date: '2007-09-13 14:26:20 +0200'
  date_gmt: '2007-09-13 13:26:20 +0200'
  content: "Hmm.. \r\nSounds pretty similar to something I have been doing at work
    for the past day or so.. Although the \"convention\" used in what I have been
    implementing is annotations for the most part, for instance, if you want a String
    field to be represented by a TextField in a form, you simply annotate it with
    @TextField. \r\nSimilar things are used for validation, and annotations for DropDownChoices
    can define the source and type of the choices (for instance, how to retrieve a
    List)."
---
<p>
Today a new <a href="http://wicket.apache.org/" title="Apache Wicket">Wicket</a> based project has announced itself: <a href="http://wicketwebbeans.sf.net/" title="Wicket Web Beans">Wicket Web Beans</a> (WWB). WWB is project that allows you to use the JavaBeans specification to quickly, and I really mean <strong>quickly</strong> create CRUD type user interfaces.</p>
<p style="text-align:center"><img src="http://martijndashorst.com/blog/blog/wp-content/uploads/2007/09/wicket_web_beans.png" alt="Wicket Web Beans" width="480"/></p>
<p>
Dan, the creator of Wicket Web Beans writes:</p>
<blockquote><p>Wicket Web Beans (WWB) is a Wicket component toolkit for displaying and editing POJOs that conform to the JavaBeans specification. Web pages are automatically generated based on bean properties and certain conventions. If necessary, the layout, editability, and actions of these pages can be customized on an exception basis. In other words, the toolkit normally does what you'd expect, but when it doesn't, you can override its behavior.</p></blockquote>
<p>
From the documentation I could peruse, this sounds like an amazing addition to the Wicket framework space. You can get it now, <a href="http://sourceforge.net/project/showfiles.php?group_id=205206" title="Download Wicket Web Beans">downloads</a> start at Wicket 1.2.6, and I think support for Wicket 1.3 is in the works.</p>
