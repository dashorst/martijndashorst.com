---
layout: post
status: publish
published: true
title: Eclipse + OS X = unhappy
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 355
wordpress_url: http://martijndashorst.com/blog/2008/04/03/eclipse-os-x-unhappy/
date: '2008-04-03 14:47:01 +0200'
date_gmt: '2008-04-03 13:47:01 +0200'
categories:
- java
tags:
- eclipse
- os x
- apple
comments:
- id: 48627
  author: Alex
  author_email: alexandru.objelean@isdc.ro
  author_url: ''
  date: '2008-04-03 15:04:19 +0200'
  date_gmt: '2008-04-03 14:04:19 +0200'
  content: I also encounter a lot of issues with latest distribution of Eclipse (ver.
    3.3.2). I've allocated 1024MB, but that doesn't help at all. Eclipse crashes every
    5 minutes. This drives me crazy!
- id: 48657
  author: Jan
  author_email: jan.stette@gmail.com
  author_url: ''
  date: '2008-04-03 16:24:24 +0200'
  date_gmt: '2008-04-03 15:24:24 +0200'
  content: "Alex: I also got hit with frequent crashes on OS/X after upgrading to
    Eclipse 3.3.  Turns out there's a known problem in the OS/X SWT bindings: http://www.cornilliac.com/blog/2008/02/fix-for-eclipse-33-crashing-under-osx-leopard/\r\n\r\nI'm
    currently running the latest milestone release of 3.4 which works much better."
- id: 48681
  author: Daniel Spiewak
  author_email: djspiewak@gmail.com
  author_url: http://www.codecommit.com/blog
  date: '2008-04-03 18:06:50 +0200'
  date_gmt: '2008-04-03 17:06:50 +0200'
  content: "This isn't a Java issue.  This is actually being caused by the operating
    system attempting to aggressively page out memory that it perceives as stale.
    \ The JVM of course knows better, but it can't do anything about it because of
    the virtual memory model.  OS X being a desktop operating system tries to determine
    stale memory based on apps which are running in the background or even which no
    longer have WS focus.  For the most part, this is a good thing, but for long running
    apps which eat tons of memory (basically, any IDE), it can cause problems like
    the one you experienced.\r\n\r\nTheoretically, this could be avoided either by
    the OS being less aggressive in its memory swapping, or by the JVM communicating
    with the kernel to hint at which bits of memory can be safely swapped.  Either
    fix would be trivial for Apple (because they control the VM on Mac), but I don't
    see them actually *doing* it any time soon.\r\n\r\nBTW, I've never experienced
    this problem to the degree you describe on either Windows or Linux."
- id: 48689
  author: Fabrizio Giudci
  author_email: Fabrizio.Giudici@tidalwave.it
  author_url: http://weblogs.java.net/blog/fabriziogiudici/
  date: '2008-04-03 18:35:18 +0200'
  date_gmt: '2008-04-03 17:35:18 +0200'
  content: I agree with Daniel. BTW, I have this issue with NetBeans and any major
    desktop Java application, including those I'm developing. I never did any specific
    measurement, but I do believe the problem is indeed caused by the bad GC + swapping
    interaction. I try to control that by avoiding to allocate too much memory to
    Java application, I know that a good rule is to avoid passing the amount of physical
    memory. Of course this effort would be jeopardized if you run multiple applications
    that would prevent the Java application to reside entirely in memory. Mac OS X
    is way, way, way worse than Windows or Linux in this case, running the same things
    in similar configurations I don't get this crazy trashing on the other two operating
    systems. You would expect that a custom-made JVM by Apple as the one in Mac OS
    X would address this kind of issues, and instead it doesn't.
- id: 48850
  author: Alex
  author_email: alexandru.objelean@isdc.ro
  author_url: ''
  date: '2008-04-04 07:00:07 +0200'
  date_gmt: '2008-04-04 06:00:07 +0200'
  content: I'm running my Eclipse on Windows XP platform and have no idea why this
    is happening.
