---
layout: post
status: publish
published: true
title: Spotlight goes out for Maven
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 41
wordpress_url: http://martijndashorst.com/2006/06/30/spotlight-goes-out-for-maven/
date: '2006-06-30 21:41:03 +0200'
date_gmt: '2006-06-30 21:41:03 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 41
  author: Rob
  author_email: ''
  author_url: ''
  date: '2006-06-30 22:29:56 +0200'
  date_gmt: '2006-06-30 22:29:56 +0200'
  content: "Wow, what a nuisance. So every target dir of every project should be configured.
    The age of agent-based intelligent behavior beckons here; the OS should be able
    to either learn what is transitive or let you provide some kind of mask. \n\n(Part
    of the reason I say this is that having it index the java parts of the workspace
    is not a bad idea...)."
- id: 42
  author: Martijn Dashorst
  author_email: dashorst@users.sourceforge.net
  author_url: http://jroller.com/page/dashorst
  date: '2006-07-03 10:30:05 +0200'
  date_gmt: '2006-07-03 10:30:05 +0200'
  content: |-
    Hmm, that is a matter of preference. I think my IDE is much better suited for indexing and searching for Java related files than a generic searching tool like spotlight. I typically only search for Java files/classes when I'm in a development process, and as such working inside an IDE.

    Therefore I don't mind not having spotlight index my workspace.
---
<p>For the Wicket project we use <a href="http://maven.apache.org">Maven</a> as a build tool. Today I was building a new release candidate for the 1.2.1 Wicket branch, and I noticed that my MacBookPro was having a difficult time building it.</p>
<p>
Looking in the activity monitor, I saw some weird process claiming half my CPU time, thus greatly exercising my CPU. This appeared to be the Mac OS-X spotlight importer. Googling for the process I found a way to shut that process off for a particular directory, so I told Spotlight *NOT* to index my (Java) workspace. This should be a great improvement in performance.</p>
<p>
You can tell spotlight to stop indexing particular folders in the settings preference panel for spotlight, on the tab for privacy. Just drag your folder to the list you don't want to be indexed.</p>
