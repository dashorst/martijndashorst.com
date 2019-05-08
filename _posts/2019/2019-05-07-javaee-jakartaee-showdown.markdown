---
layout: post
status: publish
published: true
title: The Future of Jakarta EE in the Wake of JavaEE
---

_Gentle doctors make stinking wounds_ -- dutch proverb

In the wake of [the announcement][mike1] that Oracle won't provide the `javax` namespace to the Jakarta EE community to allow for modifications and future development within the existing APIs, I would like to vent my opinion.

First of all, I'm grateful to Oracle for providing all the standards work, code and documentation to the Jakarta community.
This was not a light endeavor, and has cost millions of real money.
It is unfortunate that the namespace and JavaEE trademarks are not transferred as well, but looking at what they already have contributed, we have a net win overall.

So what now?
[Mark Struberg][struberg1] and [David Blevins][blevins1] both have given two options:

1. Big Bang: migrate (mostly) everything in one go (in a next Jakarta release)
2. On a per-case basis: migrate only when necessary

There is a continuum between those two options: migrate only the most commonly used or preferred APIs (e.g. only microprofile) at first and on demand migrate the rest.

In my opinion a Big Bang release is the way forward, and the big bang should happen with Jarkarta EE 8.

Make Jakarta EE 8 an equivalent standard to JavaEE 8 with the exact same standards, and do the package rename in this release.

Why? Because of clarity, ease of migration for users and the ecosystem as a whole.
The future of JavaEE is Jakarta EE, might as well make it official with the proper package names.
This will delay the release of Jakarta EE 8, but I don't think anyone was anxiously to adopt this release as the only change would be a new steward for the standards.

There are some folks that are pushing hard for microprofile as the successor of JavaEE, not Jakarta EE.
I don't agree with them.
If you work in the microprofile projects it is easy to see the rest of the world as ancient, e.g. not see the forrest through the trees.
An enormous amount of code depends on JavaEE and the evolution of the parts of JavaEE.
We are not asking for revolution, but evolution of those components.
If you want revolution, then by all means switch to microprofile or quarkus, but those are always suitable for all applications.

Other folks want a clean slate for Jakarta EE, so they can pick and choose from JavaEE for the future.
This is effectively the _on a per-case basis_ migration option. 

The Java EE ecosystem is very diverse with many different customer profiles, but from my understanding even the glacial users of Java EE are moving ahead towards newer Java EE versions.
(At least the dutch IRS and the various banks are migrating away from Java 6 and Java EE 5)

In my company we use a model where we follow the latest release of Wildfly almost immediately.
So our production servers are now all running on Wildfly 16, and when Wildfly 17 is released, we will adopt that quickly as well.
And we use the full JavaEE profile.
So to say we should just start to innovate and migrate our application to Microprofile is ingenious at best.

Given our code base of around 3 million lines of Java code, we should be afraid of any change right?
Well, we actually would prefer the big bang approach.
A package rename is something we can manage in a week or so, would not lead to massive retesting and would land in one sprint on our production servers.
From there we can build forward on the new Jakarte EE platform and continue to follow the Jakarate EE standards.

In short: please do a big bang release of Jakarta EE 8 including the package rename.


[struberg1]: https://struberg.wordpress.com/2019/05/06/the-way-forward-for-jakartaee-packages/
[blevins1]: https://www.eclipse.org/lists/jakartaee-platform-dev/msg00029.html
[mike1]: https://blogs.eclipse.org/post/mike-milinkovich/update-jakarta-ee-rights-java-trademarks
