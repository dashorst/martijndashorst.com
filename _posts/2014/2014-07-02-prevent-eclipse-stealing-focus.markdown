---
layout: post
status: publish
published: true
title: 'Prevent Eclipse from stealing focus'
author: Martijn Dashorst
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
date: '2014-07-02 17:20:54 +0100'
date_gmt: '2014-07-02 16:20:54 +0100'
categories:
---

A typical workday starts like this: I open up my notebook, type in my
password, fire up Eclipse using [QuickSilver](http://qsapp.com)
(⌘-space, ec⏎), fire up
[Tweetbot](http://tapbots.com/software/tweetbot/) using QuickSilver
(⌘-space, tw⏎), start [Adium](https://adium.im) (⌘-space, ad⏎), start
Mail (⌘-space, m⏎), start Safari (⌘-space, s⏎).

Any time when I try to start one such application Eclipse can swoop in
with its "Select workspace" dialog, causing me to create workspaces
with names "ec", "ad", "mail", etc. This is because I try to get my day
started quickly, and Eclipse is an asocial attention seeker stealing
the input from other applications.

So one day I was fed up with the umptieth unfortunate workspace
creation event and I looked up if someone had encountered this problem
and thought about fixing it.

There's a fix for this ([full
article](http://www.cnet.com/news/keep-applications-from-stealing-focus-
when-opening-in-os-x/)): add the following two (2!) lines of XML to
Eclipse's plist file in the dist section:

{% highlight xml %}
<key>LSBackgroundOnly</key>
<string>True</string>
{% endhighlight %}

This will prevent the application from stealing the focus when you are
busy with other things. You can modify this yourself while waiting for
the [Eclipse guys to solve this
issue](https://bugs.eclipse.org/bugs/show_bug.cgi?id=438694).
