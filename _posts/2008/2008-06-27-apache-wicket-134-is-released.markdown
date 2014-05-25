---
layout: post
status: publish
published: true
title: Apache Wicket 1.3.4 is released!
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 378
wordpress_url: http://martijndashorst.com/blog/2008/06/27/apache-wicket-134-is-released/
date: '2008-06-27 00:00:39 +0200'
date_gmt: '2008-06-26 23:00:39 +0200'
categories:
- wicket
tags: []
comments: []
---
<p>The Apache Wicket team is proud to announce the availability of the fourth maintenance release: Apache Wicket 1.3.4. A lot of bugs have been squashed and several improvements implemented. Two noteworthy bugs have been squashed:</p>
<ul>
<li>cross session leakage due to a dangling thread local in exceptional circumstances</li>
<li>memory leak in localizer (<a href="https://issues.apache.org/jira/browse/WICKET-1667">WICKET-1667</a>)</li>
</ul>
<p>It is therefore recommended you update to Wicket 1.3.4 at your earliest convenience.</p>
<p>Eager people click here to download the distribution, others can read further:</p>
<p><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.3.4">http://www.apache.org/dyn/closer.cgi/wicket/1.3.4</a></p>
<p>We thank you for your patience and support.</p>
<p>
- The Wicket Team</p>
<h2>Apache Wicket</h2>
<p>Apache Wicket is a component oriented Java web application framework. With proper mark-up/logic separation, a POJO data model, and a refreshing lack of XML, Apache Wicket makes developing web-apps simple and enjoyable again. Swap the boilerplate, complex debugging and brittle code for powerful, reusable components written with plain Java and HTML.</p>
<p>You can find out more about Apache Wicket on our website:</p>
<p><a href="http://wicket.apache.org">http://wicket.apache.org</a></p>
<h2>This release</h2>
<p>This release is the fourth maintenance release for the Wicket 1.3 product. This release fixes several bugs and adds some minor improvements. You can find out about the changes at the bottom of this announcement.</p>
<h3>Migrating from 1.2</h3>
<p>If you are coming from Wicket 1.2, you really want to read our migration guide, found on the wiki:</p>
<p><a href="http://cwiki.apache.org/WICKET/migrate-13.html">http://cwiki.apache.org/WICKET/migrate-13.html</a></p>
<h3>Downloading the release</h3>
<p>You can download the release from the official Apache mirror system, and you can find it through the following link:</p>
<p><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.3.4/">http://www.apache.org/dyn/closer.cgi/wicket/1.3.4/</a></p>
<p>For the Maven and Ivy fans out there: update your pom's to the following, and everything will be downloaded automatically:</p>
<p>&lt;dependency&gt;<br />
   &lt;groupId&gt;org.apache.wicket&lt;/groupId&gt;<br />
   &lt;artifactId&gt;wicket&lt;/artifactId&gt;<br />
   &lt;version&gt;1.3.4&lt;/version&gt;<br />
