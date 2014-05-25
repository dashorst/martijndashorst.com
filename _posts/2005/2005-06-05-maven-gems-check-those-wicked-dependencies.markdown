---
layout: post
status: publish
published: true
title: 'Maven gems: Check those Wicked Dependencies'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 179
wordpress_url: http://martijndashorst.com/2005/06/05/maven-gems-check-those-wicked-dependencies/
date: '2005-06-05 14:42:09 +0200'
date_gmt: '2005-06-05 14:42:09 +0200'
categories:
- java
- maven
tags: []
comments: []
---
<p>While building the final 1.0 release for <a href="http://wicket.sourceforge.net" title="Wicket">Wicket</a> I needed to see whether all projects use the same version of the Wicket libraries. Using the <a href="http://maven.apache.org/reference/plugins/multiproject/" title="Maven Multiproject plugin">Maven multiproject plugin</a> I am able to quickly see whether the projects are using the same version of each library.</p>
<p>
First you need to check out the projects you want to check into the same workspace:</p>
<pre>wicket/
wicket-extensions/
wicket-examples/
wicket-contrib-data/
wicket-contrib-hibernate2/
wicket-contrib-hibernate3/</pre>
<p>Then create in the root directory of the workspace two files: <em>project.xml</em> and <em>project.properties</em>. The <em>project.xml</em> file contains the following:</p>
<pre><project>
    <reports>
        <report>maven-multiproject-plugin</report>
    </reports>
</project></pre>
<p>Note that this is not a <a href="http://maven.apache.org/reference/project-descriptor.html">complete, nor a valid project.xml</a> for serious development using <a href="http://maven.apache.org" title="maven">maven</a>.</p>
<p>The <em>project.properties</em> file contains the following properties:</p>
<pre>maven.multiproject.basedir=.
maven.multiproject.includes=*/project.xml</pre>
<p>Now all you need to do is to run:</p>
<pre>maven site</pre>
<p>in the workspace root folder where you saved the two Maven project files. The resulting report can then be found in the subdirectory: <strong><em>target/docs/dependency-convergence-report.html</em></strong>.</p>
<p>This is one of the gems why I <em>really</em> like <a href="http://maven.apache.org">Maven</a> as a project management tool.</p>
<p><!-- technorati tags start -->
<p>Technorati Tags: <a href="http://technorati.com/tag/maven" rel="tag">maven</a>, <a href="http://technorati.com/tag/java" rel="tag">java</a>, <a href="http://technorati.com/tag/wicket" rel="tag">wicket</a></p>
<p><!-- technorati tags end --></p>
