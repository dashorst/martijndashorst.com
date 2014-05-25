---
layout: post
status: publish
published: true
title: Switching from Sourceforge.net CVS to SVN
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 84
wordpress_url: http://martijndashorst.com/2006/03/11/switching-from-sourceforgenet-cvs-to-svn/
date: '2006-03-11 18:54:00 +0100'
date_gmt: '2006-03-11 18:54:00 +0100'
categories:
- wicket
- java
tags: []
comments: []
---
<p>As mentioned earlier on this blog, <a href="http://wicketframework.org">Wicket</a> is moving its repository from CVS to subversion. Here's a small entry on how we did the conversion.</p>
<p>
First we tried the automatic conversion utility offered by sourceforge, but that borked with an unexplained error, insisting that we use the cvs2svn utility.</p>
<p>
I downloaded the CVS tarball, to discover that it was a very old copy dating from January 24th 2006. No matter, we just converted the repository and constructed a testing environment for our repository. This would give us an idea if it would work or not. And the preliminary tests suggest this would work. The waiting has begun for a fresh CVS tarball.</p>
<p>
Yesterday I requested the sourceforge support staff to make a fresh tarball so that we can go forward with the conversion. Almost immediately they responded by providing us with the new tarball. Unfortunately I wasn't able to download the file until a couple of hours ago.</p>
<p>
I converted the repository on my local power mac. cvs2svn gave two errors:</p>
<ol>
<li>ERROR: A CVS repository cannot contain both wicket/wicket/wicket.ipr,v and wicket/wicket/Attic/wicket.ipr,v</li>
<li>ERROR: The following symbols are tags in some files and branches in others.<br />
Use --force-tag, --force-branch and/or --exclude to resolve the symbols.<br />
    'WICKET_1_1' is a tag in 117 files, a branch in 1646 files and has commits in 91 files.</li>
</ol>
<p>
the first error was resolved by removing the file from the Attic. The second by forcing the branch.</p>
<pre>
cvs2svn --username=CVS2SVN --dump-only --force-branch=WICKET_1_1 wicket
... snip ...
cvs2svn Statistics:
------------------
Total CVS Files:              4951
Total CVS Revisions:         22762
Total Unique Tags:              92
Total Unique Branches:          10
CVS Repos Size in KB:       127077
Total SVN Commits:            4854
First Revision Date:    Tue Sep 21 17:10:53 2004
Last Revision Date:     Fri Mar 10 11:49:13 2006
------------------
Timings:
------------------
pass 1:    27 seconds
pass 2:     4 seconds
pass 3:     0 seconds
pass 4:     7 seconds
pass 5:    21 seconds
pass 6:     2 seconds
pass 7:     1 second
pass 8:   662 seconds
total:    728 seconds
</pre>
<p>
I am uploading the repository as I write, and I'll import the repository shortly.</p>
