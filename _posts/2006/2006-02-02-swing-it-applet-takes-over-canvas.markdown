---
layout: post
status: publish
published: true
title: Swing it! applet takes over canvas
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 99
wordpress_url: http://martijndashorst.com/2006/02/02/swing-it-applet-takes-over-canvas/
date: '2006-02-02 08:23:26 +0100'
date_gmt: '2006-02-02 08:23:26 +0100'
categories:
- wicket
- java
tags: []
comments:
- id: 112
  author: Jonathan Locke
  author_email: jonl@muppetlabs.com
  author_url: ''
  date: '2006-02-02 10:01:45 +0100'
  date_gmt: '2006-02-02 10:01:45 +0100'
  content: "In my prototype, this code creates a fully functional applet in Wicket:\n\npublic
    class Home extends WebPage\n{\n        public Home()\n        {\n                add(new
    Applet(\"applet\", Wapplet.class));\n        }\n}\n\npublic class Wapplet implements
    IAppletInitializer\n{\n        public void init(Container container, Object model)\n
    \       {\n            container.setLayout(new FlowLayout());\n            container.add(new
    JButton(\"Button 1\"));\n            container.add(new JButton(\"Button 2\"));\n
    \           container.add(new JButton(\"Button 3\"));\n        }\n}\n\n<?xml version=\"1.0\"
    encoding=\"UTF-8\"?>\n<html xmlns=\"http://www.w3.org/1999/xhtml\" >\n<head>\n
    \   <title>Wapplet Application</title>\n</head>\n<body>\n\n\t<applet wicket:id=\"applet\"/>\n\n</body>\n</html>"
- id: 1187
  author: ketan gote
  author_email: ketan.gote@gmail.com
  author_url: ''
  date: '2007-04-02 11:27:15 +0200'
  date_gmt: '2007-04-02 10:27:15 +0200'
  content: "hi\r\nhad you solved above problem,\r\ni am also having same problem,
    \r\ncan you help me\r\n\r\nregard's\r\nketan d.gote"
- id: 55975
  author: sr
  author_email: stuart.rose@pnl.gov
  author_url: ''
  date: '2008-04-24 19:43:21 +0200'
  date_gmt: '2008-04-24 18:43:21 +0200'
  content: "I like the Wapplet name, however in Firefox, with java plug-in 1.6.0_03
    I get the following exception in the Java Console. \r\n\r\nJava Plug-in 1.6.0_03\r\nUsing
    JRE version 1.6.0_03 Java HotSpot(TM) Client VM\r\n\r\n----------------------------------------------------\r\nAPPLET
    tag missing CODE parameter.\r\njava.lang.NullPointerException: name\r\n\tat sun.applet.AppletClassLoader.getResourceAsStream(Unknown
    Source)\r\n\tat sun.applet.AppletPanel$7.run(Unknown Source)\r\n\tat java.security.AccessController.doPrivileged(Native
    Method)\r\n\tat sun.applet.AppletPanel.createApplet(Unknown Source)\r\n\tat sun.plugin.AppletViewer.createApplet(Unknown
    Source)\r\n\tat sun.applet.AppletPanel.runLoader(Unknown Source)\r\n\tat sun.applet.AppletPanel.run(Unknown
    Source)\r\n\tat java.lang.Thread.run(Unknown Source)"
---
<p><a href="http://www.jroller.com/page/jonathanlocke">Jonathan Locke</a> never lost his love for Swing, and now he's made it possible to mash-up <a href="http://wicket.sf.net">Wicket</a> web applications with the old web technology: applets. His old high school friend <a href="http://weblogs.java.net/blog/timboudreau/">Tim Boudreau</a> has an article about it.</p>
<p>
Even though they are convinced it has to do with Ajax, I think it is much more a precursor for the new <a href="http://developer.mozilla.org/en/docs/Drawing_Graphics_with_Canvas">Canvas technology</a> that seems to get a lot of <a href="http://digg.com/technology/Firefox_Canvas_based_First_Person_Shooter_">attention</a>. So who will create a <i>First Person Blogger</i> where you can hunt down blog spammers? Or a <i>Grand Theft Shopping Cart</i>?</p>
<p>
Many people ask whether <a href="http://blogs.msdn.com/ie/">Internet Explorer</a> will ever support the canvas, so the applet may get us graceful degredation! And best of all: <b>APPLETS ARE ALREADY HERE!</b></p>
<p>
Be sure to watch <a href="http://www.jroller.com/page/gfx">this blog</a> (or <a href="http://weblogs.java.net/blog/gfx/">this one</a>) of one of our greatest fans, as he already enjoyed Wicket without Swing:</p>
<blockquote><p><i>Anyway, Wicket was the only web oriented thingie that got me excited in a long time and now they are planning to mix it with Swing. Damn, how better could this framework be?</i></p></blockquote>
