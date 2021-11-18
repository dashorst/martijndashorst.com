---
layout: post
status: publish
published: true
tags: SDKMan, zsh, bash, Linux, JDK
title: "Easy JDK selection using SDK-man"
---
<img src="https://martijndashorst.com/uploads/sdkman-logo.png" width="100%" alt="SDKman Logo" />

SDKMan is a great tool for installing Java versions and a lot more. But it is not handy when you just want to
switch between Java 11 and Java 17 on the commandline:

```bash
$ sdk use java 17.0.1-tem

Using java version 17.0.1-tem in this shell.

```
You have to provide the full version and vendor (in my case Eclipse Temurin) for SDKMan to select the JDK of choice.
But I just want to say `sdk 17` or `sdk 11`. On macOS you can use the default installers and use `/usr/libexec/java_home`
to select the right Java version. But unfortunately SDKMan doesn't provide such an experience.

In order to get this:

```bash
$ jdk 17

Using java version 17.0.1-tem in this shell.

```

I wrote the shell function below to select the top installed version for the JDK you request:

```bash
function jdk() {
  sdk use java `sdk ls java | grep installed | grep $1 | awk '{print $NF}' | head -1`
}
```

It uses SDKman's functionality to:

- list the installed java versions, 
- filters out the installed java versions,
- filters the requests versions (you can have multiple installed, e.g. 17.0.0-tem and 17.0.1-tem)
- selects the last column of the SDKman line
- instructs SDKman to use that version

Have fun with this one!
