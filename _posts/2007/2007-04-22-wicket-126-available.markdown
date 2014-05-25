---
layout: post
status: publish
published: true
title: Wicket 1.2.6 available
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 255
wordpress_url: http://martijndashorst.com/blog/2007/04/22/wicket-126-available/
date: '2007-04-22 22:04:22 +0200'
date_gmt: '2007-04-22 21:04:22 +0200'
categories:
- wicket
tags: []
comments:
- id: 1708
  author: dulanov
  author_email: dulanov@gmail.com
  author_url: http://dulanov.wordpress.com
  date: '2007-04-24 10:57:58 +0200'
  date_gmt: '2007-04-24 09:57:58 +0200'
  content: Will try it, thanks. I have written the internal enterprise controlling
    system on it, I am very happy with it ;)
---
<p>
The Wicket team is proud to announce another maintenance release for Wicket 1.2. With our first 1.3 release looming on the horizon, this probably marks the last 1.2 release. This release contains numerous fixes.</p>
<h3>IMPORTANT NOTE</h3>
<p>
A critical bug has been identified in the request processing of Wicket. In rare cases this bug could lead to users being presented with a page from another user's session. This bug is caused by a failure to  clean up resources in the processing thread under very rare circumstances. See [<a href="https://issues.apache.org/jira/browse/WICKET-476">WICKET-476</a>] for more information on this issue.</p>
<p>
Users are advised to upgrade their Wicket to 1.2.6. If you are using a custom built Wicket, please apply <a href="http://svn.apache.org/viewvc?view=rev&rev=529917">revision 529917</a> to your code.</p>
<h3>Other issues</h3>
<p>
This release fixes other issues as well:</p>
<h3>Bugs:</h3>
<ul>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-9">WICKET-9</a>] - OnError does not work on file upload exceding max size</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-134">WICKET-134</a>] - servlet.jar is included in the wicket examples war file.</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-260">WICKET-260</a>] - Wicket uses trivial encryption if com.sun.crypto.provider.SunJCE is not available</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-268">WICKET-268</a>] - NPE in ListView.renderItem(ListItem)</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-269">WICKET-269</a>] - Calls to enabled and visibleInHierarchy should not be done in component resolving.</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-276">WICKET-276</a>] - AbstractHeaderContributor.cleanup() will never be called</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-281">WICKET-281</a>] - wicket-ajax.js is sometime missing from <head> section</head></li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-290">WICKET-290</a>] - Inconsistent url generation</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-291">WICKET-291</a>] - return immutable parameter map or a copy of parameters</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-304">WICKET-304</a>] - AnnotSpringInjector corrupted class file in 1.2.5 release.</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-342">WICKET-342</a>] - Application_sv.properties variable bugs</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-349">WICKET-349</a>] - ListView can't undo changes to model</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-378">WICKET-378</a>] - autocomplete does not explicitly call input's onchange event</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-395">WICKET-395</a>] - Bookmarkable page problems</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-432">WICKET-432</a>] - getvariation() is called from webpage constructor through commoninit()</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-438">WICKET-438</a>] - File handles are leaked when loading images from a jar file, Tomcat crashes</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-475">WICKET-475</a>] - NPE in WebClientInfo when user-agent header is not sent</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-476">WICKET-476</a>] - Backport RequestCycle#updateSession and pagemap#session removal to 1.2.x</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-490">WICKET-490</a>] - The wicket-auth-roles-1.2.5.jar contains the .svn subdirectories.</li>
</ul>
<h3>Improvement</h3>
<ul>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-324">WICKET-324</a>] - AjaxFormComponentUpdatingBehavior updating other Component</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-325">WICKET-325</a>] - Enable WebMarkupContainer as target for wicketSerialize</li>
</ul>
<h3>New Feature</h3>
<ul>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-3">WICKET-3</a>] - listen for "selection changed"  event at AutocompleteTextField</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-338">WICKET-338</a>] - DateTextField</li>
</ul>
<p>
Although Wicket has recently entered the ASF Incubator, this interim release is provided outside of the ASF, solely as a service to existing Wicket users to resolve existing bugs in the Wicket product. As such, this release of the  Wicket project is not endorsed or approved by the Apache Software Foundation. The Apache Software Foundation is in  no way affiliated with this release.</p>
<ul>
<li>Download Wicket 1.2.6 <a href="http://sourceforge.net/project/showfiles.php?group_id=119783">here</a></li>
</ul>
