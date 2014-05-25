---
layout: post
status: publish
published: true
title: Wicket 1.1-beta and AJAX
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 150
wordpress_url: http://martijndashorst.com/2005/07/29/wicket-11-beta-and-ajax/
date: '2005-07-29 00:02:25 +0200'
date_gmt: '2005-07-29 00:02:25 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p><a href="http://wicket.sourceforge.net/wicket-1.1">Wicket 1.1</a> has basic, <em>yet highly <strong>experimental</strong></em> support for <a href="http://www.ajaxian.com">AJAX</a>. Pending <a href="http://wicket.sourceforge.net/wiki/index.php/AJAX">our AJAX efforts</a> scheduled for Wicket 1.2, I wanted to show how this AJAX thingy might work using Wicket. Nothing fancy dandy, but something I can use directly in my current project.</p>
<p><em>NOTA BENE</em></p>
<ul>
<li>this is my first AJAX experiment, so this is definetely not a best practise</li>
<li>AJAX support is in its infancy in Wicket 1.1, so this may not work in future versions</li>
<li>Wicket 1.1 is still BETA software. Stuff may break</li>
<li>I used stuff that is currently only in HEAD (<code>updateModel</code> change), so this won't work with a vanilla wicket-1.1-b1</li>
</ul>
<p>That said, let's continue with my AJAX experiment!</p>
<p>My current project will be something like a webbased spreadsheet, so I see a lot of AJAX stuff happening in the future with this project (if that darn manager would only let me): calculations done on the serverside would be done 'instantaneously'. The results of the calculations would be sent directly to the client, without having to submit anything. Needless to say, I'm pretty enthousiastic on putting AJAX into good use here.</p>
<p>To start slowly I want to update the data on the serverside of a text field on a form without doing a full blown post. <a href="http://www.jroller.com/page/eelco12">Eelco</a> pointed me to the <a href="http://www.wicket-library.com/wicket-examples/forminput">Form input example</a>, where on the integer field an AJAX call is performed (<em>NOTE</em> the demo currenlty only works with internet explorer, this has already been fixed!). This call only calls the validation on the field itself, but this is nearly enough functionality for me to begin with:</p>
<ul>
<li>send modified field data to server</li>
<li>validate value</li>
<li>when data is valid, update the model</li>
<li>send status back to client (error or success)</li>
<li>update class of field to show status</li>
</ul>
<p>So when I take this code, I should be almost finished. The example uses the <a href="http://www.dojotoolkit.org">dojo</a> toolkit for the AJAX request handling, so this is what I'm using.</p>
<p>The markup for the page I'm creating is very simple:</p>
<pre><html>
<head>
<style type="text/css">
.success { background-color : #0F0; }
.error { background-color : #F00; }
</style>
<body>
<form wicket:id="form">
<input wicket:id="field" type="text />
</form>
</body>
</html></pre>
<p>And the corresponding Java code is also simple:</p>
<pre>public class MyPage extends WebPage {
    public class FormObject implements Serializable {
        private String field;
        public String getField() { return field; }
        public void setField(String value) { field = value; }
    }

    public MyPage() {
        Form myForm = new Form("form", 
                new CompoundPropertyModel(new FormObject()), null) {
            protected void onSubmit() {
            }
        };
        TextField field = new RequiredTextField("field");
        myForm.add(field);
    }
}</pre>
<p>And a properties file for the RequiredValidator (required textfield automatically adds the validator to the textfield):</p>
<pre>form.field.RequiredValidator=${name} is required.</pre>
<p>This is basically a very simple input form. No special stuff happening here. On with the AJAX stuff!</p>
<p>Now, when the AJAX event has been executed on the server and a response is returned, I want the classname of the inputfield set to one of the two defined CSS classes: success or error. The dojo kit supplies us with a bind method which does the call to the server and takes a handler for when the answer is returned:</p>
<pre>dojo.io.bind({
    url: "http://foo.bar.com/sampleData.txt",
    load: function(type, data, evt){ <font>/*do something w/ the data */ </font>},
    mimetype: "text/plain"
});</pre>
<p>(shamelessly taken from the dojo site). I need to change the 'function' part here: the string <code>/*do something w/ the data*/</code> will have to become something like:</p>
<pre>
field.className = data;</pre></p>
<p>The next thing to do is add a listener for the AJAX request to the field. Wicket provides the daring with <code>DojoEventRequestHandler</code> giving me out-of-the-box Dojo support. But I take a short cut. Eelco already has a <tt>ValidationEventRequestHandler</tt>, so I just copy that sourcecode and modify the bits I need:</p>
<pre>protected final IResourceStream getResponse() {
    StringBufferResourceStream s = new StringBufferResourceStream();

    formComponent.validate();
    <font>if (formComponent.isValid()) {
        formComponent.updateModel();
    }
    s.append(formComponent.isValid() ? "success" : "error");</font>

    return s;
}</pre>
<p>This performs the actual AJAX action on the server. I validate the incoming value, and when valid, I update the model on the form component. Lastly I return either 'success' or 'error' to the browser.<br />
For the JavaScript side, we need to add an <code>onchange</code> handler which calls the dojo functionality. The update function that is called from here will be added to the header of the page (this uses<br />
the new Wicket JavaScript support!):</p>
<pre><script language="JavaScript" type="text/javascript">
    function update(componentUrl, componentPath, field) { 
        dojo.io.bind({
            url: componentUrl + '&' + componentPath + '=' + field.value,
            mimetype: "text/plain",
            load: function(type, data, evt) {
                <font>field.className = data;</font>
            }
        });
    }
</script>;</pre>
<p>Here you see that we call the <code>dojo.io.bind</code> function, and provide it with our own functionality to set the class of the field. When we add this to the header from within the Wicket code it looks like this:</p>
<pre>public final void doPrintHead(HtmlHeaderContainer container) {
    String s =

    "\t<script language=\"JavaScript\" type=\"text/javascript\">\n"
            + "\tfunction update(componentUrl, componentPath, field) { \n"
            + "\t\tdojo.io.bind({\n"
            + "\t\t\turl: componentUrl + '&' + componentPath + '=' + field.value,\n"
            + "\t\t\tmimetype: \"text/plain\",\n"
            + "\t\t\tload: function(type, data, evt) {\n"
            + "\t\t\t\tfield.className = data;\n" + "\t\t\t}\n"
            + "\t\t});\n" + "\t}\n" + "\t</script>\n";

    container.getResponse().write(s);
}</pre>
<p>This looks complex, but it is just escaped JavaScript (the same as above). As a final thing to do, we need to change the <code>onchange</code> event handler on the field so that it calls the <code>update</code> JavaScript function.</p>
<pre>public final void onComponentTag(final Component component, final ComponentTag tag) {
    final ValueMap attributes = tag.getAttributes();
    final String url = formComponent.urlFor(IEventRequestListener.class) 
        + "&id=" + getId();
    final String attributeValue = "<font>javascript:update(</font>'" 
        + url + "', '" + formComponent.getPath() + "', this);";
    attributes.put(getEventName(), attributeValue);
}</pre>
<p>Put in the rest of the functions that are already provided for by Eelco, and we have a working Ajax enabled field.</p>
<p>The accomplishment is not huge on a global scale, but I find it very cool to have done this basic stuff. <strong>Now before<br />
you start doing this yourself</strong>: <em>this is experimental code</em>, and is not the official AJAX support of Wicket. There are<br />
no guarantees that this will work in any version of Wicket now or in the future.</p>
<p><!-- technorati tags start --></p>
<p>Technorati Tags:<br />
<a href="http://technorati.com/tag/wicket" rel="tag">wicket</a>,<br />
<a href="http://technorati.com/tag/ajax" rel="tag">ajax</a>,<br />
<a href="http://technorati.com/tag/javascript" rel="tag">javascript</a>,<br />
<a href="http://technorati.com/tag/xmlhttprequest" rel="tag">xmlhttprequest</a></p>
<p><!-- technorati tags end --></p>
