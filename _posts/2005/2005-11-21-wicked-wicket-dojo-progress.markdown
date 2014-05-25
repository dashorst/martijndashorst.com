---
layout: post
status: publish
published: true
title: Wicked Wicket Dojo Progress
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 118
wordpress_url: http://martijndashorst.com/2005/11/21/wicked-wicket-dojo-progress/
date: '2005-11-21 14:17:21 +0100'
date_gmt: '2005-11-21 14:17:21 +0100'
categories:
- wicket
- java
tags: []
comments: []
---
<p>At my employer (<a href="http://www.topicus.nl">Topicus</a>) we have <a href="http://www.jroller.com/page/ruudmarco">two interns</a> that are building <a href="http://www.dojotoolkit.org">Dojo</a> Ajax components for the <a href="http://wicket.sf.net">Wicket</a> framework.</p>
<p>They are progressing steadily, and (after todays progress meeting) are going to build a formal release of their efforts, based on <a href="http://wicket.sourceforge.net/wicket-1.1">Wicket 1.1</a>. The release and its notes should become available on the <a href="http://wicket-stuff.sf.net/wicket-contrib-dojo">Wicket Dojo</a> project.</p>
<p>As an example, let me show you what they can do with one line of code. In our current (commercial project) we introduced serverside validation for social security numbers. For this we used one of the components of Ruud and Marco. When the validation of the input fails, the input field should fade to red. When it is corrected, it should fade back to the original color. With one line of code, we were able to add this functionality, and have the Ajax call implemented:</p>
<pre>ssnField = new RequiredTextField("ssn");
ssnField.add(SsnValidator.getInstance());
ssnField.add(new FXValidationAjaxHandler("onBlur",
        FXValidationAjaxHandler.REQUIREDCOLOR));
</pre>
<p>That is all there's to it!</p>
<p>Keep an eye on <a href="http://www.jroller.com/page/ruudmarco">their progress</a> as they are building very nice components!</p>
