---
layout: post
status: publish
published: true
title: Getting Maven 2 to work
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 205
wordpress_url: http://martijndashorst.com/2005/04/27/getting-maven-2-to-work/
date: '2005-04-27 00:20:10 +0200'
date_gmt: '2005-04-27 00:20:10 +0200'
categories:
- maven
tags: []
comments: []
---
<p>In my previous post, I mentioned that I was going to run maven 2, continuum, fedora core 3, IBM JDK 1.4, etc. on an obsolete laptop (Toshiba satelite pro 4200). I use this 4 year old laptop mainly because of the following reasons:</p>
<ul>
<li>I have trouble letting hardware go unused</li>
<li><a href="http://wicket.sourceforge.net" title="Wicket">Wicket</a> needs a continuous integration machine</li>
<li>I want to test maven 2, but don't want to do this on my own boxes, it might <em>break</em> stuff</li>
<li>I heard from co-workers that the IBM JDK is faster on Linux than the Sun JDK</li>
<li>I like a challenge</li>
<li>more things I can't think of right now</li>
</ul>
<p>After downloading the maven 2 distribution, I unzipped the archive in my home directory and <tt>chmod +x */bin/m2</tt> made sure that the m2 script is executable. I also made sure <tt>$JAVA_HOME</tt> is set to my IBM JDK installation (for some reason in <tt>/opt</tt> :-S).</p>
<p>According to the maven 2 website, I can issue <tt>m2 --version</tt> in order to verify the installation:</p>
<pre>[dashorst@localhost maven2-test]$ ~/maven-2.0-alpha-1/bin/m2 --version
Maven version: 2.0-alpha-1
</pre>
<p>
So far so good... Next in the getting started guide is creating your own project:</p>
<blockquote><p>m2 archetype:create -DgroupId=com.mycompany.app -DartifactId=my-app</p></blockquote>
<p>Alas, this doesn't work, as apparently, a transitive dependency cannot be resolved, as it isn't in the ibiblio repository... It appears to be the velocity 1.4 pom (to be found in your local repository, most probably in a subdir called <tt>.m2/repository</tt> in your home directory). Removing this dependency from the velocity 1.4 pom made sure the project generation works. Now I have my first Maven 2 project!</p>
<p>First findings:</p>
<ul>
<li>I don't find it particularly <em>fast</em>, but that can be attributed to several factors: slow laptop (<strong>very likely</strong>, slow operating system (not likely), slow JDK (possibility)</li>
<li>I don't like the fact I need to download some (unknown!) jdbc jar, or edit the velocity pom in order to pass the 'getting started'</li>
<li>The current structure is still a blur to me, I don't know how to run the unittests</li>
</ul>
<p>As my experience with maven 2 will grown, this blog will be filled with more findings on this subject! Keep posted...</p>
