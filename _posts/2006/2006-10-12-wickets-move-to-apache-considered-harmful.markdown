---
layout: post
status: publish
published: true
title: Wicket&#39;s move to Apache considered harmful?
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 24
wordpress_url: http://martijndashorst.com/2006/10/12/wickets-move-to-apache-considered-harmful/
date: '2006-10-12 23:42:50 +0200'
date_gmt: '2006-10-12 23:42:50 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 17
  author: apache quality skeptic
  author_email: ''
  author_url: ''
  date: '2006-10-13 00:11:41 +0200'
  date_gmt: '2006-10-13 00:11:41 +0200'
  content: "<i>For many organisations, the Apache brand is synonymous with quality,
    stability and a solid legal backing. </i>\n\nWhile I don't disagree with the assertion
    that many people think that, it's rather ridiculous. \n\nWhile Apache has some
    quality software (httpd being a good example) they've got a lot of crap too. The
    legal backing is \"WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND\"."
- id: 18
  author: n8han
  author_email: ''
  author_url: http://technically.us/n8/
  date: '2006-10-13 00:21:40 +0200'
  date_gmt: '2006-10-13 00:21:40 +0200'
  content: Look, it's working--Wicket is already getting more attention! Also, I won't
    miss that horrible sourceforge bug tracker.
- id: 19
  author: Jess Sightler
  author_email: jesse.sightler@gmail.com
  author_url: http://www.jroller.com/page/jsight/
  date: '2006-10-13 16:21:03 +0200'
  date_gmt: '2006-10-13 16:21:03 +0200'
  content: |-
    I guess I can't really say that Wicket's choice to move to Apache is a bad thing, per se.

    I just think Apache's choice to take projects on in droves (esp. in areas where they already maintain a multitude of choices) is probably a mistake.

    You state that you prefer Apache, as it feels more like a community than an ISP, but if they keep adding projects (esp. dead ones) like they do, they are eventually going to find themselves in the same shape.

    The "apache quality skeptic" is exactly right, and the constant addition of new projects that serve the same roles is only serving to serving to dilute the Apache brand, IMO.
- id: 20
  author: Closet Wicket lover
  author_email: ''
  author_url: ''
  date: '2006-10-14 05:31:41 +0200'
  date_gmt: '2006-10-14 05:31:41 +0200'
  content: |-
    I hope that Apache will help Wicket more than it will harm it. Most of all I hope that Apache doesn't ruin you the way it has ruined Tapestry. Tapestry has become one big sludgey unmanageable behemoth. I hope you resist scope creep and keep Wicket lean and mean.

    Best,
    Closet Wicket lover
---
<p>Jesse Sightler asked the following question in the comment system regarding <a href="http://wicketframework">Wicket's</a> move to Apache:</p>
<blockquote><p>Er, how many web frameworks can Apache host? Aren't you guys afraid of being lost in the piles that are already there?</p></blockquote>
<p>
The answer is: we aren't afraid of being lost over there. The question never arised when we moved to sourceforge, and the number of open source web frameworks is far greater at our current home than at Apache. I think that moving to Apache will open doors previously closed to Wicket. Many companies will not accept code that is not backed by a legal entity. For many organisations, the Apache brand is synonymous with quality, stability and a solid legal backing.</p>
<p>
The reasons for us to join Apache is that we think it is one of the leading open source communities, whereas sourceforge is as much a community as your ISP is. It provides a great (however sometimes not so excellent) service to the open source community at large, but doesn't foster a community.</p>
<p>
We think that Wicket is a great addition to the Apache foundation: we have a very active and friendly community, we have a great framework and we see enough possibilities for us to cooperate with existing frameworks within the Apache foundation. Being close together might actually help drive our and the other communities ahead.</p>
<p>
I don't have any illusions for merging our framework with MyFaces, Tapestry or Struts but I think that some parts of our frameworks could benefit of being shared. There have been talks on creating a shared property resolver to replace the now stagnant <a href="http://www.ognl.org">OGNL library</a>. Other possibilities for cooperation exist with <a href="http://incubator.apache.org/felix">Felix</a>, <a href="http://jackrabbit.apache.org">Jackrabbit</a>, <a href="http://portals.apache.org/">Portals</a>, and others.</p>
<p>
I think that us moving to Apache will not only increase the visibility of the Wicket framework, but also strengthen both the Wicket and the Apache brand. Wicket because it now is part of an open source, highly visible and open community, Apache because it gains one of the best web frameworks out there and the Apache community will be expanded with <a href="http://frappr.com/wicket">enthousiastic and friendly Wicket developers from over the whole world</a>.</p>
<p>
So, is joining Apache considered harmful? I don't think so and a many of our community share that answer with me.</p>
