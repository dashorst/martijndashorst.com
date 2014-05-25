---
layout: post
status: publish
published: true
title: Wicket 1.3.0-beta4 released
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 313
wordpress_url: http://martijndashorst.com/blog/2007/10/11/wicket-130-beta4-released/
date: '2007-10-11 21:09:29 +0200'
date_gmt: '2007-10-11 20:09:29 +0200'
categories:
- wicket
tags: []
comments: []
---
<p>This is a major milestone in Wicket history. Since Wicket became open source, this is the first Wicket release <strong>not</strong> created by me. Instead, Frank Bille has taken the torch and crafted this release for the community. Congratulations Frank!</p>
<p>
Here are the release notes:</p>
<h2>Apache Wicket 1.3.0-beta4</h2>
<p>This is the fourth beta for Apache Wicket we have prepared for your pleasure. It contains over 120 fixes to issues with previous releases and todo items we have cleared.</p>
<p>In this announcement:</p>
<ul>
<li>Apache Wicket</li>
<li>This release</li>
<li>Portlet support</li>
<li>Migrating from 1.2</li>
<li>Downloading the release</li>
<li>Validating the release</li>
<li>Reporting bugs</li>
</ul>
<p>Eager people click here to download the distribution, others can read further:</p>
<p><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-beta4/">http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-beta4/</a></p>
<p>We thank you for your patience and support. Given the current list of remaining issues and the fact that we have just accepted portlet support back in, we think a fifth beta release is necessary. But that is no excuse for not giving this fourth installment a test drive!</p>
<p>The Wicket Team</p>
<h2>Apache Wicket</h2>
<p>Apache Wicket is a component oriented Java web application framework. With proper mark-up/logic separation, a <span class="caps">POJO</span> data model, and a refreshing lack of <span class="caps">XML</span>, Apache Wicket makes developing web-apps simple and enjoyable again. Swap the boilerplate, complex debugging and brittle code for powerful, reusable components written with plain Java and <span class="caps">HTML</span>.</p>
<p>Our migration to a top level project is now completed and you can find our website and documentation here:</p>
<p><a href="http://wicket.apache.org">http://wicket.apache.org</a></p>
<h2>This release</h2>
<p>This release is the fourth in a series of beta releases until we feel confident to finalize Wicket 1.3. This is called a beta because we donâ€™t have fixed all bugs, and probably havenâ€™t found them all either.</p>
<h3>Portlet support</h3>
<p>A new feature in this beta4 release is the merge of Ate Doumaâ€™s portlet branch into trunk. This reintroduces portlet support in Wicket.</p>
<p><a href="http://cwiki.apache.org/WICKET/portal-howto.html">http://cwiki.apache.org/WICKET/portal-howto.html</a></p>
<h2>Migrating from 1.2</h2>
<p>If you are coming from Wicket 1.2, you really want to read our migration guide, found on the wiki:</p>
<p><a href="http://cwiki.apache.org/WICKET/migrate-13.html">http://cwiki.apache.org/WICKET/migrate-13.html</a></p>
<h2>Downloading the release</h2>
<p>You can download the release from the official Apache mirror system, and you can find it through the following link:</p>
<p><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-beta4/">http://www.apache.org/dyn/closer.cgi/wicket/1.3.0-beta4/</a></p>
<p>For the Maven and Ivy fans out there: update your pomâ€™s to the following, and everything will be downloaded automatically:</p>
<pre>
    &lt;dependency&gt;
        &lt;groupid&gt;org.apache.wicket&lt;/groupid&gt;
        &lt;artifactid&gt;wicket&lt;/artifactid&gt;
        &lt;version&gt;1.3.0-beta4&lt;/version&gt;
    &lt;/dependency&gt; 
