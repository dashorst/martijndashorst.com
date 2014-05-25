---
layout: post
status: publish
published: true
title: Subversion is subzero
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 79
wordpress_url: http://martijndashorst.com/2006/03/19/subversion-is-subzero/
date: '2006-03-19 15:34:16 +0100'
date_gmt: '2006-03-19 15:34:16 +0100'
categories:
- java
tags: []
comments:
- id: 84
  author: kramer
  author_email: kramer@spam.com
  author_url: ''
  date: '2006-03-19 16:38:25 +0100'
  date_gmt: '2006-03-19 16:38:25 +0100'
  content: You don't need a tag at all. You just need the change number of the repository
    and you can completely recreate the source code at that time.
- id: 85
  author: Martijn Dashorst
  author_email: dashorst@users.sf.net
  author_url: http://www.jroller.com/page/dashorst
  date: '2006-03-19 17:13:39 +0100'
  date_gmt: '2006-03-19 17:13:39 +0100'
  content: |-
    Yeah, but that is the same as remembering all revision numbers in CVS. A copy in subversion is much better: it communicates intent, it shows where you can get the sources for a particular release and it is not too much work.

    How should I remember that the build I created for the Wicket 1.2 is 53223? Having a copy with label "WICKET_1_2" gives me a way to retrieve it.
---
<p>As I am in the progress of learning the ropes of subversion, and becoming appalled by the support for subversion in Eclipse when compared to the CVS support, I am learning to like subversion.</p>
<p>
A little gem while releasing <a href="http://wicketframework.org">Wicket 1.2-beta2</a> struck my mind. My previous, CVS era, modus of operandi was to select all my projects in the workspace and tag them at once as "WICKET_1_2_BETA2", so the projects current state would be traceable when a bug emerged.</p>
<p>
To my amazement, this feature doesn't work in <a href="http://www.polarion.org/p_subversive.php">Subversive</a>, probably the best subversion integration currently available for Eclipse. You can't select multiple projects, and tag them as a version. "Ah, well" I thought, "Then I'll do them by hand one at a time". Can you imagine the following scenario, tagging all the projects in my workspace? Here is a list of the projects that need to be tagged:</p>
<ol>
<li>wicket</li>
<li>wicket-extensions</li>
<li>wicket-examples</li>
<li>wicket-quickstart</li>
<li>wicket-spring</li>
<li>wicket-spring-examples</li>
<li>wicket-spring-annot</li>
<li>wicket-spring-annot-examples</li>
<li>wicket-spring-cattr</li>
<li>wicket-spring-cattr-examples</li>
<li>wicket-auth-roles</li>
<li>wicket-auth-roles-examples</li>
</ol>
<p>
That is quite some work when you have to do each project on its own. Especially with the GUI speed of Eclipse including Subversive on OSX. So I tried versioning the Wicket core project and Subversive or sourceforge presented me with <tt>"502 bad gateway"</tt>. So that's a clear no go on the Subversive versioning.</p>
<p>
At this moment I decided to go to my bookshelve and pull out the 'Pragmatic Version Control using Subversion" from the Pragmatic Programmers. And then it struck me: <i>Why didn't I just do a serverside copy of the trunk to a tag</i>. We're working with Subversion now. So I downloaded the OS-X <a href="http://metissian.com/projects/macosx/subversion/">subversion client</a> from <i>Metissian</i>, and installed the package.</p>
<p>
<b>One note</b>: don't forget to add <tt>/usr/local/bin</tt> to your path variable, otherwise you'll keep staring at a command prompt that says: <tt>svn: command not found</tt>.</p>
<p>
From there on it was plain and simple:</p>
<pre>
$ svn --username dashorst -m "Releasing Wicket 1.2-beta2" 
       copy https://svn.sourceforge.net/svnroot/wicket/trunk 
           https://svn.sourceforge.net/svnroot/wicket/tags/WICKET_1_2_BETA2
</pre>
<p>
That was it! Now we are the proud owner of a new tag in subversion, with the name WICKET_1_2_BETA2, and the whole repository state has been reflected in this tag. Now that is something to write about.</p>
<p>
Subversion: though the Eclipse support sucks, it is subzero -> cooler than cool.</p>
