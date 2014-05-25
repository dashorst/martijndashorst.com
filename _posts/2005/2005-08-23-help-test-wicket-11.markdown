---
layout: post
status: publish
published: true
title: Help Test Wicket 1.1!
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 134
wordpress_url: http://martijndashorst.com/2005/08/23/help-test-wicket-11/
date: '2005-08-23 00:45:49 +0200'
date_gmt: '2005-08-23 00:45:49 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>
I've just released 1.1-beta 3. It contains the first cut of the IPageable interface change, and it is the first release after the validation changes. Please test this release and see how we can possibly improve on these parts.</p>
<p>
We want to finalize the 1.1 branch as soon as possible, but not without sacrificing quality. So please help us test this release and send in your bug reports. The sooner we are able to finalize 1.1, the sooner we can focus on 1.2 and bring you Ajax, Portlets and all other nice things.</p>
<p><b>The announcement</b></p>
<p>
<a href="http://wicket.sf.net/wicket-1.1">Wicket 1.1-beta 3</a> is available for download and testing. This is a beta release, so<br />
you may expect some API changes. Most notable features in this release are:</p>
<ul>
<li>Component developers can now initialize resources when the app starts up</li>
<li>Added WebSession.getId() and WebRequestCycle.getWebSession()</li>
<li>Added AbstractReadOnlyModel Issue: 1250030. Thanks to Igor Vaynberg.</li>
<li>Fixed: AbstractDetachableModel doesn't propogate attach/detach, Thanks to Cameron Braid</li>
<li>Fixed: Can't have two FeedbackPanels, Thanks to Simon Berriman</li>
<li>Fixed: FeedbackPanel produces illegal HTML, Thanks to Gili Tzabari</li>
<li>Fixed: WicketServlet.doGet URI bug, Thanks to Jan Bares</li>
<li>Fixed: Classloading problems that caused problems loading markup/resources for components that were loaded by another classloader than the current one</li>
<li>Extended markup inheritance to support panels and borders</li>
<li>Made a significant reduction in the size of pages, especially big pages</li>
<li>Refactored feedback completely. The new code is smaller, more powerful and more elegant, but it will break clients.</li>
<li>Added automatic multiPart support to Form.</li>
</ul>
<p>
See the complete <a href="http://wicket.sourceforge.net/changes-report.html#1_1-b3">list of changes here</a>.</p>
