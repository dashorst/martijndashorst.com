---
layout: post
status: publish
published: true
title: "Getting Exchange to work with Fedora 35 GNOME Calendar"
---
Getting Fedora (35) to work with Exchange and having your calender show the appointments is really, really nice.
Unfortunately even though the settings app allows you to configure an exchange account, it doesn't sync with the Gnome Calendar app out-of-the-box.

Lo and behold, you need to install additional software to make this work:

```bash
% sudo dnf install -y evolution-ews
```

will install **Evolution Exchange Web Services** on your system. This allows Gnome Calendar to retrieve your appointments. I did see some
crashes of some related service, but after reconfiguring the exchange account information I now have my appointments on my Fedora 35 system.
