---
layout: post
status: draft
published: false
title: "Fixing Eclipse won't start issue on macOS"
---

Sometimes, when you update your Eclipse plugins, it won't start after you've shut it down (e.g. after a reboot). 
This means that the system finds that the Eclipse application bundle has different cryptographic signature than when it was installed. 
In order to reassure macOS that this is what you intended, you need to let macOS update the signature with the following terminal command:

```bash
xattr -cr /Applications/Eclipse.app
```

You may need to relogin for the operating system to use the recalculated signature.
