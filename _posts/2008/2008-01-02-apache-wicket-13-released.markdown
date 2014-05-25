---
layout: post
status: publish
published: true
title: Apache Wicket 1.3 released
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 334
wordpress_url: http://martijndashorst.com/blog/2008/01/02/apache-wicket-13-released/
date: '2008-01-02 21:15:54 +0100'
date_gmt: '2008-01-02 20:15:54 +0100'
categories:
- wicket
tags: []
comments:
- id: 28696
  author: Gabriel K.
  author_email: GabrielKastenbaum@yahoo.fr
  author_url: ''
  date: '2008-01-02 23:11:42 +0100'
  date_gmt: '2008-01-02 22:11:42 +0100'
  content: Fantastic! Great news!
- id: 57161
  author: Apache Wicket 1.3 at Java Guru
  author_email: ''
  author_url: http://blog.javaguru.hu/2008/01/11/apache-wicket-13/
  date: '2008-08-18 08:59:14 +0200'
  date_gmt: '2008-08-18 07:59:14 +0200'
  content: "[...] ami egy komponens alapú web keretrendszer. A JavaLobby internetes
    portál interjút készített Martijn Dashorst-al, a projekt vezet?jével, bel?le a
    Wicket újdonságairól, a projekt céljairól tudhatunk meg [...]"
---
<p>
Starting the new year with a bang the Wicket Team has released Apache Wicket 1.3.  With this release comes a lot of great successes, but most of all the team wanted to express their wishes to everyone for a happy new year.</p>
<p>
<a href="http://wicket.apache.org">Apache Wicket</a> is one of the fastest growing Java open source component based web frameworks. With a focus on producing valid html and a logical separation between design and code.  Within minutes you can start to enjoy throwing out tag soup, complex components and high maintenance overhead for a simple POJO + html data model.</p>
<p>Take a look at some of the following highlights or skip to the bottom and get started now.</p>
<ul>
<li>last JDK-1.4 release (next release will be Java 5 based)</li>
<li>first Apache release: renamed packages to <code>org.apache.wicket</code></li>
<li>simplified several core APIs</li>
<li>now works with zero-config behind a proxy server using relative URLs</li>
<li>added Google Guice support</li>
<li>use your Wicket pages directly in a portal without changing a line of code (JSR-168/JSR-286 support)</li>
<li>switched logging API from commons-logging to slf4j</li>
<li>integrate velocity templates as panels in your pages</li>
<li>YUI-calendar and Joda time based date picker (wicket-datetime)</li>
<li>contribute new javascript dependencies to the page header using an Ajax requeset</li>
<li>improved, more robust header contributions</li>
<li>scale to extremely large numbers of users with stateless pages and components</li>
<li>improved AjaxTree/AjaxTreeTable</li>
<li>hybrid URL encoding to make search engines and your users happy</li>
<li>create form panels and use them anywhere without worrying about the nesting of form tags</li>
<li>minimized session use by storing component hierarchy in file system (DiskPageStore)</li>
</ul>
<p>
Get started today by checking out the following examples or follow the download link directly at the bottom.</p>
<ul>
<li><a href="http://wicketstuff.org/wicket13/ajax/tree/table/editable">An editable Ajax tree table</a></li>
<li><a href="http://wicketstuff.org/wicket13">All examples</a></li>
<li><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.3.0">Download Apache Wicket 1.3</a></li>
</ul>
<p>
Best wishes from the Wicket Team and a prosperous 2008!</p>
