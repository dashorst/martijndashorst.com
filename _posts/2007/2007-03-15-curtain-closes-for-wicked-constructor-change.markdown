---
layout: post
status: publish
published: true
title: Curtain closes for wicked constructor change
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 246
wordpress_url: http://martijndashorst.com/blog/2007/03/15/curtain-closes-for-wicked-constructor-change/
date: '2007-03-15 11:00:33 +0100'
date_gmt: '2007-03-15 10:00:33 +0100'
categories:
- wicket
tags: []
comments:
- id: 875
  author: n8han
  author_email: nathan@technically.us
  author_url: http://technically.us/code
  date: '2007-03-15 16:52:22 +0100'
  date_gmt: '2007-03-15 15:52:22 +0100'
  content: I feel for anyone who's been working on 2.0, but I think you guys have
    been consistent in recommending 1.3 for, basically, everything but experimentation.
    I got the hint, anyway. ;)
- id: 876
  author: James Cook
  author_email: wicket@visualxs.com
  author_url: ''
  date: '2007-03-15 17:50:47 +0100'
  date_gmt: '2007-03-15 16:50:47 +0100'
  content: I guess this would also push back any thoughts of getting Wicket in Action
    soon?
- id: 878
  author: Yeroc
  author_email: cpnotify@yeroc.ca
  author_url: ''
  date: '2007-03-15 19:47:46 +0100'
  date_gmt: '2007-03-15 18:47:46 +0100'
  content: I like the plan but don't the Java 5 changes warrant a v2.0 rather than
    v1.4?
- id: 882
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2007-03-16 11:10:33 +0100'
  date_gmt: '2007-03-16 10:10:33 +0100'
  content: "James: not as much. We will target the book for Java 5 and all other changes
    that were in 2.0, excluding the constructor stuff. This would not matter much,
    just some minor tweaks and a re-read of the content. If anything, the book is
    considerably delayed by the 2.0 delay in itself. Would we have had a 2.0 earlier,
    then we could have written several chapters more quickly. Up til now we had to
    wait for discussions to finalize or take a gamble, or not write about the subject.\r\n\r\nYeroc:
    that is something we are considering."
- id: 4380
  author: A Wicket Diary&raquo; Blog Archive &raquo; Wicket in Action writers blog
  author_email: ''
  author_url: http://martijndashorst.com/blog/2007/06/18/wicket-in-action-writers-blog/
  date: '2007-06-19 21:09:58 +0200'
  date_gmt: '2007-06-19 20:09:58 +0200'
  content: "[...] As for the writing, it currently has gained speed again. The chapters
    are being revised to cover the reversal of the constructor change (and you thought
    you were the only one being bitten by that!), and keeping up with renaming efforts
    of other team members. We expect to have chapters 1 through 4 available in a couple
    of weeks, which is dependent on us giving the chapters a final last make over
    and handing them over to the production team. [...]"
---
<p>The vote is running, and things are looking bleak for the wicked Wicket 2.0 constructor change.</p>
<p>What is that constructor change you might ask? Well, currently you construct your component hierarchy using an <code>add</code> method as can be seen in the next example:</p>
<pre>public class MyPage extends Page {
    public MyPage() {
        add(new Label("label", "Hello, World!"));
        Form form = new Form("form", ...);
        form.add(new TextField("field", ...));
        add(form);    
    }
}
</pre>
<p>As you can see, you can construct components and add them to the component hierarchy at will. This has advantages and disadvantages. One disadvantage is that you don't know the component hierarchy until render time. This puts extra burden on building Ajax components that require to know the markup id to do some JavaScript magic.</p>
<p>You can't use some functions in your component constructors, such as getPage (the component isn't added to the page yet), getMarkupAttributes (you don't know where to look for the tag of the component, it is not added to the page).</p>
<p>
There are more motivations to embark on the quest for the Holy Grail, and we went for it. The previous example looks like the following in the post constructor change (SWT style component wiring)</p>
<pre>public class MyPage extends Page {
    public MyPage() {
        new Label(this, "label", "Hello, World!"));
        Form form = new Form(this, "form", ...);
        new TextField(this, "field", ...));
    }
}
</pre>
<p>As you can see, we now provide the component constructor with the parent, solving the previous gripes. After working about a year on it and with it, we found that the grass actually isn't greener on the other side. Going back and forth, we now have a vote on the future of the constructor change:</p>
<blockquote>
<table>
<tr>
<th>When</th>
<th>What</th>
</tr>
<tr>
<td>Now</td>
<td>Backport the Model refactor and other remaining non-JDK-5 features from 2.0 to the 1.3.x branch.</td>
</tr>
<tr>
<td>Soon</td>
<td>Release a 1.3.0-beta to the community.</td>
</tr>
<tr>
<td>Soon</td>
<td>Release a 1.3.0-rc1. [2, 3, etc. if required]</td>
</tr>
<tr>
<td>A bit later</td>
<td>Release a 1.3.0 final.<br />
              Fork a 1.4.x branch from the 1.3.0 release.<br />
              Apply generics and other JDK-5 features to 1.4.x branch.<br />
              This will make 1.4.x look just like 2.0, but with the same<br />
              constructor/add logic as 1.2.x/1.3.x currently have.</td>
</tr>
</table>
<ul>
<li>"now" ~= right now.</li>
<li>"soon" ~= within a couple of weeks.</li>
<li>"A bit later" ~= within a month or so.</li>
</ul>
<p>
We will discontinue support for 2.0 once we have branched 1.4.x and<br />
added generics support into it, at which point the 2.0 branch will be<br />
renamed in subversion and left to stagnate.</p>
<p>
As already thrashed out in various discussions, this will achieve the<br />
following:</p>
<ul>
<li>Provide a migration path for 2.0 users within a month or so, so they<br />
   are not left high and dry. 1.4.x will be basically the same as 2.0<br />
   currently is, only with the constructor change backed out.</li>
<li>Give us two branches that will be very similar apart from JDK 5<br />
   features, and thus make it easy to back-port fixes/features from<br />
   the 1.4 branch to the 1.3 branch.</li>
<li>Give us a 1.3.0 beta that is feature-complete, and thus make<br />
   upgrading from beta >> RC >>final releases trivial.</li>
</ul>
</blockquote>
<p>I voted +1 for this, because I think the API break creates a too big chasm in our community, which would force us to fork our effort or to abandon (the larger) part of our community. Both are things I don't like. The upgrade path seems reasonable and will not let our early adaptors out to dry. Yes you have to do some effort to revert the constructor change, but we will do our best to get the other features as quickly available in the current and next Wicket version as possible.</p>
