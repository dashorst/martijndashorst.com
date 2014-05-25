---
layout: post
status: publish
published: true
title: Apache Wicket 1.3.1 is released!
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 344
wordpress_url: http://martijndashorst.com/blog/2008/02/06/apache-wicket-131-is-released/
date: '2008-02-06 00:00:32 +0100'
date_gmt: '2008-02-05 23:00:32 +0100'
categories:
- wicket
tags:
- wicket
- release
comments: []
---
<p>The Apache Wicket team is proud to announce the availability of the first maintenance release: Apache Wicket 1.3.1. A lot of bugs have been squashed and several improvements implemented. The most notable improvement is the addition of out-of-the-box, transparent clustering support (WICKET-1272).</p>
<p>Eager people click here to download the distribution, others can read further:</p>
<p><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.3.1">http://www.apache.org/dyn/closer.cgi/wicket/1.3.1</a></p>
<p>We thank you for your patience and support.</p>
<p>The Wicket Team</p>
<h3>Apache Wicket</h3>
<p>Apache Wicket is a component oriented Java web application framework. With proper mark-up/logic separation, a <span class="caps">POJO</span> data model, and a refreshing lack of <span class="caps">XML</span>, Apache Wicket makes developing web-apps simple and enjoyable again. Swap the boilerplate, complex debugging and brittle code for powerful, reusable components written with plain Java and <span class="caps">HTML</span>.</p>
<p>You can find out more about Apache Wicket on our website:</p>
<p><a href="http://wicket.apache.org">http://wicket.apache.org</a></p>
<h3>This release</h3>
<p>This release is the first maintenance release for the Wicket 1.3 product. Development for a new version of Wicket will commence soon. This release fixes several bugs and adds some minor improvements. You can find out about the changes at the bottom of this announcement.</p>
<h3>Migrating from 1.2</h3>
<p>If you are coming from Wicket 1.2, you really want to read our migration guide, found on the wiki:</p>
<p><a href="http://cwiki.apache.org/WICKET/migrate-13.html">http://cwiki.apache.org/WICKET/migrate-13.html</a></p>
<h3>Downloading the release</h3>
<p>You can download the release from the official Apache mirror system, and you can find it through the following link:</p>
<p><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.3.1/">http://www.apache.org/dyn/closer.cgi/wicket/1.3.1/</a></p>
<p>For the Maven and Ivy fans out there: update your pom?s to the following, and everything will be downloaded automatically:</p>
<pre><code>&lt;dependency&gt;
    &lt;groupId&gt;org.apache.wicket&lt;/groupId&gt;
    &lt;artifactId&gt;wicket&lt;/artifactId&gt;
    &lt;version&gt;1.3.1&lt;/version&gt;