&lt;/dependency&gt;</p>
<p>Substitute the artifact ID with the projects of your liking to get the other projects.</p>
<p>Please note that we don't prescribe a Logging implementation for SLF4J. You need to specify yourself which one you prefer. Read more about SLF4J here: <a href="http://slf4j.org">http://slf4j.org</a></p>
<h3>Validating the release</h3>
<p>The release has been signed by Martijn Dashorst, your release manager for today. The public key can be found in the KEYS file in the download area. Download the KEYS file only from the Apache website.</p>
<p><a href="http://www.apache.org/dist/wicket/1.3.4/KEYS">http://www.apache.org/dist/wicket/1.3.4/KEYS</a></p>
<p>Instructions on how to validate the release can be found here:</p>
<p><a href="http://www.apache.org/dev/release-signing.html#check-integrity">http://www.apache.org/dev/release-signing.html#check-integrity</a></p>
<h3>Reporting bugs</h3>
<p>In case you do encounter a bug, we would appreciate a report in our JIRA:</p>
<p><a href="http://issues.apache.org/jira/browse/WICKET">http://issues.apache.org/jira/browse/WICKET</a></p>
<h3>The distribution</h3>
<p>In the distribution you will find a README. The README contains instructions on how to build from source yourself. You also find a CHANEGELOG-1.3 which contains a list of all things that have been fixed, added and/or removed since Wicket 1.3.0.</p>
<h3>Release Notes - Wicket - Version 1.3.4</h3>
<h4>Bug</h4>
<ul>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-613'>WICKET-613</a>] -         Prototype scoped Spring beans</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1152'>WICKET-1152</a>] -         MetaDataRoleAuthorizationStrategy.unauthorize() doesn't work</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1292'>WICKET-1292</a>] -         WicketTester continueToOriginalDestination() uses application home page instead of original redictor</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1366'>WICKET-1366</a>] -         &quot;ava.lang.IllegalStateException: No Page found for component&quot; when collapsing nodes in a LinkTree</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1418'>WICKET-1418</a>] -         org.apache.wicket.MarkupContainer swallows AbortException</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1453'>WICKET-1453</a>] -         WicketServlet does not set content type on fallback()</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1473'>WICKET-1473</a>] -         BaseWicketTester.isComponentOnAjaxResponse() test is too strong</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1476'>WICKET-1476</a>] -         Referencing Page may cause StackOverflowError</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1499'>WICKET-1499</a>] -         AjaxEditableMultiLineLabel + race condition / </li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1501'>WICKET-1501</a>] -         MarkupCache.putIntoCache doesn't behave correctly!!</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1504'>WICKET-1504</a>] -         AutoCompleteTextField - javascript error &quot;type mismatch&quot; in line 227 in IE</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1507'>WICKET-1507</a>] -         MarkupCache style/variation/locale support broken</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1510'>WICKET-1510</a>] -         FormDispatcherRequest creates invalid parameter map</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1521'>WICKET-1521</a>] -         ClassCastException in MixedUrlCodingStrategy</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1527'>WICKET-1527</a>] -         WicketTester can not deal with null values in page parameters</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1536'>WICKET-1536</a>] -         Enclosure permanently hides direct children after it has been itself hidden once</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1537'>WICKET-1537</a>] -         SelectOption generates non xhtml compliant markup</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1541'>WICKET-1541</a>] -         PopupSettings' windowName fixes for IE</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1544'>WICKET-1544</a>] -         Update Javadoc for AbstractValidator</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1547'>WICKET-1547</a>] -         Add getterfor IPageable to PagingNavigation</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1548'>WICKET-1548</a>] -         PagingNavigator calls factory methods from constructor</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1549'>WICKET-1549</a>] -         Memory leak with PropertyResolver (in running test suites)</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1551'>WICKET-1551</a>] -         javascript status variable hides the window.status variable because it is not declared as a far in wicket-ajax.js</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1556'>WICKET-1556</a>] -         Non-existant package resources lazily added to pool</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1558'>WICKET-1558</a>] -         WicketTester.startPage(page) throws &quot;No requestCycle is currently set&quot;</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1560'>WICKET-1560</a>] -         MarkupFragmentFinder fails on transparent resolvers within Repeaters</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1569'>WICKET-1569</a>] -         AjaxButton break form data when IRequestSettings.#getResponseRequestEncoding is not UTF-8.</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1570'>WICKET-1570</a>] -         We should mark session dirty when at least one page is touched</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1575'>WICKET-1575</a>] -         AjaxEventBehavior does not check for component.isEnableAllowed before adding the ajax event to the tag</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1598'>WICKET-1598</a>] -         Typos in JavaDoc of IMarkupResourceStreamProvider.java</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1607'>WICKET-1607</a>] -         addDomReadyEvent unreliable for Safari</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1626'>WICKET-1626</a>] -         Typo in src/main/java/org/apache/wicket/protocol/http/WebApplication.java</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1632'>WICKET-1632</a>] -         IE bug causes wicket problems when id auto generation is active</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1635'>WICKET-1635</a>] -         Stripping javascript comments and whitespace breaks application when using prototype library</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1645'>WICKET-1645</a>] -         Syntactic errors in the manifest OSGi headers</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1646'>WICKET-1646</a>] -         AjaxFormComponentUpdatingBehavior not working correctly when using IE 7</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1649'>WICKET-1649</a>] -         Manifests use incorrect Dynamic-ImportPackage header</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1658'>WICKET-1658</a>] -         WicketTester#clickLink doesn't update lastRenderedPage</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1659'>WICKET-1659</a>] -         Prolem with 'mouseactive' in wicket-autocomplete.js when AutoCompleteBehaviour is added (twice) during Ajax roundtrip</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1667'>WICKET-1667</a>] -         Memory leak in Localizer</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1669'>WICKET-1669</a>] -         TimeFrame.equals(Object)  does not work as expected</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1670'>WICKET-1670</a>] -         Time.valueOf() does not clear miliseconds</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1682'>WICKET-1682</a>] -         HtmlHandler can't handle tags not requiring closed tags if the tag names are uppercase</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1697'>WICKET-1697</a>] -         Bad caching in &lt;wicket:message&gt; tag for the same key in same markup structure</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1701'>WICKET-1701</a>] -         org.apache.wicket.markup.html.CompressedPackageResource$CompressingResourceStream.cache needs to avoid being serialized</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1704'>WICKET-1704</a>] -         ResourceStreamRequestTarget.configure set wrong ContentLength for non-ascii characters</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1705'>WICKET-1705</a>] -         GuiceComponentInjector mishandles static fields</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1706'>WICKET-1706</a>] -         org.apache.wicket.util.lang.Objects.convertValue returns null if it cannot convert the value</li>
</ul>
<h4>Improvement</h4>
<ul>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1492'>WICKET-1492</a>] -         Allow form to specify prefix for formcomponent names</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1524'>WICKET-1524</a>] -         Disable javadoc plugin in regular build to make it faster</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1590'>WICKET-1590</a>] -         AjaxEditableChoiceLabel ignores ChoiceRenderer in newLabel(...)</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1592'>WICKET-1592</a>] -         html.form.Form object should have method to obtain all FormValidator objects associated with</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1595'>WICKET-1595</a>] -         AutoCompleteTextField: Scrolling down the Choice Menu Only When the Bottom of the Menu Is Reached</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1608'>WICKET-1608</a>] -         make AutoCompleteBehavior's configuration more flexible</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1618'>WICKET-1618</a>] -         Localizer API should be enhanced so that the cache implementation can be overwritten</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1668'>WICKET-1668</a>] -         Application_es.properties (added translations)</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1708'>WICKET-1708</a>] -         Allow the module init parameter to contain multiple class names</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1709'>WICKET-1709</a>] -         Allow configuration of the guice Stage for GuiceWebApplicationFactory</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1711'>WICKET-1711</a>] -         Improve Locale fallback in BundleStringResourceLoader</li>
</ul>
<h4>New Feature</h4>
<ul>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1322'>WICKET-1322</a>] -         NormalUrlCodingStrategy: It does not append / to the end of the url before the parameters</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1428'>WICKET-1428</a>] -         AutoLinkResolver and Parent-Relative (../) Links</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1609'>WICKET-1609</a>] -         add RedirectToExternalException</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1641'>WICKET-1641</a>] -         provide OSGi metadata</li>
</ul>
<h4>Wish</h4>
<ul>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-1562'>WICKET-1562</a>] -         Autocomplete should display the selection list even if the input field is empty</li>
</ul>
