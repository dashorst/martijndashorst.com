---
layout: post
status: publish
published: true
title: Wicket 1.1-rc1 released!!!
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 130
wordpress_url: http://martijndashorst.com/2005/09/11/wicket-11-rc1-released/
date: '2005-09-11 22:25:20 +0200'
date_gmt: '2005-09-11 22:25:20 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>
I've just <a href="http://sourceforge.net/project/showfiles.php?group_id=119783">uploaded the first release candidate</a> for <a href="http://wicket.sf.net/wicket-1.1">Wicket 1.1</a>. With this release, Wicket 1.1 is now feature complete and we will soon deliver the final release. Notable features in Wicket 1.1 are:</p>
<ul>
<li>JavaScript support</li>
<li>CSS support</li>
<li>Basic AJAX support</li>
<li>Markup inheritence</li>
<li>Date picker component (in wicket-extensions)</li>
<li>and much more</li>
</ul>
<p>
<i>Please help us test this release so we can make finalize 1.1 before the end of the month!</i></p>
<p>Here is the announcement:</p>
<p>The wicket team is pleased to announce the Wicket 1.1-rc1 release!</p>
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
<p><b>New Features:</b></p>
<ul>
<li>Resource.setHeaders(WebResponse response) so that users can add any header<br />
  they want (cacheable/content disposition) when the resource is served<br />
  Issue: 1286190,1221732. </li>
<li>Buttons can have a model now, for the buttons value attribute </li>
<li>added protected method Session.attach() that is called right before a<br />
  session is used for a request</li>
<li>Added FormComponent.getInputName() that by default generates a name from<br />
  the Form (not included) to the component for better/smaller input names</li>
</ul>
<p><b>Fixed bugs:</b></p>
<ul>
<li>AttributeModifer can't be shared between components Issue: 1286620.</li>
<li>Infinite loop when adding attributemodifier twice Issue: 1286607.</li>
<li>StaticFileResource wasn't used and seemed to be a relic that was refactored<br />
  to PackageResource. StaticFileResource is removed from Wicket. Issue:<br />
  1263833. Thanks to Johan Compagner. </li>
<li>Attributes should preserve case. Before this fix, attributes were converted<br />
  to lower case. Not anymore now. Issue: 1286616. Thanks to Cameron Braid. </li>
<li>Internal Error when using back buttons and Links in ListView Issue:<br />
  1284498. Thanks to Kenneth Foo Chuan Khit.</li>
<li>Odd behaviour when Wicket is the "root" (/*) servlet Issue: 1284029. Thanks<br />
  to Gwyn Evans. </li>
<li>null values in PageParameters are now ignored totally when generating urls,<br />
  instead of resulting in 'x=null'. Issue: 1284508. Thanks to Matej Knop. </li>
<li>fix: now allow multiple ajax handler implementations to contribute to the<br />
  page's header Thanks to Arto Arffman. </li>
<li>Redirect url generating issues. The url was generated before<br />
  Component.onInternalBeginRequest() and that method can generate another<br />
  version. </li>
<li>Clearer message when trying to render abstract Page. Issue: 1255061. Thanks<br />
  to Gili Tzabari. </li>
<li>&lt;wicket:head&gt; behaviour slighty changed to be more intuitiv. </li>
<li>addToHeader() is nor longer required. Just use add() to add components<br />
  which are inside a head section </li>
<li>xmlns:wicket="http:/..." is now removed from markup as well if<br />
  setStripWicketTag(true) Issue: 1276640. Thanks to Simon Berriman. </li>
<li>&lt;select .../&gt; is now allowed and will automatically be converted into<br />
  a open-body-close tag Issue: 1243152. Thanks to Eelco Hillenius. </li>
<li>Fixed wrong implementation off getParameters() in WebRequestWithCryptedUrl<br />
  Issue: 1275726. Thanks to Ingram Chen. </li>
<li>Unescaped &lt;b&gt; tag in XmlTag Javadoc Issue: 1280468. Thanks to Simon<br />
  Berriman. </li>
</ul>
<p><b>Changes:</b></p>
<ul>
<li>Moved resource reference classes from extensions into core Issue: 1255188.<br />
  Thanks to Gili Tzabari. </li>
</ul>
<p><b>Removed features:</b></p>
<ul>
<li>Integrated classes from concurrent.jar into wicket.util, removing the need<br />
  for concurrent.jar Issue: 1283301.</li>
</ul>
<p>
Have fun!</p>
<p>
<i>-The wicket team</i></p>
