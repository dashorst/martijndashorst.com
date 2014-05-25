---
layout: post
status: publish
published: true
title: Wicket 1.1.1 released
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 101
wordpress_url: http://martijndashorst.com/2006/01/26/wicket-111-released/
date: '2006-01-26 00:28:47 +0100'
date_gmt: '2006-01-26 00:28:47 +0100'
categories:
- java
tags: []
comments: []
---
<p>Dear Wicket community,</p>
<p>
After a couple of months without any significant problem the Wicket team has made available the first maintenance release of <a href="http://wicket.sf.net/wicket-1.1">Wicket 1.1</a>. This release features a backport of a Wicket 1.2 feature: the  tag, which enables you to create internationalized pages without having to resort to adding Label components with StringResourceModel for internationalizing the texts on a page. See the WicketMessageResolver JavaDoc for more information.</p>
<p>
Further enhancements include:</p>
<ul>
<li>Added check and better exception when servlet's init param is missing
<li>Added label tags for generated input tags in CheckBoxMultipleChoice and RadioChoice
<li>Fixed autolink NPE problem
<li>Fixed bug in button that caused the value attirbute to disappear after form submit
</ul>
<p>
Together with this release, the Wicket <a href="http://wicket.sf.net/wicket-extensions">extensions</a>, examples and <a href="http://wicket.sf.net/wicket-quickstart">quickstart</a> projects receive a maintance release and are also released as 1.1.1.</p>
<p>
This release is available through the <a href="http://sourceforge.net/project/showfiles.php?group_id=119783">download pages</a> on SourceForge.</p>
<p>
Enjoy this release!</p>
