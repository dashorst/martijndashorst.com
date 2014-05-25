---
layout: post
status: publish
published: true
title: Wicket 1.2-rc3 available
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 58
wordpress_url: http://martijndashorst.com/2006/05/02/wicket-12-rc3-available/
date: '2006-05-02 09:01:35 +0200'
date_gmt: '2006-05-02 09:01:35 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 65
  author: Anders Holmbech Brandt
  author_email: ''
  author_url: ''
  date: '2006-05-02 10:14:27 +0200'
  date_gmt: '2006-05-02 10:14:27 +0200'
  content: |-
    hi,

    Cool with the maven2 repository but you should correct the link to: http://wicket.sourceforge.net/maven2

    regards

    Anders
- id: 66
  author: Paul Russell
  author_email: blog@paulrussell.org
  author_url: http://www.paulrussell.org/
  date: '2006-05-08 13:54:27 +0200'
  date_gmt: '2006-05-08 13:54:27 +0200'
  content: |-
    Not 100% sure, but I was under the impression remote deployment of sources/javadocs was a case of generating the appropriate artifacts as part of the same build as the deploy?

    mvn source:jar javadoc:jar deploy

    ?
---
<p>After the usual struggles with Maven 2, I was able to build another release candidate of <a href="http://wicketframework.org">Wicket 1.2</a>. This release contains all major packages of the wicket project, including wicket, extensions, quickstart, spring, spring annot and auth roles.</p>
<p>
You can download the release from the <a href="http://sourceforge.net/project/showfiles.php?group_id=119783">sourceforge servers</a>.</p>
<p>
As an experiment I also created our own Maven 2 repository on the sourceforge servers. You can find it at: <a href="http://wicketframework.org/maven2">http://wicketframework.org/maven2</a>. As a statistics maniac I would appreciate downloads to go through the sourceforge.net download service, but being a Maven fan, I understand the need for a Maven repository containing the latest releases.</p>
<ul>
<li>Deadlock fixed when trying to render a page that was expired the second time.</li>
<li>body tag onLoads contributed by Panel are now removed when the the Panel gets removed</li>
<li>Ajax ClassCast exception at AjaxFormSubmitBehavior</li>
<li>Made Tree better extensible. Added two more examples of customized tree to wicket examples, and display them in a table for better utilization of space</li>
<li>and of course the numerous contributed translations of Application.properties. Many thanks to everyone that contributed!</li>
</ul>
<p>
If anyone has a good idea to automatically upload the sources and javadoc jars  to a remote repository using maven I'm all ears. Apparently they have some setting <code>${pom.additionalArtifacts}</code>, but no way of setting that.</p>
