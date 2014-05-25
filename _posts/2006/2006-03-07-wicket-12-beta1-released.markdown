---
layout: post
status: publish
published: true
title: Wicket-1.2-beta1 released
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 87
wordpress_url: http://martijndashorst.com/2006/03/07/wicket-12-beta1-released/
date: '2006-03-07 09:13:41 +0100'
date_gmt: '2006-03-07 09:13:41 +0100'
categories:
- wicket
- java
tags: []
comments:
- id: 98
  author: Tom
  author_email: ''
  author_url: ''
  date: '2006-03-08 14:52:06 +0100'
  date_gmt: '2006-03-08 14:52:06 +0100'
  content: |-
    Great, this is becoming awesome !

    But, does this release include Portlet JSR168 support ?
- id: 99
  author: Martijn Dashorst
  author_email: dashorst@users.sf.net
  author_url: http://www.jroller.com/page/dashorst/
  date: '2006-03-08 17:42:33 +0100'
  date_gmt: '2006-03-08 17:42:33 +0100'
  content: Unfortunately no JSR-168 support.
---
<p>
	Finally we have released our first beta of the <a href="http://wicketframework.org">Wicket</a> 1.2 product. Wicket 1.2<br />
	has many improvements and features over Wicket 1.1, including:</p>
<ul>
<li>Native, cross-platform AJAX support: use AJAX without having to write a single line of JavaScript.<br />
		Wicket's AJAX cross-platform capabilities<br />
		<a href="http://www.musingsfrommars.org/2006/03/ajax-dhtml-library-scorecard.html">have been rated 'A'</a></li>
<li>Render multiple components in one AJAX call, where each component can occupy any part of the page</li>
<li>Improved markup inheritance: panels, pages, header contributions</li>
<li>Improved and simplified internationalization (i18n) support, using <wicket:message>,<br />
	    better resource bundle lookup strategy</li>
<li>Multiple form component validation, validate two or more fields that are related</li>
<li>Improved form handling: clear form validation workflow that allows you to much easier defined required and type conversion attributes of a form component</li>
<li>Nice URL support through URL mounting</li>
<li>Markup fragments (inline panels)</li>
<li>Improved performance by replacing OGNL with our own object graph language parser</li>
<li>Response filter support, added ServerTime and ServerClientTime filters</li>
<li>Reloading of resource bundles in development mode</li>
<li>Improved unit test support for your Wicket components and pages through the WicketTester,<br />
	    create unittests that run outside the container.</li>
<li>Out-of-the-box AJAX components: paging navigator, link with fallback, auto-updater,<br />
	    AJAX form, AJAX submit buttons, etc.</li>
<li>Improved authorization and authentication support, giving you the power to specify<br />
	    authorization at the component level. An example project featuring a<br />
	    role based, annotation framework is now part of the standard distribution.</li>
<li>Spring support for injecting your business logic into your web pages in a<br />
		non-intrusive manner, while still being able to use the convenient Wicket<br />
		idiom for creating pages (using the Java <tt>new</tt> operator).</li>
<li>Improved settings system: settings are now partitioned into logical groupings to make them easier to find</li>
<li>Numerous bug fixes and minor improvements</li>
</ul>
<p>	The upcoming final Wicket 1.2 release will be a major landmark in the history of<br />
	Wicket and is highly anticipated.</p>
<p>
	We have tried to keep API changes to a minimum, but had to change and remove<br />
	some methods and classes. Wicket 1.2 will not be a drop-in replacement, though most of your application's pages and<br />
	components should not be affected. There is a migration guide available on our wiki:</p>
<p>
	<a href="http://www.wicket-wiki.org.uk/wiki/index.php/Migrate-1.2">Migrating to Wicket 1.2</a></p>
<p>
	This is the first beta release, so not considered production ready. Please help us iron<br />
	out the last bugs by downloading and testing this beta release.</p>
<p>
<a href="http://sourceforge.net/project/showfiles.php?group_id=119783">Download Wicket and supporting packages</a></p>
