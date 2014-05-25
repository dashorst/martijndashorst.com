---
layout: post
status: publish
published: true
title: I&#39;m upgrading to Wicket 1.2-rc1, are you?
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 63
wordpress_url: http://martijndashorst.com/2006/04/18/im-upgrading-to-wicket-12-rc1-are-you/
date: '2006-04-18 00:01:00 +0200'
date_gmt: '2006-04-18 00:01:00 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 71
  author: Rui Pacheco
  author_email: rui.pacheco@gmail.com
  author_url: ''
  date: '2006-04-18 13:15:16 +0200'
  date_gmt: '2006-04-18 13:15:16 +0200'
  content: |-
    Hi

    I'm using Wicket 1.2 but I have a problem. Most of the examples on the website are about Wicket 1.1. Could you update them? Make them more 1.2?
    I know we still have Javadocs and all, but examples are the fastest route to productivity.
- id: 72
  author: n8
  author_email: ''
  author_url: http://technically.us/n8/
  date: '2006-04-18 21:23:38 +0200'
  date_gmt: '2006-04-18 21:23:38 +0200'
  content: |-
    You can download up-to-date Wicket examples from the link for rc1 (above). There are also examples online (mine) that use 1.2, ajax, etc:
    http://databinder.net/examples.html
---
<p>
	The<br />
	<a href="http://wicketframework.org">Wicket</a><br />
	project has released the first release candidate of the<br />
	1.2 effort.</p>
<p>
	This release is available on the SourceForge file release system for our project.<br />
	You can download the released files on the next link:</p>
<ul>
<li><a href="http://sourceforge.net/project/showfiles.php?group_id=119783">Download Wicket-1.2-rc1</a></li>
</ul>
<p>
	This is our first release candidate of the Wicket 1.2<br />
	version. We expect to finalize the 1.2 release very soon.<br />
	Major features of Wicket 1.2 include:</p>
<ul>
<li>
		Native, cross-platform AJAX support: use AJAX<br />
		without having to write a single line of<br />
		JavaScript. Wicket's AJAX cross-platform<br />
		capabilities<br />
		<a href="http://www.musingsfrommars.org/2006/03/ajax-dhtml-library-scorecard.html"><br />
			have been rated 'A'<br />
		</a>
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
		Spring support for injecting your business logic<br />
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
	The upcoming final Wicket 1.2 release will be a<br />
	major landmark in the history of Wicket and is<br />
	highly anticipated.</p>
<p>
	We have tried to keep API changes to a minimum, but<br />
	had to change and remove some methods and classes.<br />
	Wicket 1.2 will not be a drop-in replacement for<br />
	Wicket 1.1 applications (and earlier).<br />
	Most of your application's pages and components<br />
	should not be affected though. There is a migration guide<br />
	available on our wiki:</p>
<p>
	<a href="http://www.wicket-wiki.org.uk/wiki/index.php/Migrate-1.2"><br />
		Migrating to Wicket 1.2<br />
	</a></p>
<p>
	This release contains numerous fixes over the Wicket 1.2-beta3 release,<br />
	so you are encouraged to upgrade to 1.2-rc1. We consider the API to<br />
	be stable and expect following releases to be drop-in releases. We do<br />
	keep the right to break this promise in case of a nasty bug.</p>
<p>
	We hope you will <a href="http://sourceforge.net/project/showfiles.php?group_id=119783">download</a> and test this release to flesh out the last<br />
	bugs. Have fun!</p>
