---
layout: post
status: publish
published: true
title: Wicket 1.0.1 available
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 156
wordpress_url: http://martijndashorst.com/2005/07/18/wicket-101-available/
date: '2005-07-18 10:34:47 +0200'
date_gmt: '2005-07-18 10:34:47 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 162
  author: Daniel
  author_email: zxvcbvcew@yahoo.com
  author_url: www.mynicemailat.com
  date: '2005-09-16 21:46:43 +0200'
  date_gmt: '2005-09-16 21:46:43 +0200'
  content: Very nice site!
---
<p>The <a href="http://wicket.sf.net">Wicket team</a> is pleased to announce the Wicket 1.0.1 release!</p>
<p><a href="http://wicket.sourceforge.net">http://wicket.sourceforge.net</a></p>
<p>Wicket is a Java web application framework that takes simplicity, separation of concerns and ease of development to a whole new level. Wicket pages can be mocked up, previewed and later revised using standard WYSIWYG HTML design tools. Dynamic content processing and form handling is all handled in Java code using a first-class component model backed by POJO data beans that can easily be persisted using your favourite technology.</p>
<p>Changes in this version include:</p>
<h3>Fixed bugs:</h3>
<ul>
<li>Only validate components that are visible</li>
<li>fixed bug in AbstractPropertyModel which gave problems using custom converters (overriding getConverter for a component) with compound property models Thanks to Adam Howard.</li>
</ul>
<h3>Changes:</h3>
<ul>
<li>FeedbackPanel: made some methods that were not meant for overriding final, and added methods that make extending feedbackpanel easier Thanks to Phil Kulak.</li>
<li>o ComponentStringResourceLoader: resources are now inherited from parent classes when components have been subclassed Thanks to Jonathan Carlson.</li>
</ul>
<p>Have fun!</p>
<p>-The wicket team</p>
