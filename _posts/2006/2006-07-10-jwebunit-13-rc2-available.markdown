---
layout: post
status: publish
published: true
title: jWebUnit 1.3-rc2 available
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 38
wordpress_url: http://martijndashorst.com/2006/07/10/jwebunit-13-rc2-available/
date: '2006-07-10 10:57:32 +0200'
date_gmt: '2006-07-10 10:57:32 +0200'
categories:
- java
tags: []
comments:
- id: 37
  author: Michael Slattery
  author_email: ''
  author_url: http://jroller.com/page/MikeSlattery
  date: '2006-07-10 16:32:13 +0200'
  date_gmt: '2006-07-10 16:32:13 +0200'
  content: |-
    And there is a way to have jWebUnit directly drive the IE browser like watir does, or drive any browser like selenium does.

    http://svn.sourceforge.net/viewcvs.cgi/jwebunit/trunk/jwebunit-selenium-plugin/
    http://jacobie.sourceforge.net/

    JWebUnit is looking good!
---
<p>The functional web application testing framework <a href="http://jwebunit.sf.net">jWebUnit</a> has released the <a href="https://sourceforge.net/project/showfiles.php?group_id=61302&amp;release_id=430419">second release candidate</a> for the revival release 1.3. New fixes to the first release candidate are:</p>
<ul>
<li>Show the getTable() method in WebTestCase to allow custom assertions. Thanks to Tetyana Gimgina</li>
<li>Introduce the setFormElement() back as a deprecated method that wraps setTextField(). Fixes 1517851. Thanks to Tetyana Gimgina</li>
<li>Update to HtmlUnit 1.9.</li>
<li>Allow selection of forms with same name (with index).</li>
<li>Add setWorkingForm(String nameOrId, int index) to the API. Fixes 1515297. Thanks to Jeffrey W. Badorek</li>
</ul>
<p>
Please help test this release candidate!</p>
<p>
Great work, Julien!</p>
