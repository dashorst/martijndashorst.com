---
layout: post
status: publish
published: true
title: How I revived my HP ScanJet 3300c on OS X
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 372
wordpress_url: http://martijndashorst.com/blog/2008/06/08/how-i-revived-my-hp-scanjet-3300c-on-os-x/
date: '2008-06-08 18:46:54 +0200'
date_gmt: '2008-06-08 17:46:54 +0200'
categories:
- os x
tags: []
comments:
- id: 57054
  author: scottso
  author_email: imarugger-photo@yahoo.com
  author_url: ''
  date: '2008-07-05 18:00:59 +0200'
  date_gmt: '2008-07-05 17:00:59 +0200'
  content: I've been using this scanner on my iMac for about 2 1/2 years now.  It's
    not the greatest scanner, but it does the job, and I didn't have to buy a new
    one to use on the Mac.  I use the scanimage program that comes with, if I remember
    correctly, the sane drivers.
- id: 57582
  author: Matt Hancock
  author_email: matthew-h@paradise.net.nz
  author_url: http://www.wordpress.geek.nz
  date: '2009-05-21 02:45:39 +0200'
  date_gmt: '2009-05-21 01:45:39 +0200'
  content: Thanks for posting this information. I managed to pick up a second hand
    model for fairly cheap and this post was the first in the Google search. Cheers.
    :)
- id: 57849
  author: Max
  author_email: maxhentsch@web.de
  author_url: ''
  date: '2009-12-20 14:27:05 +0100'
  date_gmt: '2009-12-20 13:27:05 +0100'
  content: "I tried to make it work , but i have a little Problem,\r\nI installed
    all the Drivers and if i test the connection with the terminal it says \"3300c
    found\" but if i try to scan something it dont work , the scanner device makes
    a short noise but thats it ... any solutions ?\r\nSorry my english isnt the best
    :)"
- id: 60488
  author: iMac France
  author_email: carclub@hotmail.fr
  author_url: ''
  date: '2011-05-04 10:46:38 +0200'
  date_gmt: '2011-05-04 09:46:38 +0200'
  content: "Super, après installation des paquets \"SANE backends\" + \"libusb\" +
    \"TWAIN SANE Interface\" + \"SANE Preference Pane\" trouvés sur le site http://www.ellert.se/twain-sane/\r\nj'ai
    réussi à connecter mon vieux scanner Scanjet 3300c sur Mac OS X 10.6 Leopard (le
    scan était obsolète, puisque HP ne fournit même plus de driver pour Vista ou Windows
    7 et rien du tout pour Mac) , et à l'utiliser avec tout simplement le logiciel
    Aperçu, menu Fichier/importer depuis le scanner/SANE.\r\n\r\nSimple et efficace
    !\r\nC'est excellent.\r\nGRAND MERCI !!! :D"
- id: 60518
  author: David Mings
  author_email: mings@xs4all.nl
  author_url: http://none
  date: '2011-05-13 14:07:33 +0200'
  date_gmt: '2011-05-13 13:07:33 +0200'
  content: I too want to go back to my HP 3300C but which power brick came with it?
    I have several lying about but what are te specs listed on it?
- id: 65597
  author: Mikael
  author_email: miklu11@hotmail.com
  author_url: ''
  date: '2013-05-07 07:04:52 +0200'
  date_gmt: '2013-05-07 06:04:52 +0200'
  content: "Please install the Mac OS X 10.8 SDK package before installing the sane-backends
    10.8 SDK package . After I have followed these steps-\r\n2) Open \"Libsub - binary\"
    and install it. Then open Libsub SDK and install it.\r\n3) Open Sane Backends
    - and install binary and then SDK.\r\n\r\nIt doesn't allow to go further on that
    3) SDK. why ?"
---
<p>I had this old scanner laying around and found the need to scan some old photos. Of course I could take a picture of the picture using a 10MP digital camera, but somehow that isn't as pretty or convenient as just scanning.</p>
<p>
	Apparently I didn't search well enough for OS X scanner support last time I wanted to scan something. If you go looking for support for your old trusted Windows scanner after you've migrated to OS X, you may run into the same trouble I got myself in. Fortunately open source developers have provided the world with a <a href="http://www.ellert.se/twain-sane/">set of drivers for OS X</a> that enables your old trusted scanner under OS X. W00T!</p>
<p>
	Developers of <a href="http://www.ellert.se/twain-sane/">TWAIN SANE</a>: THANKS!</p>
