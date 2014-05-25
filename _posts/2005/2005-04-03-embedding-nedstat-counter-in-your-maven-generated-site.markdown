---
layout: post
status: publish
published: true
title: Embedding NedStat counter in your maven generated site
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 220
wordpress_url: http://martijndashorst.com/2005/04/03/embedding-nedstat-counter-in-your-maven-generated-site/
date: '2005-04-03 16:21:07 +0200'
date_gmt: '2005-04-03 16:21:07 +0200'
categories:
- maven
tags: []
comments: []
---
<p>
It is really a shame that <a href="http://www.sf.net">SourceForge.net</a> has <a href="http://sourceforge.net/docman/display_doc.php?group_id=1&amp;docid=2352">disabled</a> their <a href="http://sourceforge.net/project/stats/?group_id=119783#stats_notice">statistics service</a>. It would be nice to see what kind of effect creating a release has on your downloads. Just as we are planning to release our <a href="http://www.jroller.com/page/JonathanLocke/20050402#rc1_status">first release candidate</a> we <em>really</em> would like to see some notion about whether the release makes an impression.</p>
<p>
In order to be able to monitor some activity on the <a href="http://wicket.sf.net">Wicket project</a> I've installed a <a href="www.nedstat.com">nedstat</a> counter. As usual, it is not too trivial to embed the counter in a <a href="http://maven.apache.org">maven</a> build. The JavaScript used by the <a href="http://www.nedstatbasic.net/stats?ADUqkAqz13yUdWzu82RZ+ob42qQg">nedstat counter</a> was eaten by the XML processor used by <a href="http://maven.apache.org/reference/plugins/xdoc">Maven's XDoc plugin</a>.</p>
<p>According to the <a href="http://en.wikipedia.org/wiki/JavaScript#Environment">Wikipedia</a> the JavaScript should be configured as follows inside XHTML documents (XDoc documents are XML, so they are treated the same)</p>
<pre>&lt;script type="text/javascript"&gt;
//&lt;![CDATA[
   nedstat script goes here
//]]&gt;
&lt;/script&gt;</pre>
<p>And this works as advertized! Be careful to only put the call to the nedstatbasic function inside this piece of markup.</p>
