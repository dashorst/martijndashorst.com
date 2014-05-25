---
layout: post
status: publish
published: true
title: Finally some positive feedback on maven
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 219
wordpress_url: http://martijndashorst.com/2005/04/04/finally-some-positive-feedback-on-maven/
date: '2005-04-04 11:14:49 +0200'
date_gmt: '2005-04-04 11:14:49 +0200'
categories:
- maven
tags: []
comments: []
---
<p>
Finally someone writing a <a href="http://www.jroller.com/page/RickHigh/20050402#why_maven_does_not_suck">good editorial</a> about <a href="http://maven.apache.org">Maven</a>, after the <a href="http://howardlewisship.com/blog/2005/02/crawl-walk-run.html">heat</a> Maven got from community 'leaders'. They seem to constantly <a href="http://www.beust.com/weblog/archives/000244.html">regurgitate</a> <a href="http://howardlewisship.com/blog/2004/05/moving-away-from-maven.html">old beliefs</a>.</p>
<p>
I got introduced to Maven in the first half of 2003, when I was wrestling with maintaining <a href="http://ant.apache.org">Ant</a> build scripts. Maven tickled my curiosity but I didn't grasp the concepts. Only when I switched employers to <a href="http://www.topicus.nl">Topicus</a> my new collegues introduced me to Maven and I was hooked.</p>
<p>Maven was still in beta7 or so, but I found it really usable. I <em>like</em> the standard project structure, I <em>do</em> think that creating only one artifact per project is the correct way to build and maintain your projects, I <em>enjoy</em> writing my project documentation about building, installing, deployment and so forth in the XDoc format.</p>
<p>For my open source projects (<a href="http://jwebunit.sourceforge.net">JWebUnit</a>, and <a href="http://wicket.sourceforge.net">Wicket</a>) I constantly use Maven to maintain the dependencies and generate the website. For Wicket, I've created a special template to allow a much nicer design of the website than is possible with the default Maven template. Our corporate designer, Wouter de Jong, has created a special look-and-feel for the Wicket website, and I had little difficulty to transform his design into the stylesheet you <a href="http://wicket.sourceforge.net">see here</a>.</p>
<p>In my distribution work for Wicket I use several plugins that make my life easier:</p>
<ul>
<li>the distribution plugin (dist:build-bin)</li>
<li>the site plugin (site and site:sshdeploy)</li>
<li>the xdoc plugin (to generate the changed XDocs quickly use the <a href="http://maven.apache.org/reference/plugins/console/">maven console</a>)</li>
<li>the sourceforge plugin</li>
<li>the create-upload-bundle plugin</li>
</ul>
<p>Areas in which Maven could improve are the performance and the integration of the plugins. If I have run the test plugin, and then I run the site plugin, the tests are performed again, regardless whether anything has changed. This makes using Maven feel slow, and especially the process of performing a release on Sourceforge quite painful.</p>
<p>Although there are enough areas in which Maven could be better, it really makes my job a lot easier and I wouldn't want to go back to solely using Ant at any time.</p>
