---
layout: post
status: publish
published: true
title: 'Wicket 1.2.7: the last maintenance release'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
excerpt: "The Wicket team announces the last maintenance release of Wicket 1.2: Wicket
  1.2.7.\r\n\r\nThis release fixes the remaining issues for Wicket 1.2. For future
  support we ask you to upgrade to Apache Wicket 1.3 or newer.\r\n\r\nThis release
  of the Wicket project is not endorsed or approved by the Apache Software Foundation.
  The Apache Software Foundation is in no way affiliated with this release.\r\n\r\nBelow
  are the release notes for Wicket 1.2.7.\r\n\r\n- the Wicket team\r\n\r\n"
wordpress_id: 352
wordpress_url: http://martijndashorst.com/blog/2008/03/23/wicket-127-the-last-maintenance-release/
date: '2008-03-23 14:42:04 +0100'
date_gmt: '2008-03-23 13:42:04 +0100'
categories:
- wicket
tags:
- wicket
- release
comments: []
---
<p>The Wicket team announces the last maintenance release of Wicket 1.2: Wicket 1.2.7.</p>
<p>This release fixes the remaining issues for Wicket 1.2. For future support we ask you to upgrade to Apache Wicket 1.3 or newer.</p>
<p>This release of the Wicket project is not endorsed or approved by the Apache Software Foundation. The Apache Software Foundation is in no way affiliated with this release.</p>
<p>Below are the release notes for Wicket 1.2.7.</p>
<p>- the Wicket team</p>
<p><a id="more"></a><a id="more-352"></a></p>
<h2>Release Notes - Wicket - Version 1.2.7</h2>
<h3>Bug</h3>
<ul>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-117">WICKET-117</a>] - Page expired using ajax</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-311">WICKET-311</a>] - race condition between wicket.session.pagemap.LeastRecentlyAccessedEvictionStrategy and Session.getPage()</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-312">WICKET-312</a>] - AjaxFormComponentUpdatingBehavior doesn't call onError when FormComponent is not valid</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-349">WICKET-349</a>] - ListView can't undo changes to model</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-427">WICKET-427</a>] - WebRequestCodingStrategy.urlCodingStrategyForPath() passes null as key</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-487">WICKET-487</a>] - Buggy behaviour in PageMap.access(IPageMapEntry,int). Wicket1.2.4</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-511">WICKET-511</a>] - New ServletWebRequest.getParameterMap() implementation changed between 1.2.5 and 1.2.6</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-524">WICKET-524</a>] - ClassCastException in WebRequestCodingStrategy</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-540">WICKET-540</a>] - ServletWebRequest.getContextPath() ignores ContextPath as set by user (accesses HttpServletRequest directly)</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-546">WICKET-546</a>] - SubmitLink issue : Need for handling user's own onclick javascript call + default &amp;&amp; modification in onComponentTag call.</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-571">WICKET-571</a>] - AjaxLinks throws java.lang.ClassCastException</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-593">WICKET-593</a>] - equals() in ResourceStreamRequestTarget compares the wrong filename</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-623">WICKET-623</a>] - Backport call to super onComponentTag in ExternalLink</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-642">WICKET-642</a>] - Need to escape select html option value</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-828">WICKET-828</a>] - Using form method=get does not work</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-943">WICKET-943</a>] - java.lang.NullPointerException at wicket.markup.html.list.ListView.renderItem(ListView.java:676)</li>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-1076">WICKET-1076</a>] - SubmitLink component does not render markup id</li>
</ul>
<h3>Improvement</h3>
<ul>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-1145">WICKET-1145</a>] - Patch for allowing &lt;input type="search"/&gt; to be serialized</li>
</ul>
<h3>New Feature</h3>
<ul>
<li>[<a href="https://issues.apache.org/jira/browse/WICKET-786">WICKET-786</a>] - Add "deny" capability to AuthorizeAction</li>
</ul>
