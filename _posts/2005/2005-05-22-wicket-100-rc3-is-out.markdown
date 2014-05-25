---
layout: post
status: publish
published: true
title: Wicket 1.0.0-rc3 is out!
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 190
wordpress_url: http://martijndashorst.com/2005/05/22/wicket-100-rc3-is-out/
date: '2005-05-22 18:00:54 +0200'
date_gmt: '2005-05-22 18:00:54 +0200'
categories:
- wicket
tags: []
comments: []
---
<p>Finally the <a href="http://wicket.sourceforge.net" title="Wicket">Wicket</a> project has delivered the last release before 1.0 final. This release marks a significant portion of work (normally this shouldn't be on a release candidate, but hey, we want only the best for you). From the release notes:</p>
<blockquote><p>Finally, after a month of some silence, we have produced our last release candidate before we deploy 1.0. If all goes well, you will see the final release within a week or two. The bug list now only contains an issue relating to clustering. As such we advise you currently to not deploy your application on a cluster, until the issues are resolved, or to be very thorough in your clustering tests.<br />
In this release you won't see major API changes, however the internals have improved significantly. The request cycle has now correct semantics, we have improved the redirect after post pattern, which now performs significantly better than before, and allows you to do your request handling and rendering in one pass, and then redirect to the rendered page. CompoundModel support has improved and works with more components than before. We added support for redirecting to external url's (e.g. Google) directly by introducing RedirectPage.<br />
For the complete list of fixes, updates and changes please see the <a href="http://wicket.sourceforge.net/changes-report.html">release history</a>.</p></blockquote>
<p>At the end of the coming week, we will release the final version. So <em>PLEASE TEST THIS RELEASE</em> and see if you can find bug which we haven't discovered yet!<!-- technorati tags start -->
<p>Technorati Tags: <a href="http://technorati.com/tag/java" rel="tag">java</a>, <a href="http://technorati.com/tag/web framework" rel="tag">web framework</a>, <a href="http://technorati.com/tag/wicket" rel="tag">wicket</a></p>
<p><!-- technorati tags end --></p>
