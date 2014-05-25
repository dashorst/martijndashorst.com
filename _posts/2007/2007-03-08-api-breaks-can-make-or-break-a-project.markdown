---
layout: post
status: publish
published: true
title: API breaks can make or break a project
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 242
wordpress_url: http://martijndashorst.com/blog/2007/03/08/api-breaks-can-make-or-break-a-project/
date: '2007-03-08 22:36:39 +0100'
date_gmt: '2007-03-08 21:36:39 +0100'
categories:
- wicket
- java
tags: []
comments:
- id: 639
  author: Eelco
  author_email: eelco.hillenius@gmail.com
  author_url: http://chillenious.wordpress.com/
  date: '2007-03-09 00:39:16 +0100'
  date_gmt: '2007-03-08 23:39:16 +0100'
  content: If you haven't yet, please reply on this http://www.nabble.com/IMPORTANT%3A-your-opinion-on-the-constructor-change-in-2.0-tf3358738.html
    thread.
- id: 646
  author: Jesse Kuhnert
  author_email: jkuhnert@gmail.com
  author_url: http://blog.opencomponentry.com
  date: '2007-03-09 07:45:56 +0100'
  date_gmt: '2007-03-09 06:45:56 +0100'
  content: "If you mean by \"pulling a tapestry\" designing something that doesn't
    make you look like a bunch of green morons then yes, please don't do that. A good
    framework would be competition and that wouldn't be fun. \r\n\r\nIt's really painful
    to watch you guys in action. It's kind of like looking at the equivalent of framework
    special ed. Ah well, can't slight you for trying....."
- id: 648
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-03-09 07:56:50 +0100'
  date_gmt: '2007-03-09 06:56:50 +0100'
  content: LOL
- id: 649
  author: Anonymous Coward
  author_email: anon@coward.com
  author_url: ''
  date: '2007-03-09 08:11:58 +0100'
  date_gmt: '2007-03-09 07:11:58 +0100'
  content: "Hello all,\r\n\r\nI'm sure this is me having a moment of insanity so I
    won't feel bad if everyone tells me to f- myself ;)\r\n\r\nI was just thinking
    that though our frameworks are different in a lot of respects, they are also similar
    in overall design goals. You also happen to have a great deal of brain power behind
    your project which I find nice.\r\n\r\nWell, I think I'm proposing that we somehow
    merge our projects. Dojo did it with their toolkit and now they're probably the
    #1 in their space more or less..\r\n\r\nWouldn't it be nice if we could both experience
    the same thing? I have no doubts about the technology behind tapestry, nor do
    I think you have with yours, but we could both do a lot better together than not
    I think. Tapestry just received two more very active committers (other than myself)
    who will be trying as hard as possible to keep the boat afloat while I work on
    tapestry 4.1 (using all of my dojo background to integrate the crap out of it
    and tapestry) and howard on tapestry 5 (all kinds of unspeakable goodies). We're
    also moving to a top level project at tapestry.apache.org, as well as having the
    logo/site/everything redesigned by the same guy that did everything for http://dojotoolkit.org.\r\n\r\nI'm
    just sick and tired of seeing these other guys float around  with gaining popularity
    based solely on coporate sponsorship (or...specification) ..Two underdogs together
    are better than two apart no?\r\n\r\nI know you guys have to feel the same way
    about this that I do, at least the part about wanting to crush our enemies :)\r\n\r\nOk,
    I understand if we're both two big for our britches to even ponder it...but it
    could be done ..It really could !\r\n\r\n-- \r\nJesse Kuhnert\r\nTacos/Tapestry,
    team member/developer\r\n\r\nOpen source based consulting work centered around
    dojo/tapestry/tacos/hivemind.  http://opennotion.com"
- id: 650
  author: Anonymous Coward
  author_email: anon@coward.com
  author_url: ''
  date: '2007-03-09 08:12:14 +0100'
  date_gmt: '2007-03-09 07:12:14 +0100'
  content: go fuck yourself
