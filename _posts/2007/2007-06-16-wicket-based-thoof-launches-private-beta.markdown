---
layout: post
status: publish
published: true
title: Wicket based Thoof launches private beta
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 267
wordpress_url: http://martijndashorst.com/blog/2007/06/16/wicket-based-thoof-launches-private-beta/
date: '2007-06-16 14:22:39 +0200'
date_gmt: '2007-06-16 13:22:39 +0200'
categories:
- wicket
- technology
- hibernate
tags: []
comments:
- id: 4269
  author: G.
  author_email: iguane18@yahoo.fr
  author_url: ''
  date: '2007-06-18 09:05:16 +0200'
  date_gmt: '2007-06-18 08:05:16 +0200'
  content: 'almost solid : thoof.com/home : "Internal Error..." This happends to the
    best! ;-)'
- id: 4270
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-06-18 09:11:25 +0200'
  date_gmt: '2007-06-18 08:11:25 +0200'
  content: "heh... this happened to us as well, but we had an e-mail appender for
    exceptions... recursive message spam killed our exchange server.\r\n\r\nI like
    the recursive error though :)"
---
<p>The veil has been lifted. <span><a href="http://thoof.com">Thoof</a></span> is now officially in private beta (and I got to play around with it a bit). Given that the famous (from <span><a href="http://www.revver.com/">Revver</a></span> and other successful website) entrepreneur <a href="http://locut.us/blog/">Ian Clarke</a> is behind this effort and that <a href="http://web.mac.com/jonathan.locke/iWeb/JonathanLocke/Blog/Blog.html">Jonathan Locke</a> is one of the architects behind the site, the foundation is solid.</p>
<p style="text-align:center">
<img id="image269" src="http://martijndashorst.com/blog/blog/wp-content/uploads/2007/06/thoof_1.png" alt="Thoof" /></p>
<p><span>VentureBeat</span> <a href="http://venturebeat.com/2007/06/15/thoof-a-news-ranking-site-that-wants-to-serve-the-masses">writes</a>:</p>
<blockquote><p>Like <span>Digg</span>, <span>Thoof</span> provides a synopsis of articles on its home page â€”this includes headline, brief summary, and tags to designate <span>topic matter</span>. It then provides a link to the article, and sends the reader <span>to the</span> original source.</p>
<p>Thatâ€™s where the similarities with <span>Digg</span> end. It <span>doesn</span>â€™t let <span>otherreaders</span> rank the articles for you. Rather, it offers articles to <span>youbased</span> on what knows about you, such as <span>IP</span> address (which <span>providesgeographical</span> location), the browser you use, your operating system <span>andthe</span> site you were on when you clicked through to <span>Thoof</span> â€” all of <span>whichoffer</span> subtle clues about you. Then, additionally, as you <span>searcharticles</span>, it tracks the tags of the articles you read. Finally, it <span>maysoon</span> begin asking you a random question from time to time, to <span>gathermore</span> information.</p>
</blockquote>
<p><strong>Thoof</strong> was also <a href="http://www.techcrunch.com/2007/06/15/revver-founder-launches-thoof-personalized-news-service/">covered</a> by Michael Arrington's <a href="http://techcrunch.com">TechCrunch</a> and he seems sceptical, as most of the previous attempts (SearchFox, Findory and more) did not succeed or even ended up in the <em>deadpool</em>. Many of the comments seem to share the sentiment. However, Ian Clarke <a href="http://www.techcrunch.com/2007/06/15/revver-founder-launches-thoof-personalized-news-service/#comment-1430525">explained more</a> of the new selection algorithm behind the site, and if it works, I predict a bright future. In the private beta run I already saw a couple of links I liked (and I hadn't even clicked!).</p>
<p>Now this may look to the regular reader that I'm promoting a web site because a friend is working on it, but there's more to it: it is <a href="http://wicketframework.org">Wicket</a> based (which is one of the reasons Jonathan was asked to come aboard I presume). If it is a successful endeavor (and I trust Ian Clarke to be correct here), then it may become the biggest website running Wicket.</p>
<p>I like the unobtrusive Ajax functionality they built in: when you click the header of a story, the browser sends a notification to the server using Ajax, and then replaces the story panel with a 'this story has been read' variant). In the mean time the news article has been loaded in a new window.</p>
<p style="text-align:center"><img id="image270" src="http://martijndashorst.com/blog/blog/wp-content/uploads/2007/06/thoof_2.png" alt="Read/unread article" /></p>
<p>If you have some Wicket experience, you can see how they construct their pages based on the markup: <code>ListView</code> or <code>Repeaters</code>, and <code>Panels</code> and <code>Behaviors</code> have been put to good use. I expect there will be some tweaking going on (removing superfluous span tags, or too <span>enthousiastic</span> use of Ajax component replacement) but on the whole it really looks great.</p>
<p>All in all, a very exiting time for <strong>Thoof</strong> and its creators, and I hope they succeed.</p>
