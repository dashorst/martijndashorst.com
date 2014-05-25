---
layout: post
status: publish
published: true
title: Custom Wicket Stock Quote Component
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 140
wordpress_url: http://martijndashorst.com/2005/08/18/custom-wicket-stock-quote-component/
date: '2005-08-18 01:22:03 +0200'
date_gmt: '2005-08-18 01:22:03 +0200'
categories:
- wicket
- java
tags: []
comments: []
---
<p>
This entry is written as a reaction to Chris Schalke's article, <a href="http://www.theserverside.com/news/thread.tss?thread_id=35900">Building Custom JSF UI Components</a> on the serverside. It shows how to obtain the same functionality with different technology: a custom Stock Quote component using <a href="http://wicket.sf.net">Wicket</a>.</p>
<p><p>
The discussed files are avialable through ViewCVS on:</p>
<ul>
<li><a href="http://cvs.sourceforge.net/viewcvs.py/wicket/wicket-examples/src/java/wicket/examples/stockquote">package directory</a></li>
<li>Component: <a href="http://cvs.sourceforge.net/viewcvs.py/wicket/wicket-examples/src/java/wicket/examples/stockquote/StockQuoteLabel.java?rev=1.1&view=log">StockQuoteLabel.java</a></li>
<li>Webpage: <a href="http://cvs.sourceforge.net/viewcvs.py/wicket/wicket-examples/src/java/wicket/examples/stockquote/StockQuote.html?rev=1.2&view=auto">StockQuote.html</a> and <a href="http://cvs.sourceforge.net/viewcvs.py/wicket/wicket-examples/src/java/wicket/examples/stockquote/StockQuote.java?rev=1.2&view=auto">StockQuote.java</a>.</li>
<li>Application: <a href="http://cvs.sourceforge.net/viewcvs.py/wicket/wicket-examples/src/java/wicket/examples/stockquote/StockQuoteApplication.java?rev=1.1&view=auto">StockQuoteApplication.java</a></li>
</ul>
<p>
Intended audience: anyone seeking a better way of developing web applications. I trust you have Java development experience and know your HTML. Other than that.... well... just see. You might want to take a look at some <a href="http://wicket.sf.net/Examples.html">Wicket Examples</a> to see what <a href="http://wicket.sf.net">Wicket</a> is all about.</p>
<p>
In Wicket building custom components is very easy. A normal web application will contain many, tailor made components for your application. In fact, each Page you create is a <code>Component</code> and could be put in a jar, and reused in another application.</p>
<p><b>Creating a Stock Quote component</b></p>
<p>
The Stock Quote component should take a symbol and display the value of the stock obtained through a webservice in its body. I've used the same webservice as Chris did, and found some code on devx.com for calling the webservice. In order to keep it simple, I've not included this code here, but you can see it in our CVS. The webservice calling code is not the prettiest around, but it suffices.</p>
<p>
So: <code><span wicket:id="stockquote">Price of IBM goes here</span></code> should replace the body contents with the actual value of IBM stock. Here's the Java code for the component (there is no markup file associated with it):
<pre>
public class StockQuoteLabel extends WebComponent
{
    public StockQuoteLabel(String id, String symbol)
    {
        super(id, new Model(symbol));
    }
    public StockQuoteLabel(String id, IModel model)
    {
        super(id, model);
    }
    protected void onComponentTagBody(
              final MarkupStream markupStream
            , final ComponentTag openTag)
    {
        String symbol = getModelObjectAsString();
        String quote = getQuote(symbol);
        replaceComponentTagBody(markupStream, openTag, quote);
    }
    private String getQuote(String symbol)
    {
        // do SOAP stuff
    }
}
</pre>
<p>
The first constructor adds the symbol string as a Model to the component. Models are what bind your business application logic to components, they are the glue between your world and the Wicket components. The first constructor is a convenience constructor, allowing you to create the component quickly with a stock symbol such as "IBM". The second constructor allows you to retrieve the stock symbol from somewhere else, such as a property from a POJO.<br />
The first line in the onComponentTagBody method returns the contents of the model as a String. The second line replaces the text between the span tags with the stock quote retrieved from the web service.</p>
<p>
So how would you use this component? Let's first take a look at the markup (StockQuote.html):</p>
<p><pre>
<html>
<head><title>StockQuote</title></head>
<body>
    <p>The quote for IBM is: 
    <span wicket:id="stockIBM">foo bar</span></p>
