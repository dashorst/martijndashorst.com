---
layout: post
status: publish
published: true
title: Apache Wicket 1.4-m3 with improved generics
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 384
wordpress_url: http://martijndashorst.com/blog/2008/07/14/apache-wicket-14-m3-with-improved-generics/
date: '2008-07-14 11:11:54 +0200'
date_gmt: '2008-07-14 10:11:54 +0200'
categories:
- wicket
tags: []
comments:
- id: 57084
  author: Jörn Zaefferer
  author_email: joern.zaefferer@gmail.com
  author_url: http://bassistance.de
  date: '2008-07-17 15:31:10 +0200'
  date_gmt: '2008-07-17 14:31:10 +0200'
  content: "That thread is slightly going overboard and I don't want to register on
    Nabble (storing passwords in cleartext, bah), so I'll share my thoughs on the
    m3 here:\r\n\r\nI just updated my current project to see what will happen. Its
    not encouraging. My impression is that generified models are worthless without
    generified components. Most of the time adding the type parameter gains nothing
    then to satisfy the compiler. The only place where I can remove a cast is in ListView's
    populateItem method, where I can use getModelObject directly, without having to
    cast first. All in all I have to add code to get very barely more type safety.\r\nIn
    the case of PropertyModel I gain nothing, as the constructor still takes Object,
    while I don't ever call the generified get/setObject methods myself.\r\n\r\nI'm
    having two TextField subclasses to implement my own Converter for certain fields.
    Just registering a new Converter doesn't do the trick, as I need to have a special
    converter for one Long field. Without generics I can overwrite the getConverter()
    method, with generics I can't, as getConverter doesn't care for the component
    type, just for the type of the class being passed. So I'd replace Object with
    X and still have to cast to Long.\r\n\r\nHaving generic Links doesn't help either
    - my Links all interact with the parent component's model object, usually a page
    or panel. Setting models to each and every nested components seems like a waste
    of code as using the parent model object works fine.\r\n\r\nI hope this helps
    in deciding how to move on!\r\n\r\nRegards\r\nJörn"
---
<p>Help the Apache Wicket team to determine the future of your Wicket based web application development. We have released our third and hopefully final milestone release of our Java 5 based web framework and are anxious to receive feedback on our use of generics.</p>
<p>This release is our final take on how to apply generics to our codebase with restraint. We hope to provide an elegant programming model without having to specify generic parameters everywhere, while still providing type safety when you need it.</p>
<p>A significant change from the earlier Wicket 1.4 milestone versions is that <tt>Component</tt> is no longer generified. This means that <tt>Component</tt> and most of its subclasses in Wicket do not take a class-level type parameter. Some <tt>Component</tt> subclasses remain generified, such as <tt>Link</tt>, <tt>Form</tt>, <tt>FormComponent</tt>, <tt>ListView</tt>, etc. You can read more details regarding these changes here:</p>
<ul>
<li><a href="http://wicket.apache.org/wicket-14-m3-news.html" title="Wicket 1.4 M3 News">New and noteworthy in 1.4-m3</a></li>
<li><a href="http://www.nabble.com/generics-to18083910.html#a18083910">New generics discussion</a></li>
</ul>
<p>We feel that this might provide a good middle ground between being unable to add typing to <tt>IModel</tt> on one hand and a proliferation of unneeded typing information on modelless components on the other hand. Your feedback is appreciated!</p>
<p><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.4-m3">Download Wicket 1.4-m3</a> now and help us decide whether to tone down, remove or increase the application of Java 5 generics to our API. We have started the discussion on the user mailing list:</p>
<ul>
<li><a href="http://www.nabble.com/users%2C-please-give-us-your-opinion%3A-what-is-your-take-on-generics-with-Wicket-td17589984.html">What is your take on generics with Wicket</a></li>
</ul>
<p>Eager people click here to download the distribution, others can <a href="http://wicket.apache.org/news.html#News-wicket1.4-m3">read further</a>:</p>
<ul>
<li><a href="http://www.apache.org/dyn/closer.cgi/wicket/1.4-m3">http://www.apache.org/dyn/closer.cgi/wicket/1.4-m3</a></li>
</ul>
<p>We thank you for your patience and support.</p>
<p>The Wicket Team</p>
