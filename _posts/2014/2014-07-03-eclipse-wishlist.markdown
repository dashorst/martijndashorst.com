---
layout: post
status: publish
published: true
title: 'Eclipse Console Wish List'
author: Martijn Dashorst
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
date: '2014-07-03 13:20:54 +0100'
date_gmt: '2014-07-03 12:20:54 +0100'
categories:
---

There are a lot of things I like about working with Eclipse. This is
not a post about those things. Here I'd like to vent small frustrations
I have with Eclipse that would make it feel more like a thoughtful
product than something incidental.

This instance I'll rip on Eclipse's Run/Debug Console.

Eclipse's debug/run console is really barebones. It's my guess that a
MS DOS 2.0 prompt gives more formatting possibilities. So here's my
wish list for Eclipse's console:

 - default infinite scroll buffer ([bugzilla](https://bugs.eclipse.org/bugs/show_bug.cgi?id=438270))
 - ANSI escape character support ([bugzilla](https://bugs.eclipse.org/bugs/show_bug.cgi?id=112948))
 - smart scroll lock behavior ([bugzilla](https://bugs.eclipse.org/bugs/show_bug.cgi?id=149393))

There are more gripes to be had with the console, but for now let's
look at these three.

### Default infinite scroll buffer

Vi, less, more, and all other utilities are capable of displaying
gigabytes of log files, yet Eclipse's console seems stuck in the
Notepad era. With each new installation and workspace I have to
instruct the console to use a infinite scroll buffer. Should Eclipse
actually support an infinite scroll buffer, without memory overhead,
[why not make it the default?](https://bugs.eclipse.org/bugs/show_bug.cgi?id=438270)

###  ANSI escape character support

Granted most of the times I'm looking at a long list of log lines
produced by SLF4J or some similar logging framework. But even in those
circumstances it would be beneficial to have color coded lines (e.g.
red colored lines for error level messages)

Sometimes though I have a commandline utility where I'd like to show a
progress using a percentage (overwriting the previous state). ANSI
control characters would allow that (and is properly supported in most
terminals).

Unfortunately someone closed the [feature request in Eclipse's
bugzilla](https://bugs.eclipse.org/bugs/show_bug.cgi?id=112948)
instance with no option to reopen it.

### Smart scroll lock behavior

Currently the scroll behavior of the console is abysmal. When you
scroll back in the log to see if something went awry during startup,
any logging activity will put your view back to the end of the log. You
can of course lock the scroll position, but then no update will ever be
visible because the position is locked. You then have to manually
scroll to the end to see the action.

In my opinion scroll behavior could be quite a bit smarter when
implemented as follows:

 - When I look at the end of the buffer, scroll lock should be disabled
   and updates should scroll before my eyes keeping the most recent
   update in view.

 - Whenever I scroll back, scroll lock should be enabled immediately.
   There is no use in moving back to the end of the buffer when
   something new arrives while I am looking at a stack trace.
   
 - Whenever I scroll forward and reach the end of the buffer, scroll
   lock should be disabled and updates should scroll before my eyes,
   keeping the most recent update in view.

I really would like to see these implemented and I think numbers 1 and
3 should not be too hard to implement. 
