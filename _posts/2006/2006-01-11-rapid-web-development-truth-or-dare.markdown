---
layout: post
status: publish
published: true
title: 'Rapid Web Development: truth or dare?'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 108
wordpress_url: http://martijndashorst.com/2006/01/11/rapid-web-development-truth-or-dare/
date: '2006-01-11 21:43:35 +0100'
date_gmt: '2006-01-11 21:43:35 +0100'
categories:
- wicket
- java
tags: []
comments:
- id: 124
  author: Jacob Hookom
  author_email: ''
  author_url: ''
  date: '2006-01-11 23:03:41 +0100'
  date_gmt: '2006-01-11 23:03:41 +0100'
  content: I guess I'm somewhat confused by the constant 'no-xml' stuff-- especially
    when A) You still are producing equivable lengthed HTML files (w/o framework tags)
    and B) You have an equally long Java class to support the page.  While I do enjoy
    the type safety, I think the better solution for Wickett would be to produce more
    robust 'components' instead of just persistence helper objects.  Rick Hightower's
    blog has an example of taking a simple entity and a single component tag to produce
    complete forms on the page for persistence.
- id: 125
  author: n8han
  author_email: ''
  author_url: http://technically.us/n8
  date: '2006-01-12 23:49:29 +0100'
  date_gmt: '2006-01-12 23:49:29 +0100'
  content: |-
    People constantly make fun of XML because it has constantly been a pain in our asses for the past five years. HTML templates in Wicket I can edit and see results in immediately. Same with Java sources. With XML configured web frameworks, we're all used to this incredibly unproductive cycle of editing XML, starting a server, seeing XML syntax or logical errors, cursing, trying again...

    As for form components (robust or otherwise) talking to DBs in Wicket, that's just not the way things work there. Data moves from components to models, and from there -- with Databinder anyway -- straight to the DB.
- id: 126
  author: ali
  author_email: a_sharghi@hotmail.com
  author_url: ''
  date: '2006-01-13 01:25:44 +0100'
  date_gmt: '2006-01-13 01:25:44 +0100'
  content: "feed of your comments can add to my feed reader ,\nplease see <a href=\"http://feedvalidator.org/check.cgi?url=http%3a%2f%2fjroller.com%2fpage%2fdashorst%2fcomments\">validate</a>\n\n==========\nSorry\n\nThis
    feed does not validate.\n\nFeeds should not be served with the \"text/html; charset=utf-8\"
    media type [help]\n\n\nline 3, column 0: Undefined root element: comments [help]\n\n<comments
    xmlns=\"http://www.joehewitt.com/content/blog.dtd\"\n\nSource: http://jroller.com/page/dashorst/comments\n<?xml
    version=\"1.0\" encoding=\"UTF-8\"?>\n \n<comments xmlns=\"http://www.joehewitt.com/content/blog.dtd\"\n
    \  entryid=\"$entry.Id\">\n</comments>"
---
<p><a href="http://en.wikipedia.org/wiki/User:Nathan_Hamblen">Nathan Hamblen</a> has created a <a href="http://databinder.net/">databinding package</a> for <a href="http://wicket.sf.net">Wicket</a> and <a href="http://www.hibernate.org">Hibernate</a>. It certainly is worth checking out, as it will allow you to:</p>
<blockquote><p>start using the best programming technologies today, without fussing over their configuration.</p></blockquote>
<p>Nathan writes:</p>
<blockquote><p>Your job is to feed annotated data classes to Databinder, then write your view classes and HTML templates to render them in a browser. (You can take ?fastest XML typist in the West? off your resume now.)</p></blockquote>
<p>When I ask rapid web development: truth or dare? Nathan takes the <a href="http://databinder.net/directory/app?bookmarkablePage=example.ListAndEdit">dare</a>!</p>
