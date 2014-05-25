---
layout: post
status: publish
published: true
title: Hibernate 3.1-something performance problems
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 16
wordpress_url: http://martijndashorst.com/2006/11/27/hibernate-31-something-performance-problems/
date: '2006-11-27 12:53:41 +0100'
date_gmt: '2006-11-27 12:53:41 +0100'
categories:
- java
- hibernate
tags: []
comments:
- id: 9
  author: Benoit
  author_email: ''
  author_url: ''
  date: '2006-11-27 17:39:34 +0100'
  date_gmt: '2006-11-27 17:39:34 +0100'
  content: try hibernate.jdbc.wrap_result_sets = true
---
<p>In our current project, we found out that Hibernate uses the column-names in queries to retrieve data from the resultsets. Now this is usually not a problem (it debugs pretty good thank you very much), but it adds quite the overhead for our Oracle driver. About 50% or more of the time for retreiving objects (dehydrating them) is spent in finding the correct column.</p>
<p>
We are using a pretty archaic version of Hibernate (3.1 something), and therefore I was looking at 3.2 to see if this has improved. I found the following todo comment in the dehydrate logic:</p>
<pre>
for ( int i = 0; i //TODO:  this is kinda slow...</b>
    }
}
</pre>
<p>Something tells me there is room for improvement.</p>