- id: 49138
  author: Jonathan Locke
  author_email: jonathan.locke@gmail.com
  author_url: ''
  date: '2008-04-05 04:07:29 +0200'
  date_gmt: '2008-04-05 03:07:29 +0200'
  content: i'm using 3.4m6 and it works pretty good.
- id: 51489
  author: CAT
  author_email: info@catmedia.us
  author_url: http://www.catmedia.us
  date: '2008-04-11 15:20:58 +0200'
  date_gmt: '2008-04-11 14:20:58 +0200'
  content: "I partly agree with that. \r\nOf course, my Mac OS X is over 1 year old,
    so memory is the biggest problem since it only got 500MB back then (so I wold
    not dare to set 1024 ;-)\r\n\r\nWindows and Java in particular also have strange
    behaviour regarding memory. On Win XP on a 3GB Dell Notebook I constantly got
    only 2GB usable by the OS despite BIOS accepting all 3GB. Also if you try to allocate
    over 1024MB (mx option) on most JVMs prior to Java 5 on Windows this does not
    work at all. There are also known JVM issues with memory over 2GB on Windows,
    both 32 and 64bit. Some VMs have fixed that (e.g. BEA's own) but in general this
    still lags into Java 5 or 6 at least on Windows.\r\n\r\nComing back to Mac and
    Eclipse. 3.4 seems a lot better in some areas. Maybe it is just the parts SpringSource
    has put into their new STS, but RC1 of their Tools Suite based on Ganymede Preview
    has impressed me by performing a lot better in most similar use cases than e.g.
    the Europa Java EE Bundle by Eclipse. I may still look for more GB e.g. for Leopard,
    but those discoveries tend towards a combination of JVM and Eclipse itself (plus
    Plugins underneath) with a lot of room for their own improvement."
- id: 52559
  author: Eelco
  author_email: eelco.hillenius@gmail.com
  author_url: http://chillenious.wordpress.com/
  date: '2008-04-14 17:42:25 +0200'
  date_gmt: '2008-04-14 16:42:25 +0200'
  content: I'm using Eclipse 3.3.2 on OSX and I'm very happy with it. It never crashes
    and is always responsive.
- id: 54508
  author: Jonathan Locke
  author_email: jonathan.locke@gmail.com
  author_url: ''
  date: '2008-04-20 15:39:41 +0200'
  date_gmt: '2008-04-20 14:39:41 +0200'
  content: I am a Leopard, not a Tiger.  I think Eelco is also a Leopard.
- id: 56624
  author: Eelco
  author_email: eelco.hillenius@gmail.com
  author_url: http://chillenious.wordpress.com
  date: '2008-04-28 07:27:38 +0200'
  date_gmt: '2008-04-28 06:27:38 +0200'
  content: Right, I'm on Leopard.
- id: 56625
  author: Fernanda
  author_email: foertter@gmail.com
  author_url: ''
  date: '2008-04-28 23:12:56 +0200'
  date_gmt: '2008-04-28 22:12:56 +0200'
  content: I run Photran and it eats 100% of my CPU and god knows how much ram...now
    do I fix it? ugh!
- id: 56707
  author: Newton
  author_email: newton.whitman@gmail.com
  author_url: ''
  date: '2008-05-06 19:38:04 +0200'
  date_gmt: '2008-05-06 18:38:04 +0200'
  content: I have run Eclipse on OS X for years and the only problem I had was early
    on when SWT didn't play nice on OS X. My guess is that your machine is in general
    low on memory. Check your activity monitor with just a browser and see how much
    memory you have available. My guess is that it is pretty low. Leopard takes a
    lot of memory by itself and all those cool desktop widgets eat even more even
    when they aren't being displayed. I have 1gig on my current machine which was
    plenty under 10.4 but I am going to add another gig with Leopard. Luckily memory
    is cheap.
- id: 56862
  author: Harald Walker
  author_email: harald@bitwalker.nl
  author_url: http://www.bitwalker.nl
  date: '2008-05-17 00:15:44 +0200'
  date_gmt: '2008-05-16 23:15:44 +0200'
  content: How much RAM does your Mac have? For over a year I had 2 GB and most of
    the time it went very well with Mac OS X (first Tiger, then Leopard) and Eclipse
    (3.3.2, 3.3.3). When I started running multiple Eclipse instances next to each
    other plus Oracle XE on a Linux VM and the usual other programs (Firefox, Thunderbird,...)
    things started to get unbearable slow. I've since the upgraded the hard disk in
    my MacBook Pro to a 7200 rpm drive and added another 2GB of memory. That helped
    a lot and everything is running fine. I've never had problems with crashing Eclipse
    (except when a memory module was defect).
- id: 56897
  author: srecko toroman
  author_email: sreckotoroman@gmail.com
  author_url: http://toroman.objectis.net
  date: '2008-05-23 00:08:14 +0200'
  date_gmt: '2008-05-22 23:08:14 +0200'
  content: "Well it only happens with Eclipse 3.3 Enterprise Edition on Unix platforms.
    For example Classic eclipse (*without some plugins e.g. mylyn*) has never crashed
    on my Debian. \r\n\r\nAnyway, Eclipse is just great for being a powerful platform,
    SWT is great too, but it is not quite perfect, yet :)"
