---
layout: post
status: publish
published: true
title: Wicket StockQuote component
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 141
wordpress_url: http://martijndashorst.com/2005/08/17/wicket-stockquote-component/
date: '2005-08-17 16:24:51 +0200'
date_gmt: '2005-08-17 16:24:51 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 155
  author: Jonathan Locke
  author_email: jonl@muppetlabs.com
  author_url: ''
  date: '2005-08-20 10:17:53 +0200'
  date_gmt: '2005-08-20 10:17:53 +0200'
  content: "Here's another approach for this particular problem that's nicer since
    we already have a label superclass to draw on:\n\npublic class StockQuoteLabel
    extends Label \n{\n  public StockQuoteLabel(String id, final String symbol)\n
    \ {\n    super(id, new AbstractReadOnlyModel()\n    {\n      public Object getObject(Component
    component)\n      {\n        return soapThingy(symbol);\n      }\n    }\n  }\n}\n\nI
    haven't tested this, but it should work fine."
---
<p>
On <a href="http://www.theserverside.com/news/thread.tss?thread_id=35900">The Serverside.com</a> there is a JSF Custom Component article, and probably you came from there expecting the full explanation of my StockQuote example component. It is currently 15:00 (3pm) so I have to do some business before I have time for a full disclosure.<br />
In the mean time, you may want to check out the CVS code:</p>
<p>
Via viewcvs, you can see the files <a href="http://cvs.sourceforge.net/viewcvs.py/wicket/wicket-examples/src/java/wicket/examples/stockquote">here</a>. The component is called 'StockQuoteLabel', and is defined in the file <a href="http://cvs.sourceforge.net/viewcvs.py/wicket/wicket-examples/src/java/wicket/examples/stockquote/StockQuoteLabel.java?rev=1.1&view=log">StockQuoteLabel.java</a>.<br />
The web page files are <a href="http://cvs.sourceforge.net/viewcvs.py/wicket/wicket-examples/src/java/wicket/examples/stockquote/StockQuote.html?rev=1.1&view=auto">StockQuote.html</a> and <a href="http://cvs.sourceforge.net/viewcvs.py/wicket/wicket-examples/src/java/wicket/examples/stockquote/StockQuote.java?rev=1.1&view=auto">StockQuote.java</a>.</p>
