---
layout: post
status: published
published: true
title: "HTMX: Web 1.0 with the benefits of Web 2.0 without the grift of Web 3.0-at JFall 2023"
---
[JFall 2023][jfall] is a Dutch Java User Group 3-day conference packed into 1 day, and this year celebrated its 20th anniversary!

I was honored to be able to present at the conference and my presentation "HTMX: Web 1.0 with the benefits of Web 2.0 without the grift of Web 3.0" was selected.
In this post I'm giving you the cliff notes of the presentation and the slides, as we eagerly await the upload of the recorded video.

These are [the slides](https://www.slideshare.net/dashorst/htmx-web-10-with-the-benefits-of-web-20-without-the-grift-of-web-30):

<iframe src="https://www.slideshare.net/slideshow/embed_code/key/jsLxHdZbzkVfJU?hostedIn=slideshare&page=upload" width="476" height="400" frameborder="0" marginwidth="0" marginheight="0" scrolling="no"></iframe>

## What is HTMX?

[HTMX](https://htmx.org) is a client side javascript library that extends HTML using attributes to enable interactivity and dynamic web pages.

## Why does HTMX exist?

Current web archicture focusses on oodles of JavaScript and SPA's to work around the limitations of HTML as a client side application platform:

  - HTML only provides GET and POST, and
  - only <a> and <form> tags provide client-server communication

Effectively HTML is stuck in 1995. SPA's solve the "stuck in 1995" problem by working around HTML. HTMX solves the problem by extending HTML

## How does HTMX work?

HTMX provides the following to extend HTML, augment the client-server communication and allow you to provide rich user experiences.

- attributes on elements
- request and response headers to give server a way to respond to and direct HTMX
- classes for animations and indicators
- events for hooking into the various stages of HTMX and provide additional interactivity
- javascript functions for configuring HTMX and working with classes, finding and working with elements, and adding extensions
- extensions to provide more functionality like websockets, server-sent events and various DOM morphing algorithms

In the presentation I gave some examples for each of these HTMX additions, and then I proceeded to give a live demo.

## A live demo

The live demo consisted of two parts:
- HTMX core functionality [htmx-jfall](https://github.com/dashorst/htmx-jfall)
- A websocket multiplayer flag guessing game [Fun with Flags](https://github.com/dashorst/funwithflags)

You can find the code at github (see the links).

## Conclusions

With HTMX a backend developer can now make HTML pages more dynamic without having to switch to a full client-side application build.
You just render out HTML and progressively enhance the application with HTMX tags and such to make a rich application.

I heartily recommend checking out HTMX and give it a 9/10.


[jfall]: https://jfall.nl
