---
layout: post
status: publish
published: true
title: IntelliJ IDEA experiences
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 45
wordpress_url: http://martijndashorst.com/2006/06/05/intellij-idea-experiences/
date: '2006-06-05 15:37:38 +0200'
date_gmt: '2006-06-05 15:37:38 +0200'
categories:
- java
tags: []
comments:
- id: 50
  author: Kevin Riff
  author_email: ''
  author_url: ''
  date: '2006-06-05 16:35:12 +0200'
  date_gmt: '2006-06-05 16:35:12 +0200'
  content: |-
    I find it's uncanny just how well IDEA is able to figure out what I want to do from the context of my code. It's so good I find myself wondering if it's reading my mind.

    Personnally I hate the way that Eclipse puts *everything* in one feature. I'm constantly faced with a long list of options to choose from. IDEA on the other hand splits these functions into 3 or 4 different features which are activated by different shortcuts. The result is that IDEA can usually figure out from the context exactly what I want and give me a much shorter list of choices. Often, it's only one choice which means IDEA can just go ahead and do it without any further action from me. Eclipse just slows me down by giving me choices that have nothing to do with what I wanted.

    The key sequence you want is Ctrl-Alt-Space. This will function like Ctrl-Space but show possibilities from any package, not just those you have already imported. Also, try using Alt-Enter in lots of different contexts. It activates the "code intentions" feature which I find very useful.