- id: 658
  author: saki
  author_email: saki@chare.eu
  author_url: ''
  date: '2007-03-09 11:58:37 +0100'
  date_gmt: '2007-03-09 10:58:37 +0100'
  content: "Martijn,\r\nI do not know how many projects are written in 2.0 and in
    production use - would be interesting to see. I personally think very few. For
    me the constructor change was definitely big stopper - we even did no try to use
    2.0 because I can not imagin to rewrite let say 50 pages  with one or more forms
    on each with no chance to use refactoring. Because this constructor change means
    you have to change every f..king component.\r\n\r\nSo I think loss of 2.0 branch
    will be minimal, if all goodies (models, conversions) would go to 1.x. \r\n\r\nHope
    you will end the discussion soon, so the development can continue. \r\nAnyway
    thanks for great work to all wicket developers.\r\nsaki"
- id: 659
  author: el raichu
  author_email: raichu@raichu.raichu
  author_url: ''
  date: '2007-03-09 13:40:59 +0100'
  date_gmt: '2007-03-09 12:40:59 +0100'
  content: "thank goodness!  after all, an open source project is as much a social
    phenomenon as it is an engineering one.  that's one of the reasons why i stopped
    trying to learn tapestry; i'm not that bright or kickass so i couldn't keep up
    back then.\r\n\r\nthere are a few times when it all boils back down to \"worse
    is better\": simplicity, correctness, consistency, and completeness.  \r\n\r\n\r\nif
    the constructor change makes things more complicated, drop it.\r\nif the constructor
    change makes things more inconsistent, drop it.\r\nif the constructor change doesn't
    cover more important situations as is practical than the previous design, drop
    it.\r\n\r\n\r\n\r\nit's all about framework <strong>survival</strong>, and a framework
    needs users to survive.  if they want generics and can't get it with wicket, they'll
    go somewhere else.  igor vaynberg's <a href=\"http://papernapkin.org/pastebin/view/4900\"
    rel=\"nofollow\">code</a> (http://papernapkin.org/pastebin/view/4900) makes me
    wanna go somewhere else. "
- id: 789
  author: Eelco
  author_email: eelco.hillenius@gmail.com
  author_url: http://chillenious.wordpress.com/
  date: '2007-03-11 01:52:07 +0100'
  date_gmt: '2007-03-11 00:52:07 +0100'
  content: "@al raichu. I think the problem with building software (and anything in
    life) is that you can't have it all. The end of the day, you have to choose between
    tradeoffs. Now, the constructor change was something we truly believed was going
    to make our framework a lot better. We didn't implement it right away, as we thought
    it would break too many clients etc. From a 'management' point of view, I believe
    that decision was bad; had we done it right away, we wouldn't have had the branch
    problem. Otoh, had we done it, we would have ended up with the new constructor
    being the default, of which we now doubt it is better.\r\n\r\nAnd that doubt expresses
    best what is going on here. There are still pros and cons for both. They seem
    to be more balanced now that we have actual experience with it, maybe with a slight
    preference to the old method. And when the the advantage isn't that clear, we
    believe we really should choose for the solution that most people are working
    with now, and get rid of the big overhead that maintaining two branches is.\r\n\r\nSo,
    I don't think the constructor change was all bad. It's just that the gain isn't
    as large as we expected, and is generally not worth maintaining a separate branch
    and fragmented user base for."
- id: 818
  author: ZedroS
  author_email: zedros.schwartz@gmail.com
  author_url: ''
  date: '2007-03-13 08:50:27 +0100'
  date_gmt: '2007-03-13 07:50:27 +0100'
  content: "Hum, I don't get it properly : so at the end of the day will all the constructor
    change be left over and all its benefits lost ?\r\n\r\nOr will we have them in
    \"another way\" ?\r\n\r\nPersonally, if this constructor changes is such a good
    stuff, I would rather like to have it. :$\r\n\r\nAnd what would happen next time
    a ground breaking innovation is found and changing the API ? Will it be left as
    well ?\r\n\r\nJust a side question : would it be possible to have this constructor
    change available in some kind of extension project ?"
