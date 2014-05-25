---
layout: post
status: publish
published: true
title: Selenium rocks!
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 96
wordpress_url: http://martijndashorst.com/2006/02/10/selenium-rocks/
date: '2006-02-10 15:07:13 +0100'
date_gmt: '2006-02-10 15:07:13 +0100'
categories:
- java
tags: []
comments:
- id: 109
  author: Anthony Garcia
  author_email: ''
  author_url: ''
  date: '2006-02-15 18:24:58 +0100'
  date_gmt: '2006-02-15 18:24:58 +0100'
  content: Have you had a chance try WATIR? I'm mainly just curious about another
    informed opinion about WATIR vs. Selenium.
---
<p>A couple of weeks ago, I 'stumbled' upon a blog post by the <a href="http://www.ajaxian.com">Ajaxian</a> guys in which they mentioned <a href="http://www.openqa.org/selenium">Selenium</a>'s ability to test AJAX applications.</p>
<p>
As a not so active as I should be maintainer of the <a href="http://jwebunit.sf.net">jWebUnit</a> project, it sparked my curiosity immediately. JavaScript support in jWebUnit (and HTTPUnit, on which jWebUnit is based) is mediocre at best and not well supported. Running inside the browser makes cross-browser testing much easier: all you need is the browser version you want your application to run in, and point it to the selenium testsuite for your application.</p>
<p>
When I took 2 hours to play with Selenium, I was blown away. Together with the Selenium recorder (now Selenium IDE) you have testing dynamite in your hands. Usually deploying a website takes a lot of regression testing which doesn't happen too often. Using Selenium you can run a good sanity test within 5 minutes.</p>
<p>
I find it hard to say, but in my opinion the days of jWebUnit as a functional/integration test suite are numbered. Perhaps one release to fix the outstanding bugs, upgrade the libraries, and then move over to the new world: Selenium.</p>