</body>
</html>
</pre>
<p>
The idea is to replace the "foo bar" text with the actual value of IBM stock. In the corresponding Java file for this web page the component is added to the page like (StockQuote.java):</p>
<p>
<pre>
public class StockQuote extends WebPage {
     public StockQuote() {
        add(new StockQuoteLabel("stockIBM", "IBM"));
     }
}
</pre>
<p>
That is it.</p>
<p>
<b>Using a Form to get the symbol</b></p>
<p>
Now lets use user input for dynamically retrieving the stockquote. The page alters like so:</p>
<p><pre>
<html>
<head><title>StockQuote</title></head>
<body>
    <form wicket:id="form">
        Enter symbol: <input wicket:id="symbol" type="text" />
        <input type="submit" />
    </form>

    <p>The quote for <span wicket:id="symbol">symbol</span> is: 
    <span wicket:id="quote">quote</span></p>
</body>
</html>
</pre>
<p>
As you can see, I've only added the form and an input field, and I've added a label to render the symbol in, and renamed the stock quote component. In the Java this looks like:</p>
<p><pre>
public class StockQuote extends WebPage {
    private static class Quote implements Serializable {
        private String symbol;
        public Quote() {}
        public String getSymbol() { return symbol; }
        public void setSymbol(String s) { symbol = s; }
    }

    private final Quote quote = new Quote();

    public StockQuote() {
        Form form = new Form("form");
        IModel model = new PropertyModel(quote, "symbol");
        form.add(new TextField("symbol", model));
        add(form);
        add(new Label("symbol", model));
        add(new StockQuoteLabel("quote", model));
    }
}
</pre>
<p>
Here I've wired the page such that the text field, label and stock quote label all use the same instance of the Quote class. The property model uses the OGNL library to get and set the value of the property that is bound to the model, in this case the symbol property of the Quote object.</p>
<p>
In order to run this example we need to create an application object and tell it what our home page is:</p>
<p>
<pre>
public class StockQuoteApplication extends WebApplication {
    public StockQuoteApplication() {
        getPages().setHomePage(StockQuote.class);
    }
}
</pre>
<p>
Lastly we need to adjust the web.xml to make Wicket available to the servlet container:</p>
<p>
<pre>
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE web-app
          PUBLIC "-//Sun Microsystems, Inc.//DTD Web Application 2.3//EN"
          "http://java.sun.com/dtd/web-app_2_3.dtd">

<web-app>
    <display-name>Wicket Examples</display-name>
    <servlet>
        <servlet-name>StockQuoteApplication</servlet-name>
        <servlet-class>wicket.protocol.http.WicketServlet</servlet-class>
        <init-param>
            <param-name>applicationClassName</param-name>
            <param-value>wicket.examples.stockquote.StockQuoteApplication</param-value>
        </init-param>
    </servlet>
    <servlet-mapping>
        <servlet-name>StockQuoteApplication</servlet-name>
        <url-pattern>/stock/*</url-pattern>
    </servlet-mapping>
</web-app>
</pre>
<p>
And we're ready to run.</p>
<p>
<b>Conclusion</b></p>
<p>
Wicket makes custom component creation a breeze. In just a few lines of code we've created a component that can play nicely with other Wicket components, and works without having to resort to configuration files, component registries and other fluff.</p>
<p>
<b>NB</b></p>
<p>
Normally you wouldn't want to make a custom component for this functionality. The <code>getQuote()</code> soap client would be part of a POJO that looks like:</p>
<p><pre>public class StockQuote {
    private String symbol;
    public StockQuote() {}
    public StockQuote(String s) {symbol = s; }
    public void setSymbol(String s) {symbol = s; }
    public String getSymbol() { return symbol; }
    public String getQuote() { return getQuote(symbol); }
    private String getQuote(String symbol) {
        // do SOAP thingy
    }
}</pre>
<p>
So all functionality of getting a quote is located in the StockQuote POJO. Now you can<br />
use this directly in your pages, without having to create a new component, just using<br />
the default <code>Label</code> component to display the value of the quote:</p>
<p><pre>quote.setSymbol("IBM");
add(new Label("quote", new PropertyModel(quote, "quote")));</pre>
<p>
