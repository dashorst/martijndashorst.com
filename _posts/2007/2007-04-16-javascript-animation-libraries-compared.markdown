---
layout: post
status: publish
published: true
title: JavaScript animation libraries compared
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 252
wordpress_url: http://martijndashorst.com/blog/2007/04/16/javascript-animation-libraries-compared/
date: '2007-04-16 22:43:21 +0200'
date_gmt: '2007-04-16 21:43:21 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 1508
  author: RÃ¼diger Schulz
  author_email: rueschu@googlemail.com
  author_url: http://www.2rue.de
  date: '2007-04-17 10:01:51 +0200'
  date_gmt: '2007-04-17 09:01:51 +0200'
  content: "I tried both pages with Firefox 2.0 and MSIE 6.0. Firefox is fine in both
    cases, and I like what you have created :) I think it would be very nice having
    such a startpage!\r\n\r\nSadly, MSIE 6 is just a mess, as you probably already
    feared. The result is equally bad in both cases:\r\n\r\nThe text boxes (left and
    right) are visible from the beginning. Along with the bouncing Wicket logo, the
    large text \"Wicket\" is horizontally moving at the top of the window. The license
    text is visible at the top of the page, the word \"Wicket\" is moving over it.\r\nyahoo.html
    also produces a javascript error, but the error message is not very helpful (line
    1, column 1, \"Object expected\").\r\n\r\nWhen the animation is finished, the
    page looks almost like in Firefox, just the text is now very blurry. It looks
    like it is displayed twice with one pixel offset.\r\nScreenshot: http://www.2rue.de/stuff/wicket_startpage.png\r\n\r\nThis
    last mis-effect is also on script.aculo.us startpage, but they seem to do something
    at the end of the animation, as it is visible only for a short time. After that,
    the text appears normally.\r\n\r\nYeah MSIE 6 is a real bitch, as always.\r\nIn
    my current wicket project we decided to scrap cool effects for MSIE users if we
    cannot get it to work within a decent timeframe."
- id: 1511
  author: Per Ejeklint
  author_email: ejeklint@mac.com
  author_url: http://www.ejeklint.se
  date: '2007-04-17 10:37:15 +0200'
  date_gmt: '2007-04-17 09:37:15 +0200'
  content: "I tried them both on Safari 2.0.4 and Firefox 2.0.0.2 on my MacBook Pro.\r\n\r\nThe
    Yahoo version seems to suffer in both browsers. When reloading the page some frames
    are lost and you often see only the few last frames in the animation. This happens
    on both browsers but with different outcome.\r\n\r\nThe animator version runs
    much more complete, with all frames drawn at all reloads. Interestingly, the animation
    is slightly more than twice as long in Firefox. I don't know if Firefox is slow
    or if Safari runs it too fast, but the most pleasant to view is actually Firefox.
    Except for the speed difference, animator seems to render more consistent on both
    browsers.\r\n\r\nSo in my eyes, animator.js is a clear winner."
- id: 1512
  author: Interesting JavaScript animation test - ejeklint-dot-se
  author_email: ''
  author_url: http://www.ejeklint.se/blog/2007/04/17/interesting-javascript-animation-test/
  date: '2007-04-17 10:41:01 +0200'
  date_gmt: '2007-04-17 09:41:01 +0200'
  content: "[...] Have a look at Martijns test of Yahoo Animation vs. animator.js,
    and tell Martijn what you think. [...]"
- id: 1514
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-04-17 11:04:04 +0200'
  date_gmt: '2007-04-17 10:04:04 +0200'
  content: "Actually, I had to tweak the animator.js version to speed up the animation
    in safari. The animation renders all intermediate frames in animator.js, and on
    safari that runs very slow with the default settings. I tried increasing the interval,
    but that didn't give the right results, so I cut down the time for the animation
    instead (use the source, Luke!)\r\n\r\nFirefox just runs the animations much,
    much better in both yahoo and animator."
- id: 1518
  author: Martin
  author_email: martin@martinfunk.de
  author_url: ''
  date: '2007-04-17 11:44:26 +0200'
  date_gmt: '2007-04-17 10:44:26 +0200'
  content: Yeah, verry nice indeed. I'd agree that Yahoo apears smoother (using Firefox).
    The rest I didn't check. Are you aware of Firebug? http://www.getfirebug.com/
    Hating JavaScript too, it at least eased my pain with it a little bit.
- id: 1527
  author: Ryan
  author_email: crumley@gmail.com
  author_url: ''
  date: '2007-04-17 16:47:59 +0200'
  date_gmt: '2007-04-17 15:47:59 +0200'
  content: Why not check out moo.fx? http://moofx.mad4milk.net/
- id: 1530
  author: James Cook
  author_email: wicket@visualxs.com
  author_url: ''
  date: '2007-04-17 16:59:56 +0200'
  date_gmt: '2007-04-17 15:59:56 +0200'
  content: "I would highly recommend you look again at jQuery. You discounted it because
    it \"covers too much\". If you look at the jQuery reference documentation (http://docs.jquery.com/Main_Page)
    you will notice that it covers a very nice sweetspot of functionality. It is also
    one of the fastest performing libraries for selector-based development, and they
    continuously obsess on performance.\r\n\r\nOf the three (YUI, Sciptaculous, and
    jQuery) that I have used, jQuery is the first that allowed me to extend it easily
    and sanely when I needed. There are a ton of plugins (jQuery extensions) to enable
    additional effects. One of the most polished and complete is called Interface
    (http://docs.jquery.com/Plugins:Interface).\r\n\r\njQuery weighs in at only 19kb
    packed, and designed to play nicely with the other major libraries, jQuery meets
    all of your criteria.\r\n\r\nAs a self-confessed person who \"hates writing Javascript\",
    it will be interesting to see where this leads. I believe that you truly must
    embrace the elegance of Javascript in order to make it work well in these next-gen
    web environments."
- id: 1531
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-04-17 17:04:03 +0200'
  date_gmt: '2007-04-17 16:04:03 +0200'
  content: "The biggest advantage of animator.js is that it is completely orthogonal
    to other libraries and focusses on just one thing: animation. It also doesn't
    require any other base libraries, minimizing the dependencies.\r\n\r\nThe library
    is quite stable and mature so I expect it to keep working for a whole Wicket release
    cycle."
- id: 1532
  author: n8han
  author_email: nathan@technically.us
  author_url: http://technically.us/code
  date: '2007-04-17 17:28:18 +0200'
  date_gmt: '2007-04-17 16:28:18 +0200'
  content: "Yeah, Safari js is pretty slow; I ran into that doing RSA in javascript.
    Newer WebKit builds are supposed to be much better, but with the OS 10.5 delay
    we'll have to wait even longer for a fix. Still, Safari's my favorite browser
    because it does job number one (rendering text) the best.\r\n\r\nI'm seeing exactly
    the same thing with yahoo, that it drops the beginning frames most of the time
    (at work, opera linux). The animator version always renders from the start, but
    flickers badly."
- id: 1540
  author: Ivan
  author_email: functionform@yahoo.com
  author_url: ''
  date: '2007-04-18 03:21:24 +0200'
  date_gmt: '2007-04-18 02:21:24 +0200'
  content: "You definitely want to use Ext.  www.extjs.com.\r\nIt is a wrapping library
    that is very much community tested and abstracts away various other libraries
    such as Prototype/JQuery/and YUI.  It has a gorgeous component lib, but I think
    it would function very well as a low-level library that lets the user (in this
    case a Wicket programmer) choose their JS provider.  I typically use it with YUI
    since I find YUI's seem to be consistently the fastest to my eye."
- id: 1541
  author: Ivan
  author_email: functionform@yahoo.com
  author_url: ''
  date: '2007-04-18 03:22:38 +0200'
  date_gmt: '2007-04-18 02:22:38 +0200'
  content: incidently, ext sounds like such a great match for wicket, you should just
    talk to Jack directly.. pop on over to the forum- He's also a Java guy.  (or was
    at some point.)
- id: 1553
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-04-18 10:11:02 +0200'
  date_gmt: '2007-04-18 09:11:02 +0200'
  content: "Gents, this is not a pimp my 'complete Ajax library that also happens
    to do animation' post. It is focussed on providing specific functionality for
    adding effects and animation to your Wicket application without tying into a specific
    framework (other than Wicket).\r\n\r\nExt-js is LGPL licensed, so we can't ship
    it with Wicket core, and /if/ we're going to support it, it most likely will end
    up at http://wicketstuff.org Given that Jack wants to make a living from ext-js,
    I can't blame him for using the LGPL license.\r\n\r\nI do think that ext-js looks
    pretty awesome, and it has been on my radar for months. Just waiting for an excuse
    and time to use it."
- id: 1555
  author: Per Ejeklint
  author_email: ejeklint@mac.com
  author_url: http://www.ejeklint.se
  date: '2007-04-18 12:16:56 +0200'
  date_gmt: '2007-04-18 11:16:56 +0200'
  content: "Just for fun I built the latest Webkit and now runs Safari with it. The
    Yahoo version now runs very smooth and elegant when opening a new window, but
    if I reload the animation will only show the last frames.\r\n\r\nThe animator
    version now runs WAY too fast and not so smooth, but it's much more consistent
    when you reload.\r\n\r\nI agree with Martijn that animation support in Wicket
    should be done without sideeffects like lots of new dependencies or license woes
    dropped in users knees. And yes, I too hate writing JavaScript even if I did make
    some pretty good money doing it. :-)"
