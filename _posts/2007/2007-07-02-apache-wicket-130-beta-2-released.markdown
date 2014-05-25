---
layout: post
status: publish
published: true
title: Apache Wicket 1.3.0 Beta 2 released
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
excerpt: |+
  <p>
  This is the second beta for <a href="http://incubator.apache.org/wicket/">Apache Wicket</a> we have prepared for your and our
  pleasure. It also marks the first release since we have been graduated to a
  top level project of the <a href="http://www.apache.org/">Apache Software Foundation</a>.
  </p>


wordpress_id: 277
wordpress_url: http://martijndashorst.com/blog/2007/07/02/apache-wicket-130-beta-2-released/
date: '2007-07-02 11:08:50 +0200'
date_gmt: '2007-07-02 10:08:50 +0200'
categories:
- wicket
tags: []
comments:
- id: 5175
  author: University Update - Yahoo - Apache Wicket 1.3.0 Beta 2 released
  author_email: ''
  author_url: http://www.universityupdate.com/Technology/Yahoo/3550145.aspx
  date: '2007-07-02 12:00:31 +0200'
  date_gmt: '2007-07-02 11:00:31 +0200'
  content: "[...] YouTube                       Link to Article                yahoo
    Apache Wicket 1.3.0 Beta 2 released &#187;  Posted at A Wicket Diary on Monday,
    July 02, 2007   This is the second beta for Apache Wicket we have prepared for
    your and our pleasure. It also marks the first release since we have been graduated
    to a top level project of the Apache Software Foundation. In this announcement:
    Apache Wicket This release Migrating from 1  View Entire Article &#187; [...]"
- id: 14420
  author: Richard Livingstone
  author_email: wicket@bananasoft.net
  author_url: ''
  date: '2007-10-11 18:22:42 +0200'
  date_gmt: '2007-10-11 17:22:42 +0200'
  content: Is it possible to get hold of the sources for this 1.3 beta ? They aren't
    in the zip distro
- id: 14422
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-10-11 18:27:30 +0200'
  date_gmt: '2007-10-11 17:27:30 +0200'
  content: Yes they are. Did you bother to look in the src folder?
- id: 56962
  author: freelancer
  author_email: gyrus@ukr.net
  author_url: http://www.haveahobby.com
  date: '2008-06-13 18:39:39 +0200'
  date_gmt: '2008-06-13 17:39:39 +0200'
  content: Wicket would not contribute from  section if the panel is invisible. Is
    this a bug?  What is the purpose of contributing from  at the point when i make
    the panel visible, after DomReady fired? I would just place code from  to the
    beginning of the panel markup if i wanted such behavior.
---
<p>
This is the second beta for <a href="http://incubator.apache.org/wicket/">Apache Wicket</a> we have prepared for your and our<br />
pleasure. It also marks the first release since we have been graduated to a<br />
top level project of the <a href="http://www.apache.org/">Apache Software Foundation</a>.</p>
<p><a id="more"></a><a id="more-277"></a></p>
<p>
In this announcement:</p>
<ul>
<li>Apache Wicket</li>
<li>This release</li>
<li>Migrating from 1.2</li>
<li>Downloading the release</li>
<li>Validating the release</li>
<li>Reporting bugs</li>
</ul>
<p>Eager people click here to download the distribution, others can read further:</p>
<ul>
<li><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-beta2/">http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-beta2/</a></li>
</ul>
<p>We thank you for your patience and support. Next stop: 1.3 final!</p>
<p>- <i>The Wicket Team</i></p>
<h3>Apache Wicket</h3>
<p>
Apache Wicket is a component oriented Java web application framework that is<br />
recently established as a top level project at the Apache Software foundation.<br />
With proper mark-up/logic separation, a POJO data model, and a refreshing lack<br />
of XML, Apache Wicket makes developing web-apps simple and enjoyable again.<br />
Swap the boilerplate, complex debugging and brittle code for powerful,<br />
reusable components written with plain Java and HTML.</p>
<h3>This release</h3>
<p>
This release is the second in a series of beta releases until we feel<br />
confident to finalize Wicket 1.3. This is called a beta because we don't have<br />
fixed all bugs, and probably haven't found them all either (can you ever be<br />
sure?). However, we are confident that most major API changes are in and<br />
therefore want to give you access to a more stable platform than depending on<br />
trunk.</p>
<p>
The most notable change (apart from then numerous bug fixes) is the new Guice<br />
integration: Wicket now ships with integration for Google's Guice. To make<br />
that happen, some shared functionality has been extracted from Wicket Spring<br />
and put into a new module: Wicket IoC.</p>
<h3>Migrating from 1.2</h3>
<p>
If you are coming from Wicket 1.2, you really want to read our migration<br />
guide, found on the wiki:</p>
<ul>
<li><a href="http://cwiki.apache.org/WICKET/migrate-13.html">http://cwiki.apache.org/WICKET/migrate-13.html</a></li>
</ul>
<h3>Downloading the release</h3>
<p>
You can download the release from the official Apache mirror system, and you<br />
can find it through the following link:</p>
<ul>
<li><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-beta2/">http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-beta2/</a></li>
</ul>
<p>
For the Maven and Ivy fans out there: update your pom's to the following, and<br />
everything will be downloaded automatically:</p>
<pre>
&lt;dependency&gt;
    &lt;groupId&gt;org.apache.wicket&lt;/groupId&gt;
    &lt;artifactId&gt;wicket&lt;/artifactId&gt;
    &lt;version&gt;1.3.0-beta2&lt;/version&gt;
