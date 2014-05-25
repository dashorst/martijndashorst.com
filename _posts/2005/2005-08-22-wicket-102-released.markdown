---
layout: post
status: publish
published: true
title: Wicket 1.0.2 released
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 135
wordpress_url: http://martijndashorst.com/2005/08/22/wicket-102-released/
date: '2005-08-22 22:23:11 +0200'
date_gmt: '2005-08-22 22:23:11 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>
The <a href="http://wicket.sourceforge.net">Wicket</a> team is pleased to announce the <a href="http://wicket.sourceforge.net/wicket-1.0">Wicket 1.0.2 release</a>! </p>
<p>
<a href="http://wicket.sourceforge.net">http://wicket.sourceforge.net</a></p>
<p>
Wicket is a Java web application framework that takes simplicity, separation of concerns and ease of development to a whole new level. Wicket pages can be mocked up, previewed and later revised using standard WYSIWYG HTML design tools. Dynamic content processing and form handling is all handled in Java code using a first-class component model backed by POJO data beans that can easily be persisted using your favourite technology. </p>
<p>
This release fixes some bugs, and with that introduces one API breaking change.The API change involves the IResourceStreamLocator  interface, where the locate method now takes a ClassLoader as an extra parameter. Passing in null  will use the context classloader.</p>
<p>
So while this is a maintenance release, please make sure your code still compiles with this release. </p>
<p>
Changes in this version include:</p>
<p>
  Fixed bugs:</p>
<ul>
<li>newChoiceItem does not use object parameter but selects directly from list Issue: 1263892. Thanks to Arjan Zwaan.</li>
<li>Backport: AbstractDetachableModel doesn't propogate attach/detach Issue: 1253113. </li>
<li>Backport: serialization bug in LocalizedImageResource</li>
<li>Backport: possible NullPointerException in DynamicImageResource.getResourceStream() </li>
<li>Backport: catch if session is saved to disk and reloaded again but locale is changed </li>
<li>fix for classloading problems that caused problems loading markup/ resources for components that were loaded by another classloader than the current one. </li>
<li>Backport: closed FileOutputStream in wicket.util.file.Files in finally block  </li>
</ul>
<p>
Have fun!</p>
<p>
<i>-The wicket team</i></p>
<p>
