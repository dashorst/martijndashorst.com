---
layout: post
status: publish
published: true
title: 'iPhoto Considered Harmful'
author: Martijn Dashorst
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
date: '2014-08-25 08:30:00 +0100'
---

<img src="/uploads/iPhotoRepairingDatabase.png" width="100%" alt="Screenshot of iPhoto repairing my library">

I collect my precious photos in iPhoto. iPhoto is Apple's photo
management application for families--or so I thought. Unfortunately
while designing the application Apple in all its wisdom thought that
the personal computer would be the 'Digital Hub', without taking into
account that people would own multiple PC's to access that Digital
Hub--in our case our photo library.

The last few weeks I have been repairing, rebuilding and restarting my
iPhoto library to no avail. iPhoto is completely and utterly unsuited
as a photo library management application. It looses track of your
photos, it looses metadata, EXIF information and worst of all denies
you access to the precious photos of your family on a regular basis.

iPhoto's library is not just a folder structure with your photos neatly
distributed around it such as normal users would structure a photo
library, but it is a structure that encompasses a database. I should
give the Apple engineers credit for not putting the actual photos into
said database--if you open the libary you can see the originals sitting
comfortably in a folder called Masters, organized by the date of import.

To accomodate the following usecases we keep our iPhoto libraries on a
NAS:

 - accessibility from multiple computers in our home network
 - redundancy in hardware through a RAID-1 setup, which uses two drives
   to store all data twice, also called mirrorring
 - automatic backups of our memories through autobackup tools supplied
   by the NAS vendor

For the last 4 weeks since I uploaded my vacation photos to my iPhoto
library I cross my fingers in idle hope every time I start iPhoto that
the gods that be will allow unhampered access to my photos. 

I have memorized the <cmd-option> startup key sequence necessary to
coerce iPhoto to do its magic on the database:

 - [repair permissions][1] ([what's up with that, Apple?][2])
 - repair thumbnails
 - repair database and
 - rebuild database. 
 
I have started all options in vain. I had to create a new, empty iPhoto
library and import all photos from my broken beyond help original
library. This removed all metadata, all event information and even
modified EXIF data.

<img src="/uploads/iPhotoUpdatingLibrary.png" style="float:right;max-width:50%;margin-left:1em" alt="Screenshot of iPhoto updating my library">
 
With this new library in place it took two nights of work to
recategorize all photos and movies into the vacations we have had over
the years. We did loose all metadata associated with the photos: the
detailed location information added because our 2005 camera didn't have
a GPS for example.

> Insanity is repeating the same mistakes and expecting different results.

And yet when we were selecting the photos of our last vacation to put
into a photoalbum, iPhoto randomly corrupted the database **again**.
This with a clean library only 2 weeks old. I had to do the restart
machine, repair permissions, rebuild library and repair database rain
dance all over again. I was **this close** to raiding the freezer of a
chicken and waving it in front of my MacBook.
 
I desperately await the day Apple pulls the plug on iPhoto. I hope the
new Photos platform will be of this day and age and won't force me to
start using Google's Picasa--they already read all my email and search
queries, I don't want them to own my photos too.

Can I fault the developers at Apple for this? I'd like to but I guess a
multi-user design for the underlying system didn't make the drawing
board as that doesn't demo well enough. I blame the internal system at
Apple that is responsible for such design decisions for this
monstrocity of an application.

After last couple of weeks' experience I consider iPhoto harmful, and
so should you.

[1]: http://support.apple.com/kb/PH2512
[2]: http://google.com/search?q=repair+permissions+mac
