---
layout: post
status: publish
published: true
title: Wicket Most Widely Used Framework!
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 139
wordpress_url: http://martijndashorst.com/2005/08/18/wicket-most-widely-used-framework/
date: '2005-08-18 22:59:54 +0200'
date_gmt: '2005-08-18 22:59:54 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 154
  author: kumar
  author_email: neel5_kumar@yahoo.com
  author_url: ''
  date: '2005-08-25 13:23:11 +0200'
  date_gmt: '2005-08-25 13:23:11 +0200'
  content: "Hi,\nI am just wondering if wicket is that much of worth. I mean for each
    page you write you need to write \n1. one Html page\n2. One Java code where you
    insert you code for writing form and action...\nIs not it true that JSP way of
    writing tags or velocity with struts much cleaner and better architecture? Wicket
    will add another thousands and thousands line of java code to existing application
    just for display."
---
<p>
On <a href="http://www.javalobby.org/java/forums/t43982.html">JavaLobby.org</a> a discussion was started on whether or not <a href="http://wicket.sf.net">Wicket</a> was the most widely used framework. <a href="http://raibledesigns.com/page/rd?entry=wicket_is_the_most_widely">Matt Raible</a> commented that it was most likely <em>guerilla warfare</em> from the Wicket team.</p>
<p>
Well, I consider myself to be somewhat the evangelist for Wicket, and though I had noticed the <a href="http://java.about.com/b/a/185819.htm">about.com</a> blog post requesting which framework was the most popular, I found the method of emailing him rather cumbersome, and I prefer open forums so everybody can see who posted what. I can't remember asking anybody to respond, so <em>it wasn't me</em> :-)</p>
<p>
Matt also gives some graphs on mailinglist statistics. And yes, Wicket has soared in July with mailinglist activity. More so than 'competing' frameworks such as MyFaces, Cocoon, Echo, WebWork. And he quotes me saying that huge mailinglist activity may be a bad sign. I still stand by my standpoint: it may be an AntiPattern when a mailinglist is highly active. But just looking at the number of messages is not enough: looking at the type of messages is more indicative. It is a bummer that qualitative measurements are nigh impossible to take.</p>
<p>
So another rather cool measurement Matt likes to do is download numbers. So lets try to figure out what the stats are for our frameworks (sourceforge is not helping though, and Tapestry downloads are missing):</p>
<table>
<tr>
<th>Framework</th>
<th>Last week</th>
<th>Last 2 months</th>
</tr>
<tr>
<td>Wicket</td>
<td>195</td>
<td>2851</td>
</tr>
<td>WebWork</td>
<td>9</td>
<td>123</td>
</tr>
<td>MyFaces (sourceforge)</td>
<td>102</td>
<td>4368</td>
</tr>
<td>MyFaces (apache)</td>
<td>~180</td>
<td>~400</td>
</tr>
<td>Struts</td>
<td>~3200</td>
<td>~78000</td>
</tr>
</table>
<p>Because I don't have the actual data for the Apache projects, I am not able to calculate them precisely. I have tried to guess the numbers based on the graphs found <a href="http://people.apache.org/~vgritsenko/stats/projects/struts.html">here</a>.</p>
<p>One thing that is striking is that a lot of people still download the old (2004) release of MyFaces from sourceforge.net. Another is that that number is much higher than the Apache numbers. Struts still dwarfs all other frameworks.</p>
<p>What does this tell us? Not too much. Wicket is at the moment compareable in popularity to MyFaces, and WebWork is seriously falling behind. If you want job security, then download struts now, as it will be around for <em>FAR TOO LONG</em> considering these numbers. <b>When you also want to have fun in your job, download Wicket</b>.</p>