- id: 1556
  author: James Cook
  author_email: wicket@visualxs.com
  author_url: ''
  date: '2007-04-18 13:38:16 +0200'
  date_gmt: '2007-04-18 12:38:16 +0200'
  content: "Is the homepage you demo written using Wicket? With the effects provided
    by the framework?\r\n\r\nIf so, can you provide the wicket project?"
- id: 1563
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-04-18 15:29:17 +0200'
  date_gmt: '2007-04-18 14:29:17 +0200'
  content: "No, it is static HTML (no need for serverside interaction). The effects
    are kindly provided by animator.js and Yahoo! Animation.\r\n\r\nFrom the looks
    of it, animator.js will become the part of Wicket in the near future."
- id: 1592
  author: Scott Sauyet
  author_email: lists@sauyet.com
  author_url: http://scott.sauyet.com/
  date: '2007-04-19 17:48:59 +0200'
  date_gmt: '2007-04-19 16:48:59 +0200'
  content: "In Firefox 2.0 on Windows XP, the Yahoo animation was MUCH more smooth
    than the Animator one, and I don't know if that's just a matter of tweaking of
    the code.\r\n\r\nLike many Java people, I used to hate Javascript, but I'm finding
    now that I have a good JS library behind me, that it's not bad at all.  My library
    of choice is JQuery, but I agree that it is not a good fit for this.  It is compact,
    elegant, and efficient, but it's built-in animation is relatively limited, and
    it does too much else.  It's not nearly as intrusive or as large as Prototype
    or Dojo, and if Martijn were looking for a good overall JS library to plug into
    Wicket, I would highly recommend it.\r\n\r\nAs it is, if Animator can be made
    as smooth as the Yahoo library, I would go for it."
