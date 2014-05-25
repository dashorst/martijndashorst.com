---
layout: post
status: publish
published: true
title: Pages in iWork'08 not very workable
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 305
wordpress_url: http://martijndashorst.com/blog/2007/09/27/pages-in-iwork08-not-very-workable/
date: '2007-09-27 14:53:27 +0200'
date_gmt: '2007-09-27 13:53:27 +0200'
categories:
- os x
tags: []
comments:
- id: 13061
  author: n8han
  author_email: nathan@technically.us
  author_url: http://technically.us/code
  date: '2007-09-27 15:59:01 +0200'
  date_gmt: '2007-09-27 14:59:01 +0200'
  content: You didn't try to open Wicket in Action with it, did you?
- id: 13063
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-09-27 16:29:55 +0200'
  date_gmt: '2007-09-27 15:29:55 +0200'
  content: Both Eelco and I write Wicket in Action using Pages. It worked pretty well
    with iWork'06, though the Word export of '06 didn't work well (all pictures were
    black).
- id: 13064
  author: John Patterson
  author_email: jdp2000@gmail.com
  author_url: ''
  date: '2007-09-27 16:34:34 +0200'
  date_gmt: '2007-09-27 15:34:34 +0200'
  content: At least it looks pretty.
- id: 13072
  author: Iman Rahmatizadeh
  author_email: iman.rahmatizadeh@gmail.com
  author_url: ''
  date: '2007-09-27 20:04:30 +0200'
  date_gmt: '2007-09-27 19:04:30 +0200'
  content: Wow 471 GB !! How many pages has Wicket In Action ?! ;-)
- id: 13073
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-09-27 20:08:24 +0200'
  date_gmt: '2007-09-27 19:08:24 +0200'
  content: "We are not sure yet, but the document in question has about 32 pages (one
    chapter)\r\n\r\n(I will also adjust the number to MB -> my mac book pro can only
    address about 2GB before smoke comes out of it)"
- id: 13078
  author: n8han
  author_email: nathan@technically.us
  author_url: http://technically.us/code
  date: '2007-09-27 22:05:07 +0200'
  date_gmt: '2007-09-27 21:05:07 +0200'
  content: "From what I've heard pretty much all word processing (do we still call
    it that?) software disappoints when it comes to book writing. That is, anything
    pushing 100 pages. Word fails in certain ways, but enough people have used it
    for books over the years that it's been forced to cooperate. Pages probably has
    a way to go, starting with the programmers never daring to test its limits. ;)\r\n\r\nAnd
    then supposedly the best thing to use is TeX or LaTeX or some weirdly capitalized
    name for a text format that sounds complicated but in the end is probably worth
    learning. Personally I would start off trying to write in Textile or Markdown,
    see if that hits a wall. I haven't really used a word processor in years."
- id: 13080
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-09-27 22:23:14 +0200'
  date_gmt: '2007-09-27 21:23:14 +0200'
  content: "We actually started out using DocBook, but that is really impossible to
    write without a decent wysiwyg editor. Nothing open source is available that supports
    DocBook in any workable way.\r\n\r\nNext we tried open office, but that was slow
    to work with, and images are not very well supported (they copied that from Word).
    So we settled on Pages and that hasn't been disappointing until the recent version.\r\n\r\nI've
    used latex for my master thesis and I'd love to use that for writing, except for
    the obvious problem of just plain word processing. The biggest hurdle is that
    it is not compatible with publishers and editors that want to use Word's change
    tracking for feedback."
- id: 13086
  author: Matej Knopp
  author_email: matej.knopp@gmail.com
  author_url: ''
  date: '2007-09-28 00:16:24 +0200'
  date_gmt: '2007-09-27 23:16:24 +0200'
  content: I remember using Mellel (http://www.redlers.com/index.html). The huge advantage
    over everything else in OS X was that I was able to paste a Omnigraffle drawing
    as vector (i guess that's also possible with Pages though, but not with Open office
    or MS Office). Compared to pages Mellel uses subpixel antialiasing, which is an
    obvious difference (at least for me, maybe I'm antialiasing freak). What I was
    kinda missing were references inside document, I know they were working for it
    but I'm not sure it's implemented yet.
- id: 13099
  author: Eelco Hillenius
  author_email: eelco.hillenius@gmail.com
  author_url: http://chillenious.wordpress.com/
  date: '2007-09-28 03:09:44 +0200'
  date_gmt: '2007-09-28 02:09:44 +0200'
  content: I have memory problems with Pages, but if I shut it down once a day it
    isn't too bad for me.
- id: 13115
  author: A Wicket Diary&raquo; Blog Archive &raquo; New update for iWork&#8217;08
    available
  author_email: ''
  author_url: http://martijndashorst.com/blog/2007/09/27/new-update-for-iwork08-available/
  date: '2007-09-28 06:48:31 +0200'
  date_gmt: '2007-09-28 05:48:31 +0200'
  content: "[...] I just wrote about my troubles with Pages and trying to write for
    Wicket in Action. Apple support is really quick: my blog entry was not up for
    longer than 8 hours, and they apparently already have fixed it! About Pages 3.0.1
    This update primarily addresses issues with change tracking and performance. [...]"
---
<p>The new Pages in iWork'08 seems to have some uncomfortable bugs: it claims quite a lot of memory, hogs the CPU, and often freezes my whole OS X GUI. To put it mildly: I have to restart Pages several times a day to make it usable.</p>
<p>It looks like the memory management of Pages 3 is b0rked. While I'm typing this, Pages is trying to shut down (now for over a minute!). It is using one core of my CoreDuo, and about 70-80% of the time it is spending time in the kernel, increasing the real memory usage (now 471 MB).</p>
<p>The shutdown has now finished, in over 5 minutes!!! AAAARGH.</p>
