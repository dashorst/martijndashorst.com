---
layout: post
status: publish
published: true
title: Kent Tong on Tapestry and Wicket
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 304
wordpress_url: http://martijndashorst.com/blog/2007/09/26/kent-tong-on-tapestry-and-wicket/
date: '2007-09-26 14:22:10 +0200'
date_gmt: '2007-09-26 13:22:10 +0200'
categories:
- wicket
tags: []
comments:
- id: 12964
  author: Niall
  author_email: niallp@apache.org
  author_url: ''
  date: '2007-09-26 16:00:16 +0200'
  date_gmt: '2007-09-26 15:00:16 +0200'
  content: Reading that blog entry it looks to me like Tapestry would fail to graduate
    from the Apache Incubator (if it was put thru it now) as its effectively a developer
    community of one (genius!) committer - unlike Wicket which recently graduated
    with flying colours.
- id: 12965
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-09-26 16:25:58 +0200'
  date_gmt: '2007-09-26 15:25:58 +0200'
  content: "I don't think it was written as a criticism on the dynamics of the Tapestry
    community. The communities are just different, just as the technology. It is very
    fortunate that Kent is in a position to see both communities first hand, which
    is an unicum IMO. Though he is not a Wicket committer nor PMC member, he has worked
    with the Wicket community and code base enough to have a well founded opinion.\r\n\r\nThere
    have been some studies on communities at the last Apache Con EU, I wonder what
    they might say about the differences between the two. Does anyone have the results?"
- id: 12972
  author: Karthik
  author_email: karthik.guru@gmail.com
  author_url: ''
  date: '2007-09-26 19:24:10 +0200'
  date_gmt: '2007-09-26 18:24:10 +0200'
  content: "In  the sections - \"Technical advances vs version compatibility/Technology
    driven vs user driven\",  he observes something along these lines - \r\n\r\n\"T4=&gt;T5
    using annotations replacing for XML\"\r\n\r\nI'm not sure if things like this
    applies to Wicket. Tapestry, i believe had lot of XML based configuration stuff
    (the .page file for every template and the like) just like say hibernate 2 had
    for the mapping stuff. \r\n\r\nSo when annotations came along , they probably
    moved stuff from XML -&gt; Code so that you have one place to maintain everything.
    Hibernate did that and so did other frameworks that were running out of XML config.
    May be t4 did some other cool stuff as well with annotations.\r\n\r\nBut my understanding
    is that Wicket didn't have this problem to begin with. I know annotations look
    cool , especially people love it when they see custom framework annotations but
    then if you don't have a problem, why bother.\r\n\r\nI believe tapestry uses javaassist
    to do \"bytecode\" manipulation of your abstract page class ? again really 'cool'
    but then , well, does it make sense in wicket?.\r\n\r\nOne of the issues could
    also be that Kent has probably not seen Wicket evolving w.r.t design the way he
    has seen Tapestry.\r\n\r\nAs a Wicket user for the last one year, I personally
    have seen things like behaviors, component instantiation listeners , Ajax support
    and stuff evolving and to me they appeared really cool. Not cool \"technology\"
    in that sense , but cool incremental \"design\" decisions for sure in order to
    solve some interesting problems remaining within the realms of the bare bones
    JDK. Now all this w/o breaking existing code (or may be little breakage) - doesn't
    that require some expertise?\r\n\r\nBut that's just me. I do agree that it might
    not appeal (or seem that big-a-deal) to everyone."
- id: 12974
  author: Jonathan Locke
  author_email: jonathan.locke@gmail.com
  author_url: ''
  date: '2007-09-26 19:33:23 +0200'
  date_gmt: '2007-09-26 18:33:23 +0200'
  content: Howard is certainly a very talented and prolific coder, but I'm curious
    why "genius" would produce a framework that needs to be completely refactored
    every so many months.  I also didn't agree with the bit about Wicket code quality.
    There are things that could be better, but it's still head-and-shoulders above
    most projects I've ever worked on.  Also, turning everything into an interface
    is just as wrong as turning everything into XML was and I fail to see how interfaces
    are more testable than concrete classes or any other unit of code.  Of course,
    good solutions to all these quibbles lie in Scala.  We just need that refactoring
    support in Eclipse...
- id: 12975
  author: Jonathan Locke
  author_email: jonathan.locke@gmail.com
  author_url: ''
  date: '2007-09-26 19:43:48 +0200'
  date_gmt: '2007-09-26 18:43:48 +0200'
  content: BTW, I don't mean to put Howard down, but I'm more interested in great
    /teams/ with top-notch leaders than one-man coding teams (as romantically cool
    as that seems!).  Frankly, although I provided the initial vision and architecture
    for Wicket, it would not be the framework it is without key ideas from a dozen
    other people.  I'm very skeptical of the idea that one person, however bright,
    can really see all the problems in something as vexingly complex as a web framework.
    It simply has too many facets to yield to powerful intellect alone.  I think Wicket
    turned out as well as it did because I'm an excellent architect, but also someone
    who builds community, who not only listens to but actively seeks out and includes
    the best people and ideas.  I think the core team is doing a great job of carrying
    on that tradition.  If I could complain about something it would simply be lack
    of resources.  Where Wicket code quality is not as high as we'd like, I think
    that often has to do with the fact that Wicket is being "dogfooded" on dozens
    of major projects now and when you don't have a day job working on Wicket, you
    tend to just get the job done.  But that's really a gripe about OSS, not Wicket.
