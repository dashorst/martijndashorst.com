---
layout: post
status: publish
published: true
title: One thing I don&#39;t like about Dojo
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 71
wordpress_url: http://martijndashorst.com/2006/03/27/one-thing-i-dont-like-about-dojo/
date: '2006-03-27 23:29:49 +0200'
date_gmt: '2006-03-27 23:29:49 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 81
  author: Tim Fennell
  author_email: jroller@tfenne.com
  author_url: http://jroller.com/page/tfenne
  date: '2006-03-28 03:13:13 +0200'
  date_gmt: '2006-03-28 03:13:13 +0200'
  content: |-
    No, you're not the only one.  I had a similar experience with dojo.  It's made worse by the fact that the docs pretty explicitly say "just drop dojo.js *here* and go".  Well, erm, no.

    While I'm here, the other thing I don't like is that the documentation for dojo is poor to non-existent.  For someone like me who doesn't want to spend weeks getting up to speed (isn't that the point of a toolkit?) it's a real downer.
---
<p><a href="http://www.dojotoolkit.org">Dojo</a> is one of the best, most used and most popular AJAX and JavaScript toolkit out there. They have brought software engineering to the browser space, and I applaud them for it. There is a downside to it though.</p>
<p>
Because Dojo wants to do everything, it is huge. It requires its own build system and one dojo.js file is possibly quite different when compared to another. As a framework user, I just want the .js file, include it and start using the thing. With Dojo that is not how it is done. Either you assemble your own dojo.js, and from there start using it, or include the bohemoth 150kb JavaScript file.</p>
<p>
I'm not against downloading that 150kb, nor am I afraid that any of our customers might notice the download. It is only done once in the session, or when you set your headers correctly, once per day or even week. Most of our applications get deployed on corporate intranets, so the delay is hardly noticable.</p>
<p>
This is all understandable and workable. I'm not a fan of assembling my own thing, so I just use the standard Ajax distribution and be done with it.</p>
<p>
The build process and packaging of the dojo.js library is also its downside. It is impossible to actually <em>debug</em> anything inside a packaged dojo.js. And <strong>worst</strong> of all, a packaged dojo.js file <em>still</em> tries to include external files. The whole idea of a packaged dojo.js file is that it is standalone. Yes most browsers will ignore the missing files and continue as advertised, but on OS X, Safari stops evaluating JavaScript code when <tt>__package__.js</tt> files are missing. <em>Why does dojo want to include those files?</em> Here is the list of files, files marked in <b>bold</b> are reported missing.</p>
<ul>
<li><b>file:///wicket-examples/src/java/wicket/examples/preview/__package__.js</b></li>
<li>file:///wicket-examples/src/java/wicket/examples/preview/behaviour.js</li>
<li>file:///wicket-examples/src/java/wicket/examples/preview/dojo.js</li>
<li>file:///wicket-examples/src/java/wicket/examples/preview/Home.html</li>
<li>file:////wicket-examples/src/java/wicket/examples/preview/login/Login.html?dojo.transport=xmlhttp&</li>
<li><b>file:///wicket-examples/src/java/wicket/examples/preview/src/__package__.js</b></li>
<li><b>file:///wicket-examples/src/java/wicket/examples/preview/src/io/__package__.js</b></li>
<li>file:///wicket-examples/src/java/wicket/examples/preview/wicket-preview-behaviour.js</li>
<li>file:///wicket-examples/src/java/wicket/examples/preview/wicket-preview.js</li>
</ul>
<p>
So what is the one thing I don't like about dojo? It is just too damn complex.</p>
