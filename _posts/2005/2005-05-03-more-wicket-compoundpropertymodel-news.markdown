---
layout: post
status: publish
published: true
title: More Wicket CompoundPropertyModel News
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 201
wordpress_url: http://martijndashorst.com/2005/05/03/more-wicket-compoundpropertymodel-news/
date: '2005-05-03 16:02:57 +0200'
date_gmt: '2005-05-03 16:02:57 +0200'
categories:
- wicket
tags: []
comments: []
---
<p>Just updated <a href="http://wicket.sourceforge.net" title="Wicket">Wicket</a> to enable even more CompoundPropertyModel magic! You can now use the following construct without pain:</p>
<p>The most important change is that you can just use the <em>'children'</em> property as a model for a ListView, as you would any other property with any other Component.</p>
<pre>/** Constructor */
public FooPage() {
    Form form = new Form("form", new CompoundPropertyModel(new Person(), null);
    add(form);

    form.add(new TextField("name"));
    form.add(new ListView("children") {
        <strong>protected IModel getListItemModel(final IModel listViewModel, final int index)
        {
            return new CompoundPropertyModel(super.getListItemModel(listViewModel, index));
        }</strong>
        void populateItem(ListItem item) {
            item.add(new TextField("name"));
            item.add(new TextField("favouriteDoll"));
        }
    }
}</pre>
<p>The area marked in <strong>bold</strong> allows you to add components to your listitem using a CompoundPropertyModel.</p>
<p>I think this is pretty cool, and makes working with Wicket feel like a charm.</p>