- id: 56935
  author: Matthew Peterson
  author_email: matt@peterson.org.au
  author_url: ''
  date: '2008-06-06 04:36:44 +0200'
  date_gmt: '2008-06-06 03:36:44 +0200'
  content: Just use Xcode or any editor that does syntax highlighting instead of wasting
    time with an IDE......then you can allocate that RAM to JVM instead of to the
    IDE
- id: 56960
  author: Tim Michalski
  author_email: tim@lssinc.com
  author_url: http://www.lssinc.com
  date: '2008-06-11 23:00:49 +0200'
  date_gmt: '2008-06-11 22:00:49 +0200'
  content: "Xcode?? That takes up way too much memory. Why not just use vi or emacs
    on the terminal for coding. In fact, it would really help if you disabled the
    Mac OSX user interface and just booted into the console. You'd probably not have
    any more IDE issues then. ;)\r\n\r\nI'm having the same issues and figured that
    I would just put a hammer through my monitor. The JVM &amp; Kernel quickly stopped
    bickering and started bi-lateral communications with all parties involved."
- id: 57857
  author: Objective-C rocks
  author_email: nothanks@somewhere.com
  author_url: ''
  date: '2010-01-09 10:40:16 +0100'
  date_gmt: '2010-01-09 09:40:16 +0100'
  content: "I've studied J2ME, J2SE and J2EE for two years but then I discovered Objective-C.
    I switched and regard this as the best decision I have ever made. I suggest that
    others do the same. I found the class libraries to be works of art - the documentation
    excellent and the development tools to be far superior to anything I've used before.
    I've programmed on various platforms and various languages- in windows linux OSX
    and a few handhelds. I remember the disappointment and frustration caused by badly
    designed components and that the only way I could achieve my goals most times
    was to rewrite those components from scratch. Even this wasn't enough when one
    implementation of the same API differs from the next - even devices created by
    the same manufacturers supposedly implementing the same APIs broke basic functionality
    like that buttons were mapped to the wrong keys.\r\n\r\nOpen source is great only
    because its free - it is inferior in all other regards and that is to be expected
    if you understand that money translates into time, effort and expertise being
    allocated to making something the best it can be. Why not pay people what they
    justly deserve for delivering outstanding work? Work that improves quality of
    life (for programmers that is) and gives us peace of mind. I have never once experienced
    the frustrations and disappointments in Objective-C and Cocoa that I used to on
    a nearly daily basis with open source. Although you finally get the job done its
    how you get it done that makes the difference. I can finish an objective-c project
    with a smile on my face but the same project in Java makes me want to find the
    authors of some of these components and classes and just ask them what the hell
    they were smoking at the time - or just suggest they get another day job or a
    different hobby. I can't say the same about Cocoa and Objective-C. I know it was
    written by veteran software engineers so if I do find something wrong its going
    to be something small and insignificant - so far I'm happy - I've been happy for
    over a year now and thats a record no Java worshipper can beat. I'd like to have
    liked Java - hell I spent a great deal of money and time hoping to become an \"expert\"
    but I've just been disappointed too many times."
