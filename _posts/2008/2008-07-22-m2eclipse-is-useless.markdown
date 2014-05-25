---
layout: post
status: publish
published: true
title: m2eclipse is useless
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 387
wordpress_url: http://martijndashorst.com/blog/2008/07/22/m2eclipse-is-useless/
date: '2008-07-22 09:27:28 +0200'
date_gmt: '2008-07-22 08:27:28 +0200'
categories:
- maven
tags: []
comments:
- id: 57099
  author: Mark Phippard
  author_email: markphip@gmail.com
  author_url: ''
  date: '2008-07-22 14:17:33 +0200'
  date_gmt: '2008-07-22 13:17:33 +0200'
  content: "Subclipse does not require you to update after a commit.  It simply had
    a feature that let you know your local folders were out of date with the server.
    \ If you do not know that and you try to rename them, your commit will fail.  It
    was always a preference to turn this off and in the current release it is off
    by default.\r\n\r\nI am virtually certain that m2eclipse is not hardcoded to Subclipse.
    \ I recall that it even supports Subversive.  Are you sure this is not a case
    of needing to expand their update site and deselect their Subclipse integration
    plugin?  We have this problem all the time with Subclipse and users thinking they
    have to install Mylyn and Buckminster to use Subclipse.  We simply host plugins
    that integrate with those tools -- if you have them installed."
- id: 57100
  author: Martin
  author_email: funkattack@arcor.de
  author_url: ''
  date: '2008-07-22 17:58:53 +0200'
  date_gmt: '2008-07-22 16:58:53 +0200'
  content: "Little research on nabble I came up with this.\r\nhttp://www.nabble.com/m2eclipse-and-subversive-td16045807.html\r\nWonder
    were that code went?\r\n\r\nmf"
- id: 57102
  author: Toby
  author_email: toby@telegraphics.com.au
  author_url: http://telegraphics.com.au/sw/
  date: '2008-07-22 23:53:42 +0200'
  date_gmt: '2008-07-22 22:53:42 +0200'
  content: Why do you have to update after a commit? (I use Subclipse all the time.)
- id: 57176
  author: Mike Wilson
  author_email: mikewse@hotmail.com
  author_url: ''
  date: '2008-08-23 17:47:05 +0200'
  date_gmt: '2008-08-23 16:47:05 +0200'
  content: "&gt; Wonder were that code went?\r\n\r\nhttp://docs.codehaus.org/display/M2ECLIPSE/Integration+with+Subversive"
- id: 57188
  author: PB
  author_email: pbbr@trashmail.net
  author_url: ''
  date: '2008-08-27 20:48:14 +0200'
  date_gmt: '2008-08-27 19:48:14 +0200'
  content: The complete ignorance ;-). As Mark Phippard says the updating in subclipse
    is an option. And subversive has the exact same option, only it is turned of by
    default. And no, m2eclipse has no hardcoded dependency on subclipse, I use it
    without sublcipse.
---
<p>I've installed Subversive as my Eclipse subversion connector, and don't like Subclipse for one bit (having to update after a commit is weird for a workflow). The decision of m2eclipse to <strong>hardcode</strong> a dependency on Subclipse baffles me. Now nobody is able to use m2eclipse with git, cvs or any other SCM. This renders the m2eclipse support complete and utterly useless. Fail.</p>