- id: 1658
  author: Kubino
  author_email: jstein@centrum.cz
  author_url: ''
  date: '2007-04-21 23:59:49 +0200'
  date_gmt: '2007-04-21 22:59:49 +0200'
  content: I have to agree with RÃ¼diger Schulz , I am experiencing the same problems
    with Internet Explorer 7. I tried also Opera 9.10, animation is much more smoother
    and nicer with animator than yahoo. Animation also begings before the all resources
    are loaded.
- id: 4763
  author: wicket-animator &laquo; wicketeer
  author_email: ''
  author_url: http://wicketeer.wordpress.com/2007/06/25/wicket-animator/
  date: '2007-06-25 22:04:20 +0200'
  date_gmt: '2007-06-25 21:04:20 +0200'
  content: "[...] June 25th, 2007   inspired by this post on wicket-diary, i decided
    to take this in my own hands and see how far i&#8217;ll get. [...]"
- id: 11459
  author: Ryan
  author_email: ryan@darksleep.com
  author_url: ''
  date: '2007-09-14 05:43:20 +0200'
  date_gmt: '2007-09-14 04:43:20 +0200'
  content: Have you looked at MochiKit for this purpose?
- id: 25527
  author: Life is Beautiful
  author_email: ''
  author_url: http://satoshi.blogs.com/uie/2007/12/wicket-animatio.html
  date: '2007-12-12 05:53:59 +0100'
  date_gmt: '2007-12-12 04:53:59 +0100'
  content: |-
    <strong>Wicket animation using iAnime.js...</strong>

    I found a good blog entry comparing various animation libraries, which has implemented Wicket homepage in two different animation libraries. As a comparison, I have implemented the same animaition using iAnime.js. Wicket home page using iAnime.js Becau...
- id: 25528
  author: Satoshi Nakajima
  author_email: satoshi.nakajima@gmail.com
  author_url: http://satoshi.blogs.com/uie/2007/12/wicket-animatio.html
  date: '2007-12-12 05:57:17 +0100'
  date_gmt: '2007-12-12 04:57:17 +0100'
  content: "I have implemented the same animation using iAnime.js. Please take a look.
    \r\n\r\nhttp://satoshi.blogs.com/uie/2007/12/wicket-animatio.html\r\n\r\nAlthough
    iAnime.js is a Javascript library, the entire animation sequence can be described
    as an array of JSONs, which makes it a lot easlier to generate it on the server
    side."
