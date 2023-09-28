---
layout: post
status: published
published: true
title: "Fixing Eclipse won't start issue on macOS"
---

Sometimes, when you update your Eclipse plugins, it won't start after you've shut it down (e.g. after a reboot). 
This means that the system finds that the Eclipse application bundle has different cryptographic signature than when it was installed. 

To check if the signature is (in)valid you can use this Terminal command:

```bash
$ pkgutil --check-signature /Applications/Eclipse\ 2023.09.app 
Package "Eclipse 2023.09":
   Status: package is invalid (checksum did not verify)
```

When the signature is invalid, you need to recalculate the signature:

```bash
$ codesign --force --deep --sign - /Applications/Eclipse\ 2023.09.app 
/Applications/Eclipse 2023.09.app: replacing existing signature
```

And voilà! your Eclipse will start again.
