---
layout: post
status: publish
published: true
title: Updating your maven2 plugins to new releases
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 51
wordpress_url: http://martijndashorst.com/2006/05/23/updating-your-maven2-plugins-to-new-releases/
date: '2006-05-23 22:18:58 +0200'
date_gmt: '2006-05-23 22:18:58 +0200'
categories:
- java
- maven
tags: []
comments:
- id: 57
  author: Geoffrey De Smet
  author_email: ''
  author_url: ''
  date: '2006-05-24 10:04:07 +0200'
  date_gmt: '2006-05-24 10:04:07 +0200'
  content: |-
    The site plugin is still considered beta (latest is beta-5), so they break backwards compatiblity on it as they see fit.
    The navigation.xml structure has changed from beta 4 to 5, to support skins and inheritance.

    Still, I 'd recommend any team using maven to lock down their plugin versions, so one guy can try out new plugin version and they appear and commit it to all if it works.
---
<p>Whilst building our final release, I wanted to upgrade the <a href="http://maven.apache.org/plugins/maven-assembly-plugin">maven assembly plugin</a> because currently it always appends <tt>-bin</tt> to the distribution. As our packages always include both source and binary in the same zip file, the <tt>-bin</tt> is not correct. The 2.1 version of this plugin fixes this with a setting.</p>
<p>
The biggest challenge is finding out <em>how to update your maven plugins, <strong>without having to specify the version in your pom</strong></em>. As you may notice, I have scourged the maven documentation site and wasn't able to find it within 5 minutes. So to save you the trouble of having to go through this yourself, here's how you update your plugins to use the newest released versions:</p>
<p><pre>mvn -U somegoal</pre>
<p>
Where you substitute the 'somegoal' string with a goal of your liking. The documentation doesn't state wether the goal you supply has any relationship to the plugins that get updated. I have my new version of the assembly plugin, so I'm a happy camper again. On with releasing 1.2 final!</p>
<p>
<b>UPDATE</b> OK, I've celebrated too early. The update also 'fixed' bugs in other plugins, and now my carefully constructed velocity template for our website doesn't work anymore. AARGH.</p>
<p>
And <em>WORST OF ALL</em> somehow now my Wicket homepage is called 'Maven - Home'. WTF?</p>
<p>
Apparently, the 'name' attribute of the 'project' tag in the site-descriptor is now actually used, where it previously wasn't.</p>
