---
layout: post
status: publish
published: true
title: 'Help wanted: test wicket 1.3 serialization'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 239
wordpress_url: http://martijndashorst.com/blog/2007/02/16/help-wanted-test-wicket-13-serialization/
date: '2007-02-16 09:54:27 +0100'
date_gmt: '2007-02-16 08:54:27 +0100'
categories:
- wicket
- java
- technology
tags: []
comments: []
---
<p><a href="http://chillenious.wordpress.com">Eelco</a> writes on the mailinglist after some (luke warm) discussion on how to test the new custom serialization Johan is building into the next Wicket versions. This is what he wrote:</p>
<blockquote><p>Hi all,</p>
<p>We're (Johan mostly) are experimenting with custom serialization to<br />
see whether we could speed things up a bit (which doesn't mean what we<br />
have now is bad btw).</p>
<p>For anyone working on 1.3: we could use your help testing that<br />
feature. The only thing you need to do is turn it on on your<br />
development machine, by doing this in e.g. your application's class<br />
init method:</p>
<p><code>Objects.setObjectStreamFactory(new wicket.util.io.WicketObjectStreamFactory());</code></p>
<p>And then just report any issues you encounter to this list or the<br />
developers list. Of course, if you have tweaks, test reports etc,<br />
that'd be even cooler.</p>
<p>The default can be set like this:</p>
<p><code>Objects.setObjectStreamFactory(new IObjectStreamFactory.DefaultObjectStreamFactory());</code></p>
<p>which is based on JDK's serialization. If you don't configure<br />
otherwise, that is what is used.</p>
<p>Thanks,</p>
<p>Eelco</p>
</blockquote>
<p>So please help us out here and use the new <code>WicketObjectStreamFactory</code> in your development efforts and create bug reports if/when you find anything wrong.</p>
<p>The promise of this custom serialization is that it will improve the throughput and memory footprint of your Wicket application considerably. So help yourself, your employer and the Wicket community by testing the new serialization.</p>
