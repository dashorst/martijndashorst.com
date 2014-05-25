---
layout: post
status: publish
published: true
title: Wicket Ajax now replaces table elements such as TR and TD
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 12
wordpress_url: http://martijndashorst.com/2006/12/05/wicket-ajax-now-replaces-table-elements-such-as-tr-and-td/
date: '2006-12-05 22:22:15 +0100'
date_gmt: '2006-12-05 22:22:15 +0100'
categories:
- wicket
- java
tags: []
comments:
- id: 4
  author: Jess Sightler
  author_email: jesse.sightler@gmail.com
  author_url: http://www.jroller.com/page/jsight/
  date: '2006-12-06 15:45:15 +0100'
  date_gmt: '2006-12-06 15:45:15 +0100'
  content: Isn't this really just replacing the whole table also?
---
<p>Thanks to a <a href="http://issues.apache.org/jira/browse/WICKET-143">contribution</a> done by Vincent Demay, Wicket Ajax is now able to replace table parts such as <code>&lt;tr&gt;</code>, <code>&lt;td&gt;</code> and <code>&lt;tbody&gt;</code> in Internet Explorer.</p>
<p>
As you may know, Internet Explorer refuses to replace the inner-/outerhtml property of tags when they are tr, td, th, tbody, tfoot or thead. Until this patch you had to resort either to invalid markup such as:</p>
<pre lang="html"><table>
    <b><span wicket:id="rows"></b>
        <tr>...</tr>
    <b></span></b>
</table></pre>
<p>or replace the whole table using Ajax.</p>
<p>
With this patch we can replace just a part of a table, say a list item, instead of having to render the whole table again.</p>
