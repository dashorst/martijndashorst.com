---
layout: post
status: publish
published: true
title: 'No Wicket release yet: maven failing on me'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 126
wordpress_url: http://martijndashorst.com/2005/10/05/no-wicket-release-yet-maven-failing-on-me/
date: '2005-10-05 01:36:38 +0200'
date_gmt: '2005-10-05 01:36:38 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>
I don't think I'm able to create the release of Wicket 1.1-rc2 this evening. I'm having trouble with <a href="http://maven.apache.org">Maven 1.1-beta2</a>. Everything worked perfectly last build, but somehow I'm not able to run the 'maven dist' command in order to produce the Wicket distribution. And the reason I stepped up onto the 1.1 wagon was that my previous maven installation (1.0.2) was busted and has been ever since.</p>
<p>
I'll try running it on my Power mac, and hope I'm finished around 1:30am, otherwise I'm off to bed and have to postpone till tomorrow. I'd hate to arrive at the office with an apple symbol engraved in my forehead.</p>
<p>
Note that I don't complain: it is still beta, and I enjoy using Maven. It probably is something <i>I</i> did wrong in customizing my build. For anyone reading this: this is the error I recieve:</p>
<pre>BUILD FAILED
File...... c:\maven-1.1-beta2\cache\maven-xdoc-plugin-1.9.2\plugin.jelly
Element... x:parse
Line...... 122
Column.... -1
Error on line 30381 of document  : Parser has reached the entity expansion limit "64,000" set by the Application. Nested
 exception: Parser has reached the entity expansion limit "64,000" set by the Application.
Total time   : 37 seconds
Finished at  : Wednesday, October 5, 2005 12:36:11 AM CEST
</pre>
<p>
Update: I've confirmed this also happens on Mac OSX. Too bad... I'm hoping for some response on the maven mailinglist. I'll keep everyone informed, and you'll be the first to know when the release has been baked.</p>
