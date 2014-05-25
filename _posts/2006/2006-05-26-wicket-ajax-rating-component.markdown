---
layout: post
status: publish
published: true
title: Wicket Ajax Rating Component
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 48
wordpress_url: http://martijndashorst.com/2006/05/26/wicket-ajax-rating-component/
date: '2006-05-26 15:20:05 +0200'
date_gmt: '2006-05-26 15:20:05 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>I just committed an Ajax Wicket component for rating stuff, similar to the <a href="http://www.redalt.com/downloads/">Votio</a> wordpress plugin.</p>
<p>
<img src="http://www.jroller.com/resources/d/dashorst/rating.gif" /></p>
<p>
The links are rendered as Ajax links, which also provide a fallback in case Ajax isn't available. This way the vote almost always gets through. The component renders itself when the ajax request returns, and as a component user, you can also update other components yourself in the same request.</p>
<p>
Adding the rating component should be as simple as:</p>
<pre>Rating ratingModel = new Rating();
add(new RatingPanel("rating", new PropertyModel(ratingModel, "rating"), 5))
{
    protected boolean onIsStarActive(int star)
    {
        return ((RatingModel)getModelObject()).isActive(star);
    }

    protected void onRated(int rating, AjaxRequestTarget target)
    {
        ((RatingModel)getModelObject()).addRating(rating);
    }
});
</pre>
<p>and in your markup all you have to do is:</p>
<pre><span wicket:id="rating"></span>
</pre>
<p>where you want your rating box to go.</p>
<p>All you have to supply is your own implementation of a Rating object, which will keep track of the number of votes, averages the votes, and creates a rating.</p>
<p>Features of the rating component:</p>
<ul>
<li>use your own icons for the images</li>
<li>allow a user to vote only once (the implementation is up to you)</li>
<li>customize the styling</li>
<li>customizable rating system (it's all in the model, so ratings from 1-10, 1-5, F-A, are all possible)</li>
<li>label showing the absolute value of the rating (3.7 from 5 votes) can be turned off, or replaced with your own implementation</li>
</ul>
<p>The component will be part of wicket-extensions-1.2.1 (the next maintenance release of Wicket).</p>
