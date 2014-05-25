---
layout: post
status: publish
published: true
title: Ganymede Mylyn Mantis woes
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 385
wordpress_url: http://martijndashorst.com/blog/2008/07/17/ganymede-mylyn-mantis-woes/
date: '2008-07-17 17:30:27 +0200'
date_gmt: '2008-07-17 16:30:27 +0200'
categories:
- technology
tags: []
comments:
- id: 57085
  author: Robert Munteanu
  author_email: robert.munteanu@gmail.com
  author_url: ''
  date: '2008-07-17 18:57:37 +0200'
  date_gmt: '2008-07-17 17:57:37 +0200'
  content: "Hi Martin,\r\n\r\nThe Ganymede version of the Mantis-Mylyn connector (
    http://mylyn-mantis.wiki.sourceforge.net/ ) is in beta stage right now, with known
    issues.\r\n\r\nIf you have specific problems to report, please visit the bug tracker
    ( http://sourceforge.net/tracker/?group_id=189858&amp;atid=931013 ) and let us
    know.\r\n\r\nIf you don't depend on Mylyn 3.0 , you can always install Mylyn 2.3.2
    from http://www.eclipse.org/mylyn/downloads/ and use our stable version ofthe
    connector.\r\n\r\nRobert"
- id: 57233
  author: Jeremy
  author_email: nowayareyougetting@myemail.com
  author_url: ''
  date: '2008-09-08 18:13:27 +0200'
  date_gmt: '2008-09-08 17:13:27 +0200'
  content: "When I finally got around to installing Ganymede, I discovered what you
    have already found: that Ganymede was released way before several key Eclipse
    extensions, such as Mylyn, were ready for it.  And I'm not even using Mantis!
    \ I use Mylyn with Bugzilla, and it's buggy as hell in Ganymede (I literally had
    to uninstall it and go back to the 2.3.2 version as Robert suggested, because
    I couldn't run for more than an hour with the current version).\r\n\r\nIt's amazing
    that Eclipse is as good as it is given what terrible project planning it has."
- id: 57532
  author: Peter Thung
  author_email: peter.thung@navy.mil
  author_url: ''
  date: '2009-04-08 17:21:16 +0200'
  date_gmt: '2009-04-08 16:21:16 +0200'
  content: "I tried the link.\r\nIf you have specific problems to report, please visit
    the bug tracker ( http://sourceforge.net/tracker/?group_id=189858&amp;atid=931013
    ) and let us know.\r\n\r\nto report specific problems, but it says the tracker
    has been disabled for that group."
---
<p>Working with the new Eclipse Ganymede for a while now, and on my Mac it is worthwhile: faster and more stable. Except for Mylyn/Mantis. Mylyn is a resource hog, and the mantis connector doesn't want to store my updates to tasks in our mantis installation. I synchronize my ass off, but no f-ing way that the carefully crafted status in my workspace is sync'd with our tracker.</p>
<p>
	Gawd... I hate these halfbaked solutions.</p>
