---
layout: post
status: publish
published: true
title: Maven repository woes easily solved
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 11
wordpress_url: http://martijndashorst.com/2006/12/09/maven-repository-woes-easily-solved/
date: '2006-12-09 15:34:20 +0100'
date_gmt: '2006-12-09 15:34:20 +0100'
categories:
- java
- maven
tags: []
comments: []
---
<p>Maven 1 users might have discovered this already: the Maven 1 repository at <a href="http://ibiblio.org">ibiblio.org</a> doesn't work with Maven 1 anymore. Some network setting at the ibiblio server was changed, which causes a redirect that the httpclient library used by Maven 1 doesn't know how to follow, and fails.</p>
<p>
Fortunately the fix is <b>easy</b>: put the following setting in your <code>build.properties</code> in your home directory (<code>C:\Documents and Settings\[username]</code>):</p>
<pre>
maven.repo.remote=http://repo1.maven.org/maven
</pre>
<p>and you're back in business.</p>
