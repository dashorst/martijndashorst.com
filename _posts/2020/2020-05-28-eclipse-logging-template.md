---
layout: post
status: publish
published: true
title: "Eclipse Pro Tip: Autocomplete Template for Logging"
---

In many of my classes I need to add some logging. We use SLF4J for that
in our projects. But having to type

```java
Logger<ctrl-space> log = LoggeF<ctrl-space>.getLo<ctrl-space>(MyCla<ctrl-space>.class);
```

every time gets annoying and tiresome. In many live coding demos folks
use templates for autocompletion, so I figured to implement one for
this logging.

Eclipse supports autocomplete coding templates (Preferences -> Java ->
Editor -> Templates), where you can add the snippet below:

```java
${:import(org.slf4j.Logger,org.slf4j.LoggerFactory)}private static final Logger log = LoggerFactory.getLogger(${enclosing_type}.class);
```

This template will automatically insert the appropriate imports and
fill in the class name for the logger.

I have named this template `log`, so whenever I type `log<ctrl-space>`
Eclipse will suggest the autocompletion template above.

This probably will save a couple of hours of your life.
