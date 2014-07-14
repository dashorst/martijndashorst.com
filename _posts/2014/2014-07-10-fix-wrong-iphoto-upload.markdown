---
layout: post
status: publish
published: true
title: 'Fix wrong iPhoto upload'
author: Martijn Dashorst
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
date: '2014-07-10 18:30:00 +0100'
date_gmt: '2014-07-10 17:30:00 +0100'
categories:
---

When you select the wrong iPhoto library--say a backup copy of your
iPhoto library--and upload your son's birthday pictures, and then erase
your memory card to take more pictures, you find yourself in a pile of
hurt.

It is unclear if an rsync between both libraries will work: will the
extra photos appear in the library or not. Will they have an event
attached, etc. Your main library with over 5 years of photos of your
child is not something to experiment with.

So I figured that you need to find out the files that are present in one library and not in the other, and copy them to an outside location. From that point on, you can just import the photos using the standard iPhoto tooling into the correct library.

Now my NAS (a Synology) creates additional files and folders, and OS X
is also notorious for adding hidden folders. I particularly wanted to
exclude those files and folders as they were not instrumental in
re-importing the missing photographs.

Fortunately [rsync][1] has an [option to compare two folders and
synchronize the missing or updated files to a third location][2]. The
command below will copy over the missing or updated files in my master
iPhoto library from my backup iPhoto library to an external folder.

Note the exclusion of the "CR2" files--I exclude the RAW versions of my
photographs because I didn't want to have to edit 250 RAW pictures. The
JPGs will be good enough for this birthday party. If you care about
your RAWs then remove that line.

{% highlight bash %}
rsync --verbose --exclude=".AppleDouble" --exclude="*Syno*" \
      --exclude="@eaDir" \
      --exclude="*.CR2"  \
      -h  \
      --archive  \
      --ignore-existing  \
      /volume2/backup/iPhoto.photolibrary/Masters/2014/ \
      --compare-dest=/volume1/Photos/Liam.photolibrary/Masters/2014 \
      /volume1/Photos/2014
{% endhighlight %}

I can then import these photos from the /volume1/Photos/2014 folder
into my master iPhoto library. 

Of course note that this is provided as is and you should check if this
works for your usecase before running the script on your own photo
libraries. Use at your own risk!

[1]: http://rsync.samba.org/ftp/rsync/rsync.html
[2]: http://serverfault.com/questions/506005/compare-2-directories-and-copy-differences-in-a-3rd-directory
