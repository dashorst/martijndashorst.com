---
layout: post
status: publish
published: true
title: What? No JavaDoc for javax.persistence?
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 83
wordpress_url: http://martijndashorst.com/2006/03/13/what-no-javadoc-for-javaxpersistence/
date: '2006-03-13 11:05:07 +0100'
date_gmt: '2006-03-13 11:05:07 +0100'
categories:
- java
- hibernate
tags: []
comments:
- id: 88
  author: defectus
  author_email: defectus@seznam.cz
  author_url: http://www.defectus.org/news.php
  date: '2006-03-13 11:49:43 +0100'
  date_gmt: '2006-03-13 11:49:43 +0100'
  content: In my opinion this is because the persitence layer is part of Oracle Toplink
    Essential unlike the rest of the Java 5 EE that is mainly part of of the Glassfish
    project. If you're looking for Javadoc for persitence try to search JBoss (namely
    Hibernate) site ;-)
- id: 89
  author: Mats Henricson
  author_email: mats@henricson.se
  author_url: http://www.henricson.se/mats
  date: '2006-03-13 12:32:23 +0100'
  date_gmt: '2006-03-13 12:32:23 +0100'
  content: |-
    No, defectus, even if you look at, and use, JBoss, you will end up importing the same classes Martijn talks about.

    We noticed the same lack of documentation just a few days ago, and we also found it to be quite disturbing.

    But, then again, we can always buy the expensive books that are soon to be published...?
- id: 90
  author: defectus
  author_email: defectus@seznam.cz
  author_url: http://www.defectus.org/news.php
  date: '2006-03-13 13:53:45 +0100'
  date_gmt: '2006-03-13 13:53:45 +0100'
  content: "Oops, you're right Mats ! You know, I'm playing a lot with EJB3 and if
    I encounter any problem I take a look in to the EJB3 specification (http://java.sun.com/javaee/5/javatech.html).
    \nBut you must bear in mind that in EJB3 everything is in a move and things are
    changing from release to release that it's impossible to maintain up-to-date javadoc.
    Hopefully the documentation will done until final release date ..."
- id: 91
  author: Martijn Dashorst
  author_email: dashorst@users.sf.net
  author_url: http://www.jroller.com/page/dashorst/
  date: '2006-03-13 14:15:54 +0100'
  date_gmt: '2006-03-13 14:15:54 +0100'
  content: |-
    I was under the impression that the EJB3 spec, and especially the javax.persistence package was finished. So I expect there to be some form of documentation.

    I tried the Hibernate documentation, but that is a mix'n'match between old versions of the javax.persistence and Hibernate specific annotations, while there seems to be a newer version of the EJB3 jar available for a couple of months already.

    Sorry to say, but for a specification this is rather poor. It is not that they don't get paid to work on the specification is it? Fortunately I didn't pay for it :-)
- id: 92
  author: defectus
  author_email: defectus@seznam.cz
  author_url: http://www.defectus.org/news.php
  date: '2006-03-13 15:09:08 +0100'
  date_gmt: '2006-03-13 15:09:08 +0100'
  content: I don't pay them as well :-) And as I said, from my point of view, the
    problem is Oracle - they're responsible for persistence part so they should provide
    thorough documentation. And it's a pity that such company is not even able to
    provide javadoc ...
- id: 93
  author: Eelco Hillenius
  author_email: eelco12@users.sourceforge.net
  author_url: ''
  date: '2006-03-13 22:48:28 +0100'
  date_gmt: '2006-03-13 22:48:28 +0100'
  content: I was under the impression I just didn't look hard enough. There is absolutely
    no good reason imo NOT to write Javadocs, even if it is a moving target. As soon
    as you publish something public like that, at least some basic javadoc should
    be provided.
- id: 94
  author: defectus
  author_email: defectus@seznam.cz
  author_url: http://www.defectus.org/news.php
  date: '2006-03-14 09:27:08 +0100'
  date_gmt: '2006-03-14 09:27:08 +0100'
  content: It should be like this, but I must confess that I make documentation as
    a last part of a project - when everything is stable and I'm sure that the documentation
    won't change ...
- id: 216
  author: pachif
  author_email: pachif81@yahoo.com.ar
  author_url: ''
  date: '2007-02-12 13:20:25 +0100'
  date_gmt: '2007-02-12 12:20:25 +0100'
  content: "I thought , the main problem (maybe) that there are no ways to do things
    (persistence, mappings, relational DBs, etc.) in a STANDAR form, the things we
    look now, will later change to another form to do this issues. \r\nAll vendors
    of that part of solutions has their own form to resolve de problem, implementating
    things in diferents way, with its benefits and disavantages. And Is a part of
    us wich solution we prefeer.\r\nThere are no stable documentacion, always is in
    change, the main question is THE PErSISTENT API will change in future?"
---
<p>
After searching the 'net for some documentation on the upcoming and much touted <a href="http://java.sun.com/javaee/5">JEE5</a> persistence API I couldn't help noticing the<br />
<strong>ABSOLUTE ABSENCE OF API DOCUMENTATION</strong><br />
on the <em>whole</em> of the <tt>javax.persistence</tt> package. Probably the most popular, and awaited package from the whole JEE5 stack has <strong><a href="http://java.sun.com/javaee/5/docs/api/javax/persistence/package-summary.html">no documentation</a></strong>.</p>
<p>
This is sub par from Sun and the persistence API spec. Am I the first one that thinks this is a serious oversight? Will this not hinder adoption of the persistence API?</p>
<p>
Lot's of people rightfully criticize open source projects for not writing (enough) documentation. I know the Wicket documentation could be better, but at least our <a href="http://wicketframework.org/wicket-1.1/apidocs/index.html">API docs</a> are quite solid.</p>
