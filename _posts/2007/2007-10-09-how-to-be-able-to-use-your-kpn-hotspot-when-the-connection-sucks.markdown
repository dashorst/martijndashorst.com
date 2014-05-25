---
layout: post
status: publish
published: true
title: How to be able to use your KPN hotspot when the connection sucks
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 311
wordpress_url: http://martijndashorst.com/blog/2007/10/09/how-to-be-able-to-use-your-kpn-hotspot-when-the-connection-sucks/
date: '2007-10-09 11:12:53 +0200'
date_gmt: '2007-10-09 10:12:53 +0200'
categories:
- technology
tags: []
comments:
- id: 14197
  author: Odi
  author_email: odi@odi.ch
  author_url: http://www.odi.ch
  date: '2007-10-09 13:40:12 +0200'
  date_gmt: '2007-10-09 12:40:12 +0200'
  content: Isn't a router supposed to notify the sender with ICMP to reduce its packet
    size (Fragmentation Needed)? See http://en.wikipedia.org/wiki/Path_MTU_discovery.
    Maybe you or their network are filtering out too much ICMP.
- id: 14252
  author: links for 2007-10-09 &laquo; Object neo = neo Object
  author_email: ''
  author_url: http://neobject.wordpress.com/2007/10/09/links-for-2007-10-09/
  date: '2007-10-10 00:25:02 +0200'
  date_gmt: '2007-10-09 23:25:02 +0200'
  content: "[...] Follow any comments here with the RSS feed for this post. Post a
    comment or leave a trackback: Trackback URL.    &laquo; linksfor&nbsp;2007-10-08
    [...]"
---
<p>The connection here is awful, I experience almost 100% packet loss when trying to connect to the internet using the KPN Hotspot. And it costs me about 45 euros to get the right of not being able to use internet. This is highly frustrating, as even complaints don't get through.</p>
<p>Combine this fact that I have a Mac, which is of course not supported by the KPN, so I <em>could</em> call the support desk, but they would directly tell me that I have an unsupported platform and that I should go make love to myself.</p>
<p>Fortunately one of our readers on the wicket development list was smart enough to mention the TLA 'MTU'. This sparked me to go and see how pinging would work out. So I set up a ping to the dutch news site "nu.nl" and saw that all 64 byte messages came through (though with about 1-10% packet loss). When I set the size to 2048, no reply came back. Setting the size to 1024 (or rather 1016 to compensate for the additional 8 bytes that is added to the ping message), I still got a 1-10% packet loss, but I got replies back.</p>
<p>Browsing through the man pages of <tt>ifconfig</tt> gave me the option to modify the MTU of my wireless connection:</p>
<pre>sudo ifconfig en1 mtu 1024</pre>
<p>This sets my wireless network to broadcast 1024 sized packages instead of 1500. And immediately everything started to work again.</p>
<p>So the recipe to get your wireless connection to work is to try pinging a known website with different package sizes and see which one works best. Then setting that on your wireless connection.</p>