- id: 57392
  author: Antonio Cisternino
  author_email: cisterni@di.unipi.it
  author_url: http://www.codeplex.com/animej
  date: '2008-11-30 17:09:54 +0100'
  date_gmt: '2008-11-30 16:09:54 +0100'
  content: Have a look also at AnimeJ library (http://www.codeplex.com/animej)
- id: 57731
  author: Kevin Dolan
  author_email: kevin@jsanim.com
  author_url: http://www.jsanim.com
  date: '2009-07-18 20:18:26 +0200'
  date_gmt: '2009-07-18 19:18:26 +0200'
  content: You should also check out jsAnim, http://www.jsanim.com.  I think this
    is the most fully featured one, but I guess I'm biased.
- id: 64860
  author: Margaret Thatcher
  author_email: margaret@mailinator.com
  author_url: ''
  date: '2013-02-19 07:57:50 +0100'
  date_gmt: '2013-02-19 06:57:50 +0100'
  content: You could also try out http://github.com/relay/anim/ which is an animation
    library at 1.2 KB gzipped.
---
<p>The <a href="http://wicketframework.org">Wicket framework</a> is adding animation (effects) support to its capabilities. Instead of reinventing the wheel we are looking at different libraries. Our list of requirements is not that big:</p>
<ul>
<li>the footprint of the library should be small</li>
<li>the philosophy of the library should be similar to Wicket's</li>
<li>the library should enable most if not all effects available in most popular libraries</li>
<li>the code should be clean and work in all modern browsers</li>
<li>the library should play nice with the leading javascript libraries such as <a href="http://prototypejs.org">prototype</a>, <a href="http://script.aculo.us">scriptaculous</a>, <a href="http://dojotoolkit.org">dojo</a>, <a href="http://jquery.com">jquery</a> and <a href="http://developer.yahoo.com/yui/">Yahoo! ui</a>
</li>
</ul>
<p>Now not a very impressive list, but apparently enough to drop <a href="http://script.aculo.us">scriptaculous</a> and <a href="http://dojotoolkit.org">dojo</a> (too large), <a href="http://prototype.js">prototype</a> (not an effects library, can enable conflicts with scriptaculous, <a href="http://www.openrico.org/">rico</a> and others). I haven't got much experience with jquery, but it seems to cover too much for our taste: we don't need a full stack Ajax framework (already have that in place), but merely the animation part.</p>
<p>So that leaves <a href="http://developer.yahoo.com/yui/animation/">Yahoo! Animation</a> and ... <a href="http://berniecode.com/writing/animator.html">animator.js</a> created by Bernard Sumption. I discovered animator.js when it was <a href="http://ajaxian.com/archives/animatorjs-animations-using-css">first featured on ajaxian.com</a> and added it to my list of things to check out. Recently I was looking at some effects for our application and wanted to remove dependencies left over from the time Wicket didn't support Ajax out of the box. Currently we have superb Ajax support and are now ready to take it to the next level.</p>
<p>I already had created a proof of concept, <i>"I'm jealous of the Scriptaculous front page design", </i>new front page  for Wicket. I made my first cut using animator.js and wanted to see how much work it would be to build it with Yahoo! Animation. So I spent a day to rewrite it using Yahoo! and tried to tweak the animation a bit to make it smoother.</p>
<p>You can see the animation on my people.apache.org page (links provided below). I have tried the animations using Safari and Firefox (1.5 and 2.0) and it led me to the following conclusions:</p>
<ul>
<li>safari's javascript is horribly slow</li>
<li>firefox's javascript is extremely fast (compared to IE and safari)</li>
<li>I hate writing javascript</li>
<li>Yahoo's event model is a bit more advanced than animate.js, somehow it looks smoother
</li>
<li>Animate.js seems to deliver more snappier animations</li>
<li>I hate writing javascript</li>
</ul>
<p>Try the animations yourself and don't limit it to one browser. Comments are welcomed and appreciated. Press the back button to return here and select the other animation:</p>
<ul>
<li>Wicket homepage <a href="http://people.apache.org/~dashorst/animation/yahoo.html">using Yahoo! Animation</a></li>
<li>Wicket homepage <a href="http://people.apache.org/~dashorst/animation/animator.html">using animator.js</a></li>
</ul>
<p>Enjoy!</p>
