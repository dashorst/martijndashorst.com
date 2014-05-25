---
layout: post
status: publish
published: true
title: Wicket Page Counter Example
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 142
wordpress_url: http://martijndashorst.com/2005/08/16/wicket-page-counter-example/
date: '2005-08-16 22:17:59 +0200'
date_gmt: '2005-08-16 22:17:59 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>Sometimes it is very helpful to read old messages in your mail archive. I found a short discussion where I promised Stefan Arentz that we would incorporate some code he sent to the mailinglist into our examples. Well, of course I forgot all about it, and just 5 minutes ago rediscovered his message and example. So without any delay: here's a page counter component made in <a href="http://wicket.sf.net">Wicket</a>:</p>
<p><b>Stefan Arentz wrote:</b></p>
<blockquote><p>
As an experiment I create a little counter panel.  The markup looks like this:</p>
<pre><html><body>
<wicket:panel>
    <span wicket:id="count">123</span>
</wicket:panel>
</body></html></pre>
<p>And this is the code (quick hack, not thread safe):</p>
<pre>public class Counter extends Panel
{
    static Map mCounters = new HashMap();
    private String mCounterName;

    public Counter(String componentName, String counterName)
    {
        super(componentName);
        mCounterName = counterName;
        Integer count = (Integer) mCounters.get(mCounterName);
        if (count == null) {
            count = new Integer(1);
        } else {
            count = new Integer(count.intValue() + 1);
        }
        mCounters.put(mCounterName, count);
        add(new Label("count", count.toString()));
    }
}</pre>
<p>Pretty simple. And I can now make different counters for pages like  this:</p>
<p><b>Markup:</b></p>
<pre><span wicket:id="counter" /></pre>
<p><b>Java:</b></p>
<pre>add(new Counter("counter", "HomepageCounter"));</pre>
</blockquote>
<p>
The fun part is, that this is a full fledged component, that can be put in a jar, put in the classpath of your webapplication, and all you have to do is use the two little fragments at the end of the quote, to incorporate the hit counter in your page(s).</p>
<p>
I like the simplicity of this example. It doesn't take rocket science to create such a component. It doesn't take any XML to create or use this component. Now that is where JSF still has something to gain.</p>
