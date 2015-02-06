---
layout: link
status: publish
published: true
title: 'Maven incremental builds'
link: http://takari.io/book/40-lifecycle.html
author: Martijn Dashorst
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
date: '2015-02-06 14:00:00 +0100'
---

One of the issues we have at our company is that build times for our
major products take a long time to complete, hindering adoption of
non-incremental build IDEs such as Netbeans.

A possible way out is to adopt _takari_'s incremental build features.
This is certainly something we are going to try out in the coming
week(s).

From the [Takari Lifecycle as a replacement for Maven's default lifecycle](http://takari.io/book/40-lifecycle.html) 
page:

> TEAM includes an optimized replacement for the Maven default
> lifecycle. The Takari Lifecycle Plugin provides you access to a number
> of significant advantages:
>
> 1. One plugin with a small set of dependencies provides equivalent
> functionality to five plugins with a large set of transitive
> dependencies. This reduces the download times to retrieve the
> needed components as well as the storage space requirements in your
> repositories.
>
> 2. The configuration for a number of aspects for your build is
> centralized to one plugin and simplified.
>
> 3. The reduced complexity of the plugins involved in the build,
> results in higher build performance on the command line and in the
> IDE.
>
> 4. The build is fully incremental, not only for your source code, but
> also for your resources, which in turn again speeds up development
> cycle and build times.
>
> 5. Dedicated IDE support brings the advantages of the lifecyle to your
> daily development work.
