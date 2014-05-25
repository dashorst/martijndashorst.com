---
layout: post
status: publish
published: true
title: Anonymizing artifactory - removing usage tracker
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 380
wordpress_url: http://martijndashorst.com/blog/2008/07/01/anonymizing-artifactory-removing-usage-tracker/
date: '2008-07-01 10:04:36 +0200'
date_gmt: '2008-07-01 09:04:36 +0200'
categories:
- wicket
tags: []
comments: []
---
<p>I'm currently toying around with <a href="http://www.jfrog.org/sites/artifactory" title="Artifactory - About">Artifactory</a>, a Maven repository manager built with Wicket. The first thing that struck me when I looked at the generated source (I am a sucker for really nice semantic HTML markup, always trying to learn new tricks), was an image that was loaded directly from a remote IP. Now I can understand JFrog to want to know how often their free open source Maven repository manager is used, but I figured letting them know just once was enough.</p>
<p>
	Fortunately it is not too difficult to remove the offending image from the templates. You have to edit the file:</p>
<ul>
<li>artifactory\WEB-INF\classes\org\artifactory\webapp\wicket\BasePage.html</li>
</ul>
<p>And remove the image from the footer. After a restart of your server you are using Artifactory without tracking.</p>
