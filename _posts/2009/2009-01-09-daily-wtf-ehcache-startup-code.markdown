---
layout: post
status: publish
published: true
title: 'Daily WTF: ehcache startup code'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 413
wordpress_url: http://martijndashorst.com/blog/?p=413
date: '2009-01-09 15:54:37 +0100'
date_gmt: '2009-01-09 14:54:37 +0100'
categories:
- wicket
tags: []
comments:
- id: 57426
  author: Sylvain Wallez
  author_email: sylvain@bluxte.net
  author_url: http://bluxte.net/
  date: '2009-01-09 18:59:41 +0100'
  date_gmt: '2009-01-09 17:59:41 +0100'
  content: Nice catch :-)
- id: 57585
  author: JustJoe
  author_email: junkemailaddress101@gmail.com
  author_url: ''
  date: '2009-05-22 12:39:02 +0200'
  date_gmt: '2009-05-22 11:39:02 +0200'
  content: Very nice catch - this is hardly a 'gem' though and is really just an all
    too common programming error....
---
<p>I found this gem in the ehcache library while debugging my own code and using the thrown and uncaught exception breakpoint filter from Eclipse (in <a href="http://ehcache.sourceforge.net/apidocs/net/sf/ehcache/config/ConfigurationHelper.html#createBootstrapCacheLoader(net.sf.ehcache.config.CacheConfiguration.BootstrapCacheLoaderFactoryConfiguration)">ConfigurationHelper</a>:</p>
<pre lang="java">public final BootstrapCacheLoader createBootstrapCacheLoader(
        CacheConfiguration.BootstrapCacheLoaderFactoryConfiguration factoryConfiguration) throws CacheException {
    String className = null;
    BootstrapCacheLoader bootstrapCacheLoader = null;
    try {
        className = factoryConfiguration.fullyQualifiedClassPath;
    } catch (Throwable t) {
        //No class created because the config was missing
    }
    if (className == null || className.length() == 0) {
        LOG.debug("No BootstrapCacheLoaderFactory class specified. Skipping...");
    } else {
        BootstrapCacheLoaderFactory factory = (BootstrapCacheLoaderFactory)
                ClassLoaderUtil.createNewInstance(className);
        Properties properties = PropertyUtil.parseProperties(factoryConfiguration.getProperties());
        return factory.createBootstrapCacheLoader(properties);
    }
    return bootstrapCacheLoader;
}</pre>
<p>Notice that the parameter given to this method can be null. I always suspected that using an if-statement to check for null-ness was an over-engineered approach.</p>
