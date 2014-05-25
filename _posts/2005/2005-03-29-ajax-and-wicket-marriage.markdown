---
layout: post
status: publish
published: true
title: Ajax and Wicket Marriage
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 221
wordpress_url: http://martijndashorst.com/2005/03/29/ajax-and-wicket-marriage/
date: '2005-03-29 17:17:34 +0200'
date_gmt: '2005-03-29 17:17:34 +0200'
categories:
- wicket
tags: []
comments: []
---
<p>
We keep getting requests to support <a href="http://www.ajaxian.com">Ajax</a> in the <a href="http://wicket.sf.net">Wicket</a> framework. Apparently, Ajax is <i>HOT</i>, and supporting it will be <i>cool</i>. But should a framework always cater to the latest fad and have it working? What if some <a href="http://eireneh.thorubio.org/dwr/index.html">alternative technology</a> arrives (<a href="http://eireneh.thorubio.org/dwr/index.html">Direct Web Remoting</a>), should we also support that? How will we be able to actually ship the framework? And <a href="http://www.google.com/search?q=Extracting+Ajax+to+an+add-in">should the framework support</a> the latest and hottest, or should it provide the means and extension points, so that others can provide great support for <em>their</em> hottest and coolest thing in <a href="http://www.sf.net/project/wicket-stuff">add-ons</a>?</p>
<p>
We want the support to be <strong>REALLY</strong> good. Not just an afterthought, not just something we slammed into our framework, but good if not perfect. Supporting Ajax means supporting Javascript, and for our 1.0 release, we don't have that perfect, easy to use support. It is on the <a href="http://wicket.sourceforge.net/wiki/doku.php?id=todo">Wicket roadmap</a> for 1.1 and we are going to put some real effort into that <em>after</em> we ship 1.0 and that will be in the coming weeks as we squash our <a href="http://sourceforge.net/tracker/?group_id=119783&amp;atid=684975">bugs</a>.</p>
<p>
Just as the <a href="http://wiki.rubyonrails.com/rails/show/Ajax+Discussion">Ruby on Rails</a> guys, I'm all for creating native support for Javascript in Wicket, and provide the <a href="http://www.ajaxian.com">ajax support</a> as an <a href="http://www.sf.net/projects/wicket-stuff">add-on</a>.</p>
