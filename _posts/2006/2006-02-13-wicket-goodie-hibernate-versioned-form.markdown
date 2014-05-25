---
layout: post
status: publish
published: true
title: 'Wicket goodie: Hibernate Versioned Form'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 95
wordpress_url: http://martijndashorst.com/2006/02/13/wicket-goodie-hibernate-versioned-form/
date: '2006-02-13 10:38:31 +0100'
date_gmt: '2006-02-13 10:38:31 +0100'
categories:
- wicket
- java
- hibernate
tags: []
comments:
- id: 107
  author: n8han
  author_email: ''
  author_url: http://technically.us/n8/
  date: '2006-02-13 17:06:12 +0100'
  date_gmt: '2006-02-13 17:06:12 +0100'
  content: Good idea! I'll have to copy it in Databinder, if that's all right with
    you.
- id: 108
  author: Martijn Dashorst
  author_email: dashorst@users.sf.net
  author_url: http://www.jroller.com/page/dashorst/
  date: '2006-02-13 18:15:57 +0100'
  date_gmt: '2006-02-13 18:15:57 +0100'
  content: |-
    Sure, that is what this blog is for: sharing information for others to use.

    Martijn
---
<p>Last week I had the pleasure to add optimistic locking to our web application, using automatic versioning in Hibernate. What we want is to detect a stale object when a form is submitted and displaying the new representation from the database, overriding the submitted data.</p>
<p>
So when two people open an edit form for the same contact, and the first to submit renames the contact from 'Foo' to 'Bar', the database will be updated, changing the name from 'Foo' to 'Bar'. When the second user tries to save the contact, changing the name from 'Foo' (that was the last information he got) to 'John', we want to show him that the data has been changed by someone else, and show him the new information, disregarding his change to 'John'.</p>
<p>
Now, how would you do this for <i>all</i> your forms in your application without resorting to the usual hidden field option? <a href="http://wicket.sf.net">Wicket</a> has allowed me to do such a thing without much trouble. Here's a short description.</p>
<p><pre>public class VersionedForm extends Form {
    private Long version;

    public VersionedForm(String id, IModel model) {
        super(id, model);
        version = getVersion();
    }

    protected void validate() {
        Long newVersion = getVersion();

        if(!newVersion.equals(version)) {
            // new method in 1.2
            clearInput();

            // detaches the model of the page, and evicts the
            // object from the hibernate session
           ((MyPage) getPage()).reloadModel();

           // copy the new version onto the form
           version = newVersion;
           error("Someone else modified the object already, try again");
        } else {
           // do the default form processing.
           super.validate();
        }
    }
    private Long getVersion() {
        // get the version of the model object
        // either through reflection or just a cast to your base object
        return ((MyBaseObject)getModelObject()).getVersion();
    }
}
</pre>
<p>Here you see three important steps:
<p>
1. set the current version in the constructor<br><br />
2. check the version in the validate() method<br><br />
3. reload the object when it is not valid, and clear the user input</p>
<p>
Retrieving the version can be implemented using reflection, searching for the @version annotation, or by implementing a custom interface IVersioned, or something to your liking.</p>
<p>
The reloading of the object and evicting it from the Hibernate session is something we implement at the page level, as we always put the object that is edited into the page model.</p>
<p>
The best part is that in any edit page we have, we now just have to subclass our forms from VersionedForm, and we have instant optimistic locking.</p>
