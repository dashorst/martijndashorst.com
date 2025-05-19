---
layout: post
status: published
published: true
title: Clean up stack traces with one line of macOS bash
---
One of the biggest issues with stack traces in Java web applications (Jakarta EE and/or Spring alike) is the enormous stack traces they produce when you get an error.

It is easy to just give up and start drinking. But you can make the stack traces a bit more palatable by just filtering the stack trace such that only the method calls from your own classes remain.

A simple one-liner for macOS "spring cleans" your stack trace into something readable:

```bash
pbpaste | grep -i -E 'nl.topicus.|ERROR|caused' | pbcopy
```

For linux users:
```bash
xsel --clipboard --output | grep -i -E 'nl.topicus.|ERROR|caused' | xsel --clipboard --input
```

For Windows users ("it's complicated"):
```
powershell.exe -Command "Get-Clipboard" | grep -i -E 'nl.topicus.|ERROR|caused' | clip
```

You have to substitute `nl.topicus.` with your own package name of course, but for our [company](https://topicus.nl/onderwijs) this works really well.
