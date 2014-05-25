---
layout: post
status: publish
published: true
title: Hibernate 3.1-something performance problems cont&#39;d
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 15
wordpress_url: http://martijndashorst.com/2006/11/28/hibernate-31-something-performance-problems-contd/
date: '2006-11-28 11:05:47 +0100'
date_gmt: '2006-11-28 11:05:47 +0100'
categories:
- java
- hibernate
tags: []
comments:
- id: 5
  author: Benoit WIART
  author_email: ''
  author_url: http://www.ubik-ingenierie.com
  date: '2006-11-28 11:37:45 +0100'
  date_gmt: '2006-11-28 11:37:45 +0100'
  content: You're welcome
- id: 6
  author: Martijn Dashorst
  author_email: dashorst@users.sourceforge.net
  author_url: http://jroller.com/page/dashorst
  date: '2006-11-28 12:23:54 +0100'
  date_gmt: '2006-11-28 12:23:54 +0100'
  content: LOL, thanks very much for this quick fix. You're a man of few words but
    great deeds!
- id: 7
  author: Craig
  author_email: ''
  author_url: ''
  date: '2006-11-28 19:29:52 +0100'
  date_gmt: '2006-11-28 19:29:52 +0100'
  content: Pretty interesting find, I've worked with hibernate for quite a while now
    and never knew about this feature.  The only thing I'd question is how much does
    this increase the memory foot print of an application.  It looks like for every
    entity you have mapped in your application you will have a cache (map) of column
    name to index number.  This is probably ok, unless your application has thousands
    or entities.  Either way, nice find.
- id: 8
  author: Benoit WIART
  author_email: ''
  author_url: http://www.ubik-ingenierie.com
  date: '2006-11-30 10:36:30 +0100'
  date_gmt: '2006-11-30 10:36:30 +0100'
  content: |-
    Hibernate seems to maintain this cache per resulset through the loader (see org.hibernate.jdbc.ResultSetWrapper and org.hibernate.jdbc.ColumnNameCache)
    For others (good ?) jdbc implementations this trick is done inside the driver...
- id: 57418
  author: Optimizing Oracle and Hibernate performance &laquo; Rambling about&#8230;
  author_email: ''
  author_url: http://ramblingabout.wordpress.com/2009/01/07/optimizing-oracle-and-hibernate-performance/
  date: '2009-01-07 16:31:42 +0100'
  date_gmt: '2009-01-07 15:31:42 +0100'
  content: "[...] See http://martijndashorst.com/blog/2006/11/28/hibernate-31-something-performance-problems-contd/
    hibernate.jdbc.wrap_result_sets = [...]"
---
<p>In a response to my <a href="http://www.jroller.com/page/dashorst?entry=hibernate_3_1_something_performance">previous rambling</a>, Benoit was kindly enough to point me at a severely under-documented Hibernate configuration property:</p>
<pre>hibernate.jdbc.wrap_result_sets = true</pre>
<p>I did some performance tests with getting some date out of our database and look and behold:</p>
<pre>Method                                       Time(ms)     Count
oracle.findColumn(String)                      2793       19292
oracle.getLong(String)                         1630       12836
oracle.getBigDecimal(String)                    397        1068
oracle.getInt(String)                           258        2152
oracle.getString(String)                        192        1068
oracle.getTimestamp(String)                     190        1068
oracle.getDouble(String)                        101        1068
oracle.getBoolean(String)                        21          32

hibernate.ResultSetWrapper.findColumn(String)   409       19292
hibernate.ResultSetWrapper.getLong(String)      225       12836
hibernate.ResultSetWrapper.getInt(String)        63        2152
hibernate.ResultSetWrapper.getBigDecimal(String) 52        1068
hibernate.ResultSetWrapper.getDouble(String)     21        1068
hibernate.ResultSetWrapper.getTimeStamp(String)  21        1068
hibernate.ResultSetWrapper.getString(String)     20        1068
hibernate.ResultSetWrapper.getBoolean(String)     3          32
</pre>
<p>If you use Oracle in combination with Hibernate, I urge you to use the setting Benoit kindly provided (your mileage may vary though).</p>
