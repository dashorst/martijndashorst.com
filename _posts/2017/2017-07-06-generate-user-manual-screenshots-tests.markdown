---
layout: post
status: publish
published: true 
title: Generate a User Manual - With Your Tests
---

_This article was published in [Java Magazine, 4th edition of 2017](https://github.com/dashorst/nljug-article-2017/raw/master/pdf/JAVA_MAGAZINE_2017_4.pdf) in Dutch. This is a augmented Google Translate version of that article._

"Do we have a manual for the users already?" Asks the product owner.
As your teammates dive under their desks, you stammer something about no time, varying priorities and the endless backlog. 
Without success of course, so you are the volunteer to provide the 96-page Word document with 149 screenshots. 
Four sprints later, the application no longer looks like the screenshots and you can start all over again.

But it can be different! After all, we stepped into this field to automate time-consuming human activities, to have time left to do fun, valuable things. We also like to write software and solve complex problems.

If I tell you that you can take screenshots automatically with the right development tools, you can integrate them into a nicely formatted manual in HTML and PDF format, _and_ you can test your application at the same time, will I have your attention?

In this article I will show you how to generate an always up-to-date manual with AsciiDoctor, Graphene, Arquillian and aShot. 
It solves an actual problem, it consists of a lot of programming work, it can become as complex as you want and is also fun. 
To illustrate this, I use a simple project: an online cheese shop.

## The Cheesr Online Cheese Shop 

The cheese shop 'Cheesr' was invented in 2005 for the book _Wicket in Action_, because my co-author Eelco really missed the cheese shop "De Brink" in Deventer when he emigrated to the US. 
Cheesr is a standard web application with two screens: selecting cheeses and placing an order. 
In figure 1 you see a number of pages of the manual.

![Figure 1: Cheesr Manual][fig1]
_Figure 1. Some example pages from the Cheesr Manual_

The cheese shop uses [Apache Maven](https://maven.apache.org) to connect the various components of the building process. Figure 2 illustrates the steps that are taken to get from the source code to a web application, containing the manual bundled together.

![Figure 2: The build process][fig2]
_Figure 2. The phases and files that play a role in building the cheese shop and the manual_

After the source code has been compiled, the tests are run. Arquillian ensures that the web application is started and controls the browser with WebDriver . Thanks to Graphene , we can describe HTML pages as Java objects and use them to perform the tests. The library aShot makes the screenshots and puts these files in the folder target / screenshots. You will learn more about these technologies later on.

In the "pre-package" phase of the construction process, just before the web application is assembled by Maven, AsciiDoctor converts the manual from AsciiDoc to HTML and PDF. Ultimately, the web application is ready and there is also the manual as a PDF and as an HTML file.

As an example, the code in Listing 1 tests that the checkout button is not available, if you do not have an item in your shopping cart yet. In addition, the test also makes the first screenshots immediately.

_Listing 1. The first test of the cheese shop_
```java
@RunWith(Arquillian.class)
public class IndexTest {
    @Deployment (testable = false)
    public static WebArchive createDeployment () {
        return CheesrDeployment.createWar ();
    }

    @Drone
    private WebDriver browser;

    @Test
    public void step1EmptyCart (@InitialPage GIndex index) {
        Camera.takeScreenshot (browser, "cheesr-1-home.png");
        Camera.takeScreenshot (browser, "cheesr-1-home-navigator.png", By.id ("navigator"));

        // nothing was selected, so the checkout should not be present
        assertFalse (index.checkoutPresent ());
    }
}
```

The annotation `@RunWith(Arquillian.class)` indicates that this test case should be run with Arquillian.
With Arquillian you can perform integration tests, start and stop servers and deploy your application code.
You can also use Arquillian to run your tests against an already running remote server, so you do not have to set it up entirely from your tests.

The `createDeployment` method with the `@Deployment` annotation tells Arquillian what needs to be deployed to the server: a WAR in our case, containing our application code.

The `@Drone WebDriver browser` field is an instruction for Arquillian to inject an instance of WebDriver in the test case, in order to control the browser.

The `@InitialPage GIndex index` parameter of the test method indicates that this test should start with the `GIndex` page. 
`GIndex` is a representation of the interaction possibilities of the Cheesr homepage: an implementation of the [Page Object Pattern][fow].
This class includes the location (URL) to which the browser should be sent.
Graphene ensures that the `GIndex` instance is created correctly and that the browser loads the page just before the test has started.
You can immediately interact with that page, such as taking screenshots, clicking on links and asking if certain elements are present.

For now it is useful to see how the screenshots of this test are used in the text of the manual.
_A piece of AsciiDoc_ from Listing 2 is an example of this.

_Listing 2. A piece of AsciiDoc from the cheese shop manual._
```asciidoc
== Buying Cheese

When you point your browser to our store front using the URL _http://example.com_.
This will show you the page from <<cheesr-home>>.

[[cheesr-home, figure 1]]
.The home page of the Cheesr store.
image::cheesr-1-home.png[{half-width}]

You can browse the cheeses using the navigator at the bottom of the page (<<cheesr-navigator>>).

[[cheesr-navigator, figure 2]]
.The navigator to discover even more cheese!
image::cheesr-1-home-navigator.png[]

When you have found the cheese of your liking, you can add it to your shopping cart using the _add_ link.
This will add the cheese to the cart, as shown in <<cheesr-cart>>.
```

The test case from _Listing 1_ generates screenshots with names such as "cheesr-1-home.png".
The AsciiDoc of _Listing 2_ picks it up in image elements such as `image::cheesr-1-home.png[]`.
Finally the result will look like the manual of Figure 1.

## AsciiDoc and AsciiDoctor

AsciiDoc is a text format for writing documents.
AsciiDoc is very similar to the widely used Markdown, but offers more options: includes, table of contents, automatic numbering of sections, warnings, annotations on code samples and much more.

AsciiDoctor is a project that can process AsciiDoc files and convert into PDF, HTML, EPub and DocBook.
There is a commandline tool, which you can call directly, but also plug-ins for Maven and Jekyll (a static website generator).
AsciiDoctor also integrates with chart tools such as PlantUML and GraphViz.
This allows you to describe UML diagrams in plain text.

AsciiDoc is an ideal format for storing in a Git repository, because it is a plain text format.
You can keep your your documentation up-to-date together with the code of your project, and even include it in code reviews (_did you update the manual?_)

The AsciiDoc content of the sample project (in which this article is also written) looks like this:

```bash
src/main/asciidoc
├── artikel.adoc
├── cheesr.adoc
└── images
    ├── build-process.png
    ├── cheesr-cover.jpg
    ├── cheesr-manual.jpg
    └── pageobjects.png
```

With these documents AsciiDoctor can generate the manual and include the screenshots (from `target/screenshots`) in the manual.
The screenshots are taken during the execution of the application tests.
This has been set up using Arquillian, WebDriver and Graphene.

## WebDriver and Graphene

WebDriver is a technology for controlling and reading browsers. This can produce fragile code if you are not paying attention: changes in the structure of the HTML in the browser can easily make your tests fail. Graphene is a shell around WebDriver to describe your application at a higher level of abstraction by encapsulating the (interaction with) HTML by enabling the [Page Object pattern][fow].

Instead of looking for a link in the HTML document to add a cheese to the shopping cart, you call the `addCheese` method on your page object. 
Of course behind the scenes, the search in the HTML goes to the link in question, but that is hidden from your tests.
Figure 3 shows the difference between working directly with the WebDriver API (and with it the HTML) and working with a Page Objects API.

![WebDriver API vs Page Objects][fig3]
_Figure 3. The difference between the WebDriver API and Page Objects_

The use of page objects makes your tests much easier to read. The code in Listing 3 gives an example of the difference between the WebDriver API and the use of Page Objects.

_Listing 3. Example of working with the WebDriver API and Page Objects_
```java
// WebDriver code:

List <WebElement> addLinks = browser
    .findElements(By.cssSelector("a[id^=add]"));

addLinks.stream ()
    .filter(e -> e.getAttribute("id").contains("edam"))
    .findFirst()
    .click();

Assert.assertTrue(browser.findElement(By.linkText("checkout")).IsPresent());

// page objects code:

indexPage.addCheese("edam");

Assert.assertTrue(index.checkoutIsPresent ());
```

In the example of the page objects code the intention of the test is immediately clear, while that in the WebDriver code is hidden in pitting the HTML structure. Of course this is simply moving the WebDriver logic to a façade, but that is precisely the essence of the Page Object pattern.

The code in Listing 4 shows the implementation of the GIndex page object.

_Listing 4. A Page Object for the Cheesr homepage_
```java
@Location("")
public class GIndex {
    @FindBy(css="a[id^=add]")
    private List <GrapheneElement> addLinks;

    @FindBy(css="input[type=button]")
    private GrapheneElement checkout;

    public void addCheese(String cheese) {
        addLinks.stream ()
            .filter(a -> a.getAttribute ("id").contains(safeCheeseId(cheese)))
            .findFirst()
            .orElseThrow(() -> new NoSuchElementException("Add" + cheese + "link"))
            .click();
    }

    public boolean checkoutPresent() {
        return checkout.isPresent();
    }

    public By byCart() {
        return By.cssSelector("div[id=cart], input[type=button]");
    }
}
```

The code starts with `@Location` to tell where the page is located in the application: `""` means the root. From there all the links are collected, which can add a cheese to the shopping cart. Finally, the `addCheese` method offers the possibility to add a cheese based on the name by clicking on the corresponding link.

Thanks to Graphene, you can easily apply the Page Objects pattern to create a model of your application, so that your tests remain readable and maintainable. Now we still have to actually make the screenshots. The library aShot is made to make screenshots with WebDriver.

## Screenshots with aShot

aShot has a fairly simple but powerful API. You only have to provide aShot with the WebDriver and the element you want to make the screenshot of. aShot will give you the picture. You can do some extra things and so it is useful to wrap it in a function that you can call from your tests.

You can also specify more web elements, of which a picture has to be taken. In addition, it is also possible to add extra space to the elements and you can release filters on the surrounding area, such as black-white or blur (blur) of the edge. The code in Listing 5 shows how you can achieve this with aShot.

_Listing 5. Takes a screenshot of specific elements in the page_
```java
public static void takeScreenshot(WebDriver browser, String name, By crop) {
    IndentCropper cropper = new IndentCropper(25)
        .addIndentFilter(new MonochromeFilter());

    BufferedImage screenshot = new AShot()
        .imageCropper(cropper)
        .takeScreenshot(browser, browser.findElements(crop))
        .getImage();

    saveScreenshot(name, screenshot);
}
```

Making a screenshot has become very simple with this function. Now we can save screenshots during testing and use them in our manual (see Listing 6).

_Listing 6. A test that uses the page object GIndex and takes screenshots_
```java
@Test
public void step2AddToEmptyCart(@InitialPage GIndex index) {
    Camera.takeScreenshot(browser, "cheesr-2-cart-0-empty.png", index.byCart());
    index.addCheese ("edam");
    Camera.takeScreenshot (browser, "cheesr-2-cart-1-edam.png", index.byCart());

    // assert that the checkout button is present
    assertTrue(index.checkoutPresent());
    index.removeCheese("edam");
    assertFalse(index.checkoutPresent());
}
```

An example of the screenshots taken in this test is shown in Figure 4.
!
[Screenshots of listing 6][fig4]
_Figure 5. Two screenshots of the shopping cart_

This completes the article. We can now test the application, take screenshots and generate a manual.

## Conclusion

We have one integrated whole, because the documentation lives together with the code in AsciiDoc format. We test our application via the browser, thanks to Arquillian and Graphene. During the execution of the tests we make screenshots and focus on exactly those parts that are important with aShot. Maven combines all these steps into one smooth process, which ultimately incorporates our up-to-date manual into our application.

With this setup you can also create internationalized screenshots for multilingual manuals: put your application in another language and perform the tests again. Now only someone willing to translate that 96 pages of text to translate ...

### View all code on Github

The source code is available on Github: https://github.com/dashorst/nljug-article-2017. It is a Maven project, so you can import it directly into your favorite IDE. The README.md contains instructions for building and running the project. In this article I do not dwell on the specific versions and configuration of plug-ins and dependencies. You can find this in the project.

[fig1]: https://github.com/dashorst/nljug-article-2017/raw/master/src/main/asciidoc/images/cheesr-manual.jpg

[fig2]: https://github.com/dashorst/nljug-article-2017/raw/master/src/main/asciidoc/images/build-process.png

[fig3]: https://github.com/dashorst/nljug-article-2017/raw/master/src/main/asciidoc/images/pageobjects.png

[fig4]: https://github.com/dashorst/nljug-article-2017/raw/master/src/main/asciidoc/images/screenshots.png

[fow]: https://martinfowler.com/bliki/PageObject.html