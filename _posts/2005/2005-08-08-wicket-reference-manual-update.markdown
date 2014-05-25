---
layout: post
status: publish
published: true
title: Wicket Reference Manual Update
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 146
wordpress_url: http://martijndashorst.com/2005/08/08/wicket-reference-manual-update/
date: '2005-08-08 11:06:26 +0200'
date_gmt: '2005-08-08 11:06:26 +0200'
categories:
- wicket
- java
tags: []
comments:
- id: 158
  author: Lasconic
  author_email: lasconicNOdfdSPAM@gmail.com
  author_url: ''
  date: '2005-09-08 14:17:09 +0200'
  date_gmt: '2005-09-08 14:17:09 +0200'
  content: |-
    You ask : Is this the kind of manual everybody is longing for?
    Yes it is !
---
<p>
I've begun work on a (<em>long overdue</em>) reference manual for <a href="http://wicket.sf.net">Wicket</a>, and wanted to get some initial feedback. Is this the kind of manual everybody is longing for?</p>
<p>
PS. This is a direct paste from the generated <a href="http://www.docbook.org">DocBook</a> version, so the markup is not 'optimized' for display within this JRoller template.</p>
<div>
<div>
<div>
<div>
<h2><a name="N1006E"></a>ChapterÂ 4.Â Form Input</h2>
</div>
</div>
</div>
<div>
<p><b>Abstract</b></p>
<p>                This chapter shows how you can process input from users using forms, inputs and<br />
                other form related components. We show how to add validation to your fields and<br />
                give your users feedback when they entered wrong input.
            </p>
</div>
<div>
<div>
<div>
<div>
<h2><a name="N10074"></a>4.1.Â Introduction</h2>
</div>
</div>
</div>
<p>
                Many webapplications need some sort of user input. This is an integral part<br />
                of dynamic web applications. Many web applications don't take localization and<br />
                internationalization into account. Often you have to write a lot of code for parsing<br />
                request parameters, validating and converting them into the actual types your<br />
                POJOs use.
            </p>
<p>
                With Wicket things will be different: you won't have to write lots and lots of<br />
                scaffolding: Wicket takes care of a lot of things: updating your POJOs,<br />
                converting the user input taking localization into account, validating the input,<br />
                displaying internationalized messages when the input isn't valid, etc.
            </p>
</div>
<div>
<div>
<div>
<div>
<h2><a name="N10081"></a>4.2.Â Form Components</h2>
</div>
</div>
</div>
<p>                Most, if not all, Wicket form components will be discussed in the following sections. The<br />
                goal is not to be complete and show all possible uses of each component, but to give an<br />
                initial outline of how such a component can be used. For more information, please look in<br />
                the JavaDoc of the components.
            </p>
<div>
<div>
<div>
<div>
<h3><a name="N10086"></a>4.2.1.Â Form</h3>
</div>
</div>
</div>
<p>
                    The<br />
                    <code>Form</code><br />
                    component is a container for your form components. In the markup a form looks<br />
                    like this:
                </p>
<pre><form wicket:id="myForm">
    ...
    <input type="submit" value="Submit" />

</form></pre>
<p>
                    To implement a form, subclass the<br />
                    <code>Form</code><br />
                    , add FormComponents (such as CheckBoxes, ListChoices or TextFields) to the form<br />
                    and override the<br />
                    <code>onSubmit</code><br />
                    method. You can nest multiple buttons if you want to vary submit behaviour.<br />
                    However, it is not necesary to use Wicket's button class, just putting e.g.<br />
                    <code><br />
                        <input type="submit" value="go"><br />
                    </code></p>
<p>                    suffices.
                </p>
<pre>public class MyForm extends Form {
    public MyForm(String id, IModel model, IFeedback feedback) {
        // add (form) components
    }
    public void onSubmit() {
        // handle the submission of the form.
    }
    public void onError() {
        // do something special when an error occurs,
        // instead of displaying messages.
    }
}</pre>
<p>
                    Wicket will call <code>onSubmit</code> when the user input is<br />
                    valid. When one or more child components of the form fails to validate,<br />
                    Wicket will call <code>onError</code>. Wicket also supports<br />
                    multiple buttons, which are discussed later.
                </p>
</div>
<div>
<div>
<div>
<div>
<h3><a name="N100A9"></a>4.2.2.Â TextField</h3>
</div>
</div>
</div>
<p>
                    A <code>TextField</code> receives user input in possibly its<br />
                    most basic form: a single line of text. The markup for a<br />
                    <code>TextField</code> component <em>must</em> be a<br />
                    <code><input type="text" ... /></code> tag, otherwise Wicket<br />
                    will throw an exception.
                </p>
<p>                    The markup for a textfield looks as follows:
                </p>
<pre><form wicket:id="myForm">
    <input wicket:id="textField" type="text" />
    ...
