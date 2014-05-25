---
layout: post
status: publish
published: true
title: Mac Zealotism
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 18
wordpress_url: http://martijndashorst.com/2006/11/22/mac-zealotism/
date: '2006-11-22 21:04:32 +0100'
date_gmt: '2006-11-22 21:04:32 +0100'
categories:
- technology
- os x
tags: []
comments:
- id: 12
  author: Tim Fennell
  author_email: jroller@tfenne.com
  author_url: http://jroller.com/page/tfenne
  date: '2006-11-22 21:22:49 +0100'
  date_gmt: '2006-11-22 21:22:49 +0100'
  content: |-
    You have to understand that as disk densities get greater and greater the RPM of a drive is as misleading as a MHz/GHz number for a CPU.  Meaning that a at a given density it matters, but that a 160GB drive that spins at 5400RPM will actually be able to perform sequential reads as fast if not faster than a 100GB drive at 7200RPM.

    Of course, at a give size, RPM does improve things...and it'll always help seek times.  But RPM isn't everything these days.
- id: 13
  author: Daniel WECK
  author_email: daniel.weck@free.fr
  author_url: ''
  date: '2006-11-23 00:52:36 +0100'
  date_gmt: '2006-11-23 00:52:36 +0100'
  content: |-
    SuperDuper! is nice indeed, but I use Intego's PersonalBackup (http://www.intego.com/personalbackup/) to backup a copy of my current Mac OS X Tiger system.

    It basically makes a clone copy of the entire filesystem, and keeps it synchronized as well. Nice job so far.

    One other option is to use rsync, there are several tutorials out there to make a real bootable clone copy, such as this one:
    http://www.egg-tech.com/mac_backup/

    For my system backup, I use a 2.5" firewire+usb external drive so I can do a straight-forward physical swap of the disk in case of an unfortunate hard drive crash. All my 2.5" hard disks are 5400 rpm ATA100, 60GB and 80GB, from Western Digital and Seagate.

    For my data backup, I have an external 3.5" drive (firewire 400 and usb 2.0).

    Additionally, I use a NSLU2 to provide drive shares over my Wifi LAN. ;)
- id: 14
  author: Martijn Dashorst
  author_email: dashorst@users.sourceforge.net
  author_url: http://jroller.com/page/dashorst
  date: '2006-11-23 10:06:45 +0100'
  date_gmt: '2006-11-23 10:06:45 +0100'
  content: |-
    Yep, I figured that (the RPM thing), but given that I found booting from my firewire 7200 rpm drive much faster than doing so from my current 100GB disk, I figured why not wait until the 120 or 160 7k2 drives arrive. Shouldn't be that long.

    The slug thing is something I'm still considering. But first I want the 100mbit wifi to become available ;-).
- id: 15
  author: Marc Schipperheyn
  author_email: m.schipperheyn@gmail.com
  author_url: http://www.jroller.com/page/mschipperheyn
  date: '2006-11-26 13:52:21 +0100'
  date_gmt: '2006-11-26 13:52:21 +0100'
  content: Why not just replace the drive. It should not be that hard. BTW, check
    out the dear mr. Jobs letter on my blog. Looking forward to 2.0!
---
<p>After a full new reinstall on my Mac Book Pro (first gen), I decided to create multiple partitions and take on backing up my data. Fortunately, Mac OS provides a ton of good backup tools: <a href="http://www.grapefruit.ch/iBackup/">iBackup</a> and <a href="http://www.shirt-pocket.com/SuperDuper/">SuperDuper!</a>.</p>
<p>
The former (iBackup), is great for the casual backup: it backs up all settings and data from applications. Restoring is very easy and convenient. I had my MBP up and running in no time using this tool. I don't like that I am not able to easily create bootable disk images using this tool.</p>
<p>
For creating (bootable) disk images I discovered that Super Duper! works great. I am seriously considering to shell out the necessary $$$ to use this program. Especially for trying out drivers and updates it has a great solution: sandbox images. I suggest you try both of these apps, because making a backup never has been easier: all you need is a place to store your data.</p>
<p>
The 100GB 4200RPM harddisk (G in gibi, not giga) in my MBP is now partitioned into 3 partitions: 1 boot OS X, 1 data and 1 bootcamp (winxp). The latter still has to be installed though, as I haven't got a slipstreamed SP2 Windows XP disk around. For backup purposes I use an external USB2 drive (320GB, 7200RPM), and that works great. It is fast, easy and very convenient to add my other drives in cases of transferring large amounts of data.</p>
<p>
Though I love my Mac Book Pro, I wish I could enlarge the harddisk and make it speedier: 120GB or 160GB spinning at 7200RPM would be very, very welcome. Unfortunately the current offerings in these sizes are available in 5400RPM only.</p>
