---
layout: post
status: publish
published: true
title: Wicket 1.2-rc2 availability
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 62
wordpress_url: http://martijndashorst.com/2006/04/20/wicket-12-rc2-availability/
date: '2006-04-20 06:52:44 +0200'
date_gmt: '2006-04-20 06:52:44 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>
To keep our release cycle moving, I have created and uploaded a new RC release of 1.2, with several bugs fixed, and some additional localized messages as defaults. Keep them coming! Please submit your language file using the Java unicode format as used in the finnish and hungarian examples.</p>
<p>
We now have:</p>
<ul>
<li>english</li>
<li>french</li>
<li>german</li>
<li>finnish</li>
<li>danish</li>
<li>hungarian</li>
<li>portugese (brasilian)</li>
<li>chinese (taiwan)</li>
</ul>
<p>
Looking at our frappr map we can at least get 10 or so more languages implemented (japanese, swedish, norwegian, spanish, romainian, czech, polish, indian, farsi, arabic, etc)! And of course we should get someone to submit a Klingon and Swedish Chef version (does anyone know the locale keys for that)?</p>
<p>
The list of changes between RC1 and RC2:</p>
<ul>
<li>Added EqualPasswordInputValidator, which doesn't show the user input in its feedback message.</li>
<li>Improved error message handling when exceptions occur during validation.</li>
<li>Fixed encryption issue of password, maintaining backwards compatibility, and implementing correct URL encryption using URL safe base64 encryption.</li>
<li>Added Brazilian translation of our Application.properties</li>
<li>fixed FormcomponentFeedbackBorder, which didn't display when it should</li>
<li>override setModel and added setList. The override on setModel does an additional remove of the children so that - even if optimizeItemRemoval == true - the listview will be rendered with the actual contents. setList is a convenience method and is consitent with the List constructor.</li>
<li>fixed window checker for case where app is configured for server root and has no web app name.</li>
</ul>
<p>
Have fun!</p>
<p>
<b>NOTA BENE</b> The sourceforge upload server has let me down. It took  over 2 hours to release what it currently available from the download servers, but two packages are still missing: Wicket quickstart and the Wicket Spring packages. I am unable to upload and attach the release files to the Wicket project so you will have to wait for those projects to come available. As the contents of those packages hasn't changed other than the version number, you'll be safe using the wicket-spring jars from 1.2-rc1 for the moment.</p>
