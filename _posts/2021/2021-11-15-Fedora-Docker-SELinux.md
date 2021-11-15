---
layout: post
status: publish
published: true
tags: fedora, docker, selinux, /var/run/docker.sock
title: "Fedora, Moby Engine, Docker, testcontainers and SELinux"
---
<img src="https://martijndashorst.com/uploads/itcrowd-richardayoade.gif" width="100%" alt="IT Crowd's Richard Ayoade is angry at computer" />

At $dayjob we make a portal that starts docker jobs. For this to work we need to access the Docker API
running on the host. A typical way to make this work is to use the docker socket located in `/var/run/docker.sock`.

You just mount the socket in your container and point your Docker client to it. This works on macOS and several
linux distributions. It works in Production(tm).

Then my macbook pro needed servicing so I installed Fedora on my replacement and figured things would just work out.

When you want to install docker, typically you just type in the executable name of your package manager and `install docker`:

```
$ sudo dnf install docker
```

This command doens't work out of the box because it asks you to install moby-engine instead. Alright you think: moby-engine
is just docker right?

_SELinux enters the room_

Apparently moby-engine does not work with the cgroups 2 used by SELinux, or tries to do so but fails. There was no way I
was able to let my docker client talk to the host through a mounted docker socket. I changed the rights, changed the groups,
changed the user. So we YOLO'd the container and put it in production for testing (fortunately the application is used internally
by just a couple of users a couple of days in a month). This cost me about 2 days of fiddling, reading and trying stuff. SELinux
won.

Next I wanted to use [testcontainers.org][testcontainers] for testing backup/restore procedures of databases we manage through the docker application.
Stepping through the code I saw that they try to [start a container for reaping dangling containers][ryuk] that were started during testing.
This requires... access to the docker socket. 

I tried starting the ryuk container manually using my shell, but the only way to start it was using the [privileged flag][danwalsh]. Looking at
the code from testcontainers I noticed ~[they already set the container to run privileged][privileged]~ (**UPDATE** Apparently my reading of the code was wrong
and I need to set a flag explicitly to let Ryuk run privileged. The documentation and the mitigation of ryuk at testcontainers is not good in this 
instance IMO)~, so something janky was happening with SELinux~.

One of the tickets mentioned reinstalling containerd, to fix the rights. Looking at some other posts they mentioned installing
docker-ce.

So I followed the [manual for installing docker-ce][install-docker-ce] and lo and behold: everything worked immediately.

While SELinux is [probably making my life as a user of Linux safer][danwalsh], it is frustrating that it requires you to become an expert at
it before you can actually get work done. At this time I can't say I am impressed by SELinux.

[testcontainers]: https://testcontainers.org
[ryuk]: https://hub.docker.com/r/testcontainers/ryuk
[privileged]: https://github.com/testcontainers/testcontainers-java/blob/440179d3fe372ff076426b8d1ac9ad614f6eefce/core/src/main/java/org/testcontainers/utility/ResourceReaper.java#L116
[install-docker-ce]: https://docs.docker.com/engine/install/fedora/
[danwalsh]: https://danwalsh.livejournal.com/74095.html
