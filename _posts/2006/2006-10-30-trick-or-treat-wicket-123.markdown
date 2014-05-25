---
layout: post
status: publish
published: true
title: Trick or treat! Wicket 1.2.3
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 21
wordpress_url: http://martijndashorst.com/2006/10/30/trick-or-treat-wicket-123/
date: '2006-10-30 22:05:45 +0100'
date_gmt: '2006-10-30 22:05:45 +0100'
categories:
- wicket
- java
tags: []
comments:
- id: 16
  author: Closet Wicket lover
  author_email: ''
  author_url: ''
  date: '2006-10-31 16:49:14 +0100'
  date_gmt: '2006-10-31 16:49:14 +0100'
  content: Wicked cool! Thank you!
---
<p>
The Wicket team is pleased to announce the Wicket 1.2.3 release!</p>
<p>
Wicket is a Java web application framework that takes simplicity, separation of concerns and ease of development to a whole new level. Wicket pages can be mocked up, previewed and later revised using standard WYSIWYG HTML design tools. Dynamic content processing and form handling is all handled in Java code using a first-class component model backed by POJO data beans that can easily be persisted using your favorite technology.</p>
<p>
More information on Wicket can be found here: <a href="http://wicketframework.org">http://wicketframework.org</a></p>
<p>
Although Wicket has recently entered the ASF Incubator, this interim<br />
release is provided outside of the ASF, solely as a service to existing<br />
Wicket users to resolve existing bugs in the Wicket product. As such,<br />
this release of the Wicket project is not endorsed or approved by<br />
the Apache Software Foundation. The Apache Software Foundation is<br />
in no way affiliated with this release.</p>
<p>
Changes in this version include:</p>
<p>
New Features:</p>
<ul>
<li>Added method protected void onDisabled(final ComponentTag tag) to FormComponent, which is called during rendering when the component is disabled. By default, an disabled="disabled" attribute is added, but clients may override this method. </li>
<li>Made synchronization timeout configurable on an application level. Later, we might add more fine grained control. </li>
<li>Implemented optional interface for initializers: IDestroyer that may be implemented by initializers to clear up stuff when the application is shut down. Wicket's JMX code uses this to clean up the JMX beans it registered on application shutdown. </li>
<li>Wicket now has JMX support. For 1.2 as a separate project (wicket-jmx), for 2.0 as part of the core distribution. </li>
<li>The application's configuration type is now kept in a member which can be read using Application#getConfigurationType. </li>
<li>Added AbortWithWebError abort exception. </li>
<li>Bookmarkable page links set the target attribute to the proper page map when a page map is set and when the tag has a target attribute</li>
</ul>
<p>
Fixed Bugs:</p>
<ul>
<li>Make sure that bookmarkable urls for classes containing non-ascii characters is encoded properly.  Issue: WICKET-16.</li>
<li>There was no check on render authorization action done for seperate component renders, resulting in that authorization check not being executed with ajax requests. Thanks to Benjamin Podszun.</li>
<li>Page was not checked for render authorization action.</li>
<li>Package resources that are not found now log a warning and then throw an abort error instead of a regular exception and send a 404 to the browser if in a web request.</li>
<li>Fixed deadlock possiblity on high load situations where resource managing filters (such as Spring's/ Hibernate's OpenSessionInViewFilter) run out of those resources before they are released. A test for this issue can be found in wicket-threadtest, wicket.threadtest.App2Test1. This bug is dangerous; everyone using Wicket 1.2.x is encouraged to update to this Wicket version asap. Thanks to Eelco Hillenius. </li>
<li>ResourceReference and PackageResourceReference evolved in doing almost the same thing with ResourceReference falling back to package resources. The two classes were used mixed for the same purposes, so it obviously was confusing. PackageResourceReference is now deprecated (and removed in 2.0) and ResourceReference uses package resources as the explicit default now. </li>
<li>FileUploadField's fileUpload member is now transient, and nulled at the end of a request; fileUpload depends on non-serializable classes and should be used for the upload request only anyway. </li>
<li>InputStreams returned from FileUpload is now closed at the end of the request  Issue: 1543832. </li>
<li>Fixed a bug in WicketTester.clickLink. When clicking an AjaxSubmitLink which submitted a form with a CheckGroup inside it, the test would fail. This was because I had only checked for RadioGroup when copying the data from the form to the request. </li>
<li>Do not set window.name automatically to the page map as this gives problems with frames </li>
<li>Buttons are now versioned by default </li>
<li>It is now possible to override default TypeValidator error key via ConversionException.setResourceKey() </li>
<li>Fixed bug where head contributions done through header contributors added to the page only worked on first page render </li>
<li>SubmitLink now properly supports back button Thanks to Erik Brakkee. </li>
<li>Fixed AjaxPreprocessingCallDecorator Thanks to Ingram Chen. </li>
<li>AjaxFormValidatingBehavior now property updates feedback panels when form error occurs Thanks to Adam Smyczek. </li>
<li>AjaxRequestTarget now doesn't switch component use check off, as it is no longer needed. Thanks to Tomer Mevorach. </li>
</ul>
<p>
You can download this release from the <a href="http://sourceforge.net/project/showfiles.php?group_id=119783">sourceforge.net servers</a>, and it will be pushed to the maven ibiblio repository momentarily.</p>
<p>
Have fun!</p>
<p>
- The Wicket team</p>
