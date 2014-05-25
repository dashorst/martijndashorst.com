---
layout: post
status: publish
published: true
title: More Reference Manual Progress
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 144
wordpress_url: http://martijndashorst.com/2005/08/11/more-reference-manual-progress/
date: '2005-08-11 00:50:27 +0200'
date_gmt: '2005-08-11 00:50:27 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>
This is yet another blurb from the work in progress on the <a href="http://wicket.sf.net">Wicket</a> reference manual. Again, this is just copied, and pasted, so no guarantees it looks great on your monitor. Feedback is always appreciated.</p>
<p><b>4.3. Processing User Input</b></p>
<p>
In the following section you will learn what <a href="http://wicket.sf.net">Wicket</a> does when your user presses the submit button. It is possible to add multiple buttons to a form, so that you can perform different actions when the form is submitted. This is described in the section 'Multiple Buttons'. It is also possible to bypass the Wicket form processing, which is described in 'Advanced Form Processing'.</p>
<p>
<b>4.3.1. Submitting a Form</b></p>
<p>
By default, the processing of a form works like this: The submitting button is looked up. A submitting button is a button that is nested in this form (is a child component) and that was clicked by the user. If a submitting button was found, and it has the immediate field true (default is false), its onSubmit method will be called right away, thus no validition is done, and things like updating form component models that would normally be done are skipped. In that respect, nesting a button with the immediate field set to true has the same effect as nesting a normal link. If you want you can call validate() to execute form validation, hasError() to find out whether validate() resulted in validation errors, and updateFormComponentModels() to update the models of nested form components. When no immediate submitting button was found, this form is validated (method validate()). Now, two possible paths exist:</p>
<p>
   1.</p>
<p>      Form validation failed. All nested form components will be marked valid, and onError() is called to allow clients to provide custom error handling code.<br />
<br />
   2.</p>
<p>      Form validation succeeded. The nested components will be asked to update their models and persist their data if applicable. After that, method delegateSubmit with optionally the submitting button is called. The default when there is a submitting button is to first call onSubmit on that button, and after that call onSubmit on this form. Clients may override delegateSubmit if they want different behaviour. </p>
<p>
<b>4.3.2. Multiple Buttons</b></p>
<p>
As mentioned before, Wicket allows you to use multiple buttons in your form for submitting the form. Say you want to provide a 'OK' and a 'Cancel' button on your form. The markup is as follows:</p>
<pre>
<form wicket:id="myForm">
    ...
    <input wicket:id="button1" type="submit" value="OK" />
    <input wicket:id="button2" type="submit" value="Cancel" />
</form>
</pre>
<p>Next we need to add the buttons and the code that needs to be performed when the button is pressed to the Java code:</p>
<pre>
public MyForm(String id, IModel model, IFeedback feedback) {
    ...
    add(new Button("button1") {
        public void onSubmit() {
            // do the OK bit
        }
    });
    add(new Button("button2") {
        public void onSubmit() {
            // do the cancel bit
        }
    });
}
</pre>
<p>When the user presses the 'OK' button (button1), then the onSubmit method of button1 is called. When the user presses the 'Cancel' button (button2), then the onSubmit method of button2 is called. Note that the onSubmit method is only called when the input is correctly validated. After the selected button has executed its submit method, the form's submit is called. This behaviour can be altered by overriding the delegateSubmit(Button submittingButton) of class Form.</p>
<pre>
public class MyForm extends Form {
    ...
    protected void delegateSubmit(Button submittingButton) {
        if(submittingButton != null) {
            // submit the button
            submittingButton.onSubmit();
        }
        // don't submit the form
    }
}
</pre>
<p><b>4.3.3. Advanced Form Processing</b></p>
<p>
<i>TODO: still under considerable developmen</i></p>
<p>
<b>4.4. Adding Validation</b></p>
<p>
In this section we will look at adding validation to your components, returning feedback to your users and give an overview of the validations Wicket provides.</p>
<p>
<b>4.4.1. Introduction</b></p>
<p>
Each web application needs some sort of validation of user input. Wicket provides you with localized validations that are easy to add to your components and easy to create yourself. Giving feedback to your users is paramount to the succes of your application, so Wicket makes it easy to give excellent feedback to your users in their own language using the standard Java localization and internationalization support.</p>
<p>
The basic structure of adding validation to your form components is the following:</p>
<p>
    *</p>
