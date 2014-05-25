---
layout: post
status: publish
published: true
title: Why I don't consider IntelliJ IDEA to be the best Java IDE
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 545
wordpress_url: http://martijndashorst.com/blog/?p=545
date: '2013-11-04 10:42:25 +0100'
date_gmt: '2013-11-04 09:42:25 +0100'
categories:
- java
tags: []
comments:
- id: 66111
  author: Michael Mosmann
  author_email: michael@mosmann.de
  author_url: http://wicket-praxis.de/blog/
  date: '2013-11-04 11:40:02 +0100'
  date_gmt: '2013-11-04 10:40:02 +0100'
  content: "I can only agree with this. But I am forced to use it (too often) in projects.
    Things i don't understand:\r\n- IntelliJ tries to rename much more then expected
    if you rename a method name or parameter. This can lead to changes nobody wanted..
    Sometimes there is no way to exclude stuff from refactoring, so you can get a
    change over 100+ places. And even then IntelliJ can miss some calls which leads
    to compile errors afterwards.\r\n- If you try to find something its possible you
    will miss some places. I could reproduce this behavior, but not the cause. If
    you want to be sure, maybe you should use grep on the command line.\r\n- Last
    week i had to print some code to paper. By accident i saw that IntelliJ did not
    cut a long line or did a line wrap but instead removed some code from this line
    (vararg method call, removed one entry completely).\r\n- But what i hate most:
    You can change your code without any effect. Sometimes a clean build over the
    whole projects helps. Sometimes you must change it again. Sometimes you must invalidate
    caches. But too often you search for bugs because IntelliJ did persist code changes.
    IntelliJ can hot replace code but uses the old code if you restart the server/application.\r\n\r\n..
    you have to trust your IDE, which I can not say about IntelliJ."
- id: 66125
  author: Andrey Cheptsov
  author_email: andrey.cheptsov@gmail.com
  author_url: ''
  date: '2013-11-05 09:12:18 +0100'
  date_gmt: '2013-11-05 08:12:18 +0100'
  content: "I'd like add my 2 cents to this post.\r\n \r\nFirst of all, I think it’s
    wrong to compare products feature-by-feature. It’s like trying to use a product
    the same way as you’ve used the other one of its kind before, expecting all the
    older features to be exactly in the same place as they were. The thing is, you
    don’t need a new product to use the features you had in the other one, and you
    should not waste your time on that. Instead, just try to understand the concept
    of the new product and the possibilities it offers. I could never wrap my head
    around the fact that there’re people out there, who would rather make a quick
    (and vastly incorrect) judgment about a product or tool instead of spending very
    little time to actually figure out how it works. It’s like seeing someone trying
    to cut trees with chainsaw, but using it the way as if it was an axe. The one
    thing I think you are right about is that IntelliJ IDEA and Eclipse have really
    different workflows. I would go even further and say that the concepts behind
    these products are completely different as well. I wouldn’t even try to convince
    you that IntelliJ IDEA is better than Eclipse, but I recommend you to ask someone
    you know who uses IntelliJ IDEA to explain you how it works and why he thinks
    it’s better for him. Unfortunately, I can’t teach you how to use IntelliJ IDEA
    in one comment,  but I can comment on what you said, and I will:\r\n \r\n&gt;
    I think the editor is stupid as it makes *me* think whether I have to override,
    implement or generate a method by enforcing different keybindings for those actions.
    I just want to press ?-space and select the appropriate action from there (using
    autocomplete). Eclipse gets this.\r\n \r\nIt never hurts to think a little, however,
    in IntelliJ IDEA you don’t even need to call code completion to have something
    completed, even the things you mention:\r\n \r\nhttps://dl-web.dropbox.com/get/shared/override.gif?w=AABKW7_5XWhRPvYqFDHyPiSrobb7in7kB31B5LL8WXbcWw\r\n
    \r\nIn my personal opinion, nevertheless, “Override method” (Cmd+O) action is
    much more convenient than what Eclipse offers.\r\n \r\n&gt; Smart autocomplete
    in IntelliJ is anything other than smart. More often than not it presents me with
    an empty popup.\r\n \r\nIntelliJ IDEA and Eclipse code completions are apples
    and oranges, and here’s why:\r\n \r\nhttp://jetbrains.dzone.com/articles/top-20-code-completions-in-intellij-idea\r\n
    \r\n&gt; IntelliJ has a user interface that makes me do work for the computer
    instead of making the computer do work for me: having to instruct the compiler
    to do its work after saving a Java file, organize imports on save, etc.\r\n \r\nIt
    makes me laugh to comment on this, but here’s the news: it’s not even the compiler’s
    work. Anyway, IntelliJ IDEA provides a bit different way to apply those things
    and no one has complained about them ever since version 1.0 (except for Eclipse
    fans.)\r\n \r\n&gt; There is one thing that I really don’t understand of IntelliJ:
    it doesn’t make migration from Eclipse users streamlined.\r\n \r\nYou know what?
    It was intentionally made so to make Eclipse users suffer more (joking). Truth
    is, IntelliJ IDEA 13 comes with more streamlined and otherwise improved Eclipse
    migration toolset (already available in EAP).\r\n \r\nThe bottom line is: there
    are many things I don’t like in my favorite IDE (which I think is a subject for
    a whole other blog post), but you have mentioned none of them. Personally, I recommend
    you to give it one more try, and just spend a bit more time on learning how it
    works, and then your opinion may change (of which I’m so very sure)."
