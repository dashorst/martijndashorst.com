---
layout: post
status: publish
published: true
title: Downloading the internet with Maven in a new light
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 425
wordpress_url: http://martijndashorst.com/blog/?p=425
date: '2009-05-19 23:18:11 +0200'
date_gmt: '2009-05-19 22:18:11 +0200'
categories:
- technology
- maven
- os x
tags:
- os x
- maven
- Ruby
comments:
- id: 57572
  author: Jim Gay
  author_email: jim@saturnflyer.com
  author_url: http://www.saturnflyer.com
  date: '2009-05-20 02:38:34 +0200'
  date_gmt: '2009-05-20 01:38:34 +0200'
  content: "The promise of modularity brings complexity.\r\n\r\nBut it sounds like
    you're not using a bare bones setup. Is it Rails and Radiant that are adding the
    complexity, or your project?\r\n\r\nI recall getting Rails setup on earlier versions
    of OS X being difficult, but it's part of the standard install today."
- id: 57573
  author: Stefan F
  author_email: stf+gravatar@molindo.at
  author_url: http://molindo.at/
  date: '2009-05-20 07:46:22 +0200'
  date_gmt: '2009-05-20 06:46:22 +0200'
  content: "Well, Maven ... yeah, I have quite a few things to complain about. But
    the downloads? Just put it to offline mode (mvn -o clean install) or get yourself
    a repository manager. To me, it's mostly the dependency managment that is a constant
    pain. \r\n\r\n[Attention, Your about to read a brain dump on improving Maven dependency
    management ;)]\r\nI'd love to see Maven dependeny management getting more like
    Debian (Ubuntu) package management. With things like \"jcl-over-slf4j replaces
    commons-logging\", \"org.mortbay.jetty.servlet-api provides javax.servlet-api\",
    \"hibernate conflicts with jdo\", \"wicket suggests wicket-extensions\", ... and
    another cool thing to have would be to get modules, that can be enabled, where
    a module is basically a feature set which has dependencies (e.g. the servlet module
    of commons-logging would require the servlet-api - currently it does this if you
    don't exclude it - but commons-logging still is a single jar) Or think about spring
    with it's \"get all in spring.jar\" or \"choose what you like with spring-jdo,
    spring-web, spring-...\" - too bad that dependencies don't agree in which approach
    they prefer (and you'll end up debugging weird errors due to different versions
    of the same classes on the classpath). Packages could easily be inspected, added,
    and removed with convenient command line tools (e.g. `mvn-get install wicket`
    and it would immediately list available modules to activate and suggest more packages
    to install (e.g. wicket-extensions for wicket). No manual XML wrangling or half-baked
    IDE plugins anymore. Does that sound to cool to be true? Or is there already something
    like this? If yes, I'd probably die for it :)\r\n\r\nFinally, I'd like to say
    sorry for answering questions you've never asked. It just struck me and I had
    to write it down - somewhere.\r\n\r\nCheers, Stefan"
- id: 57574
  author: Quintesse
  author_email: quintesse@gmail.com
  author_url: ''
  date: '2009-05-20 08:45:55 +0200'
  date_gmt: '2009-05-20 07:45:55 +0200'
  content: '@Stefan: you do realize that Maven is a build tool and not a package management
    system? Most of your suggestions are just not useful in a build system. "Hibernate
    conflicts with JDO"? Then why are you adding them both to the same module? But
    they could be part of the same project so both of them might need to be installed.
    "mvn.-get install wicket"? You really want others to go through that before they
    can build your project? There is a reason it''s written down in an XML file, so
    you can just give that to someone and not worry about having to explain where
    to download and how to install and configure all the dependencies. Yes, maven
    can definitely be improved a lot, but IMHO I don''t think this is the way to go.'
- id: 57575
  author: Quintesse
  author_email: quintesse@gmail.com
  author_url: ''
  date: '2009-05-20 08:51:08 +0200'
  date_gmt: '2009-05-20 07:51:08 +0200'
  content: "@Martijn: I do agree that Maven at times downloads way too much stuff,
    of course the thing is that it's almost impossible for Maven to know what you
    are going to use and what can be safely ignored.\r\n\r\nYou might do some static
    code analysis to determine dependencies but Maven would miss out on the runtime
    dependencies and once your app is running Maven isn't around anymore to download
    the missing dependencies.\r\n\r\nUntil we get proper module support in Java, that
    is."
- id: 57576
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2009-05-20 09:03:41 +0200'
  date_gmt: '2009-05-20 08:03:41 +0200'
  content: |-
    AFAIR I had to upgrade gem, upgrade rails, upgrade radiant, install ImageMagick, gem install rmagick, etc...

    I don't mind having to install stuff, but figured the grass was greener on the other side, but apparently it isn't. C'est la vie...
- id: 57577
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2009-05-20 09:05:01 +0200'
  date_gmt: '2009-05-20 08:05:01 +0200'
  content: Maven downloads 'just enough' IMO, i.e. just what's needed. This doesn't
    mean it is overwhelming for new co-workers that have to install maven for the
    first time and start working on our project. Even with a repository manager, the
    list of downloads goes on and on and on and on and on....
- id: 57578
  author: Jim Gay
  author_email: jim@saturnflyer.com
  author_url: http://www.saturnflyer.com
  date: '2009-05-20 14:07:59 +0200'
  date_gmt: '2009-05-20 13:07:59 +0200'
  content: So you wanted specific versions and specific pieces of software? Why wouldn't
    you expect to need to install them?
- id: 57580
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2009-05-20 14:12:08 +0200'
  date_gmt: '2009-05-20 13:12:08 +0200'
  content: Not sure why you feel so threatened or attacked. I merely observed from
    my Java/maven experiences that the grass is definitely not greener on other pastures.
    It is comforting to know that. Jeez.
- id: 57581
  author: Jim Gay
  author_email: jim@saturnflyer.com
  author_url: http://www.saturnflyer.com
  date: '2009-05-20 18:10:15 +0200'
  date_gmt: '2009-05-20 17:10:15 +0200'
  content: I don't know how you got the impression that I felt threatened or attacked.
    I don't. (I assume that last comment was for me)
- id: 57584
  author: Stefan F
  author_email: stf+gravatar@molindo.at
  author_url: http://www.molindo.at/
  date: '2009-05-21 13:14:52 +0200'
  date_gmt: '2009-05-21 12:14:52 +0200'
  content: "@Quintesse First of all: I know that maven isn't a package/dependency
    manager but a build tool. But imho the dependency management is one of the best
    and worst features at the same time. You also got me wrong on the dependency management
    thing. I don't want users of my project to install all the dependencies by hand
    (e.g. mvn-get install wicket) before they are able to use my stuff. That's only
    the way to add dependencies to the POM instead of doing plain XML without knowing
    what is done (So you'd be able to check those changens into your repository and
    all others could get them from there). I'd also like to be able to search repositories
    and inspect packages using the same tools I use to manage those dependencies.
    And the hibernate vs. JDO thing is simple. I didn't add them myself. But such
    things are likely to happen with transient dependencies. However, I'd also say,
    that this isn't always the problem of Maven itself as there are for instance some
    artifacts out there, that depend on JUnit without specifying a scope (which adds
    Junit to your war for instance)."
- id: 57755
  author: Internet tips
  author_email: tukangeblog@yahoo.com
  author_url: http://net-tipz.blogspot.com/
  date: '2009-08-11 06:11:24 +0200'
  date_gmt: '2009-08-11 05:11:24 +0200'
  content: It's make me confused. Maven is constructed in a highly modular fashion,
    requiring lots of different, small, focused Java libraries. Would you post about
    basic learning?
- id: 60284
  author: Anonymous coward
  author_email: A_flj_@hotmail.com
  author_url: ''
  date: '2011-03-11 19:18:04 +0100'
  date_gmt: '2011-03-11 18:18:04 +0100'
  content: "Idunno ... we are working on a project involving several quite different
    packages, where everything is bound together in a spring context. It's been over
    a year since the project started, so we already have several versions of a package
    in maven's local repository. Nevertheless, there are less than 1400 files in less
    than 100 MB. This seems reasonable to me, not in the least half the Internet.\r\n\r\nIMO,
    if you compare this with manually managing all dependencies using an ant build,
    maven is the winner by orders of magnitude. And I can't think of any better solution,
    other than sitting on top of a large library, of which you most often don't use
    a tenth, but which gets downloaded and installed separately from your app (think
    .Net).\r\n\r\nIn fact, maven _does_ have a dependency definition a la debian packages.
    Including a conflicts description feature would not make sense - you don't get
    naming conflicts when using the Java naming rules, and runtime conflicts are a
    programming issue, IMO, and not be handled at the package/dependency level. You
    also don't want to have module dependencies specified at system level. IMO, maven
    has hit it just right with its dependency management system."
---
<p>I have my share of complaints like everybody else about <a href="http://maven.apache.org">Apache Maven</a> and one of them is that upon installation (or upgrading to a new plugin version) it starts downloading half of the available internet. Maven is constructed in a highly modular fashion, requiring lots of different, small, focused Java libraries. I'd like the distribution to contain those libraries, but I digress. Tonight I saw that not only Maven is structured this way. It is something *all* open source projects got.</p>
<p>For example, the much touted Ruby on Rails project with their disdain for everything Java would probably cringe at Maven (it uses XML after all). But installing Ruby on Rails and for example Radiant CMS with some plugins is a futile attempt in finding the right invocations of: script/*, rake, gem, port and other commandline tools you'll want to get familiar with. All these tools start downloading stuff from the internet from different repositories (SVN, ruby forge, etc).</p>
<p>Maven: you're not alone anymore in downloading the internet for your builds...</p>
