---
layout: post
status: publish
published: true
title: Wicket 1.2.1 adds portlet support to Wicket!
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 32
wordpress_url: http://martijndashorst.com/2006/07/24/wicket-121-adds-portlet-support-to-wicket/
date: '2006-07-24 15:27:12 +0200'
date_gmt: '2006-07-24 15:27:12 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>
		The	<a href="http://wicketframework.org">Wicket</a><br />
		project has released the maintenance release Wicket 1.2.1. Wicket is a Java component based<br />
		web application framework licensed under the open source Apache 2 license. Wicket allows<br />
		Java developers to create highly dynamic web applications using plain Java and HTML.</p>
<p>
		This maintenance release fixes several bugs, and introduces some new features, amongst others the long awaited<br />
		<b>Portlet (JSR-168) support</b>. Due to time constraints, the portlet examples have not been released yet. You can<br />
		find them in SVN until the time has been found to build a proper release for it. The portlet support is still<br />
		young and there may be some incompatibilities to be found between various portlet containers.</p>
<p>
		Here is an (incomplete) list of bug fixes:</p>
<ul>
<li>For improved reliability, instead of utilizing cookies and falling back on a quirky JavasScript, we now use window.name to detect whether we are in sync with the proper page map.</li>
<li>AjaxFormSubmitBehavior no longer incorrectly calls onSubmit() if an error occured during form processing (this aligns it with Button.onSubmit() semantic), instead a new onError() method will be called to allow for error related ajax target processing</li>
<li>Added IDebugSettings.serializeSessionAttributes instead of relying on logger set to debug mode for the session store</li>
<li>Several bug fixes to the Palette component</li>
<li>Property model will now correctly work when chained with a compound model</li>
<li>Fix for firefox not parsing xml-responses after the pages document.domain has been changed to the base-domain.</li>
<p>		Implemented a workaround for an inconsistency between different servlet containers and a bug in the servlet spec which does not seem to state what should happen with empty valued request parameters. This caused Wicket to have some problems (like a failing required test) with Jetty 6.</p>
<li>Implemented anchors on Links. You can either provide a component that is to be used for getting the anchor, or provide an anchor in the href attribute of <a tags.</li>
<li>Portlet (JSR-168) support</li>
<li>Ajax Checkbox now uses onclick instead of onchange which works correctly</li>
<li>Replace GPL licensed diff util with a Apache licensed one</li>
<li>Redirect URLs sometimes were not being encoded for redirects, preventing 'cookie-less' operation (most notably when used with redirectTo). Fixed by always encoding redirects low-down; encoding multiple times has no effect.</li>
<li>Package resources do not have to be pre-registered anymore. When a shared resource is not found, Wicket tries to find a corresponding package resource, and if it finds one, registers it lazily. This fixes quite a few uncomfortable situations, and makes writing custom components easier. Package resources may be blocked by utilizing IPackageResourceGuard (IResourceSettings). By default everything except files with the extension 'html', 'class', 'java', and 'properties' are served. Fixes amongst others bug 1490949. All methods that took Pattern are now deprecated and will be removed in 2.0.
		</li>
<li>Fixed setting the shared resource path so that it strips any jsession id (or whatever there may be between [path];[whatever][?(optional)] which was a problem when a browser doesn't support cookies</li>
<li>Added rating component to extensions</li>
<li>Added Component.replaceWith(Component) to provide better readability and better context for errors that arise from replace actions</li>
</ul>
<p>
		This release should be a drop in release to the 1.2 version. However<br />
		we encourage you to properly test your application before pushing Wicket 1.2.1 into production.
	</p>
<p>
		The Wicket team wishes to thank everyone that has worked with us to find and solve those nasty bugs. We hope that<br />
		you will enjoy this release as much as we do. We thank our users for their continued support.
	</p>
<ul>
<li><a href="http://sourceforge.net/project/showfiles.php?group_id=119783">Download Wicket 1.2.1 now!</a></li>
<li><a href="http://wicketframework.org">Wicket site</a></li>
</ul>
