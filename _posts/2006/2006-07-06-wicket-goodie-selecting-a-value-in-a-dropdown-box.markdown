---
layout: post
status: publish
published: true
title: 'Wicket goodie: selecting a value in a dropdown box'
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 39
wordpress_url: http://martijndashorst.com/2006/07/06/wicket-goodie-selecting-a-value-in-a-dropdown-box/
date: '2006-07-06 09:58:05 +0200'
date_gmt: '2006-07-06 09:58:05 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 57870
  author: AngloPolish
  author_email: admin@anglopolish.com
  author_url: http://anglopolish.com
  date: '2010-01-21 16:39:12 +0100'
  date_gmt: '2010-01-21 15:39:12 +0100'
  content: "This doesnt work at all\r\nthis line: Arrays.asList(Gender.values())));\r\n\r\nYou
    have to set ArrayList of string not enums"
- id: 57871
  author: AngloPolish
  author_email: admin@anglopolish.com
  author_url: http://anglopolish.com
  date: '2010-01-21 16:48:49 +0100'
  date_gmt: '2010-01-21 15:48:49 +0100'
  content: "My mistake. It works perfectly.\r\n\r\nI declared ma DropList with generics
    and that was the proolem."
- id: 60555
  author: Will Sargent
  author_email: will.sargent@gmail.com
  author_url: http://tersesystems.com
  date: '2011-05-23 07:11:45 +0200'
  date_gmt: '2011-05-23 06:11:45 +0200'
  content: "What if I want a different model to be set than the one selected?  i.e.
    I have\r\n\r\nclass Foo {\r\n  public String barId;\r\n}\r\n\r\nclass Bar {\r\n
    \  public String id;\r\n   public String name;\r\n}\r\n\r\nand I want to iterate
    the choices of a list of \"bar\" but set the element of foo.barId?  I've been
    playing with this for a couple of hours now, and I still can't figure out how
    to set an attribute from a drop down list."
---
<p>A regular question on the <a href="http://wicketframework.org">Wicket</a> mailinglist is how to pre-select a value in a drop down box.</p>
<p>
If you look at the following select box, you see that I've pre-selected the value 'female', while the value 'male' is first in line.</p>
<p>
Example code:</p>
<pre>Gender:
    <select>
        <option value="male">male</option>
        <option value="female" selected="true">female</option>
    </select></pre>
<p>
<b>Example:</b><br><br />
Gender: malefemale</p>
<p>
Typically you'll select an object value from a list, or an enum value (Java 5) from the list. First, lets create the enum for Gender:</p>
<p><pre>public enum Gender {
    male, female;
}</pre>
<p>
Now if we have a form that allows you to change the gender of a person using a drop down choice, this would typically look like the following example:</p>
<pre>
form.add(new DropDownChoice(
            "gender", 
            new PropertyModel(person, "gender"), 
            Arrays.asList(Gender.values())));
</pre>
<p>
So how do we make sure that female is the default choice? As you can see, the component has a property model as its model, and it is bound to the gender of the person. By setting the gender of the person to 'female' the drop down choice box will select that value when it is rendered.</p>
<p><pre>
person.setGender(Gender.female);
</pre>
<p>
New users of the <a href="http://wicketframework.org">Wicket framework</a> typically try to use an interaction based approach when working with components. This is typically done by setting a value on the component, and in the submit handler querying the component for the value. Often people use String values to put in the component and retrieve from, having to do type conversion and checking themselves. This circumvents a lot of basic features Wicket provides to you. If you use the model based approach as shown in the example above, you will get automatic type conversions, automatic setting of values and validation.</p>