- id: 57919
  author: soldier_of_light_army
  author_email: himanshu.p.singh@gmail.com
  author_url: ''
  date: '2010-02-26 08:50:12 +0100'
  date_gmt: '2010-02-26 07:50:12 +0100'
  content: well, if using Linux, Eclipse can be one heck of pain in the neck. As many
    people stated above, it crashes a lot. Install xulrunner (you need it if you are
    using Aptana plugins or use Firefox) and boy, you just added RDX to the fire.
    No matter how many MOZILLA_FIVE_HOME paths you set, Eclipse will keep arbitrarily
    crashing, frequently enough to help any suicidal guy take the plunge. BTW, I use
    Ubuntu Jaunty.
- id: 57960
  author: philippe
  author_email: philippe@gassmann.fr
  author_url: http://cestdelamerde.com
  date: '2010-03-29 23:13:27 +0200'
  date_gmt: '2010-03-29 22:13:27 +0200'
  content: "Hi, unfortunately, Mac OS X has the worst memory manager ever seen in
    the OS world. \r\n\r\nIt is possible to keep your mac beachballing if you totally
    disable the swap (by modifying dynamic_pager, the process who is responsible for
    allocating the swap) but this is a bit  dangerous. OS X VM has been designed as
    if memory were unlimited, disabling the swap will resolve beachballing but if
    your applications requires more ram than actually present on your system, the
    system will hang. (mac os doesn't know how to say to an app: \"no there is no
    memory anymore\" so it will wait for free memory indefinitely...)\r\n\r\nI experienced
    strong pageout issue with process requiring a lot of memory I/O and disk I/O (eclipse,
    subversion when the tree is a big, copying a bunch of big files to the disk such
    as pictures from camera, lightroom...). \r\n\r\nTo conclude: mac os x sucks a
    lot if you need more than the half of the memory present on your system or if
    you need to do a lot of I/O operations."
- id: 62616
  author: Peter
  author_email: pebanfield@gmail.com
  author_url: ''
  date: '2012-10-28 13:21:18 +0100'
  date_gmt: '2012-10-28 12:21:18 +0100'
  content: "Re : Objective C Rocks - \"Open source is great only because its free...\"
    \r\n\r\nIt's not just about money. In fact, it's quite the opposite for me. I
    don't want to devote my time and energy to a mega-company that constrains and
    controls my creativity to ensure it's business objectives are always the top priority.
    \r\n\r\nYes, I concede there is some extra overhead dealing with open tools and
    frameworks. You do have to choose your tools more carefully. But when my tools
    crash or I have to deal with other problems - I think this is a reasonable trade
    off for an open philosophy that is good for my fellow programmers and maybe even
    society at large. It's the cost of not selling out. \r\n\r\nPeter"
---
<p>Eclipse and OS X (10.4 Tiger) makes me unhappy. Today I witnessed something really stupid. I have allocated 768MB for Eclipse (eclipse.ini) and to my amazement, Eclipse was beach balling (being unresponsive for you non-OS X-ers). This beach balling was due to the simple fact that the Java garbage collector was reading in pages from the swap file in order to throw everything away. Woohoo! This took of course over 2 minutes.</p>
<p>I doubt that Java will ever become a consumer technology with this kind of shit.</p>
