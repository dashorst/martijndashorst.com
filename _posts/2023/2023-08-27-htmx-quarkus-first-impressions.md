---
layout: post
status: publish
published: true
title: "HTMX and Quarkus First Impressions"
---
I've been eyeing [HTMX][htmx] ever since I've laid my eyes on it, and already want to build applications using [Quarkus][quarkus].
Fortunately €€€ dayjob provides the opportunity to combine both to build an internal tool to run several SQL scripts after one another.
In this post I wanted to note my first impressions.

![HTMX meme](https://martijndashorst.com/uploads/htmx-meme.png)

First: What is HTMX in a nutshell?
It is a JavaScript library that enables Hypertext As The Engine Of Application State (HATEOAS) in the browser by using attributes to declaritively specify what actions need to be taken and which element needs to be replaced by the HTML response of the action.
HTMX issues mostly AJAX requests and integrates with the history API.
It is fully HTML driven, no additional JavaScript is necessary, only if you want pure clientside functionality.

My notes:

- Quarkus: it is rather easy to get started and add new plugins
- For this project I needed Qute templates and JAX-RS (so rest-easy)
- Including HTMX is just using a `<script>` tag
- Using HTMX is just using the proper `hx-XYZ` attributes on your DOM elements
- Rethinking how to do templating and setting up HTML endpoints for the UI is challenging coming from a [Wicket][wicket] history

As you might know I have a [pretty strong Wicket background][wia]. 
So the serverside rendering component of HTMX and low-JavaScript usage appeals considerably to me.
I have to re-learn some stuff to actually get good in the HTMX and HATEOAS mindset, and to combine multi element updates instead of relying on full page refreshes (which HTMX takes good care of!)

I have created an already quite complicated UI with:

- a sidebard menu containing our projects,
- a row of tabs containing the contents of each project,
- a list of (SQL) files and a SQL previewer,
- a previewer that syntax highlights the TSQL files
- a link to github to directly edit the SQL file

And all these items are linked together already, with a minimum of Java code, HTML and no JavaScript of my own.

Tally for now:
- 94 lines of HTML templates
- 173 lines of Java code (sloccount)
- [bootstrap 5.3][bs53] (and bootstrap icons)
- [highlightjs][hljs] + highlight-tsql
- [HTMX][htmx]

Next up:
- securing the thing with OIDC + Topicus Keyhub
- connecting the project to a local git checkout of our project(s)
- making the scripts runnable against a database

The fun part when compared to Wicket pages is that you can easily edit the HTML templates to add functionality.
It is further enhanced by the quick reloading of my currently 3 Java classes by Quarkus' development mode.

The hardest part for me is to figure out how to make this all maintainable and discoverable.
The Qute templating engine is nice, and Quarkus has some decent defaults, so probably I need to adhere to those standards more.

The next weeks will be fun and filled with learning!

[wicket]: https://wicket.apache.org
[wia]: https://wicketinaction.com
[htmx]: https://htmx.org
[hljs]: https://highlightjs.org
[bs53]: https://getbootstrap.com/docs/5.3/)https://getbootstrap.com/docs/5.3
[quarkus]: https://quarkus.io