</form></pre>
<p>
                    In the Java code you can use several constructors for the component, depending<br />
                    on the type of model you want to bind to the textfield.
                </p>
<pre>public MyForm(String id, IModel model, IFeedback feedback) {
    super(id, model, feedback);
    add(new TextField("textField", new PropertyModel(model, "name")));
    ...
}</pre>
<p>
                    It is possible to use the true types of the fields in the textfield component.<br />
                    Say that you need an integer value. Instead of performing the dataconversion<br />
                    yourself, you specify for Wicket that you require an integer value by adding<br />
                    an extra parameter to the <code>TextField</code> constructor: the<br />
                    type of the property.
                </p>
<pre>new TextField("integerField", new PropertyModel(model, "myInt"), Integer.class)</pre>
<p>                    More information on this subject is provided in the validation section later on.
                </p>
</div>
<div>
<div>
<div>
<div>
<h3><a name="N100CE"></a>4.2.3.Â PasswordTextField</h3>
</div>
</div>
</div>
<p>
                    The <code>PasswordTextField</code> component is used for users to enter<br />
                    their passwords. The field can be used in both login forms and registration forms.<br />
                    In login forms it is usually required that the password is always cleared when the<br />
                    page is rendered. When editing account information, this is not the case, so the<br />
                    password field can be told not to clear the field when rendered. The markup looks<br />
                    like this (the <code>type="password"</code> is required!):
                </p>
<pre><input wicket:id="pwd" type="password"/></pre>
<p>
                    The corresponding Java declaration looks like this:
                </p>
<pre>PasswordTextField pwd = new PasswordTextField("pwd", new PropertyModel(model, "myPwd"));</pre>
<p>                    When you want to use the field in a registration form, or some other form where the<br />
                    password should not be reset on each render, you have to set the reset password flag<br />
                    to <code>false</code>:
                </p>
<pre>pwd.setResetPassword(false);</pre>
<p>
                    The default is to clear the field each time it is rendered.
                </p>
</div>
<div>
<div>
<div>
<div>
<h3><a name="N100EB"></a>4.2.4.Â TextArea</h3>
</div>
</div>
</div>
<p>
                    The <code>TextArea</code> component is a multi-line text editing component.<br />
                    The component requires to be attached to a <code><textarea></code></p>
<p>                    tag in the markup:
                </p>
<pre><form wicket:id="myForm">
    <textarea wicket:id="myTextArea" rows="6" cols="20"></textarea>
    ...
</form></pre>
<p>
                    The corresponding Java code looks like this:
                </p>
<pre>TextArea area = new TextArea("myTextArea", new PropertyModel(model, "text"));</pre>
<p>
                    If you have to programmatically alter the <code>rows</code> or <code>cols</code></p>
<p>                    attributes of the tag, then you can add <code>AttributeModifier</code>s<br />
                    to the <code>TextArea</code> in order to produce the required effect:
                </p>
<pre>area.add(new AttributeModifier("rows", 10));</pre>
</div>
<div>
<div>
<div>
<div>
<h3><a name="N1010F"></a>4.2.5.Â CheckBox</h3>
</div>
</div>
</div>
<p>
                    The <code>CheckBox</code> component displays a checkbox. The checkbox can<br />
                    either be checked or not, corresponding to a <code>true</code> or <code>false</code>constant></p>
<p>                    value for the bound model. The <code>CheckBox</code> requires to be attached<br />
                    to a input field whose type is 'checkbox':
                </p>
<pre><form wicket:id="myForm">
    <input wicket:id="myCheckbox" type="checkbox" />
    ...
</form></pre>
<p>
                    The corresponding Java code:
                </p>
<pre>CheckBox check = new CheckBox("myCheckbox", new PropertyModel(model, "boolValue"));</pre>
<p>                    It is also possible to have the <code>CheckBox</code> respond directly to changes. Wicket will add<br />
                    a small piece of JavaScript in order to generate the <code>onSelectionChanged(Object newSelection)</code><br />
                    event.
                </p>
<pre>CheckBox check = new CheckBox("myCheckbox", new PropertyModel(model, "boolValue")) {
    protected boolean wantOnSelectionChangedNotifications() {
        return true;
    }
    protected void onSelectionChanged(Object newSelection) {
        Boolean value = (Boolean)newSelection;
        if(value.boolValue()) {
            // do something
        }
    }
};</pre>
</div>
<div>
<div>
<div>
<div>
<h3><a name="N10133"></a>4.2.6.Â RadioChoice</h3>
</div>
</div>
</div>
<p>
                    The <code>RadioChoice</code> component creates a number of radiobuttons<br />
                    on your form. The <code>RadioChoice</code> requires both a model to bind the<br />
                    value in, and a list of choices to display and select from. The list of choices can<br />
                    come from a database or be filled from your Java code.<br />
                    It requires an <code>input</code> markup tag of type '<code>radio</code>':
                </p>
