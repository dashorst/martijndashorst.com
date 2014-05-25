---
layout: post
status: publish
published: true
title: Final release candidate for Wicket 1.2
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 54
wordpress_url: http://martijndashorst.com/2006/05/15/final-release-candidate-for-wicket-12/
date: '2006-05-15 10:40:31 +0200'
date_gmt: '2006-05-15 10:40:31 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>I have released our (hopefully) final release candidate for <a href="http://wicketframework.org">Wicket web framework</a>. You'll be able to download it when sourceforge has distributed the packages to the mirrors. Apparently they fixed the <a href="http://sourceforge.net/docman/display_doc.php?docid=2352&group_id=1">CVS service</a> but now the main download site is down. Perhaps it is just a fluke and it will be up and running soon. In the mean time, you can upgrade your packages using our <a href="http://wicketframework.org/maven2">Maven 2</a> repository.</p>
<p>
In related news, I am unable to connect to the <a href="http://repo1.maven.org">http://repo1.maven.org</a> primary repository server of Maven. This is a nuisance as I was busy upgrading my mavenized projects to use rc4, and am unable to download the sources.</p>
<p>
Here's the 'official' press release (it will take some time before I upload it to our main website):</p>
<h3>Wicket 1.2-rc4 available</h3>
<p>
	The<br />
	<a href="http://wicketframework.org">Wicket</a><br />
	project has released the fourth release candidate of the<br />
	1.2 effort. We expect this to be the final candidate and<br />
	if no serious bugs are found we will release 1.2 final<br />
	later this week.</p>
<p>
	This is our fourth release candidate of the Wicket 1.2<br />
	version. Major features of Wicket 1.2 include:</p>
<ul>
<li>
		Native, cross-platform AJAX support: use AJAX<br />
		without having to write a single line of<br />
		JavaScript. Wicket's AJAX cross-platform<br />
		capabilities<br />
		<a href="http://www.musingsfrommars.org/2006/03/ajax-dhtml-library-scorecard.html"></p>
<p>			have been rated 'A'<br />
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
<p>		Improved and simplified internationalization<br />
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
<p>	The upcoming final Wicket 1.2 release will be a<br />
	major landmark in the history of Wicket and is<br />
	highly anticipated.</p>
<p>
	We have tried to keep API changes to a minimum, but<br />
	had to change and remove some methods and classes.<br />
	Wicket 1.2 will not be a drop-in replacement, though<br />
	most of your application's pages and components<br />
	should not be affected. There is a migration guide<br />
	available on our wiki:</p>
<p>
	<a href="http://www.wicket-wiki.org.uk/wiki/index.php/Migrate-1.2"><br />
		Migrating to Wicket 1.2<br />
	</a></p>
<p>	This is the fourth release candidate. All our unit tests<br />
	work and we have fixed numerous bugs in the last weeks. We<br />
	expect this release to become the final release candidate,<br />
	and hope no big issues will surface. Please help us iron<br />
	out the last bugs by downloading and testing this release<br />
	candidate!</p>
