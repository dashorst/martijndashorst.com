---
layout: post
status: publish
published: true
title: Questioning Component Based Web Development?
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 186
wordpress_url: http://martijndashorst.com/2005/05/26/questioning-component-based-web-development/
date: '2005-05-26 11:32:37 +0200'
date_gmt: '2005-05-26 11:32:37 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p><a href="http://jroller.com/page/chandrasekhar_s">Chandrasekhar</a> questions whether Component Based Development is worth it. My answer to his question is:</p>
<h1>YES! Component Based Development Is Worth It!</h1>
<p>Let me explain. Even though I'm a committer on a <a href="http://wicket.sf.net" title="Wicket">component based web application framework</a>, I support the <em>whole idea</em> of CBD for web gui's, not just my pet project (though I'd prefer if one chooses Wicket :-P). There is no way you can create complex applications just as easily with the model2 frameworks as you can with CB frameworks.</p>
<p>In Component Based frameworks you let go of the idea of a Request, instead you work with your components and their events. There is not 'one action to rule them all', but each component can have (has) one or more events associated with them. For instance, a <tt>Form</tt> has an <tt>onSubmit</tt> event, and (in Wicket) many Forms may be present on one page. So yes you are partly right: the frameworks you mention (Struts and Spring MVC) <strong>ARE</strong> <em>request driven</em>, but the component based frameworks (JSF, Tapestry and Wicket) are <em>Event driven</em>.</p>
<p>Wicket allows you to create <a href="http://www.wicket-library.com/wicket-examples/displaytag">multiple sortable, pageable tables</a>, which can sort and navigate <a href="http://www.wicket-library.com/wicket-examples/displaytag?bookmarkablePage=wicket.examples.displaytag.ExampleTwoTables">independently</a>. Of course this can be done with model2 frameworks, but how much effort will it take? In this case the necessary code size is <a href="http://cvs.sourceforge.net/viewcvs.py/wicket/wicket-examples/src/java/wicket/examples/displaytag/ExampleTwoTables.java?rev=1.3&view=auto">very small and understandable</a>.</p>
<p>I know that Tapestry and JSF also cater for this kind of complex GUI constructs, but differently, and if I might say: more complex and less elegant. But you should try it yourself, as I'm rather biased.</p>
<p>As for the other concern, the number of XML configuration files, this is just a matter of taste and framework. Wicket allows you to use ZERO (0) extra configuration files. The only required XML file is the <tt>web.xml</tt> file, which is mandated by the servlet specification. I'll repeat: NO XML CONFIGURATION files necessary when using Wicket.</p>
<p>Considering performance, whether you choose to use a component library, or a tag library from a vendor, you should have those concerns either way. That is always a concern with vendor supplied software. When you develop your own components, you have all the power to tune the performance yourself. You are in a better position to do so, because you can test the component independently.</p>
<p>
Furthermore, when using Wicket, you get clustering support out of the box (no sticky sessions required), when the clustering becomes problematic, Wicket allows you to exchange session size for computation. Thus allowing you to make a trade.</p>
<p>When you have such concerns about using component based frameworks, I'd suggest you try out one or the other. It is always a good thing to learn new stuff. And given your concerns, I'd <em>definetely</em> suggest you give <a href="http://wicket.sf.net">Wicket</a> a decent test drive. It may just make your day a little better.</p>
