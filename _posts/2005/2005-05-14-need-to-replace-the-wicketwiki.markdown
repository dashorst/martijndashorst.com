---
layout: post
status: publish
published: true
title: Need to replace the WicketWiki
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 195
wordpress_url: http://martijndashorst.com/2005/05/14/need-to-replace-the-wicketwiki/
date: '2005-05-14 11:55:07 +0200'
date_gmt: '2005-05-14 11:55:07 +0200'
categories:
- wicket
tags: []
comments: []
---
<p>Due to a recent announcement of the sourceforge.net team saying that all file based programs should use the database services:</p>
<blockquote><p>Group Directories are Read-Only: The project web servers mount project group directories read-only. The following means are available for storing writable data (i.e. for project applications):</p>
<ul>
<li>Place the data in the MySQL database provided to your project. Projects are encouraged to make use of our project database service for application data storage.</li>
<li>Place the data in the /tmp/persistent directory, accessible from and shared between the project shell and web servers. Projects should create their own subdirectory in /tmp/persistent and make frequent backups of the data. We strongly discourage the use of file-writing applications with our services, due to the security implications of our shared web environment. Users of applications in the project web services that require file-writing are strongly encouraged to look for alternatives that can use a MySQL database for data storage instead.</li>
</ul>
</blockquote>
<p>As such we are searching for a replacement of our <a href="http://wicket.sourceforge.net/wiki" title="WicketWiki">Wicket Wiki</a>. There are a few features we need:</p>
<ul>
<li>MySQL backend</li>
<li>User authenticated editing</li>
<li>PHP/Ruby/Perl implemented</li>
</ul>
<p>If anybody knows of an alternative WIki, please leave a message here, or mail the <a href="http://wicket.sourceforge.net/mail-lists.html">Wicket development mailinglist</a>.</p>
