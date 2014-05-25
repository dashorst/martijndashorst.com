---
layout: post
status: publish
published: true
title: wicket 1.x development has moved to trunk in svn
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 253
wordpress_url: http://martijndashorst.com/blog/2007/04/19/wicket-1x-development-has-moved-to-trunk-in-svn/
date: '2007-04-19 09:10:46 +0200'
date_gmt: '2007-04-19 08:10:46 +0200'
categories:
- wicket
tags: []
comments: []
---
<p>We have now switched trunk and wicket 1.x in subversion. We have been getting reports of confused users about the status of Wicket and where to get the code from. </p>
<p>We appologize for the inconvenience this will cause.</p>
<p>From now on trunk is again our main development branch.</p>
<p>The previous Wicket 2 *with* constructor change has now been moved to branches/wicket-2-DISCONTINUED and is in maintenance mode (i.e. only bug fixes on a case-by-case basis).</p>
<h5>Staying with Wicket 1.3</h5>
<p>If you depended on branches/wicket-1.x do the following in your checked out working copy:</p>
<blockquote><p>svn switch http://svn.apache.org/repos/asf/incubator/wicket/trunk</p></blockquote>
<p>(if you are a Wicket committer, substitute http with https)</p>
<h5>Staying with Wicket 2 *with* constructor change</h5>
<p>If you were working on trunk and want to stay with the latest in that branch you will need to do the following in your working copy:</p>
<blockquote><p>svn switch http://svn.apache.org/repos/asf/incubator/wicket/branches/wicket-2-DISCONTINUED</p></blockquote>
<p>(if you are a Wicket committer, substitute http with https)</p>
<p>We will switch the svn branches in wicket-stuff too.</p>
