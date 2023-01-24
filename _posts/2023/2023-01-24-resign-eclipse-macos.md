---
layout: post
status: publish
published: true
title: "Fix 'The application 'Eclipse' can't be opened' Error on macOS"
---
You restart your Mac, and after booting up you double click on your Eclipse.app icon.
MacOS throws you a popup with the error that it can't open your carefully curated IDE and plugins.
Many hours of updates and plugin selections are on the edge of the bin.
What can you do?
Redownload Eclipse, and go through the hours of updating your settings and plugins?

No more! Apparently the code signature of the `Eclipse.app` package is not equal to the contents of the package, preventing it from starting up.

Using the following shell command you can re-sign the Eclipse.app package (if you're sure it should be resigned of course), enabling it to restart again:

```bash
sudo codesign --force --deep --sign - /Applications/Eclipse.app
```

It took quite a while on my machine to complete, but that time was a lot shorter than having to download and re-install.

Many thanks to the folks at stackoverflow.com for having an [anwser readily available](https://stackoverflow.com/questions/70725347/the-application-eclipse-can-t-be-opened-macos-monterey).