<pre><form wicket:id="myForm">

    <input wicket:id="myRadio" type="radio" value="myValue" />
    ...
</form></pre>
<p>
                    When you have a list filled with the strings 'foo' and 'bar', and you supply the<br />
                    RadioChoice with that list, Wicket will generate each choice for you in the final<br />
                    markup.
                </p>
<pre>public MyForm(String id, IModel model, IFeedback feedback) {
    super(id, model, feedback);
    List choices = new ArrayList();
    choices.add("foo");
    choices.add("bar");
    add(new RadioChoice("myRadio", new PropertyModel(model, "foobar"), choices));
}</pre>
<p>
                    It is possible to construct more advanced methods of binding and creating selection<br />
                    choices. See the chapter on database applications for more information.
                </p>
</div>
<div>
<div>
<div>
<div>
<h3><a name="N1014E"></a>4.2.7.Â ListChoice</h3>
</div>
</div>
</div>
<p>
                    This component shows a plain listbox filled with the choices to choose from. The<br />
                    component only supports single selection values. When the number of choices is bigger than<br />
                    the number of displayed values, a scrollbar is shown (by the browser). The required markup<br />
                    looks like this:
                </p>
<pre><form wicket:id="myForm">

    <select wicket:id="myListChoice" size="2">
        <option>option1</option>
        <option>option2</option>
    </select>
    ...

</form></pre>
<p>
                    The <code>size</code> attribute is merely for previewing purposes. Wicket will add the<br />
                    attribute when it is not present. The Java code for creating a <code>ListChoice</code>:
                </p>
<pre>public MyForm(String id, IModel model, IFeedback feedback) {
    List choices = new ArrayList();
    choices.add("foo");
    choices.add("bar");
    ListChoice lc = new ListChoice("myListChoice", new PropertyModel(model, "foobar"), choices);
    lc.setMaxRows(2);
    add(lc);
    ...
}</pre>
</div>
<div>
<div>
<div>
<div>
<h3><a name="N10161"></a>4.2.8.Â ListMultipleChoice</h3>
</div>
</div>
</div>
<p>
                    This component shows a plain listbox filled with the choices to choose from. The<br />
                    component supports multiple selection values. When the number of choices is bigger than<br />
                    the number of displayed values, a scrollbar is shown (by the browser). The required markup<br />
                    looks like this:
                </p>
<pre><form wicket:id="myForm">

    <select wicket:id="myMultiListChoice" size="2">
        <option>option1</option>
        <option>option2</option>
    </select>
    ...

</form></pre>
<p>
                    The component needs a <code>java.util.Collection</code> as the model object,<br />
                    in order to supply your object with the multiple choices. The Java code for this component<br />
                    looks like:
                </p>
<pre>public MyForm(String id, IModel model, IFeedback feedback) {
    List choices = new ArrayList();
    choices.add("foo");
    choices.add("bar");
    MultiListChoice lc = new MultiListChoice("myMultiListChoice", new PropertyModel(model, "foobarList"), choices);
    add(lc);
    ...
}</pre>
</div>
<div>
<div>
<div>
<div>
<h3><a name="N10171"></a>4.2.9.Â DropDownChoice</h3>
</div>
</div>
</div>
<p>
                    This component shows a dropdown box filled with the choices to choose from. The selected value<br />
                    during rendering is the value of the model object. When the selection is changed, the selected<br />
                    value is set on the model object. The required markup looks like this:
                </p>
<pre><form wicket:id="myForm">
    <select wicket:id="myDropDownChoice">

        <option>option1</option>
        <option>option2</option>
    </select>
    ...
</form></pre>
<p>                    The corresponding Java code looks like:
                </p>
<pre>public MyForm(String id, IModel model, IFeedback feedback) {
    List choices = new ArrayList();
    choices.add("foo");
    choices.add("bar");
    DropDownChoice lc = new DropDownChoice("myDropDownChoice", new PropertyModel(model, "foobar"), choices);
    add(lc);
    ...
}</pre>
<p>
                    The <code>DropDownChoice</code> also supports listening to<br />
                    <code>onchange</code> events on the clientside, like the <code>CheckBox</code><br />
                    does. Wicket will add a small piece of JavaScript in order to generate the<br />
                    <code>onSelectionChanged(Object newSelection)</code> event.
                </p>
<pre>DropDownChoice choice = new DropDownChoice("myDropDownChoice", new PropertyModel(model, "foobar"), choices) {
    protected boolean wantOnSelectionChangedNotifications() {
        return true;
    }
    protected void onSelectionChanged(Object newSelection) {
        // do something
    }
};</pre>
</div>
</div>
</div>
</div>
