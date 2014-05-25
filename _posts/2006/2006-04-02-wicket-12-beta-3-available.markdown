---
layout: post
status: publish
published: true
title: Wicket 1.2 beta 3 available
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 67
wordpress_url: http://martijndashorst.com/2006/04/02/wicket-12-beta-3-available/
date: '2006-04-02 23:56:59 +0200'
date_gmt: '2006-04-02 23:56:59 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>The <a href="http://wicketframework.org">Wicket</a> project has released the third beta release of the 1.2 effort.</p>
<p>
This is our third beta release of the Wicket 1.2 version. We expect this to be the final beta and start finalizing this version soon. Major features of Wicket 1.2 include:</p>
<ul>
<li>Native, cross-platform AJAX support: use AJAX without having to write a single line of JavaScript. Wicket's AJAX cross-platform capabilities <a href="http://www.musingsfrommars.org/2006/03/ajax-dhtml-library-scorecard.html">have been rated 'A'</a></li>
<li>Render multiple components in one AJAX call, where each component can occupy any part of the page</li>
<li>Improved markup inheritance: panels, pages, header contributions</li>
<li>Improved and simplified internationalization (i18n) support, using , better resource bundle lookup strategy</li>
<li>Multiple form component validation, validate two or more fields that are related</li>
<li>Improved form handling: clear form validation workflow that allows you to much easier defined required and type conversion attributes of a form component</li>
<li>Nice URL support through URL mounting</li>
<li>Markup fragments (inline panels)</li>
<li>Improved performance by replacing OGNL with our own object graph language parser</li>
<li>Response filter support, added ServerTime and ServerClientTime filters</li>
<li>Reloading of resource bundles in development mode</li>
<li>Improved unit test support for your Wicket components and pages through the WicketTester, create unittests that run outside the container.</li>
<li>Out-of-the-box AJAX components: paging navigator, link with fallback, auto-updater,  AJAX form, AJAX submit buttons, etc.</li>
<li>Improved authorization and authentication support, giving you the power to specify authorization at the component level. An example project featuring a role based, annotation framework is now part of the standard distribution.</li>
<li>Spring support for injecting your business logic into your web pages in a non-intrusive manner, while still being able to use the convenient Wicket idiom for creating pages (using the Java <tt>new</tt> operator).</li>
<li>Improved settings system: settings are now partitioned into logical groupings to make them easier to find</li>
<li>Numerous bug fixes and minor improvements</li>
</ul>
<p>The upcoming final Wicket 1.2 release will be a major landmark in the history of Wicket and is highly anticipated.</p>
<p>
We have tried to keep API changes to a minimum, but had to change and remove some methods and classes. Wicket 1.2 will not be a drop-in replacement, though most of your application's pages and components should not be affected. There is a migration guide available on our wiki:</p>
<p>
<a href="http://www.wicket-wiki.org.uk/wiki/index.php/Migrate-1.2">Migrating to Wicket 1.2</a></p>
<p>
This is the third beta release, so not considered production ready. Please help us iron out the last bugs by downloading and testing this beta release.</p>