- id: 12977
  author: Jonathan Locke
  author_email: jonathan.locke@gmail.com
  author_url: ''
  date: '2007-09-26 19:46:47 +0200'
  date_gmt: '2007-09-26 18:46:47 +0200'
  content: Oh, and yes, it is totally true that I no longer know how Wicket works.  It's
    grown too fast for me in the last year or so to keep up.  It's also grown into
    areas that are not my core competency (JavaScript / AJAX, for example).
- id: 12986
  author: Jesse Kuhnert
  author_email: jkuhnert@gmail.com
  author_url: http://blog.opencomponentry.com
  date: '2007-09-26 22:08:35 +0200'
  date_gmt: '2007-09-26 21:08:35 +0200'
  content: "Howard has too much class to put down another project developer - but
    luckily for him I don't.   Quite frankly,  the real reason Kent Tong isn't working
    on Tapestry anymore is because he didn't really \"work out\" when attempting to
    write actual code for the framework.   \r\n\r\nI'm sorry to see him trying to
    attribute this to Howard not providing guidance - but that's simply not the case.
    \ I watched in agony as he writhed around on the mailing list asking questions
    that committers shouldn't be asking and slowly sinking in the tumultuous waters
    that coding above your head can sometimes become.    \r\n\r\nWhenever I need design
    help Howard has always come through for me at least,  as well as others that I
    see him interacting with on the lists all the time.  He doesn't like to admit
    it but he also sort of designed some of the core cool T4 ajax features that people
    like so much - such as the @EventListener annotation.   \r\n\r\nI'm not ashamed
    to admit that he's a better coder than I am.   I'm thankful that I get to work
    with someone smarter than me that I can learn from.   Which is why I still love
    programming."
- id: 12990
  author: Eelco Hillenius
  author_email: eelco.hillenius@gmail.com
  author_url: http://chillenious.wordpress.com/
  date: '2007-09-26 23:54:18 +0200'
  date_gmt: '2007-09-26 22:54:18 +0200'
  content: "Kent is simply iterating what I've heard a dozen times by now from people
    who used to use Tapestry.\r\n\r\nI find the whole genius thing a bit off-putting
    tbh. It's the single most annoying thing about the tapestry community to me. It
    comes across like a sect. Jonathan is definitively a better coder than I am, and
    one of the most intelligent and creative guys I know (not just in software). But
    I hope someone will shoot me on the spot if I would ever try to use that as a
    defense for Wicket."
- id: 12996
  author: Jesse Kuhnert
  author_email: jkuhnert@gmail.com
  author_url: http://blog.opencomponentry.com
  date: '2007-09-27 01:10:41 +0200'
  date_gmt: '2007-09-27 00:10:41 +0200'
  content: Who was defending Tapestry?   I think it speaks for itself when being compared
    to a poor copy...
- id: 13005
  author: Fred
  author_email: xf2697@fastmail.fm
  author_url: http://functionalj.sourceforge.net
  date: '2007-09-27 02:27:16 +0200'
  date_gmt: '2007-09-27 01:27:16 +0200'
  content: "I stopped using Tapestry the day that I read a post on TSS by HLS. The
    thread was about Tap being released (I forget which version). Somebody (I forget
    who - but definitely not a Wicket committer) posted a comment saying something
    like, \"if you like Tapestry, try Wicket!\" Now, I'm not AT ALL defending that
    kind of post. Nevertheless, I lost respect for HLS when he replied, \"Bullshit.
    Wicket does not do this, or that..\" I can't remember the details but his post
    went on and on about how Wicket was inferior to Tap, and he did so in a very arrogant
    way. That really goes against the grain for me. Not much later, the post was edited
    on TSS (so don't go looking for it, the edited post is much more polite, I doubt
    HLS wrote it himself!)\r\n\r\nAnyway, since then I've dropped Tap from my web
    framework shortlist, and I'm glad I did when I did (T3), before wasting time on
    a framework that starts over at every version."
- id: 13010
  author: Eelco Hillenius
  author_email: eelco.hillenius@gmail.com
  author_url: http://chillenious.wordpress.com/
  date: '2007-09-27 03:30:51 +0200'
  date_gmt: '2007-09-27 02:30:51 +0200'
  content: 'Here is one for starters: http://tapestryjava.blogspot.com/2006/12/tapestry-5-progress-localization-assets.html#comment-2953367553692589420.'
- id: 19467
  author: hari sujathan
  author_email: hari_sujathan@yahoo.com
  author_url: http://www.kovilparambil.com
  date: '2007-11-14 16:13:25 +0100'
  date_gmt: '2007-11-14 15:13:25 +0100'
  content: "hi,\r\n\r\n  if there is a active development project being done in tapestry
    4. Does it make sense to migrate to wicket or tapestry 5?\r\n\r\nMoreover wicket
    reminds me of game cricket. India won last 20-20 world cup cricket competition
    beating Australia in semi and pakistan in finals. \r\n\r\nApart from that , I
    want to know of Howard's choice after tapestry between JSF and wicket!!!! \r\n\r\nthanks
    &amp; regards,\r\nHari."
---
<p><a href="http://www.agileskills2.org/blog/" title="Kent Tong's personal thoughts on information technology">Kent Tong</a>, a <a href="http://tapestry.apache.org/" title="Apache Tapestry">Tapestry</a> committer (and PMC member) has gotten his feet wet using Wicket and has written a nice, in my opinion fair, blog entry on what he conceives to be the differences between <a href="http://agileskills2.org/blog/2007/09/my_thoughts_on_the_differences.html" title="Kent Tong's personal thoughts on information technology: My thoughts on the differences between Tapestry and Wicket">Tapestry and Wicket</a>.</p>