- id: 51
  author: Martijn Dashorst
  author_email: dashorst@users.sf.net
  author_url: http://www.jroller.com/page/dashorst
  date: '2006-06-05 17:02:37 +0200'
  date_gmt: '2006-06-05 17:02:37 +0200'
  content: |-
    First: wow quick reaction :)

    Second I don't share your sentiment (but that you already figured, otherwise you wouldn't have commented in the first place ;-).. I like the fact that Eclipse can figure out what to do from the context without me having to tell it so.

    The only thing I find missing in the Eclipse way is type inference: it doesn't select the correct type when doing the ctrl-space routine on 'add(new Label': it presents me with java.awt.Label instead of the correct wicket.markup.html.basic.Label. IDEA is smarter in this regard, but I'll never get used to having to choose between ctrl-shift-space/ctrl-alt-space/ctrl-alt-shift-space/alt-enter/alt-shift-enter to do something basic as completing and importing a type name.
- id: 52
  author: Flemming
  author_email: ''
  author_url: ''
  date: '2006-06-05 17:33:55 +0200'
  date_gmt: '2006-06-05 17:33:55 +0200'
  content: |-
    I think THE most important feature you are missing, is Idea is more intuitive. No workspace, no 100Â´s of dialogboxes where small bits of information is stored about the IDE / you project.
    I remember first time in front of Eclipse, I have NO "idea" how to setup my project with classes and jar files.

    In IDEA you up and running with in minutes.

    But as always in these IDE discussion we are really talking religion.....


    Anyway thanks for your effort in Wicket!!  doing hello of a job!


    /Boller
- id: 53
  author: Igor Vaynberg
  author_email: ''
  author_url: ''
  date: '2006-06-05 23:20:06 +0200'
  date_gmt: '2006-06-05 23:20:06 +0200'
  content: Eclipse 3.2 remembers preferences of types, etc, so once you choose wicket.label
    over awt.label the former will always show up before the latter in choices.
- id: 54
  author: ali
  author_email: sharghi.alireza@gmail.com
  author_url: ''
  date: '2006-06-07 06:58:13 +0200'
  date_gmt: '2006-06-07 06:58:13 +0200'
  content: "in IDEA you can simulate save+compile of eclipse .\n1- compile in Background
    = true\n2- honor dependncies in compile = false\n3- \"compile\" command autosave
    bafore compile \nfile(s) / package(s)\n\nif you hit ctrl+s then \"compile\" ,
    this no needed, you only enough hit \"compile\".\n=======\nMr Igor , i respect
    you as a professianl , but want try/compare IDEA with Eclipse only in editing
    code only in a hour per day\n\nhigh quality plugins instead exist of many plugins
    .\n\nIDEA use eclipse communuty indirectly for pick up\nits plugins.\n\nEclipse
    maybe dreams that has this LiveTemplate of IDEA (again tell view of guality of
    feature = basic/advanced)"
---
<p>
As a developer of the <a href="http://wicketframework.org/">Wicket project</a>, I am/was in the proud posession of an open source license for <a href="http://www.jetbrains.com/idea/">IntelliJ IDEA</a>.<br />
This license is about to expire and I must say I haven't used it as<br />
much as I would like to. This is an account of the (limited) time I<br />
have used IDEA.</p>
<h3>(Not) using IDEA<br /></h3>
<p>The main reason for not using it is unfamiliarity with the product. I am an astute <a href="http://www.eclipse.org/">Eclipse</a><br />
user (but not a zealot). I have become accustomed to some of the things<br />
Eclipse does remarkably well. IDEA does those thing also, and probably<br />
just as good or even better. The biggest hurdle is to find those<br />
options and capabilities. That makes transition to a new IDE hard,<br />
tough. Furthermore, when you aren't allowed to use the IDE for<br />
commercial purposes (the open source license only grants Wicket related<br />
development), it is not possible to use the IDE in your daytime job. So<br />
I will be switching between the Eclipse world and the IDEA world.</p>
<p>One could say that I'm being anal about the licensing, but I have<br />
another, more pressing reason to keep working with Eclipse in my<br />
daytime job: the team. I'm part of a development team, and I have to<br />
work with them and deliver code under considerable time pressure.<br />
Learning the ropes of a new IDE is not a productivity booster. We are<br />
mainly building web applications and Eclipse works pretty well,<br />
especially with Wicket. When I were to use IDEA I'd be sacrificing some<br />
productivity (for a couple of days), but more importantly, updated<br />
dependencies in our project won't be available in my project files, as<br />
everyone else is working with Eclipse.</p>
<p>Now that I got that of my chest, I must say that the limited work I have done with IDEA does make it feel like a very good IDE.</p>
<h3>What do I like about IDEA?</h3>
<p>The formatting, the controls, the whole look'n'feel on Mac OSX. It just<br />
feels much better than Eclipse on OS X. It may not be native looking,<br />
but it does get the job done. It doesn't feel as sluggish as Eclipse<br />
(3.1.2, dual power G5, 2Gb ram).<br />
I like the default font/coloring of the editors. I really<br />
like the fact that you have a decent XML/HTML editor integrated into<br />
the workbench. I also like the bundling of resouce bundles into one<br />
folder, which take less space this way.</p>
<p>The debugger is pretty decent, though I haven't done serious enough<br />
development to see it in full action. The same goes for the refactoring<br />
support: still haven't used it enough to judge it on merit or compare<br />
it to the functionality provided by Eclipse.</p>
<h3>What I don't like about IDEA</h3>
<p>I have done some basic development in IDEA, and some things don't come<br />
naturally. For instance I'm used to pressing CTRL-SPACE to do all sorts<br />
of things: importing classes, overriding methods, implementing methods,<br />
code completion, template selection and more. Take for instance the<br />
following code snippet
<pre>public class Index extends WebPage {<br />    public Index() {<br />        add(new Label<br />                     ^<br /></pre>
<p>When I press CTRL-space in Eclipse, I get a list of classes that can be imported: java.awt.Label, wicket.markup.html.basic.Label.<br />
In IDEA I get nothing when I press CTRL-space. In IDEA I either get the<br />
message to press alt-enter, or I have to use smart completion:<br />
CTRL-SHIFT-space. Granted, IDEA is somewhat smarter in presenting the<br />
choices (it prefers the Wicket label class over the AWT one), but I<br />
have 3 keys that do the same. And why don't I want to have 'smart'<br />
completion as the default?</p>
<p>Depending on which short cut I choose, I get different code: smart complete puts parentheses behind the label's constructor and puts the cursor behind it. The other way (alt-enter) puts no parentheses but just completes the class name. My<br />
constructor takes at least 1 parameter, so I have to move the caret<br />
back. And again you have a different key combo to see which parameters<br />
are available with the method: command-p (OS-X binding). In eclipse you<br />
typically just press CTRL-space.</p>
<p>In summary, IDEA has moved some intelligence to the user of their IDE:<br />
you have to provide the context to IDEA on what you want to do: need<br />
parameter completion: press the special parameter completion magic<br />
keys. Need class name completion, use the intentions menu<br />
(command-enter), or use the smart completion (CTRL-SHIFT-space). In<br />
Eclipse this is automatically derived from the context: if you are<br />
inside a parameter construction, and press CTRL space, Eclipse deducts<br />
that you want to see the parameters.</p>
<p>Another thing I don't like is the fact you have to 'rebuild' when you<br />
change your classes or resources. Eclipse does this 'on-the-fly', which<br />
makes development very fast. This comes mostly into play when you are doing Wicket development, and you change a markup file. IDEA only copies the changes when requested to do so. Eclipse automatically copies the changes where they can be picked up by Wicket.</p>
<h3>Conclusion</h3>
<p>Although I haven't used IntelliJ IDEA nearly to its full potential,<br />
I feel it is a decent IDE and I can imagine that many benefit from<br />
using it. The markup editor is pretty awesome, and I like the way IDEA<br />
works on OS X (it just works, no problems, contrary to SWT/Eclipse). I<br />
don't like the numerous keybindings that could easily be bound to one<br />
key if the IDE would use the context a little more, and I really miss<br />
the save and continue approach used by Eclipse.</p>
<p>To bad our Open Source license will expire in a couple of days (I<br />
guess 2), as I would like to get acquinted a little better, to see if<br />
there is an idea to the different key combinations (no pun intended). </p>
<p>I encourage anyone to try out IDEA as it is a very good IDE. Especially when you are working on OS X, IDEA might be your cup of tea: the Swing UI feels much better than the SWT UI used by Eclipse (3.1.2).</p>