&lt;/dependency&gt;
</pre>
<p>Substitute the artifact ID with the projects of your liking to get the other<br />
projects.</p>
<h3>Validating the release</h3>
<p>
The release has been signed by Martijn Dashorst, your release manager for<br />
today. The public key can be found in the KEYS file in the download area.<br />
Download the KEYS file only from the Apache website.</p>
<ul>
<li><a href="http://www.apache.org/dist/wicket/1.3.0-beta2/KEYS">http://www.apache.org/dist/wicket/1.3.0-beta2/KEYS</a></li>
</ul>
<p>Instructions on how to validate the release can be found here:</p>
<ul>
<li><a href="http://www.apache.org/dev/release-signing.html#check-integrity">http://www.apache.org/dev/release-signing.html#check-integrity</a></li>
</ul>
<h3>Reporting bugs</h3>
<p>
In case you do encounter a bug, we would appreciate a report in our JIRA:</p>
<ul>
<li><a href="http://issues.apache.org/jira/browse/WICKET">http://issues.apache.org/jira/browse/WICKET</a></li>
</ul>
<h3>The distribution</h3></p>
<p>
In the distribution you will find a README and a RELEASENOTES. The README<br />
contains instructions on how to build from source yourself, the RELEASENOTES<br />
contains a list of all things that have been fixed, added and/or removed since<br />
the first beta release.</p>
<h3>Release Notes - Wicket - Version 1.3.0-beta2</h3>
<p>        Release Notes - Wicket - Version 1.3.0-beta2</p>
<h2>        Bug<br />
</h2>
<ul>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-4'>WICKET-4</a>] -         Page.onBeginRequest() [and consequently .onAttach()] not called when form on page is submitted.
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-40'>WICKET-40</a>] -         Parameters of nice URL's pages with 'sensitive' characters
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-65'>WICKET-65</a>] -         Handle String array in PageParameters
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-139'>WICKET-139</a>] -         DefaultTreeState allowSelectMultiple == false not evaluated when selecting node already selected
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-175'>WICKET-175</a>] -         Page.onDetach is called by each ComponentResourceRequestTarget
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-254'>WICKET-254</a>] -         Allow to set field values before submitting a form with Ajax in WicketTester
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-293'>WICKET-293</a>] -         PackageRequestTargetUrlCodingStrategy should interrupts the cycle and sends a 404 when a page/class cannot be found.
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-319'>WICKET-319</a>] -         No java source code in examples
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-323'>WICKET-323</a>] -         AjaxEditableLabel on setModel does not update the labels model only the editors
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-341'>WICKET-341</a>] -         [Patch] AjaxServerAndClientTimeFilter either throws an exception or displays a wrong text
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-370'>WICKET-370</a>] -         wicket.jmx.Application.getHomePageClass() returns Application's class name
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-373'>WICKET-373</a>] -         Some components miss localization (NavigatorLabel, Palette)
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-377'>WICKET-377</a>] -         Editing an AjaxEditableLabel, going to a new page, clicking the back button and editing the label again makes the page expire.
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-405'>WICKET-405</a>] -         StatelessForm and setRedirect(true) in the onSubmit method
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-409'>WICKET-409</a>] -         Page constructed twice when a BookmarkableLink has PopupSettings
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-444'>WICKET-444</a>] -         src attribute path not processed by wicket for INPUT type=image and any IMG with wicket:message in it
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-455'>WICKET-455</a>] -         mvn jetty:run; maven-jetty-plugin not configured
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-464'>WICKET-464</a>] -         Add global override to disable gzip compression (SAP double-compresses).
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-478'>WICKET-478</a>] -         WicketTester.clickLink() does not recognize SubmitLink.
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-501'>WICKET-501</a>] -         JavaScript comment stripping doesn't handle regexps
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-504'>WICKET-504</a>] -         Allow to use &lt;button&gt; in AjaxSubmitLink
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-513'>WICKET-513</a>] -         Example &quot;pub&quot; doesn't work any more. The images are no longer localized
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-514'>WICKET-514</a>] -         authorization and authentication examples throw exceptions
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-526'>WICKET-526</a>] -         URL mounting doesn't work well together with stateless pages
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-557'>WICKET-557</a>] -         RedirectPage inside ListView causes page expiration issues
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-558'>WICKET-558</a>] -         New attach-&gt;beforeRender refactor breaks ajax updating of list views
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-565'>WICKET-565</a>] -         parent poms missing in 1.3.0-beta1
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-566'>WICKET-566</a>] -         &lt;scope&gt;tests&lt;/scope&gt; should be &lt;scope&gt;test&lt;/scope&gt;
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-567'>WICKET-567</a>] -         relative paths generated incorrectly for HeaderContributor for mounted page
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-568'>WICKET-568</a>] -         Form url handled wrong when using QueryStringUrlCodingStrategy
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-576'>WICKET-576</a>] -         PopupSettings with no window name set generates invalid xhtml on Link
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-578'>WICKET-578</a>] -         AbstractTextComponent is using onAttach when it should be onBeforeRender
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-583'>WICKET-583</a>] -         Header Contribution in ModalWindow doesn't work properly
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-586'>WICKET-586</a>] -         Quickstart web.xml
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-589'>WICKET-589</a>] -         problem with Ajax and rendering
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-590'>WICKET-590</a>] -         RelativePathPrefixHandler and WicketMessageTagHandler conflict
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-591'>WICKET-591</a>] -         SignInPanel is not returning raw input
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-593'>WICKET-593</a>] -         equals() in ResourceStreamRequestTarget compares the wrong filename
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-595'>WICKET-595</a>] -         TimeOfDay.next(Calendar) can return time on same day rather than next day
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-600'>WICKET-600</a>] -         getClientInfo throws ClassCastException when Javascript is Disabled
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-603'>WICKET-603</a>] -         Injecting a reference to a bean which is of a final class fails
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-606'>WICKET-606</a>] -         AbstractTextComponent#setConvertEmptyInputStringToNull(true) does not work with IObjectClassAwareModels (affects TextField, etc.)
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-610'>WICKET-610</a>] -         header contributions fail on &lt;error-pages&gt;
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-612'>WICKET-612</a>] -         HeaderContributor forces relative URL
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-613'>WICKET-613</a>] -         Prototype scoped Spring beans
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-615'>WICKET-615</a>] -         BookmarkablePageRequestTarget respond method
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-621'>WICKET-621</a>] -         detach() is not called when nested object is IDetachable but not IModel in CompoundPropertyModel
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-624'>WICKET-624</a>] -         AbstractSingleChoice: components can't have specific null or nullValid messages
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-628'>WICKET-628</a>] -         WicketFilter tries to call setClassLoader() even if it's not changing the default - doesn't work on strict SecurityManagers.
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-629'>WICKET-629</a>] -         NPE when using DatePicker with DateTextField
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-644'>WICKET-644</a>] -         SpringWebApplicationFactory references wrong package in javadoc.
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-659'>WICKET-659</a>] -         Null form fields are converted to empty strings
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-667'>WICKET-667</a>] -         [PATCH] remove XX in firefox and palette
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-673'>WICKET-673</a>] -         synchronize AbstractBehavior#isEnabled(Component component) with Component#isEnabled
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-684'>WICKET-684</a>] -         JavaScript complains if an AjaxButton has the name &quot;submit&quot;
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-687'>WICKET-687</a>] -         DatePicker refers to gif files on Yahoo
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-688'>WICKET-688</a>] -         DatePicker doesn't work with TextField
</li>
</ul>
<h2>        Improvement<br />
</h2>
<ul>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-6'>WICKET-6</a>] -         Configuration of app mode isn't customisable
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-49'>WICKET-49</a>] -         Upgrade all war-type projects (examples, quickstart) to use jetty 6 and jetty-maven-plugin
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-301'>WICKET-301</a>] -         Translation for Czech language
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-344'>WICKET-344</a>] -         clock component doesn't display seconds in some Locales
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-348'>WICKET-348</a>] -         Propose removing 'final' modifier to AbstractSingleSelectChoice.convertValue()
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-362'>WICKET-362</a>] -         Add ability to manage disabled items from subclasses of AbstractChoice
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-388'>WICKET-388</a>] -         Change log statement in Objects#setObjectStreamFactory()
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-394'>WICKET-394</a>] -         [Patch] do not serialize choices and select in palette.
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-416'>WICKET-416</a>] -         Handle / servlet mapping or fail consistenly
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-481'>WICKET-481</a>] -         Take into account the button and input tags in AbstractLink#disableLink()
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-531'>WICKET-531</a>] -         FormComponentLabel and Radio
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-549'>WICKET-549</a>] -         HeaderContributions are missing if &lt;html&gt; is a Component.
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-556'>WICKET-556</a>] -         Prevent setTimeout for AjaxSelfUpdatingTimerBehavior from firing after its contributing component has been replaced
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-561'>WICKET-561</a>] -         TextField should determine the object type from the model if the model supports it
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-577'>WICKET-577</a>] -         Improve TabbedPanel component - add ability to change tab-row container
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-582'>WICKET-582</a>] -         Enhancement of exception message in WebExternalResourceStream
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-587'>WICKET-587</a>] -         Entity references in DTD are missing the path to w3.com
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-614'>WICKET-614</a>] -         Markup ids from markup should be honored for CSS reasons, even with outputMarkupId == true
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-616'>WICKET-616</a>] -         Provide default CSS for UploadProgressBar
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-619'>WICKET-619</a>] -         Models that can should be able to provide information about field/getter/setter
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-633'>WICKET-633</a>] -         Tree components cleanup
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-636'>WICKET-636</a>] -         Get the ability to add some properties to the html &quot;&lt;option&gt;&quot; tag for the palette component
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-637'>WICKET-637</a>] -         wicket-examples grey-on-white colour scheme is very hard to read
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-638'>WICKET-638</a>] -         wicket-examples source code view is not resizable
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-664'>WICKET-664</a>] -         Allow users to hook into onbeforeunload event so they can tell when a page is closed in the browser
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-671'>WICKET-671</a>] -         InlineFrame page constructor doesn't behave as expected
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-672'>WICKET-672</a>] -         DateTextField is too session-heavy
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-674'>WICKET-674</a>] -         when setting stripJavascriptCommentsAndWhitespace is true, also strip comments and whitespace of PackagedTextTemplates
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-689'>WICKET-689</a>] -         Please make it easier to use a custom RequestCycle
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-692'>WICKET-692</a>] -         upgrade YUI dependencies to version 2.2.2 for wicket-datetime
</li>
</ul>
<h2>        New Feature<br />
</h2>
<ul>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-580'>WICKET-580</a>] -         add EmptyPanel class
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-608'>WICKET-608</a>] -         Add possibility to output markup class as html comment
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-630'>WICKET-630</a>] -         It should be possible to specify different CSS class names for certain columns in DataTable
</li>
</ul>
<h2>        Task<br />
</h2>
<ul>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-264'>WICKET-264</a>] -         stockquote app
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-508'>WICKET-508</a>] -         Move TextTemplate to core
</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-562'>WICKET-562</a>] -         include SLF4J jar in the Wicket 1.3 zip distribution
</li>
</ul>
<h2>        Wish<br />
</h2>
<ul>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-383'>WICKET-383</a>] -         Wicket-Examples war file needs slf4j
</li>
</ul>