</pre>
<p>Substitute the artifact ID with the projects of your liking to get the other projects.</p>
<p>Please note that we donâ€™t prescribe a Logging implementation for <span class="caps">SLF4J</span>. You need to specify yourself which one you prefer. Read more about <span class="caps">SLF4J</span> here: <a href="http://slf4j.org">http://slf4j.org</a></p>
<h2>Validating the release</h2>
<p>The release has been signed by Frank Bille, your release manager for today. The public key can be found in the <span class="caps">KEYS</span> file in the download area. Download the <span class="caps">KEYS</span> file only from the Apache website.</p>
<p><a href="http://www.apache.org/dist/wicket/1.3.0-beta4/KEYS">http://www.apache.org/dist/wicket/1.3.0-beta4/KEYS</a></p>
<p>Instructions on how to validate the release can be found here:</p>
<p><a href="http://www.apache.org/dev/release-signing.html#check-integrity">http://www.apache.org/dev/release-signing.html#check-integrity</a></p>
<h2>Reporting bugs</h2>
<p>In case you do encounter a bug, we would appreciate a report in our <span class="caps">JIRA</span>:</p>
<p><a href="http://issues.apache.org/jira/browse/WICKET">http://issues.apache.org/jira/browse/WICKET</a></p>
<h2>The distribution</h2>
<p>In the distribution you will find a <span class="caps">README</span>. The <span class="caps">README</span> contains instructions on how to build from source yourself and a list of all things that have been fixed, added and/or removed since the first beta release.</p>
<h2>Release Notes â€“ Wicket â€“ Version 1.3.0-beta4</h2>
<h3>Bug</h3>
<ul>
<li>[WICKET-349] â€“ ListView canâ€™t undo changes to model</li>
<li>[WICKET-470] â€“ AjaxFormComponentUpdatingBehavior wonâ€™t work for RadioChoices </li>
<li>[WICKET-497] â€“ For stateless mounted page incorrect url is generated</li>
<li>[WICKET-520] â€“ Escape doesnâ€™t work for AjaxEditableLabel in Firefox</li>
<li>[WICKET-572] â€“ replacing tr using ajax does not work in safari </li>
<li>[WICKET-611] â€“ AbstractRequestTargetUrlCodingStrategy ignores query parameters if there is no parameter in the path</li>
<li>[WICKET-631] â€“ Resource.getParameters() empty when resource is mounted</li>
<li>[WICKET-635] â€“ FormTester Does Not Properly Handle DropDownChoice With Null Model </li>
<li>[WICKET-640] â€“ modal window close button does not cancel the event after closing the window</li>
<li>[WICKET-685] â€“ ReloadingWicketFilter not working with markup inheritance</li>
<li>[WICKET-705] â€“ StringValue javadoc incorrect regrading conversion to checked exception </li>
<li>[WICKET-707] â€“ Invoking a request listener on a page returns an Expired Error page</li>
<li>[WICKET-722] â€“ IndicatingAjaxFallbackLink does not remove indicator if the link itself is added via ajax</li>
<li>[WICKET-728] â€“ WicketTester could not handle Multipart form without upload </li>
<li>[WICKET-735] â€“ SqlTimestampConverter and itâ€™s Date and Time friends die on null and other breakage.</li>
<li>[WICKET-745] â€“ AbstractAjaxTimerBehavior triggered more than expected after a new Ajax rendering</li>
<li>[WICKET-756] â€“ FormComponent.getValue uses equals instead of == to compare NO_RAW_INPUT</li>
<li>[WICKET-775] â€“ Buggy behaviour in FormComponentPanel.setRequired(boolean)</li>
<li>[WICKET-782] â€“ Select doesnâ€™t validate â€˜Requiredâ€™ </li>
<li>[WICKET-796] â€“ setresponsepage() does not properly redirect from ajax requests</li>
<li>[WICKET-807] â€“ MockHttpServletRequest.addFile does not work with binary files</li>
<li>[WICKET-819] â€“ DefaultButtonImageResourceâ€™s fontAttributes field isnâ€™t serializable </li>
<li>[WICKET-824] â€“ Session id encoding problem in cookie-less mode</li>
<li>[WICKET-826] â€“ No scrolling behaviour of source code viewer in <span class="caps">IE 6</span></li>
<li>[WICKET-836] â€“ feedback panels not being updated when inside repeaters </li>
<li>[WICKET-842] â€“ <html wicket:id="html"> is broken againâ€¦</html></li>
<li>[WICKET-846] â€“ Javadocs for AbstractDefaultAjaxBehaviorPrecondition#getSuccessScript() and #getPreconditionScript() are swapped</li>
<li>[WICKET-849] â€“ Bad multiple select display with DatePicker and ajax debug</li>
<li>[WICKET-851] â€“ WicketTester unusable after subsequent startPage(Page) call</li>
<li>[WICKET-856] â€“ add dependency slf4j-log4j12 to wicket-quickstart </li>
<li>[WICKET-864] â€“ HttpServletResponse.encodeRedirectURL() missing in WicketFilter</li>
<li>[WICKET-869] â€“ Back button processing doesnâ€™t work in Opera</li>
<li>[WICKET-870] â€“ ignore white space in web.xml filter, filtermapping </li>
<li>[WICKET-871] â€“ Markup hirarchy gets messed up when value of  attribute â€˜backgroundâ€™ is a relative path</li>
<li>[WICKET-872] â€“ Typo in org.apache.wicket.markup.html.tree.res.tree.js causes <span class="caps">AJAX</span> tree node addition failures </li>
<li>[WICKET-874] â€“ Reloading servlet doing way too much reloading</li>
<li>[WICKET-877] â€“ stateless page + form + bookmark = trouble</li>
<li>[WICKET-878] â€“ IllegalStateException accessing Session.get() from own Resource implementation </li>
<li>[WICKET-881] â€“ AbstractChoice not taking into account html escape settings</li>
<li>[WICKET-882] â€“ RefreshingView should call super.onBeforeRender after it refreshed itâ€™s items.</li>
<li>[WICKET-883] â€“ Modification Watcher Task Log </li>
<li>[WICKET-885] â€“ ResourceSettings#getStringResourceLoaders throws an ArrayStoreException</li>
<li>[WICKET-886] â€“ InlineFrame with null PageMap raises exception</li>
<li>[WICKET-887] â€“ Unable to find InlineFrames when inside ListViews </li>
<li>[WICKET-889] â€“ Automatic multi-window support drops <span class="caps">URL</span> fragment identifier</li>
<li>[WICKET-890] â€“ Modal window causes session expires</li>
<li>[WICKET-892] â€“ RefreshingView only gets rendered when TreeTable node is opened twice </li>
<li>[WICKET-893] â€“ Relative urls are broken if there is a + in parameter</li>
<li>[WICKET-894] â€“ setStripComments corrupts other <span class="caps">HTML</span> tags</li>
<li>[WICKET-895] â€“ If a form includes a DataTable with AjaxEditableLabels and the form should be refresh an exception occurs when a user switches between a changed label to another </li>
<li>[WICKET-896] â€“ wrong redirect BrowserInfoPage and mounted Pages</li>
<li>[WICKET-897] â€“ WicketSessionFilter doesnâ€™t work with 1.3</li>
<li>[WICKET-899] â€“ Authentication example fails with â€œPasswordTextField does not support cookiesâ€ </li>
<li>[WICKET-903] â€“ WicketServlet no longer sets application on current thread</li>
<li>[WICKET-906] â€“ It is impossible to inject primitives</li>
<li>[WICKET-908] â€“ There is no way to specify what exceptions to log in RequestCycle </li>
<li>[WICKET-909] â€“ onBeforeRender not called on ModalWindow contents</li>
<li>[WICKET-913] â€“ PopupCloseLink broken with <span class="caps">REDIRECT</span>_TO_RENDER strategy</li>
<li>[WICKET-914] â€“ Tree not â€œredrawnâ€ when resetting root node </li>
<li>[WICKET-922] â€“ Inconsistent use of Button vs. IFormSubmittingComponent</li>
<li>[WICKET-923] â€“ Back button browser problem and ajax</li>
<li>[WICKET-929] â€“ ExceptionErrorPage only works with WebResponse</li>
<li>[WICKET-934] â€“ textfield strings are not trimmed when performing validation (conversion). </li>
<li>[WICKET-935] â€“ AbstractRepeater#onBeforeRender should not be final</li>
<li>[WICKET-936] â€“ Wicket:message texts do not change when session locale chages.</li>
<li>[WICKET-937] â€“ Wicket Contrib Date Picker Not Picking Up Date Properly In CompoundPropertyModel </li>
<li>[WICKET-938] â€“ Second and subsequent ajax component updates fail in Safari</li>
<li>[WICKET-946] â€“ WebRequestCodingStrategy is not synchronized</li>
<li>[WICKET-951] â€“ the javadoc of FormComponent.updateModel() states: â€.. it expect that the object is already converted through the convert() callâ€, but FormComponent.updateModel() documentation bugâ€â€ </li>
<li>[WICKET-954] â€“ Default button does not provide button name</li>
<li>[WICKET-956] â€“ Bug In Wicket Listing Using DataTables </li>
<li>[WICKET-960] â€“ FilteredAbstractColumn unary constructor expects Model instead of IModel</li>
<li>[WICKET-965] â€“ ReloadingWicketFilter gives ClassCastException with page hierarchy involved</li>
<li>[WICKET-973] â€“ setRenderAllowed not called in Tree items </li>
<li>[WICKET-974] â€“ Image#getResource always returns null even if there is a resource</li>
<li>[WICKET-976] â€“ IndexedParamUrlCodingStrategy chokes inside appendParameters() on Stateless forms</li>
<li>[WICKET-977] â€“ Static Pages -> Passing <span class="caps">URI</span> to a Wicket page == 404 Error </li>
<li>[WICKET-978] â€“ log4j.properties in quickstart archetype uses old wicket package name</li>
<li>[WICKET-981] â€“ <span class="caps">NPE</span> in Component.remove(final IBehavior behavior)</li>
<li>[WICKET-984] â€“ MockWebApplication should use PageFactory from given WebApplication. </li>
<li>[WICKET-985] â€“ AjaxFallbackDefaultDataTable in a border fails</li>
<li>[WICKET-987] â€“ Stripping javascript comments and whitespace breaks application when using prototype library</li>
<li>[WICKET-990] â€“ Localizer complains about component not being added to the page when the component is a page </li>
<li>[WICKET-993] â€“ wicket:enclosure doesnâ€™t work with multiple child components</li>
<li>[WICKET-994] â€“ Ajax requests may happen before <span class="caps">DOM</span> is ready</li>
<li>[WICKET-997] â€“ AjaxButton using null as the form in the onSubmit() callback </li>
<li>[WICKET-999] â€“ DynamicWebResource function as StaticResource</li>
<li>[WICKET-1001] â€“ Misleading  EnclosureResolver javadoc and wiki</li>
<li>[WICKET-1013] â€“ spring component injection leads to deserialization error (or page expiration) </li>
<li>[WICKET-1016] â€“ ExternalLink doesnâ€™t use model</li>
<li>[WICKET-1027] â€“ Form.appendDefaultButtonField() appends invalid <span class="caps">HTML</span></li>
<li>[WICKET-1036] â€“ Session size is constantly increasing on setResponsePage(getPage()) </li>
<li>[WICKET-1042] â€“ setResponsePage(PageClass) doesnâ€™t take current pagemap into account</li>
<li>[WICKET-1046] â€“ FeedbackMessages donâ€™t get cleaned up in an <span class="caps">AJAX</span> request when renderstrategy is <span class="caps">REDIRECT</span>_TO_RENDER </li>
<li>[WICKET-1050] â€“ MarkupParser.removeComment() does not properly parse to end of <span class="caps">HTML</span> comment</li>
</ul>
<h3>Improvement</h3>
<ul>
<li>[WICKET-544] â€“ Refactor duplicate code into ConversionException </li>
<li>[WICKET-604] â€“ â€™ Wicket.Channelâ€™ name is not accessible in ajax related classes</li>
<li>[WICKET-646] â€“ Do not throw an error when image not found while testing</li>
<li>[WICKET-669] â€“ AjaxEditableLabel needs Model for adding a IValidator </li>
<li>[WICKET-771] â€“ Provide ResourceReference with ID attribute for filtering multiple includes</li>
<li>[WICKET-780] â€“ Internal server error 500 unresolvable in Ajax Debug Window</li>
<li>[WICKET-795] â€“ Easy access to final rendered page source </li>
<li>[WICKET-800] â€“ PropertyVariableInterpolator should support escaping of the string â€™${â€˜</li>
<li>[WICKET-843] â€“ improve <span class="caps">API</span> documentation for getStatelessHint() method in org.apache.wicket.Component</li>
<li>[WICKET-845] â€“ Label constructor </li>
<li>[WICKET-853] â€“ Repaired invalid <span class="caps">HTML</span> markup produced by FilterToolbar </li>
<li>[WICKET-854] â€“ ModalWindow.setTitle needs to accept a model</li>
<li>[WICKET-879] â€“ reduce code in DatePicker.js (because it can be loaded multiple times per page) </li>
<li>[WICKET-880] â€“ Option to align DatePicker to the left of icon</li>
<li>[WICKET-898] â€“ JS namespace pollution in wicket-extensions </li>
<li>[WICKET-900] â€“ [Patch]Allow to set a custom css to the calendar</li>
<li>[WICKET-907] â€“ FeedbackMessage <span class="caps">SUCCESS</span> level? </li>
<li>[WICKET-927] â€“ Deprecate Fragment constructors that dont take a markup provider</li>
<li>[WICKET-941] â€“ Patch to fix layout and positioning issues for the maven generated wicket site</li>
<li>[WICKET-955] â€“ Make wizard work with default button </li>
<li>[WICKET-961] â€“ Add variables to ConversionException</li>
<li>[WICKET-962] â€“ Ajax updates do not work on Components with wicket id that is not \d+ when within AbstractRepeater/RepeatingView</li>
<li>[WICKET-964] â€“ provide direct access on output stream in resources </li>
<li>[WICKET-970] â€“ Wicket Javadoc Standardization: org.apache.wicket.validation.*</li>
<li>[WICKET-971] â€“ Wicket Javadoc Standardization: org.apache.wicket.util.watch</li>
<li>[WICKET-986] â€“ Wicket Javadoc Standardization: org.apache.wicket.util.value</li>
<li>[WICKET-998] â€“ Remove obsolete attribute modifier</li>
<li>[WICKET-1000] â€“ Wicket Javadoc Standardization: org.apache.wicket.time</li>
<li>[WICKET-1004] â€“ Label associated with an open/close tag should still work </li>
<li>[WICKET-1009] â€“ russian resource files</li>
<li>[WICKET-1034] â€“ Allow Custom Javascript on <span class="caps">AJAX</span> Busy Indication</li>
<li>[WICKET-1041] â€“ Fix a <span class="caps">TODO</span> for 1.3 at AjaxFormSubmitBehavior.onError()</li>
<li>[WICKET-1044] â€“ Clarification of when children are added to Component tree for TabbedPanel</li>
</ul>
<h3>New Feature</h3>
<ul>
<li>[WICKET-480] â€“ IHeaderResponse.renderOnUnLoadJavascript(String javascript);</li>
<li>[WICKET-806] â€“ add month/year selection</li>
<li>[WICKET-832] â€“ [Patch] add a UrlValidator</li>
<li>[WICKET-930] â€“ Wrap Guice-Injector with proxying for Objects </li>
<li>[WICKET-939] â€“ Make org.apache.wicket.markup.html.image work with ajax by adding either random or autoindex or??</li>
<li>[WICKET-944] â€“ ehcache based MarkupCache (1.3)</li>
<li>[WICKET-979] â€“ Wants yahoo calendar to be displayed on page by default (ie no popup) </li>
<li>[WICKET-983] â€“ Merge the portlet support branch into the trunk</li>
<li>[WICKET-1030] â€“ add support for CalendarGroup</li>
<li>[WICKET-1031] â€“ add facilities to execute javascript code to further customize the <span class="caps">YUI</span> Calendar</li>
</ul>
<h3>Task</h3>
<ul>
<li>[WICKET-858] â€“ warning note when using DefaultDataTable</li>
<li>[WICKET-1023] â€“ Release Wicket 1.3.0-beta4</li>
</ul>
<h3>Wish</h3>
<ul>
<li>[WICKET-804] â€“ Need a â€œGetting Started/Creating a new Wicket projectâ€ guide</li>
</ul>
