---
layout: post
status: publish
published: true
title: Wicket JEE integration reaches 1.0
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 228
wordpress_url: http://martijndashorst.com/blog/2007/01/23/wicket-jee-integration-reaches-10/
date: '2007-01-23 23:58:19 +0100'
date_gmt: '2007-01-23 22:58:19 +0100'
categories:
- wicket
- java
- technology
tags: []
comments: []
---
<p><a href="http://www.diotalevi.com">Filippo Diotalevi</a> (known from the Milan JUG) has released the first version of the <a href="http://wicketstuff.org/confluence/display/STUFFWIKI/wicket-contrib-javaee">Wicket JEE integration project</a>. This project integrates Jave EE 5 with Wicket in a similar fashion the Wicket Spring integration works. By specifying three annotations:</p>
<ul>
<li><a href="http://wicketstuff.org/confluence/display/STUFFWIKI/wicket-contrib-javaee-HowToUseEjbAnnotation">@EJB</a> - to inject EJB service objects into your pages
</li>
<li><a href="http://wicketstuff.org/confluence/display/STUFFWIKI/wicket-contrib-javaee-HowToUsePersistenceUnitAnnotation">@PersistenceUnit</a> - to inject EntityManagerFactory into your pages
</li>
<li><a href="http://wicketstuff.org/confluence/display/STUFFWIKI/wicket-contrib-javaee-HowToUseResourceAnnotation">@Resource</a> - for injecting resource references
</li>
</ul>
<p>you can access your JEE resources and beans from in your pages. This release is built on top of Wicket 1.2.4, so you can start using it <i>now</i> in your production web applications. For more documentation, read further on the <a href="http://wicketstuff.org/confluence/display/STUFFWIKI/wicket-contrib-javaee">Wicket Stuff Wiki</a>.
 </p>
<p>Download <a href="https://sourceforge.net/project/showfiles.php?group_id=134391&amp;package_id=219263">wicket-contrib-jee-1.0</a> from Wicket Stuff's download area at SourceForge.</p>
<p></p>
