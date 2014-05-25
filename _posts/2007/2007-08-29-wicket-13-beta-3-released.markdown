---
layout: post
status: publish
published: true
title: Wicket 1.3 beta 3 released
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 289
wordpress_url: http://martijndashorst.com/blog/2007/08/29/wicket-13-beta-3-released/
date: '2007-08-29 07:40:07 +0200'
date_gmt: '2007-08-29 05:40:07 +0200'
categories:
- wicket
tags: []
comments:
- id: 9703
  author: links for 2007-08-29 &laquo; Object neo = neo Object
  author_email: ''
  author_url: http://neobject.wordpress.com/2007/08/29/links-for-2007-08-29/
  date: '2007-08-30 00:22:47 +0200'
  date_gmt: '2007-08-29 23:22:47 +0200'
  content: "[...] A Wicket DiaryÂ» Blog Archive Â» Wicket 1.3 beta 3 released Wicket
    1.3 beta 3 released. Majotariamente composto de bug fixes rumo ao release final.
    (tags: wicket java) [...]"
---
<p>This is the third beta for Apache Wicket we have prepared for your pleasure. It contains over 100 fixes to issues with previous releases and todo items we have cleared.</p>
<p>In this announcement:</p>
<ul>
<li>Apache Wicket</li>
<li>This release</li>
<li>Migrating from 1.2</li>
<li>Downloading the release</li>
<li>Validating the release</li>
<li>Reporting bugs</li>
</ul>
<p>Eager people click here to download the distribution, others can read further:</p>
<p><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-beta3/">http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-beta3/</a></p>
<p>We thank you for your patience and support. Given the current list of remaining issues we think a fourth beta release is necessary. But that is no excuse for not giving this third installment a test drive!</p>
<p>The Wicket Team</p>
<p><b>Apache Wicket</b></p>
<p>Apache Wicket is a component oriented Java web application framework currently undergoing incubation at the Apache Software foundation. With proper mark-up/logic separation, a POJO data model, and a refreshing lack of XML, Apache Wicket makes developing web-apps simple and enjoyable again. Swap the boilerplate, complex debugging and brittle code for powerful, reusable components written with plain Java and HTML.</p>
<p>Our migration to a top level project is now completed and you can find our website and documentation here:</p>
<p><a href="http://wicket.apache.org">http://wicket.apache.org</a></p>
<p><b>This release</b></p>
<p>This release is the third in a series of beta releases until we feel confident to finalize Wicket 1.3. This is called a beta because we don't have fixed all bugs, and probably haven't found them all either (can you ever be sure?). However, we are confident that most major API changes are in and therefore want to give you access to a more stable platform than depending on trunk.</p>
<p><b>Migrating from 1.2</b></p>
<p>If you are coming from Wicket 1.2, you really want to read our migration guide, found on the wiki:</p>
<p><a href="http://cwiki.apache.org/WICKET/migrate-13.html">http://cwiki.apache.org/WICKET/migrate-13.html</a></p>
<p><b>Downloading the release</b></p>
<p>You can download the release from the official Apache mirror system, and you can find it through the following link:</p>
<p><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-beta3/">http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-beta3/</a></p>
<p>For the Maven and Ivy fans out there: update your pom's to the following, and everything will be downloaded automatically:</p>
<pre>&lt;dependency&gt;
    &lt;groupId&gt;org.apache.wicket&lt;/groupId&gt;
    &lt;artifactId&gt;wicket&lt;/artifactId&gt;
    &lt;version&gt;1.3.0-beta3&lt;/version&gt;
