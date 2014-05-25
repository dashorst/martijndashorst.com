---
layout: post
status: publish
published: true
title: Apache Wicket 1.3.0-rc1 released!
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 322
wordpress_url: http://martijndashorst.com/blog/2007/11/11/apache-wicket-130-rc1-released/
date: '2007-11-11 13:08:48 +0100'
date_gmt: '2007-11-11 12:08:48 +0100'
categories:
- wicket
tags: []
comments:
- id: 18718
  author: Gerolf Seitz
  author_email: gerolf.seitz@gmail.com
  author_url: http://wicket.apache.org
  date: '2007-11-11 19:58:39 +0100'
  date_gmt: '2007-11-11 18:58:39 +0100'
  content: dzoned -&gt; http://www.dzone.com/links/apache_wicket_130rc1_released.html
- id: 18770
  author: James Law
  author_email: jlaw@umich.edu
  author_url: ''
  date: '2007-11-12 00:40:41 +0100'
  date_gmt: '2007-11-11 23:40:41 +0100'
  content: "Hi, Can you indicate which maven repository? I don't see wicket 1.3 on
    mvn repository.com\r\n\r\nIs it in a \"public\" repository? If not, what repo
    should I add?\r\n\r\nThanks!\r\nJames"
- id: 18837
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-11-12 08:13:13 +0100'
  date_gmt: '2007-11-12 07:13:13 +0100'
  content: "Central repo: http://repo1.maven.org/maven2\r\n\r\n(http://repo1.maven.org/maven2/org/apache/wicket/)\r\n\r\nProbably
    repository.com needs to sync (it isn't the main repository AFAIK)"
- id: 18899
  author: James Law
  author_email: jlaw@umich.edu
  author_url: ''
  date: '2007-11-12 13:53:18 +0100'
  date_gmt: '2007-11-12 12:53:18 +0100'
  content: thanks Martijn !
---
<p>This is the first release candidate for Apache Wicket we have prepared for your pleasure. It contains over 80 fixes to issues with previous releases and todo items we have cleared.</p>
<p>In this announcement:</p>
<ul>
<li>Apache Wicket</li>
<li>This release</li>
<li>Migrating from 1.2</li>
<li>Downloading the release</li>
<li>Validating the release</li>
<li>Reporting bugs</li>
<li>The distribution</li>
<li>Release Notes &#8211; Wicket &#8211; Version 1.3.0-rc1</li>
</ul>
<p>Eager people click here to download the distribution, others can read further:</p>
<p><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-rc1">http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-rc1</a></p>
<p>We thank you for your patience and support.</p>
<p>The Wicket Team</p>
<h3>Apache Wicket</h3>
<p>Apache Wicket is a component oriented Java web application framework. With proper mark-up/logic separation, a <span class="caps">POJO</span> data model, and a refreshing lack of <span class="caps">XML</span>, Apache Wicket makes developing web-apps simple and enjoyable again. Swap the boilerplate, complex debugging and brittle code for powerful, reusable components written with plain Java and <span class="caps">HTML</span>.</p>
<p>Our migration to a top level project is now completed and you can find our website and documentation here:</p>
<p><a href="http://wicket.apache.org">http://wicket.apache.org</a></p>
<h3>This release</h3>
<p>This release is the first in a series of release candidates releases until we feel confident to finalize Wicket 1.3. This is called a release candidate because we strive for <span class="caps">API</span> freeze. This means only bug fixes will be done on the 1.3 release from now on.</p>
<h3>Migrating from 1.2</h3>
<p>If you are coming from Wicket 1.2, you really want to read our migration guide, found on the wiki:</p>
<p><a href="http://cwiki.apache.org/WICKET/migrate-13.html">http://cwiki.apache.org/WICKET/migrate-13.html</a></p>
<h3>Downloading the release</h3>
<p>You can download the release from the official Apache mirror system, and you can find it through the following link:</p>
<p><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-rc1/">http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-rc1/</a></p>
<p>For the Maven and Ivy fans out there: update your pom&#8217;s to the following, and everything will be downloaded automatically:</p>
<pre>
&lt;dependency&gt;  
    &lt;groupId&gt;org.apache.wicket&lt;/groupId&gt; 
    &lt;artifactId&gt;wicket&lt;/artifactId&gt; 
    &lt;version&gt;1.3.0-rc1&lt;/version&gt; 
&lt;/dependency&gt;
</pre>
<p>Substitute the artifact ID with the projects of your liking to get the other projects.</p>
<p>Please note that we don&#8217;t prescribe a Logging implementation for <span class="caps">SLF4J</span>. You need to specify yourself which one you prefer. Read more about <span class="caps">SLF4J</span> here: <a href="http://slf4j.org">http://slf4j.org</a></p>
<h3>Validating the release</h3>
<p>The release has been signed by Frank Bille, your release manager for today. The public key can be found in the <span class="caps">KEYS</span> file in the download area. Download the <span class="caps">KEYS</span> file only from the Apache website.</p>
<p><a href="http://www.apache.org/dist/wicket/1.3.0-rc1/KEYS">http://www.apache.org/dist/wicket/1.3.0-rc1/KEYS</a></p>
<p>Instructions on how to validate the release can be found here:</p>
<p><a href="http://www.apache.org/dev/release-signing.html#check-integrity">http://www.apache.org/dev/release-signing.html#check-integrity</a></p>
<h3>Reporting bugs</h3>
<p>In case you do encounter a bug, we would appreciate a report in our <span class="caps">JIRA</span>:</p>
<p><a href="http://issues.apache.org/jira/browse/WICKET">http://issues.apache.org/jira/browse/WICKET</a></p>
<h3>The distribution</h3>
<p>In the distribution you will find a <span class="caps">README</span>. The <span class="caps">README</span> contains instructions on how to build from source yourself and a list of all things that have been fixed, added and/or removed since the first beta release.</p>
<h3>Release Notes &#8211; Wicket &#8211; Version 1.3.0-rc1</h3>
<h4>Sub-task</h4>
<ul>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1022"><span class="caps">WICKET</span>-1022</a> &#8211; Created new bug &#8211; ValueMap set to null</li>
</ul>
<h4>Bug</h4>
<ul>
<li><a href="https://issues.apache.org/jira/browse/WICKET-330"><span class="caps">WICKET</span>-330</a> &#8211; CheckBox incorrectly converts its model value when a custom Boolean converter is installed</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-336"><span class="caps">WICKET</span>-336</a> &#8211; Inheritable model cannot be a wrap model</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-382"><span class="caps">WICKET</span>-382</a> &#8211; Converter misusage/mangling in RadioChoice</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-487"><span class="caps">WICKET</span>-487</a> &#8211; Buggy behaviour in PageMap.access(IPageMapEntry,int). Wicket1.2.4</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-588"><span class="caps">WICKET</span>-588</a> &#8211; continueToOriginalDestination / RestartResponseAtInterceptPageException with page parameters broken</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-605"><span class="caps">WICKET</span>-605</a> &#8211; Stateless form skips page parameters</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-607"><span class="caps">WICKET</span>-607</a> &#8211; Stateless forms don&#8217;t work with QueryStringUrlCodingStrategy</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-642"><span class="caps">WICKET</span>-642</a> &#8211; Need to escape select html option value</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-645"><span class="caps">WICKET</span>-645</a> &#8211; Form with ajaxsubmitbutton won&#8217;t submit after error</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-702"><span class="caps">WICKET</span>-702</a> &#8211; MockWebApplication doesn&#8217;t redirect  properly to mounted pages under RestartResponseAtInterceptPageException</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-734"><span class="caps">WICKET</span>-734</a> &#8211; Custom ILinkListener component causes error in cell on mounted page</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-746"><span class="caps">WICKET</span>-746</a> &#8211; Thread synchronization problems in FilePageStore</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-855"><span class="caps">WICKET</span>-855</a> &#8211; ModalWindow makes Internet Explorer 6 show an security warning dialog</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-901"><span class="caps">WICKET</span>-901</a> &#8211; DatePicker#getConfigureYUIBasePath() is useless or never called</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-916"><span class="caps">WICKET</span>-916</a> &#8211; inconsistent state after setting AjaxDebugModeEnabled to true in an AjaxRequest</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-920"><span class="caps">WICKET</span>-920</a> &#8211; ExternalLink produces invalid html</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-950"><span class="caps">WICKET</span>-950</a> &#8211; StatelessForm + QueryStringUrlCodingStrategy problem</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-953"><span class="caps">WICKET</span>-953</a> &#8211; Session invalidateNow() does not immediate remove the session from disk</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-958"><span class="caps">WICKET</span>-958</a> &#8211; Mounts ignored for PageExpiredErrorPage</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-972"><span class="caps">WICKET</span>-972</a> &#8211; IndexedParamUrlCodingStrategy seems to have problems handling resources</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-988"><span class="caps">WICKET</span>-988</a> &#8211; PropertyResolver map</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-991"><span class="caps">WICKET</span>-991</a> &#8211; StringIndexOutOfBoundsException in ServletWebRequest.getRelativePathPrefixToWicketHandler</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-995"><span class="caps">WICKET</span>-995</a> &#8211; getMarkupId generates ID which contains special characters which should be escaped or replaced</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1011"><span class="caps">WICKET</span>-1011</a> &#8211; wicketShow and wicketHide don&#8217;t check for existence of element before setting display</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1014"><span class="caps">WICKET</span>-1014</a> &#8211; AjaxEditableChoiceLabel doesn&#8217;t work in <span class="caps">IE 6</span></li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1015"><span class="caps">WICKET</span>-1015</a> &#8211; StringResourceModel does not escape interpolated properties</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1028"><span class="caps">WICKET</span>-1028</a> &#8211; WebRequestCycle.getProcessor javadoc doesn&#8217;t make sense</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1037"><span class="caps">WICKET</span>-1037</a> &#8211; Text not visible in Wicket Ajax Debug window</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1039"><span class="caps">WICKET</span>-1039</a> &#8211; parameters for Image never used when using a ResourceReference</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1040"><span class="caps">WICKET</span>-1040</a> &#8211; setEnabled() does not work on <span class="caps">YUI</span> DateField</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1047"><span class="caps">WICKET</span>-1047</a> &#8211; Amersand escaped twice for ResourceLink href</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1051"><span class="caps">WICKET</span>-1051</a> &#8211; StyleSheetReference doesn&#8217;t take style/locale into account</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1061"><span class="caps">WICKET</span>-1061</a> &#8211; Can&#8217;t enter data in any input field after closing modal window</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1062"><span class="caps">WICKET</span>-1062</a> &#8211; LocalizedImageResource does not serialize locale/style fields</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1065"><span class="caps">WICKET</span>-1065</a> &#8211; NullPointer in FileCleaner causes infinite loop</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1071"><span class="caps">WICKET</span>-1071</a> &#8211; AjaxFormSubmitBehavior creates invalid <span class="caps">HTML</span></li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1072"><span class="caps">WICKET</span>-1072</a> &#8211; Stateless pages bind to http session</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1074"><span class="caps">WICKET</span>-1074</a> &#8211; Image resource parameters fail to output in src attribute</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1075"><span class="caps">WICKET</span>-1075</a> &#8211; LocalizedImageResource: &#8216;static&#8217; Resource lost after locale/style change </li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1077"><span class="caps">WICKET</span>-1077</a> &#8211; VisitChildren + IComponentResolver broken in beta 4?</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1080"><span class="caps">WICKET</span>-1080</a> &#8211; StringResourceModel.toString() misbehavior</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1081"><span class="caps">WICKET</span>-1081</a> &#8211; ClassCastException with MetaDataEntry </li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1087"><span class="caps">WICKET</span>-1087</a> &#8211; Ajax update on a panel caused markup outside the panel to be missing</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1092"><span class="caps">WICKET</span>-1092</a> &#8211; IndexedParamUrlCodingStrategy creates a parameter in PageParameters when there is no parameter in the <span class="caps">URL</span></li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1095"><span class="caps">WICKET</span>-1095</a> &#8211; invisible TransparentResolver skips markup of visible children and thus resulting in an exception in Page#checkRendering (component not found in markup)</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1101"><span class="caps">WICKET</span>-1101</a> &#8211; NullPointerException in HybridUrlCodingStrategy</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1107"><span class="caps">WICKET</span>-1107</a> &#8211; <span class="caps">XHTML</span> code in AjaxFormSubmitBehavior.getPreconditionScript() is not well formed.</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1109"><span class="caps">WICKET</span>-1109</a> &#8211; <span class="caps">CLONE</span> -DatePicker: NaN if numerical input cannot be parsed</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1112"><span class="caps">WICKET</span>-1112</a> &#8211; wantonselectionchangednotification does not work in embedded forms</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1119"><span class="caps">WICKET</span>-1119</a> &#8211; Strings.replaceAll giving StringIndexOutOfBoundsException</li>
</ul>
<h4>Improvement</h4>
<ul>
<li><a href="https://issues.apache.org/jira/browse/WICKET-30"><span class="caps">WICKET</span>-30</a> &#8211; Nice and more practical url scheme</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-947"><span class="caps">WICKET</span>-947</a> &#8211; Add &#8216;UrlValidator&#8217; key to PL properties</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-949"><span class="caps">WICKET</span>-949</a> &#8211; ExternalLink does not support enable/disable like Link</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-957"><span class="caps">WICKET</span>-957</a> &#8211; Change default focus component for focus related events to null</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-963"><span class="caps">WICKET</span>-963</a> &#8211; add extension point to configure resource cache expiration time</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1005"><span class="caps">WICKET</span>-1005</a> &#8211; provide programmatic access to wicket-ajax.js</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1045"><span class="caps">WICKET</span>-1045</a> &#8211; mvn archetype:create -DarchetypeGroupId=org.apache.wicket -DarchetypeArtifactId=wicket-archetype-quickstart</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1052"><span class="caps">WICKET</span>-1052</a> &#8211; Wicket Javadoc Standardization: org.apache.wicket.util.thread</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1053"><span class="caps">WICKET</span>-1053</a> &#8211; Wicket Javadoc Standardization: org.apache.wicket.util.tester</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1054"><span class="caps">WICKET</span>-1054</a> &#8211; No way to escape html markup but keep non-7 bit characters in generated output</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1057"><span class="caps">WICKET</span>-1057</a> &#8211; Remove final from WebRequestCodingStrategy. urlCodingStrategyForPath</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1059"><span class="caps">WICKET</span>-1059</a> &#8211; Remove onAttach</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1060"><span class="caps">WICKET</span>-1060</a> &#8211; Allow component to a IComponentSource implementation that can reconstruct the component</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1063"><span class="caps">WICKET</span>-1063</a> &#8211; wicket-guice should support Provider injection and TypeLiteral injection</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1067"><span class="caps">WICKET</span>-1067</a> &#8211; Correct javadoc for Fragment</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1070"><span class="caps">WICKET</span>-1070</a> &#8211; Missing img alt attribute in WicketAjaxIndicatorAppender</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1083"><span class="caps">WICKET</span>-1083</a> &#8211; Inform wicket-ajax whether the application is running in a portlet</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1084"><span class="caps">WICKET</span>-1084</a> &#8211; Optimize memory usage</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1086"><span class="caps">WICKET</span>-1086</a> &#8211; Extending PagingNavigator for stateless pages</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1096"><span class="caps">WICKET</span>-1096</a> &#8211; Wicket Javadoc Standardization: org.apache.wicket.util.template, .string.interpolator</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1100"><span class="caps">WICKET</span>-1100</a> &#8211; Make portlet support configurable and default disabled</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1113"><span class="caps">WICKET</span>-1113</a> &#8211; DownloadLink support for temporary files</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1117"><span class="caps">WICKET</span>-1117</a> &#8211; FormComponent.setType is called in AbstractTextComponent.onBeforeRender</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1121"><span class="caps">WICKET</span>-1121</a> &#8211; Slight AbstractChoice refactoring</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1122"><span class="caps">WICKET</span>-1122</a> &#8211; Allow override of Pragma No-cache settings in WebPage</li>
</ul>
<h4>New Feature</h4>
<ul>
<li><a href="https://issues.apache.org/jira/browse/WICKET-445"><span class="caps">WICKET</span>-445</a> &#8211; TriStateCheckbox Component for use with CheckGroups</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-975"><span class="caps">WICKET</span>-975</a> &#8211; Update ImageButton to handle ResourceReferenc</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1106"><span class="caps">WICKET</span>-1106</a> &#8211; WicketTester or TagTester should provide access to the enclosed value of a tag</li>
</ul>
<h4>Task</h4>
<ul>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1078"><span class="caps">WICKET</span>-1078</a> &#8211; format entire codebase with wicket code format settings</li>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1126"><span class="caps">WICKET</span>-1126</a> &#8211; Release Wicket 1.3.0 <span class="caps">RC1</span></li>
</ul>
<h4>Wish</h4>
<ul>
<li><a href="https://issues.apache.org/jira/browse/WICKET-1012"><span class="caps">WICKET</span>-1012</a> &#8211; tracking dirty state (was:make setVisible, setEnable, add, addOrReplace, remove and removeAll non-final)</li>
</ul>
