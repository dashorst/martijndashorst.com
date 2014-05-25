---
layout: post
status: publish
published: true
title: Do Wicket and Ajax Rhyme?
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 136
wordpress_url: http://martijndashorst.com/2005/08/22/do-wicket-and-ajax-rhyme/
date: '2005-08-22 10:41:22 +0200'
date_gmt: '2005-08-22 10:41:22 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>
<a href="http://wicket.sf.net">Wicket</a> inspires a lot of people to write nice, clean web applications. Now the <a href="http//www.jroller.com/page/wireframe"><tt>code_poet</tt></a> has written a nice poem about Wicket and AJAX. It has good metrum and it shows that even though AJAX support is still crude, Wicket and AJAX rhyme!</p>
<p><a>Ryan Sonnek</a> has published a <a href="http://www.jroller.com/page/wireframe/?anchor=wicket_autocomplete_text_field">Auto Complete TextField</a> component for Wicket using AJAX. Although the component code is a bit complex, the usage of the component has the Wicket feel all over it.</p>
<p>How would you like to use a full fledged AJAX component with no more code than:</p>
<pre><input wicket:id="email" type="text" /></pre>
<p>And Java:</p>
<pre>
AutocompleteResultGenerator searcher = 
    new AutocompleteResultGenerator() {
        public String[] getResults(String input) {
            return new String[] {"Bob", "Jamie", "Eric"};
        }
    };
form.add(new AutoCompleteTextField("email", searcher));</pre>
<p>That would be awesome, wouldn't it? With <a href="http://wicket.sf.net">Wicket</a> this is possible.</p>
