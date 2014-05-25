---
layout: post
status: publish
published: true
title: Hibernate 3 / EJB3 annotations severely limited?
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 81
wordpress_url: http://martijndashorst.com/2006/03/14/hibernate-3-ejb3-annotations-severely-limited/
date: '2006-03-14 15:49:56 +0100'
date_gmt: '2006-03-14 15:49:56 +0100'
categories:
- java
- hibernate
tags: []
comments:
- id: 86
  author: Hazem Saleh
  author_email: ''
  author_url: http://www.jroller.com/page/HazemBlog
  date: '2006-03-14 16:30:42 +0100'
  date_gmt: '2006-03-14 16:30:42 +0100'
  content: Nice article. Thank you.
- id: 87
  author: n8han
  author_email: ''
  author_url: http://technically.us/n8/
  date: '2006-03-14 16:47:46 +0100'
  date_gmt: '2006-03-14 16:47:46 +0100'
  content: "I think you can get what you want through @Embeddable (which seems to
    be a fairly magical annotation.) I used it for a list of Ingredient objects in
    a Recipe:\n \nhttp://databinder.net/recipe-src/java/example/Ingredient.xhtml\nhttp://databinder.net/recipe-src/java/example/Recipe.xhtml\n\nJust
    checked the table and it does have a primary key index on both Recipe_ingredients.Recipe_id
    and Recipe_ingredients.ordinal (I should have capitalized that!)."
---
<p>Apparently modelling a simple parent child relationship where the primary key of the parent is part of a composite key on the child is not possible using EJB3 annotations.</p>
<p>
For <em>enterprise</em> beans this seems like a very large oversight. I know a couple of projects that use this idiom for their relational structures. It feels odd that this is not part of the current implementation of the EJB3 annotations. For those trying out Hibernate, <a href="http://forum.hibernate.org/viewtopic.php?t=955392">here is a forum post</a> regarding this problem.</p>
<p>
The problem I am facing is in my opinion a very basic mapping case. It seems strange and very limiting that it is not part of the annotations.</p>
<p>
For those that don't get what I am referring to, consider the following:</p>
<pre>
@Entity
public class Parent {
    @Id
    Long id;

    @OneToMany
    @JoinColumn(name = "parent")
    List children;
}

@Entity
public class Child {
    @ManyToOne()
    @JoinColumn(nullable = false, insertable = false, updatable = false, name = "parent")
    Parent parent;

    Long childNr;
}
</pre>
<p>
Now try to make both the <tt>parent</tt> and the <tt>childNr</tt> part of the primary key of the child using annotations.</p>
<p>
And what seems even worse, is that you need to define a composite key class especially for using a composite key. Apparently that is needed for sending over the object's key across the network.</p>
<p>
Annotations are very useful, and we have been able to build large parts of our system using them. So don't see this as a rejection of the technology as a whole. I enjoy working with annotations for mapping purposes but they just don't seem to be quite there yet.</p>