- id: 1362
  author: Wannabe WicketUser
  author_email: gabor.schermann@freemail.hu
  author_url: ''
  date: '2007-04-09 00:05:13 +0200'
  date_gmt: '2007-04-08 23:05:13 +0200'
  content: "Hi guys,\r\n\r\nI'm new to Wicket, and I have just read this article.
    I'm sorry if I misunderstood something.\r\n\r\nI'm wondering if there is a way
    to keep the constructor change optional. \r\n\r\nI imagined a simple helper/utility
    class, which would keep the current state of the component tree (path), a stack,
    basically. The implementation of this class should be a ThreadLocal variable,
    of course. That might be a little bit dirty for some of you, but will work.\r\n\r\nSuppose,
    you have an 1.x Wicket app. In each (old style) constructor you could call this
    helper class twice (push/pop the tree element, at the beginning/end of the code).
    That makes 2 lines of code per component. That is not much tradeoff I suppose.\r\n\r\nThe
    Wicket API should keep the old (parentless) constructors (perhaps marked as deprecated),
    and they should look for the parent component from that component tree helper
    class.\r\n\r\nI understand that it might require a large amount of work to keep
    the old API, but you could reach both goals - new features and backward compatibility.\r\n\r\nRegards,\r\n
    \   Gabor"
---
<p>About half a year ago the core Wicket team decided that we needed a radical new way of constructing our component hierarchies. This led to the infamous 'constructor change'. Basically this change requires you to provide the parent of your new component at construction time. The benefit is that the hierarchy for your component is available in the constructor, which opens up a lot of possibilities:</p>
<ul>
<li>line precise error reporting in your Java files: can't find the component in the markup, throw an exception and you know exactly which component violates the hierarchy</li>
<li>markup attributes available in the constructor: you can manipulate the tag's attributes directly instead of using an <span>AttributeModifier</span></li>
<li>functions as <span>getPage</span>() and <span>getForm</span>() work in the component's constructor, allowing you to generate <span>JavaScript</span> at construction time, instead of render time (the full path, and markup <span>identfier</span> are available at construction time)</li>
<li>...</li>
</ul>
<p>So we embarked on a journey that would define the future of our framework: Wicket 2.0 would be <span>tha</span> bomb, our own shark with <span>frickin</span>' lasers on top of their heads, not genetically mutated, bad tempered sea bass. However, the proof of the pudding is always in the tasting and it appeared that more things were harder and less clear to do.</p>
<p>By requiring the parent of a component at construction time, we 'fix' the hierarchy and reparenting components, moving them around across the page is really dangerous: what should you do with the markup attributes that are already set in the constructor? Suddenly you needed factories to create dynamic component structures instead of just adding the component to a list...</p>
<p>And if this is not enough, the change is such a major break that existing projects building on Wicket 1.x would never cross the 2.0 barrier. You'd have to rewrite your whole UI layer, which is not very economical. We already realized this, so we kept Wicket 1.x alive and kicking by backporting key features into that development stream. Basically we had 3 branches to keep alive:</p>
<ol>
<li>Wicket 1.2 (our current stable release)</li>
<li>Wicket 1.x (head for Java 1.4 and pre-constructor change Wicket)</li>
<li>Wicket 2.0 (trunk, using Java 5 and constructor change)</li>
</ol>
<p>This severely slowed us down. Estimates are for about 25%, but I think it is closer to 50% or even 60%.</p>
<p>So when serious development with the 2.0 changes were done, the culprit that first came up with the change came to the conclusion that the benefits were not as great as the disadvantages.</p>
<p>In my opinion the biggest disadvantage is that we create a rift between the two versions, basically doing a 'Tapestry' on our users: changing the whole project between major versions.</p>
<p>When a project decides to completely change, then your users will also look around. If they have to change their application anyway, why not see if there is anything else, maybe even better?</p>
<p>Creating a rift in our community is really not good and therefore I won't veto discontinuing the constructor change.</p>
<p>We have discussed this change in direction for our framework the last couple of days, and need your input. If you have an investment in Wicket 2.0, then please let it be heard on our user list. We want to know that you use Wicket 2 (our trunk) so that we can use your experience in deciding whether to continue or not with our current roadmap, or that we need to discontinue the constructor change.</p>
<p><strong>PS</strong> the Java 5 enhancements will be kept either way. We like them and think they are good for the framework. So <i>if</i> we decide to discontinue 2.0, we will backport the remaining changes in trunk to make the change as smooth as possible.</p>
