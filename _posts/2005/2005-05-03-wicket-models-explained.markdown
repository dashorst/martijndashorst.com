---
layout: post
status: publish
published: true
title: Wicket Models Explained
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 202
wordpress_url: http://martijndashorst.com/2005/05/03/wicket-models-explained/
date: '2005-05-03 00:59:56 +0200'
date_gmt: '2005-05-03 00:59:56 +0200'
categories:
- wicket
tags: []
comments: []
---
<p>A few weeks back, <a href="http://www.jroller.com/page/jonathanlocke" title="Jonathan Locke">Jonathan Locke</a> has written an article concerning the <a href="http://wicket.sourceforge.net/wiki/doku.php?id=models">different model types</a> in <a href="http://wicket.sourceforge.net" title="Wicket">Wicket</a>. I want to elaborate more on this subject, and shed some light on the basics of one of the most powerful models: <a href="http://wicket.sourceforge.net/apidocs/wicket/model/CompoundPropertyModel.html" title="Compound Property Model">the CompoundPropertyModel</a>.</p>
<h3>CompoundPropertyModel</h3>
<p>
When I first started working with these models, I thought: <em>WOW!</em>. Now the wow-moment has passed, I also encountered some limitations to this model type, just like an user on the <a href="http://www.mail-archive.com/wicket-user%40lists.sourceforge.net/msg01174.html">user-mailinglist</a>, First of all: what is the CompoundPropertyModel?</p>
<p>Wicket uses models to allow you to bind data objects to your web components. Wicket provides <a href="http://wicket.sourceforge.net/wiki/doku.php?id=models&amp;DokuWiki=6f1913b666507754608ba9844fbdb8a9">several models</a>, some of which are simple, some of which enable the use of <a>OGNL expressions</a> and some allow you to share your model between your web components.</p>
<p>The CompoundPropertyModel allows you to share the model between components, by binding the components at render time to the model. In a typical, non-shared model page, you'd see code like this:</p>
<pre>public class InputExamplePage extends WebPage
{
    public class Person { String name; Date birthdate; /* getters and setters */ }

    public InputExamplePage() {
        Person person = new Person();
        Form form = new Form("form", <font color="red">new Model(person)</font>, null);
        form.add(new TextField("name", <font color="red">new PropertyModel(person, "name")</font>);
        form.add(new TextField("birthdate", new PropertyModel(person, "birthdate"));
        add(form);
    }
}</pre>
<p>As you can see the model provided to the Form component on this page is a simple Model. This model only holds the data object and doesn't do anything else. Adding the TextFields you see the use of PropertyModels. These allow you to bind components to a property of a class. Note that you can't use the getter directly because that results in a read only TextField. Compare this to the following code, but now using a shared model:</p>
<pre>public class InputExamplePage extends WebPage
{
    public class Person { String name; Date birthdate; /* getters and setters */ }

    public InputExamplePage() {
        Person person = new Person();
        Form form = new Form("form", <font color="red">new CompoundPropertyModel(person)</font>, null);
        form.add(new TextField("name")));
        form.add(new TextField("birthdate"));
        add(form);
    }
}</pre>
<p>A lot shorter, isn't it? The only requirement is that the ID's of the components match property names. If this isn't the case, or if you wish to use property navigation (like person.address.street), you may consider using the <a href="http://wicket.sourceforge.net/apidocs/wicket/model/BoundCompoundPropertyModel.html">BoundCompoundPropertyModel</a>. The latter also allows you to navigate over properties, as can be seen in the last example:</p>
<pre>public class InputExamplePage extends WebPage
{
    public class Address { String street; /* getters and setters */ }
    public class Person { String name; Address address; /* getters and setters */ }

    public InputExamplePage() {
        BoundCompoundPropertyModel model = <font color="red">new BoundCompoundPropertyModel(new Person())</font>
        Form form = new Form("form", model, null);
        form.add(new TextField("name"));
        form.add(<font color="red">model.bind(new TextField("street"), "address.street")</font>);
        add(form);
    }
}</pre>
<p>There are some limitations to this model, which aren't apparent when you first start out using them.</p>
<h3>This doesn't work</h3>
<pre>public class InputExamplePage extends WebPage
{
    public class Person { String name; Person partner; /* getters and setters */ }

    public InputExamplePage() {
        Person partner = new Person();
        partner.setName("Partner");
        Person demo = new Person();
        demo.setName("Demo");
        demo.setPartner(partner);

        CompoundPropertyModel model = new CompoundPropertyModel(demo);

        Form demoForm = new Form("demo", model, null) {};
        demoForm.add(new TextField("name"));
        add(demoForm);

        Form partnerForm = new Form("partner") {};
        partnerForm.add(new TextField("name"));
        demoForm.add(partnerForm);
    }
}</pre>
<p>What kind of output do you expect? One text field with the value 'Demo', and one field with the value 'Partner'? <strong>Wrong!</strong>. You are correct in your assumption that partnerForm.getModelObject() will return the partner object, but the text field of the partner form will also be bound to the demo person. So you will see two fields with the same value: "Demo". This is because the model object of the partner form is shared between itself and all of its children. Mind you: this is not a bug, but behaviour as designed. Perhaps with the advent of <a href="http://wicket.sourceforge.net/wiki/doku.php?id=todo">Wicket 1.1</a> we will provide you with a NavigationCompoundPropertyModel enabling the navigation your datamodel by using your components.</p>
