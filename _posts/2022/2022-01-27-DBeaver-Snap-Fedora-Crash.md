---
layout: post
status: publish
published: true
title: "DBeaver Crash Due to Corrupt Font Cache on Fedora Solved"
---
Unfortunately DBeaver is not as stable as I'd like on Fedora (35) and just today it wanted to restart due to an exception, and that didn't work any more as it crashed during startup.

If the crash log shows something like this:

```
Jan 27 10:58:09 dbeaver-ce_dbeaver-ce.desktop[417763]: Fontconfig warning: FcPattern object weight does not accept value [0 205)
Jan 27 10:58:09 dbeaver-ce_dbeaver-ce.desktop[417763]: #
Jan 27 10:58:09 dbeaver-ce_dbeaver-ce.desktop[417763]: # A fatal error has been detected by the Java Runtime Environment:
Jan 27 10:58:09 dbeaver-ce_dbeaver-ce.desktop[417763]: #
Jan 27 10:58:09 dbeaver-ce_dbeaver-ce.desktop[417763]: #  SIGSEGV (0xb) at pc=0x00007f1d7a42790f, pid=417763, tid=417764
Jan 27 10:58:09 dbeaver-ce_dbeaver-ce.desktop[417763]: #
Jan 27 10:58:09 dbeaver-ce_dbeaver-ce.desktop[417763]: # JRE version: OpenJDK Runtime Environment Temurin-11.0.12+7 (11.0.12+7) (build 11.0.12+7)
Jan 27 10:58:09 dbeaver-ce_dbeaver-ce.desktop[417763]: # Java VM: OpenJDK 64-Bit Server VM Temurin-11.0.12+7 (11.0.12+7, mixed mode, tiered, compressed oops, g1 gc, linux-amd64)
Jan 27 10:58:09 dbeaver-ce_dbeaver-ce.desktop[417763]: # Problematic frame:
Jan 27 10:58:09 dbeaver-ce_dbeaver-ce.desktop[417763]: # C  [libpangoft2-1.0.so.0+0x990f]
```

Then something probably corrupted the fontconfig cache. You can remove that using:

```
sudo rm /var/cache/fontconfig/*
rm ~/.cache/fontconfig/*
```

And voila! DBeaver did startup again.

