---
layout: post
status: publish
published: true
title: 'Eclipse goodie: your actual name instead of login in JavaDoc author tags'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 60
wordpress_url: http://martijndashorst.com/2006/04/21/eclipse-goodie-your-actual-name-instead-of-login-in-javadoc-author-tags/
date: '2006-04-21 08:37:48 +0200'
date_gmt: '2006-04-21 08:37:48 +0200'
categories:
- java
tags: []
comments:
- id: 67
  author: ''
  author_email: ''
  author_url: ''
  date: '2006-04-21 09:49:50 +0200'
  date_gmt: '2006-04-21 09:49:50 +0200'
  content: "Wow! Thanks. Good tip. To overcome this I have edited the code template
    and replaced @author ${user} with hard coded name. Now I can revert this. \n\nJoni"
- id: 68
  author: Anatol Pomozov
  author_email: anatol.pomozov@gmail.com
  author_url: ''
  date: '2006-04-21 12:29:09 +0200'
  date_gmt: '2006-04-21 12:29:09 +0200'
  content: |-
    Hi guys. What you really need is Intellij IDEA :)

    Joking.
- id: 69
  author: Martijn Dashorst
  author_email: dashorst@users.sf.net
  author_url: http://www.jroller.com/page/dashorst/
  date: '2006-04-21 14:00:06 +0200'
  date_gmt: '2006-04-21 14:00:06 +0200'
  content: |-
    I have IntelliJ IDEA, but I find it hard to get working in it. I just don't find the time to properly get used to it unfortunately.

    I definetely think the whole package of IDEA is a better deal, but my investment in using Eclipse is very high.
- id: 70
  author: ''
  author_email: ''
  author_url: ''
  date: '2006-04-21 16:58:28 +0200'
  date_gmt: '2006-04-21 16:58:28 +0200'
  content: "> Define the user.name system property at startup of Eclipse and \n> presto!
    The name of your choosing will always be correct!\n\nHave any plugin that relies
    on user.name being your username, and presto! It will break.\n\n:)"
- id: 57736
  author: Martin
  author_email: nimoth@cs.tu-berlin.de
  author_url: ''
  date: '2009-07-28 07:51:30 +0200'
  date_gmt: '2009-07-28 06:51:30 +0200'
  content: "&gt; Have any plugin that relies on user.name being your username, and
    \r\n&gt; presto! It will break.\r\n\r\nIs that true? Can you name any plugins
    for which this is known?\r\n\r\nThanks"
- id: 57741
  author: Sumin
  author_email: suminb@gmail.com
  author_url: http://blog.sumin.us
  date: '2009-07-31 14:00:46 +0200'
  date_gmt: '2009-07-31 13:00:46 +0200'
  content: Thanks a lot! I'm a Mac user so I had to edit eclipse.ini within the Eclipse.app
    package. Good thing is that the Eclipse.app package is not code signed ;-)
- id: 57850
  author: sergio
  author_email: sergio.acosta@gmail.com
  author_url: ''
  date: '2009-12-21 20:13:39 +0100'
  date_gmt: '2009-12-21 19:13:39 +0100'
  content: "@Sumin:\r\n\r\nThanks, Mac user here. That helped a lot.\r\n\r\nIt's dumb
    that eclipse doesn't offer a simple option in the IDE to set the javadoc user
    name, though."
- id: 61164
  author: Lanoxx
  author_email: lanoxx@gmx.net
  author_url: ''
  date: '2011-10-07 09:45:23 +0200'
  date_gmt: '2011-10-07 08:45:23 +0200'
  content: "Almost two years in and this is still an issue in Eclipse 3.7. Sad! But
    anyway thanks alot for figuring this out.\r\nThe linux location for this depends
    on where you installed eclipse. I have eclipse.ini files at these locations:\r\n/etc/eclipse.ini\r\n/opt/Eclipse3.6/eclipse.ini\r\n/opt/Eclipse3.7/eclipse.ini\r\n/usr/lib/eclipse/eclipse.ini\r\n\r\nA
    simple # locate eclipse.ini should do it if your locate_db is up to date."
---
<p>Of course, this small tip is common knowledge amongst all developers that use <a href="http://eclipse.org">Eclipse</a> as their IDE, but I only recently came across it.</p>
<p>
Eclipse doesn't know your real name, and it doesn't provide a way to configure it in the settings panels. The default behavior of Eclipse when inserting JavaDoc comments in your code is to use the system property <tt>user.name</tt>. This generates code like:</p>
<pre>/**
 * @author dashorst
 */</pre>
<p>
or when working with Eclipse at home:</p>
<pre>/**
 * @author martijn
 */</pre>
<p>
Instead I want it to generate a comment like:</p>
<pre>/**
 * @author Martijn Dashorst
 */</pre>
<p>
Currently I have to go to the author tag and retype the generated name. Now that is not cool. And what I also don't want to do is to change the templates that are provided by Eclipse. So, instead: I altered the <tt>eclipse.ini</tt> file, which you probably already have changed to increase the available memory and have these values:</p>
<pre>-vmargs
-Xms128m
-Xmx512m
-Duser.name=Martijn Dashorst
</pre>
<p>The last parameter is the one that this tip concerns.</p>
<p>
Define the <tt>user.name</tt> system property at startup of Eclipse and presto! The name of your choosing will always be correct!</p>
