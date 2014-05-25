---
layout: post
status: publish
published: true
title: Wicket 1.1-beta1 Ready For Testing
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 152
wordpress_url: http://martijndashorst.com/2005/07/25/wicket-11-beta1-ready-for-testing/
date: '2005-07-25 18:31:45 +0200'
date_gmt: '2005-07-25 18:31:45 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>The <a href="http://wicket.sf.net">Wicket</a> team has released the first (and hopefully last) beta of the upcoming 1.1 release of <a href="http//wicket.sf.net">Wicket</a>. The 1.1 beta release has the following features available:</p>
<ul>
<li>Full JavaScript and CSS support - allowing you to package JavaScript and/or CSS with your component, and have it contribute the JavaScript/CSS to the header of the including page</li>
<li>Markup inheritence - ever wanted to create a base page with a menu, some <tt>DIV</tt>s or other standard components, which are present on <em>ALL</em> pages in your application? Wicket already supported inheritence on the Java side of things, but now includes markup inheritence. This allows you to create such template pages and have subclasses fill in the blanks.</li>
<li>Simplification of Choice component - we had some complaints on the 1.0 implementation of the Choice components being too complex, so we revisited this component. This will break stuff in your application, but it has improved considerable!</li>
<li><b><i>EXPERIMENTAL AJAX</i></b> support. There is some experimental AJAX support available. But not for the faint of heart and only when you don't mind changing API's. <em>USE AT YOUR OWN RISC!</em></li>
<li>Component seperator character has been altered from '.' (dot) to ':' (colon), paving the path for OGNL type paths in form components, this allows for even more shorter code in your forms  (e.g. <input type="text" wicket:id="child.birthday" /> )</li>
<li>Component reference examples in the Wicket examples download</li>
<li>Date picker component in extensions - as a first component utilizing our new JavaScript support, Wicket now has a very cool and rich Date picker in the extensions package. Check it out and (re)discover the ease of component based development!</li>
</ul>
<p>This release features many (small) improvements, so go to the SourceForge <a href="http://sourceforge.net/project/showfiles.php?group_id=119783">download pages</a>, download Wicket, Extensions and the examples and have fun!</p>