&lt;/dependency&gt;
</code></pre>
<p>Substitute the artifact ID with the projects of your liking to get the other projects.</p>
<p>Please note that we don?t prescribe a Logging implementation for <span class="caps">SLF4J</span>. You need to specify yourself which one you prefer. Read more about <span class="caps">SLF4J</span> here: <a href="http://slf4j.org">http://slf4j.org</a></p>
<h3>Validating the release</h3>
<p>The release has been signed by Frank Bille, your release manager for today. The public key can be found in the <span class="caps">KEYS</span> file in the download area. Download the <span class="caps">KEYS</span> file only from the Apache website.</p>
<p><a href="http://www.apache.org/dist/wicket/1.3.1/KEYS">http://www.apache.org/dist/wicket/1.3.1/KEYS</a></p>
<p>Instructions on how to validate the release can be found here:</p>
<p><a href="http://www.apache.org/dev/release-signing.html#check-integrity">http://www.apache.org/dev/release-signing.html#check-integrity</a></p>
<h3>Reporting bugs</h3>
<p>In case you do encounter a bug, we would appreciate a report in our <span class="caps">JIRA</span>:</p>
<p><a href="http://issues.apache.org/jira/browse/WICKET">http://issues.apache.org/jira/browse/WICKET</a></p>
<h3>The distribution</h3>
<p>In the distribution you will find a <span class="caps">README</span>. The <span class="caps">README</span> contains instructions on how to build from source yourself and a list of all things that have been fixed, added and/or removed since Wicket 1.3.0.</p>
<h3>Release Notes ? Wicket ? Version 1.3.1</h3>
<h4>Bug</h4>
<ul>
<li><a href="https://issues.apache.org/jira/browse/WICKET-812"><span class="caps">WICKET</span>-812</a> ? Submit button, multipart content and UploadProgressBar</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-989"><span class="caps">WICKET</span>-989</a> ? DatePicker: NaN if numerical input cannot be parsed</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1184"><span class="caps">WICKET</span>-1184</a> ? PageSavingThread keeps running after undeploy</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1194"><span class="caps">WICKET</span>-1194</a> ? UploadProgressBar incompatible with submit buttons onSubmit method (in FireFox at least)</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1243"><span class="caps">WICKET</span>-1243</a> ? the DatePicker show the same week title in china.</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1249"><span class="caps">WICKET</span>-1249</a> ? modal.js conflicts with mootools and possibly other javascript frameworks. + patch fix</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1254"><span class="caps">WICKET</span>-1254</a> ? Binding to a BigDecimal don?t honor browser locale</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1257"><span class="caps">WICKET</span>-1257</a> ? iframe get request done 2x after ajax change in IE</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1258"><span class="caps">WICKET</span>-1258</a> ? AjaxFormChoiceComponentUpdatingBehavior assumes Radio/Choice items are a direct child of the group in the client-side <span class="caps">DOM</span></li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1260"><span class="caps">WICKET</span>-1260</a> ? CheckBox.setRequired() is not picked up in 1.3-final</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1262"><span class="caps">WICKET</span>-1262</a> ? Page#readResolve is not called</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1263"><span class="caps">WICKET</span>-1263</a> ? Using nested wicket:enclosure throws exception</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1264"><span class="caps">WICKET</span>-1264</a> ? assertComponentOnAjaxResponse does not work with WicketTester.clickLink</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1270"><span class="caps">WICKET</span>-1270</a> ? <span class="caps">NPE</span> in ListMultipleChoice.updateModel()</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1271"><span class="caps">WICKET</span>-1271</a> ? Script in RenderHead method of AjaxFormChoiceComponentUpdatingBehavior needs fixing</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1274"><span class="caps">WICKET</span>-1274</a> ? Only properties from first panel-implementation loaded when using different implementations of an abstract panel on the same page</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1275"><span class="caps">WICKET</span>-1275</a> ? <span class="caps">FLAG</span>_HAS_BEEN_RENDERED is set when rendering invisible components</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1277"><span class="caps">WICKET</span>-1277</a> ? When no component is focused on AjaxRequestTarget, wicket tries to focus element with id ?null?</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1282"><span class="caps">WICKET</span>-1282</a> ? AjaxFormSubmitBehavior doesn?t work well with nested forms</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1290"><span class="caps">WICKET</span>-1290</a> ? PrependingStringBuffer.equals(Object obj) is not reflexive</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1304"><span class="caps">WICKET</span>-1304</a> ? Form processing workflow is broken for FormComponentPanels</li>
</ul>
<h4>Improvement</h4>
<ul>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1020"><span class="caps">WICKET</span>-1020</a> ? expose configuration of CompoundValidator, NumberValidator</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1193"><span class="caps">WICKET</span>-1193</a> ? i18n: Translation of resource files in Korean</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1252"><span class="caps">WICKET</span>-1252</a> ? Default start week day based on locale</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1272"><span class="caps">WICKET</span>-1272</a> ? Better clustering support for DiskPageStore</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1283"><span class="caps">WICKET</span>-1283</a> ? Allow to query component markup id without creating one</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1284"><span class="caps">WICKET</span>-1284</a> ? Report last focused element id on ajax request</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1293"><span class="caps">WICKET</span>-1293</a> ? Improve SelectOptions: allow customization of created SelectOption objects</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1299"><span class="caps">WICKET</span>-1299</a> ? HybridUrlCodingStrategy should throw a PageExpiredException if a RequestListenerInterface is targeted on a non-existent page-id/version</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1309"><span class="caps">WICKET</span>-1309</a> ? Properties files translation (_es)</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1313"><span class="caps">WICKET</span>-1313</a> ? Created Norwegian translation of Application.properties</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1318"><span class="caps">WICKET</span>-1318</a> ? NavigatorLabel should be localizable</li>
</ul>
