---
layout: post
status: publish
published: true
title: A better way of hiding and revealing markup elements?
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 59
wordpress_url: http://martijndashorst.com/2006/04/23/a-better-way-of-hiding-and-revealing-markup-elements/
date: '2006-04-23 23:38:16 +0200'
date_gmt: '2006-04-23 23:38:16 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p><a href="http://prototype.conio.net/">Prototype.js</a> uses direct manipulation of the style of an element instead of relying on CSS. For instance to hide and show an element they do the following (disclaimer, this is not <em>actual</em> prototype code, I merely interpreted it from memory):</p>
<pre>function Element.hide(elmt) {
    elmnt.style.display = 'none';
}

function Element.show(elmt) {
    elmnt.style.display = '';
}
</pre>
<p>This works most of the time, but I think this approach is flawed in the sense that it steps over the ideas of CSS. Why don't they have a <tt>prototype.css</tt> which does the following:</p>
<pre>.hidden {
    display : none;
}</pre>
<p>and in the <tt>prototype.js</tt> they could do the following:</p>
<pre>function Element.hide(elmt) {
    elmt.addClassName('hidden');
}

function Element.show(elmt) {
    elmt.removeClassName('hidden');
}
</pre>
<p>This is cross browser compatible, and doesn't mess with the default value of the display property. I'm not sure if setting <tt>element.style.display='';</tt> always reverts the display property to the correct value for the element in question. But the CSS way sure feels a lot better.</p>
<p>
I can only see the implication of deminished performance for showing and hiding elements, but I doubt you'd notice it.</p>