&lt;/dependency&gt;</pre>
<p>Substitute the artifact ID with the projects of your liking to get the other projects.</p>
<p>Please note that we don't prescribe a Logging implementation for SLF4J. You need to specify yourself which one you prefer. Read more about SLF4J here: <a href="http://slf4j.org">http://slf4j.org</a></p>
<p><b>Validating the release</b></p>
<p>The release has been signed by Martijn Dashorst, your release manager for today. The public key can be found in the KEYS file in the download area. Download the KEYS file only from the Apache website.</p>
<p><a href="http://www.apache.org/dist/wicket/1.3.0-beta3/KEYS">http://www.apache.org/dist/wicket/1.3.0-beta3/KEYS</a></p>
<p>Instructions on how to validate the release can be found here:</p>
<p><a href="http://www.apache.org/dev/release-signing.html#check-integrity">http://www.apache.org/dev/release-signing.html#check-integrity</a></p>
<p><b>Reporting bugs</b></p>
<p>In case you do encounter a bug, we would appreciate a report in our JIRA:</p>
<p><a href="http://issues.apache.org/jira/browse/WICKET">http://issues.apache.org/jira/browse/WICKET</a></p>
<p><b>The distribution</b></p>
<p>In the distribution you will find a README. The README contains instructions</p>
<p>on how to build from source yourself and a list of all things that have been</p>
<p>fixed, added and/or removed since the first beta release.</p>
<p><b>Release Notes - Wicket - Version 1.3.0-beta3</b></p>
<h2>Sub-task</h2>
<ul>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-866'>WICKET-866</a>] - Assign open issues to next release</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-867'>WICKET-867</a>] - Build and upload distribution</li>
</ul>
<h2>Bug</h2>
<ul>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-322'>WICKET-322</a>] - Odd behvavior with PasswordTextField evaluation</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-447'>WICKET-447</a>] - Password field gets reset on setResetPassword == false even after successful validation</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-492'>WICKET-492</a>] - Website Developer SVN still references the branches/ directory and results in not found</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-494'>WICKET-494</a>] - id attribute is not preserved</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-500'>WICKET-500</a>] - org.apache.wicket.extensions.yui.calendar.DateField; throws NPE upon validation.</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-525'>WICKET-525</a>] - Component.getConverter is ignored by PropertyConverter</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-555'>WICKET-555</a>] - WicketTester.assertComponentOnAjaxResponse fails if AJAX response contains line breaks</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-564'>WICKET-564</a>] - Problem with Autolinks inside panel preview code</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-570'>WICKET-570</a>] - MarkupCache does not load markup if it did not exist before</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-601'>WICKET-601</a>] - RadioGroup and CheckGroup cause XHTML validation errors because of name attribute</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-627'>WICKET-627</a>] - Can't visit components in a ListView before they're rendered.</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-641'>WICKET-641</a>] - wicket thread handling is not fully servlet container aware</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-668'>WICKET-668</a>] - PropertyResolver.getPropertySetter() depends on calling PropertyResolver.setValue() first for it to work.</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-686'>WICKET-686</a>] - Allow validators to process null value</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-695'>WICKET-695</a>] - Border.resolve() should not attempt to render contents if bodyVisible is false</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-697'>WICKET-697</a>] - FormTester crashes with NullPointerException, if FormComponent is not found</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-698'>WICKET-698</a>] - If the model is List, PropertyResolver doesn't try to find fields.</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-700'>WICKET-700</a>] - Palette, Recorder Issue - Compound Property Model does not work.</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-703'>WICKET-703</a>] - AjaxEditableChoiceLabel doesn't work</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-710'>WICKET-710</a>] - Radio/Check/Box cleared on validation error</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-712'>WICKET-712</a>] - IConverter refers to nonexistent &quot;class c&quot;</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-714'>WICKET-714</a>] - PagingNavigation examples in javadoc are out of date (patch enclosed)</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-718'>WICKET-718</a>] - authentication example on wicketstuff.org/wicket13/authentication throws exception</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-719'>WICKET-719</a>] - [WICKET-673] breaks AbstractPageableView with AjaxPagingNavigator</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-720'>WICKET-720</a>] - Image does not regenerate its LocalizedImageResource resource/resourceReference when you call setModel()</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-721'>WICKET-721</a>] - MarkupException using &lt;wicket:message&gt; tags in a fragment</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-723'>WICKET-723</a>] - A 'recorder' subcomponent of Palette is used as property expression in the CompoundPropertyModel</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-724'>WICKET-724</a>] - WicketFilter doesn't handle filter mapping parameter from FilterConfig properly</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-729'>WICKET-729</a>] - OnChangeAjaxBehavior does not work with &lt;textarea&gt; when using Safari</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-737'>WICKET-737</a>] - Trivial fix for html validation in AbstractAjaxBehavior.java</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-738'>WICKET-738</a>] - setVisible(false) on Page throws NPE</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-739'>WICKET-739</a>] - MixedParamUrlCodingStrategy : no symmetric url encoding/decoding</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-741'>WICKET-741</a>] - Double quotes aren't escaped properly in component tag attributes.</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-743'>WICKET-743</a>] - spelling mistake in Application_de.properties</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-747'>WICKET-747</a>] - wrong positioning of date pickers</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-748'>WICKET-748</a>] - ServletWebRequest.getRelativePathPrefixToContextRoot generates wrong relative path if current page has URL-encoding in the params.</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-749'>WICKET-749</a>] - ClassCastException when using ReloadingWicketFilter</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-750'>WICKET-750</a>] - Calling setCacheable(false) on WebResource don't change header properties in WebResponse</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-755'>WICKET-755</a>] - EvenOddItem constants not actually constants</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-758'>WICKET-758</a>] - HTML validation cleanliness</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-760'>WICKET-760</a>] - WicketTester no longer works with WicketFilter</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-762'>WICKET-762</a>] - Resource cleanup in WicketTester</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-763'>WICKET-763</a>] - bread crumb component does not properly detach bread crumbs</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-765'>WICKET-765</a>] - default pagemap name of null is not always properly encoded into the url</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-769'>WICKET-769</a>] - Stripping Wicket tags not completely valid</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-772'>WICKET-772</a>] - IndexOutOfBoundsException in BehaviorRequestTarget</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-774'>WICKET-774</a>] - Feedback messages get cleaned up too early when using redirect to render strategy</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-779'>WICKET-779</a>] - Constructor of Session (and subclasses) has a redundant Application parameter</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-784'>WICKET-784</a>] - Session.dirty() does not cause an unbound session to bind.</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-790'>WICKET-790</a>] - WebExternalResourceStream.close() throws NPE</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-791'>WICKET-791</a>] - page and webpage constructor with pageparameters argument does not properly initialize</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-793'>WICKET-793</a>] - PasswordTextField.setResetPassword(false) not honoring input when form has errors</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-798'>WICKET-798</a>] - A Few Wicket Projects are Missing site.xml and wicket-site-skin</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-801'>WICKET-801</a>] - getTo() in NavigatorLabel is off by one</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-802'>WICKET-802</a>] - Incorrect use of src/main/resources?</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-803'>WICKET-803</a>] - Use of parent pom?</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-809'>WICKET-809</a>] - DatePicker: invalid Javascript when component's wicket:id contains non-word character</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-813'>WICKET-813</a>] - DatePicker doesn't notify component</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-814'>WICKET-814</a>] - DateTimeField minute field needs zero-padding - it should display &quot;00&quot; not &quot;0&quot;</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-816'>WICKET-816</a>] - Component#getLocale and Component#getVariation should search their parents</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-823'>WICKET-823</a>] - Empty content inserted into Border - throws ugly exceptions</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-827'>WICKET-827</a>] - Ajax refresh fails when a fragment is included in the target</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-828'>WICKET-828</a>] - Using form method=get does not work</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-833'>WICKET-833</a>] - /wicket-datetime/   org.apache.wicket.util.license.JavaScriptLicenseHeaderHandler failed.</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-834'>WICKET-834</a>] - Cannot make border body contents visible once they were hidden</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-838'>WICKET-838</a>] - AjaxFormChoiceComponentUpdatingBehavior not working</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-839'>WICKET-839</a>] - Make FormComponent#setRequired non-final</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-841'>WICKET-841</a>] - More problems with ajax and transparent containers</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-850'>WICKET-850</a>] - Bad message resolution when sibling components require the same key</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-859'>WICKET-859</a>] - DateField's/ DateTimeField's factory methods should pass in ids</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-891'>WICKET-891</a>] - Switching locale doesn't change already rendered feedback messages' language</li>
</ul>
<h2>Improvement</h2>
<ul>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-394'>WICKET-394</a>] - [Patch] do not serialize choices and select in palette. </li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-426'>WICKET-426</a>] - Take advantage of covariant return types in getSession()</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-602'>WICKET-602</a>] - Highlighting/Preselecting the first item in the autocomplete list.</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-634'>WICKET-634</a>] - Add an AjaxFallbackButton</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-661'>WICKET-661</a>] - fire onchange event of associated component after date selection</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-699'>WICKET-699</a>] - Recover gracefully when no graphics display is available</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-709'>WICKET-709</a>] - Unable to remove an IFormValidator from a Form</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-711'>WICKET-711</a>] - Remove log4j dependency</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-716'>WICKET-716</a>] - make getConvertedInput final again and remove final from convert, which should be renamed to convertInput</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-726'>WICKET-726</a>] - make default maximum upload size an application setting</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-727'>WICKET-727</a>] - WicketTester cause SerializableChecker$WicketNotSerializableException</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-731'>WICKET-731</a>] - make SmartLinkLabel more flexible </li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-732'>WICKET-732</a>] - Qualified resource key should take priority over unqualified one</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-733'>WICKET-733</a>] - [PATCH] &lt;input type=&quot;submit&quot;&gt; doesn't render value attribute with Link component</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-736'>WICKET-736</a>] - Improve PageStore</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-740'>WICKET-740</a>] - make displaying the PageView in ExceptionErrorPage optional</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-751'>WICKET-751</a>] - DatePicker doesn't  adhere to the provided DatePattern</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-754'>WICKET-754</a>] - add support for localization</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-759'>WICKET-759</a>] - Add metadata to RequestCycle</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-761'>WICKET-761</a>] - Disable line-precise exceptions for component use check</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-766'>WICKET-766</a>] - Allowing overriding of wicket's generated ID</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-770'>WICKET-770</a>] - Contribution of Application_lv.properties.   </li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-781'>WICKET-781</a>] - AjaxFallbackDefaultDataTable and DefaultDataTable require SortableDataProvider class, not an interface</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-805'>WICKET-805</a>] - upgrade to SLF4J to version 1.4.2</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-808'>WICKET-808</a>] - renderIterator of ListView and Loop should use the number of children rather than the current size of the model</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-817'>WICKET-817</a>] - date converters should try to use any components they are coupled to get the locale</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-818'>WICKET-818</a>] - add documentation for 'criteria' parameter in IAutoCompleteRenderer</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-820'>WICKET-820</a>] - Add PL (polish) property files to wicket</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-821'>WICKET-821</a>] - Add SL (slovenian) property files to wicket</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-829'>WICKET-829</a>] - DetachableContactModel - the 'contact' property is never used</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-837'>WICKET-837</a>] - Use -DpackageName if it is specified</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-840'>WICKET-840</a>] - FormComponentPanel should be abstract and have abstract method checkRequired</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-863'>WICKET-863</a>] - don't throw exceptions when missing keys for var substitution when throwExceptionOnMissingResource setting is false</li>
</ul>
<h2>New Feature</h2>
<ul>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-786'>WICKET-786</a>] - Add &quot;deny&quot; capability to AuthorizeAction</li>
</ul>
<h2>Task</h2>
<ul>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-459'>WICKET-459</a>] - Add to API: Palette requires a ChoiceRenderer with both a displayvalue and id value</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-533'>WICKET-533</a>] - Make sure that Page and no other component requires to load the markup before constructor</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-811'>WICKET-811</a>] - upgrade YUI to 2.3.0 and use yuiloader facilities</li>
<li>[<a href='https://issues.apache.org/jira/browse/WICKET-865'>WICKET-865</a>] - Release Wicket-1.3-beta3</li>
</ul>