<p>      add a feedback component to your page<br />
<br />
    *</p>
<p>      register the feedback component with the form<br />
<br />
    *</p>
<p>      add the validators to your form components<br />
<br />
    *</p>
<p>      add validation messages to a resourcebundle</p>
<p>
<b>4.4.2. The Feedback loop</b></p>
<p>
<i>TODO: still under considerable development</i></p>
<p>
<b>4.4.3. Wicket Validations</b></p>
<p>Adding a validator to your components is not difficult: you need to get an instance of the validator (usually they are singletons) and add it to your component. The following code is taken from the form input example from the Wicket examples project.</p>
<pre>
<form wicket:id="myForm">
    <input wicket:id="required" type="text" />
    <input wicket:id="integer" type="text" />
    <input wicket:id="minmax" type="text" />
    <input wicket:id="text" type="text" />
    ... etc.
    <input type="submit" value="submit" />
</form>
</pre>
<p>In the following sections we will add to each field a different validator.</p>
<p>
<b>4.4.3.1. Required Input</b></p>
<p>
In order to force that input is available for a certain field, Wicket provides a RequiredValidator. The following code makes the first field in the example (wicket:id="required") a required field:</p>
<pre>
public MyForm(String id, IModel model, IFeedback feedback) {
    super(id, model, feedback);
    TextField field = new TextField("required", new PropertyModel(model, "text"));
    field.add(RequiredValidator.getInstance());
    add(field);
}
</pre>
<p>Note that instead of adding the RequiredValidator to the field, we could've used a RequiredTextField field. This is a Wicket component that does the validator administration for you:</p>
<pre>
public MyForm(String id, IModel model, IFeedback feedback) {
    super(id, model, feedback);
    RequiredTextField field = new RequiredTextField("required", new PropertyModel(model, "text"));
    add(field);
}
</pre>
<p>Adding the following feedback message to the MyPage.properties:</p>
<pre>myForm.required.RequiredValidator=${name} is required.</pre>
<p>The RequiredValidator only adds the ${name} parameter to the feedback message.</p>
<p>
<b>4.4.3.2. Typesafe Input</b></p>
<p>
To check whether user input is of the correct type, you'll have to add a TypeValidator to the field. A TypeValidator takes the class of the type which is required: Integer.class, Long.class etc. Usually you'd use the basic types from java.lang, because Wicket has already got the converters in place for those types. If you need more power, then you'd have to take a look at implementing your own IConverter.</p>
<pre>
public MyForm(String id, IModel model, IFeedback feedback) {
    super(id, model, feedback);
    TextField field = new TextField("integer", new PropertyModel(model, "integerField"));
    field.add(new TypeValidator(Integer.class));
    add(field);
}
</pre>
<p>As a shorthand, Wicket allows you to add the class of the property type to the field constructor. Wicket will then add a TypeValidator with the given type to the field.</p>
<pre>
public MyForm(String id, IModel model, IFeedback feedback) {
    super(id, model, feedback);
    TextField field = new TextField("integer", 
            new PropertyModel(model, "integerField"), Integer.class);
    add(field);
}</pre>
<p>Consequently, you'll have to add a message to the properties file with the following name: component.path.TypeValidator (replace the component.path bit with your path to the field).</p>
<pre>myForm.integer.TypeValidator=${input} is not a valid ${type}.</pre>
<p>This component adds ${name}, ${input}, ${type}, ${exception}, ${locale} and ${format} as parameters to the error message interpolation. Format is only valid if the type conversion involves a date.</p>
<p>
<b>4.4.3.3. Range Checking</b></p>
<p>
The IntegerValidator supplies you with the possibility to validate whether the user input lies within certain boundaries.</p>
<pre>
public MyForm(String id, IModel model, IFeedback feedback) {
    super(id, model, feedback);
    TextField field = new TextField("minmax", 
            new PropertyModel(model, "integerField"));
    field.add(IntegerValidator.range(-100, 100));
    add(field);
}</pre>
<p>The validator has the following parameters available in the error message interpolation: ${name}, ${input}, ${min} and ${max}.</p>
<pre>myForm.minmax.IntegerValidator=${input} is not between ${min} and ${max}.
</pre>
<p>For your convenience, the IntegerValidator has some default validators at hand: IntegerValidator.INT ensures that the value is in the valid integer range, IntegerValidator.LONG ensures that the value is in the valid long range, IntegerValidator.POSITIVE_INT ensures that the value is equal or larger than 0 in the valid integer range, and finally IntegerValidator.POSITIVE_LONG does the same, but then for long values.</p>
<p>
<b>4.4.3.4. Length Validations</b></p>
<p>Ensuring that user input is of a certain length, or minimaly X or maximaly Y long can be done using the LengthValidator. The LengthValidator has three factory methods. min returns a minimal length validator, max gives you a maximum length validator and range returns a validator which checks whether the user input is at least min characters long and most max characters long.</p>
<pre>
public MyForm(String id, IModel model, IFeedback feedback) {
    super(id, model, feedback);
    TextField field = new TextField("text", 
            new PropertyModel(model, "text"));
    field.add(LengthValidator.min(100));
    add(field);
}
</pre>
<p>The LengthValidator adds ${name}, ${input}, ${min} (when checking for a minimum length), ${max} (when checking for a maximum length) and ${length} (the actual length of the user's input) to the error message parameterlist.</p>
<pre>myForm.text.LengthValidator=${name} should contain between ${min} and ${max} characters
</pre>
<p><b>4.4.3.5. Pattern Validation</b></p>
<p>
Sometimes it is needed to validate whether a user has filled in text that needs to comply with some pattern. For instance, the dutch zip code format is four digits followed by two uppercase letters, seperated by a space: 1234 AB. Wicket allows you to specify a PatternValidator using the full power of the java.util.regex regular expression package.</p>
<p>
The constructor of PatternValidator takes either a regular expression string, or a precompiled regular expression.</p>
<pre>
public MyForm(String id, IModel model, IFeedback feedback) {
    super(id, model, feedback);
    TextField email = new TextField("zipcode", 
            new PropertyModel(model, "zipcode"));
    field.add(new PatternValidator("\d\d\d\d [A-Z][A-Z]"));
    add(field);
}
</pre>
<p>The PatternValidator just adds ${name} and ${input} to the error message parameters.</p>
<pre>myForm.zipcode.PatternValidator=${input} is not a valid zipcode
</pre>
<p><b>4.4.3.6. E-mail Address Validation</b></p>
<p>
To validate e-mail addresses Wicket provides a special PatternValidator which uses a standard (albeit rather complex) regular expression for e-mail addresses. Instead of creating your own e-mail address validator, we advise you to use the EmailAddressPatternValidator as it is very easy to make a mistake in validating e-mail addresses.</p>
<pre>
public MyForm(String id, IModel model, IFeedback feedback) {
    super(id, model, feedback);
    TextField email = new TextField("email", 
            new PropertyModel(model, "email"));
    field.add(EmailAddressPatternValidator.getInstance());
    add(field);
}</pre>
<p>The EmailAddressPatternValidator just adds ${name} and ${input} to the error message parameters.</p>
<pre>myForm.email.EmailAddressPatternValidator=${input} is not a valid e-mail address</pre>
