---
layout: post
status: publish
published: true
title: Wicket 1.1-rc2 RELEASED!!!
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 124
wordpress_url: http://martijndashorst.com/2005/10/05/wicket-11-rc2-released/
date: '2005-10-05 22:56:26 +0200'
date_gmt: '2005-10-05 22:56:26 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>
After some hard labour, I've finally released the second release candidate of <a href="http://wicket.sf.net">Wicket 1.1</a>. Thank you all for waiting and keeping your fingers crossed. Here are the release notes:</p>
<p>
The wicket team is pleased to announce the Wicket 1.1-rc2 release!</p>
<p>
<a href="http://wicket.sourceforge.net">http://wicket.sourceforge.net</a></p>
<p>
Wicket is a Java web application framework that takes simplicity, separation<br />
of concerns and ease of development to a whole new level. Wicket pages can be<br />
mocked up, previewed and later revised using standard WYSIWYG HTML design<br />
tools. Dynamic content processing and form handling is all handled in Java<br />
code using a first-class component model backed by POJO data beans that can<br />
easily be persisted using your favourite technology.</p>
<p>
Changes in this version include:</p>
<p>
  <b>New Features:</b></p>
<ul>
<li>added class wicket.markup.html.image.resource.BlobImageResource to make<br />
  working with images from databases easier. </li>
<li>Made FileResourceStream non-final to support using custom content type<br />
  schemas etc </li>
</ul>
<p>
  <b>Fixed bugs:</b></p>
<ul>
<li>Image components inside a border component are resolved by the parent of<br />
  the border, thus keeping pre-viewability and componentization. Issue:<br />
  1312787. Thanks to Ari Suutari. </li>
<li>Borders now treat autolinked resources within wicket:head tags correctly<br />
  Issue: 1289768. Thanks to Jan Bares. </li>
<li>skip content of script tag. Treat it as raw markup Issue: 1287640. Thanks<br />
  to Jan Bares. </li>
<li>Wrong impl. on getParameters() of WebRequestWithCryptedUrl Issue: 1275726. </li>
<li>Added serialversionuid to all the serialized wicket classes Issue: 1288373. </li>
<li>Link altered child visibility based on wicket id; hidden 'feature' is<br />
  removed now. Issue: 1297446. Thanks to Sven Meier. </li>
<li>Improved hangman letter images to use just one image reference. Issue:<br />
  1297449. Thanks to Sven Meier. </li>
<li>doc fix for Button.setDefaultFormProcessing Issue: 1287878. Thanks to Leo<br />
  West. </li>
<li>Call invalidate after each setXXX invocation on DefaultButtonImageResource<br />
  to force re-rendering Issue: 1266998. Thanks to Johan Compagner. </li>
<li>Made WicketExampleHeader.html (X)HTML compliant Issue: 1267147. Thanks to<br />
  Jan Bares. </li>
<li>Link.autoEnable is now false by default, and when setEnabled is called,<br />
  autoEnable will be set to false too as calling setEnabled is a consious<br />
  action that has no effect when autoEnable is true Issue: 1251658. Thanks to<br />
  Zhenbang Wei, Niclas Hedhman. </li>
<li>Link.autoEnable is now false by default, and when setEnabled is called,<br />
  autoEnable will be set to false too as calling setEnabled is a consious<br />
  action that has no effect when autoEnable is true. Autolinks are<br />
  autoEnabled by default, and so are the paging navigator links. CHECK YOUR<br />
  CODE WHETHER THIS HAS CONSEQUENCES FOR YOU! Issue: 1240768. Thanks to Gili<br />
  Tzabari. </li>
<li>Models not detached when checkAccess() returns false. Issue: 1290352.<br />
  Thanks to Phil Kulak. </li>
<li>DatePicker fails when used multiple times in the same page Issue: 1290843.<br />
  Thanks to Ralf Ebert. </li>
<li>Buttons with empty value are not found as submit button Issue: 1298789. </li>
<li>Persisted form values not loaded for bookmarkable/redirect pages Issue:<br />
  1298795. </li>
<li>Moved Dojo and Scriptaculous dependencies out of core into contrib packages<br />
  Issue: 1298082. </li>
<li>Renamed pageableListViewNavigation field and getter in PagingNavigator<br />
  Issue: 1288863. Thanks to Igor Vaynberg. </li>
<li>Patch for error in javadoc in ApplicationPages Issue: 1294381. Thanks to<br />
  Igor Vaynberg. </li>
<li>form now checks on enctype attribute. If the attribute is multipart, the<br />
  multipart property of the form object will be set to that. </li>
<li>AJAX component doesn't get correct request parameter path Issue: 1292416. </li>
</ul>
<p>
  <b>Changes:</b></p>
<ul>
<li>Add WebPage(PageParameters) constructor (helps with your IDE's code<br />
  completion features) Issue: 1284625. Thanks to Gwyn Evans. </li>
<li>made Link.isEnabled non final so that users can more easily customize<br />
  on/off behaviour.</li>
</ul>
<p>
<b>Have fun!</b><br />
<i>-The wicket team</i></p>
