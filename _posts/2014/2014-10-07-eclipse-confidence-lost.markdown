---
layout: post
status: publish
published: true
title: 'Eclipse: confidence lost'
author: Martijn Dashorst
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
date: '2014-10-07 11:30:00 +0100'
---

Today I lost about 2 hours of time trying to figure out why my modified
code didn't end up in my running application server, even while I use
JRebel to reload classes.

It was caused by having the "Build automatically" flag turned off.

Upfront this is clearly a PEBCAK failure on my part.

What frightens me is my complete and utter distrust of Eclipse's plugin
system that made me go on a yak shaving mission in trying to find which
plugin failed to work this time, instead of remembering the obvious,
glaring setting that enables/disables builds.

Eclipse has failed so many times to work properly that I have lost the confidence in its ability to help me be a better developer.

And no: this is not a plight for alternative IDEs: I've tried them all
and still think Eclipse is a better fit for me. YMMV.

