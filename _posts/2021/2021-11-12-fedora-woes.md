---
layout: post
status: draft
published: false
title: "Fedora 34 Workstation Woes"
---
As my trusty MacBook Pro 2018 is in the repair shop for replacing the keyboard, I am now fully embracing the Fedora lifestyle.
Trigger warning: This is a rant. If you value open source in general, and Fedora in particular you might want to skip reading this.

## Why Fedora?

Fedora is used by the red hat developers, and many of them work on Java and Java related projects. 
Therefore using the same Linux distribution as them might give me an edge over other distributions.

I have used other distributions before (wayback in 1995 I compiled my own slackware) and last year I've tried Fedora, Mint and Ubuntu.
I also trialed Manjaro, PopOS_! and several others using Ventoy.

The biggest reason to use Fedora is because it is the only distribution I got to work with letting the PC sleep, keep it asleep and have
it wake up _working_ after a day, couple of days or even weeks. All the other distributions failed directly or after a couple of weeks of
use.

Being able to sleep and wake my computer is IMO essential and a very good indicator of having and keeping a working system.

## The good parts

Fedora (and Linux in general) is _fast_. It is blazingly fast. So fast you can't even think how fast it is, because it has already passed
you. Eclipse (2021.9) is really, really fast in Fedora. Building our software using Maven is really fast. Of course, this is helped by my
hardware: an AMD 3950X with 64GB of RAM. That said, the CPU is hamstrung with a too small cooler, so probably has to throttle now and then,
not unsimilar to the i9 in the MacBook Pro.

For example: in macOS right clicking on a folder `src/test/java` and selecting `Run as -> Unit test` will take several seconds before Eclipse
starts doing literrally anything, and then starts the unit testing environment and then with luck, your tests will run in about 10 seconds.
Switching between editors feels like watching the UI compositor paint every frame at 60Hz. Double clicking on a file takes over 2 seconds
before the file is starting to open.

Contrast this to Linux (or maybe even Fedora?): running the tests is completed so fast I didn't even realize it had happened. Right click,
run as test, and all the tests had already ran. Instant results. Switching between editors is fast. Opening files is fast. No waiting on
the user interface.

## The oh-oh parts

- Software update agents keeps hanging
- Sometimes text in tree view in Eclipse turns bold for no reason
- Right click popup menu opens on different monitor
- No easy way to add _self_ downloaded software as a program icon to the menu
- Unbinding Alt-F5 from Gnome 41 doesn't allow Eclipse to capture the key (apparently you have to completely unbind 
- 
