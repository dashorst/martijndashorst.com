---
layout: post
status: publish
published: true
title: Wicket 1.2 released (finally)
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 50
wordpress_url: http://martijndashorst.com/2006/05/24/wicket-12-released-finally/
date: '2006-05-24 18:12:40 +0200'
date_gmt: '2006-05-24 18:12:40 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>It has come to the conclusion: we've finally released <a href="http://wicketframework.org">Wicket 1.2</a>. It took some very long hours and hard working days: blood, sweat and tears were spilled, <a href="http://www.vaynberg.com/joshua/">babies were born</a> (<em>congratulations Igor!</em>) and <a href="http://www.nearlygood.com/picture/hellfrozeover.html">hell froze over</a>.</p>
<p>
This release is a major landmark in the (short) history of the <a href="http://wicketframework.org">Wicket</a> project. I've blogged several times when we released the release candidates, so you may already be familiar with the new and improved list:</p>
<ul>
<li>
		Native, cross-platform AJAX support: use AJAX<br />
		without having to write a single line of<br />
		JavaScript. Wicket's AJAX cross-platform<br />
		capabilities<br />
		<a href="http://www.musingsfrommars.org/2006/03/ajax-dhtml-library-scorecard.html"><br />
			have been rated 'A'<br />
		</a></p>
</li>
<li>
		Render multiple components in one AJAX call,<br />
		where each component can occupy any part of the<br />
		page
	</li>
<li>
		Improved markup inheritance: panels, pages,<br />
		header contributions
	</li>
<li>
		Improved and simplified internationalization<br />
		(i18n) support, using <wicket:message>,<br />
		better resource bundle lookup strategy
	</li>
<li>
		Out of the box default resource bundles for many<br />
		languages, including<br />
		English, German, Spanish, Portugese, French,<br />
		Hungarian, Dutch, Finnish, Danish, Swedish, Japanese,<br />
		Chinese, Italian, Bulgarian and Farzi (Iranian).
	</li>
<li>
		Multiple form component validation, validate two<br />
		or more fields that are related
	</li>
<li>
		Improved form handling: clear form validation<br />
		workflow that allows you to much easier defined<br />
		required and type conversion attributes of a<br />
		form component
	</li>
<li>Nice URL support through URL mounting</li>
<li>Markup fragments (inline panels)</li>
<li>
		Improved performance by replacing OGNL with our<br />
		own object graph language parser
	</li>
<li>
		Response filter support, added ServerTime and<br />
		ServerClientTime filters
	</li>
<li>
		Reloading of resource bundles in development<br />
		mode
	</li>
<li>
		Improved unit test support for your Wicket<br />
		components and pages through the WicketTester,<br />
		create unittests that run outside the container.
	</li>
<li>
		Out-of-the-box AJAX components: paging<br />
		navigator, link with fallback, auto-updater,<br />
		AJAX form, AJAX submit buttons, etc.
	</li>
<li>
		Improved authorization and authentication<br />
		support, giving you the power to specify<br />
		authorization at the component level. An example<br />
		project featuring a role based, annotation<br />
		framework is now part of the standard<br />
		distribution.
	</li>
<li>
<p>		Spring support for injecting your business logic<br />
		into your web pages in a non-intrusive manner,<br />
		while still being able to use the convenient<br />
		Wicket idiom for creating pages (using the Java<br />
		<tt>new</tt><br />
		operator).
	</li>
<li>
		Improved settings system: settings are now<br />
		partitioned into logical groupings to make them<br />
		easier to find
	</li>
<li>Numerous bug fixes and minor improvements</li>
</ul>
<p>
Wicket runs on any application server supporting the servlet<br />
API version 2.3 and higher, and will work on Java 1.4 SDK's<br />
or newer.</p>
<p>
We have tried to keep API changes to a minimum, but had to change and remove some methods and classes. Wicket 1.2 will not be a drop-in replacement, though most of your application's pages and components should not be affected. There is a migration guide available on our wiki:</p>
<p>
<a href="http://www.wicket-wiki.org.uk/wiki/index.php/Migrate-1.2">Migrating to Wicket 1.2</a></p>
<p>
The Wicket 1.2 release is a highly anticipated major landmark in the history of Wicket. The core development team wishes to extend their gratitude to all users who helped build and test this release.</p>
<p>
Enjoy and have fun!</p>
