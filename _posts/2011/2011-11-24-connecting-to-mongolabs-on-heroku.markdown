---
layout: post
status: publish
published: true
title: Connecting to MongoLabs on heroku
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 501
wordpress_url: http://martijndashorst.com/blog/?p=501
date: '2011-11-24 23:54:41 +0100'
date_gmt: '2011-11-24 22:54:41 +0100'
categories:
- wicket
- technology
tags:
- Heroku
- MongoLabs
- MongoDB
comments:
- id: 61339
  author: James Ward
  author_email: james@jamesward.org
  author_url: http://www.jamesward.com
  date: '2011-11-28 02:16:14 +0100'
  date_gmt: '2011-11-28 01:16:14 +0100'
  content: "This isn't well documented at the moment.  Sorry.  It's something we are
    working on.  Check out a Java example here:\r\nhttps://github.com/jamesward/jetty-mongo-session-test/blob/master/src/main/java/com/heroku/test/Main.java\r\n\r\n-James"
---
<p>For an internal Topicus application I wanted to deploy to <a href="http://heroku.com">Heroku</a> and utilize MongoDB through <a href="http://devcenter.heroku.com/articles/mongolab">MongoLabs</a>. The main reason to use MongoLabs: they have a free 240MB database plan, and I wanted to try MongoDB to see how it would work.</p>
<p>Getting it to run on Heroku was kind of a challenge since I want to build a Java/Wicket application, and most documentation relies on Ruby deployments. In order to connect to MongoLabs you need to do the following:</p>
<pre>MongoURI mongoURI = new MongoURI(System.getenv("MONGOLAB_URI"));
DB connectedDB = mongoURI.connectDB();
connectedDB.authenticate(mongoURI.getUsername(), mongoURI.getPassword());</pre>
<p>What evaded me was that you need to explicitly authenticate using the provided username and password, otherwise you will get authorization errors. The documentation didn't show this as a required step unfortunately.</p>
<p>Of course you should check if authentication succeeded, and that no error occurred.</p>
