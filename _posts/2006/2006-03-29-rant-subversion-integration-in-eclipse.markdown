---
layout: post
status: publish
published: true
title: 'Rant: Subversion integration in Eclipse'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 69
wordpress_url: http://martijndashorst.com/2006/03/29/rant-subversion-integration-in-eclipse/
date: '2006-03-29 17:37:45 +0200'
date_gmt: '2006-03-29 17:37:45 +0200'
categories:
- java
tags: []
comments:
- id: 80
  author: Mark Phippard
  author_email: markphip@tigris.org
  author_url: http://subclipse.tigris.org/
  date: '2006-03-29 18:36:13 +0200'
  date_gmt: '2006-03-29 18:36:13 +0200'
  content: |-
    It sounds like your original checkout failed at some point.  So some or all of the files are in your workspace on disk, but since the process failed the Eclipse project was not established.  Just delete the files from your disk before trying the checkout again so that the checkout process does not have to do it.

    Subversion will not checkout on top of an existing folder structure which is why it has to do this.
---
<p>Why is the current state of subversion integration into Eclipse so lousy? Subversion is a viable platform for quite some time now (I know I have been contemplating moving to SVN 2 years ago).</p>
<p>
<a href="http://subclipse.tigris.org">Subclipse</a> checkout of our Wicket project doesn't show up in the package explorer, I had exception reports in Eclipse, a checkout that didn't do jack. Now I try to check out the wicket project, but still I get strange hangs in Eclipse. For some reason Subclipse thinks that my wicket project is still in my workspace, and wants to delete the directory. I let it do that, and then it starts deleting each file where it takes 15 seconds for it to discover that the file isn't there. This is killing me!</p>
<p>
The fairly new <a href="http://www.polarion.org/p_subversive.php">Subversive</a> plugin also does a bad job of working as a stable plugin. Granted they are in development mode, but why can't I compare my current version of a file with a previous revision, <b>WITHOUT</b> eclipse hanging itself up the trees? Why do I have to <i>choose</i> the revision in a <strong>MODAL dialog</strong>, instead of the CVS view?</p>
<p>
Also, subversion really is <b>DOG SLOW</b> when browsing the repository on sourceforge.</p>
<p>
I'm shocked that Eclipse, the most used and popular IDE doesn't integrate with Subversion the way it does with CVS. It is appalling.</p>