- id: 66130
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2013-11-05 23:45:04 +0100'
  date_gmt: '2013-11-05 22:45:04 +0100'
  content: "Why assume I haven't tried IntelliJ as my main IDE for a couple of weeks?
    Granted this was a year ago, but my gripes are valid from my perspective. As an
    eclipse user I am used to having the compiler, formatter, and hotspot code replacement
    kick in when I press CMD-S. I really got tired of having to tell IntelliJ to make,
    build all when make doesn't do the job (which results in 30 seconds loss every
    time this happens, which is often). Eclipse? CMD-S and usually a second later
    I have my running program updated with new bytecode.\r\n\r\nAnd I laugh at the
    idea that I can't compare two fricking Java IDEs. Both operate in the same market,
    hunt for the same developers and both have religious followers (though I never
    hear of folks actually loving Eclipse–I don't love Eclipse either, but it invokes
    the least stress in my day-to-day workings).\r\n\r\n I'm stating that up till
    now every time I used IntelliJ because folks keep saying that it sooooo much better,
    infinitely better than Eclipse, it turned out to be a dreadful experience for
    me. \r\n\r\nIf IntelliJ works for you then great. Keep using it. I'm not trying
    to convince you that eclipse would be better for you. I'd hope you would extend
    that courtesy to me as well."
---
<p>This is something that has bothered me for a long time. Many people I know like and love IntelliJ IDEA, but every time I try it I loathe the experience. I think the editor is stupid as it makes *me* think whether I have to override, implement or generate a method by enforcing different keybindings for those actions. I just want to press ?-space and select the appropriate action from there (using autocomplete). Eclipse <em>gets</em> this. Smart autocomplete in my book is to have ?-space work for all use cases: did I already type <em>get</em>? Then probably you want to generate a getter for a property. Did I not type anything? Then I probably want to implement (or override) a method.</p>
<p>Smart autocomplete in IntelliJ is anything other than <em>smart</em>. More often than not it presents me with an empty popup. IntelliJ wants me to press ????-space or ?????, which breaks my fingers. I have to remember which magic combination of ???? with enter or space invokes the thing I don't want to have to think about: implement an abstract method or override a super method? I already know thy name, don't make me think about the implementation detail of implementing or overriding!</p>
<p>IntelliJ has a user interface that <strong>makes me do work for the computer</strong> instead of making the computer do work for me: having to instruct the compiler to do its work after saving a Java file, organize imports on save, etc. I know you can record macros, but then everybody has different actions configured. Note that I typically work in a team with 5 to 15 people committing to the same code base. Having the exact same actions that are executed consistently on save is a life saver.</p>
<p>There is one thing that I really don't understand of IntelliJ: it doesn't make migration from Eclipse users streamlined. Yes, they provide keybindings for Eclipse users, but those only work for Windows users–not OS X users. They don't provide a working importer for Eclipse formatter rules. So when someone uses IntelliJ in an Eclipse environment the formatting is not consistent. I have used the Eclipse formatter plugin but that doesn't make working in IntelliJ more fun.</p>
<p>To sum up: even though I frequently throw a fit when Eclipse stops behaving correctly, I still consider it to be the best IDE for Java coding. It is unfortunate that m2e (the Maven integration into Eclipse) makes Eclipse bog down to barely useful. But that is material for another rant on another day.</p>
