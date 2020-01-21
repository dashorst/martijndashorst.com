---
layout: post
status: publish
published: true
title: "CDI Factory Method"
---
I'm working in a piece of software that needs a builder inside a loop
inside a CDI managed bean, but the builder should be configured using
CDI.

E.G. this is part of a JBatch step that processes rows from a `ResultSet`

```
@Dependent
public class BananaBuilder {}

@JobScoped
public class BananaProcessor extends AbstractBatchlet {
    // ...
	public void processRow(ResultSet rs) {
	    BananaBuilder bb = ...

        ..... do something with the bananabuilder
	}
}
```

As the `BananaBuilder` maintains some state that should be reset on
each invocation of `processRow`, this is not an `@Inject` away: the
injected instance of the `BananaBuilder` will only be injected once in
the lifetime of the `BananaProcessor` instance, but I need it to be
fresh on each invocation.

As I invoke `processRow` myself, I can't `@Inject` the builder as a
parameter to the method, how would I obtain that particular instance?

A Google search didn't reveal direct usable results, because factory
and CDI are rather popular generic terms together.

The correct way of doing this is either through
`Instance<BananaBuilder>` or
`CDI.current().select(BananaBuilder.class).get()`.

So if you want to get a new instance everytime you need a
`BananaBuilder`, then you could inject an `Instance` into your context:

```
@JobScoped
public class BananaProcessor extends AbstractBatchlet {
    @Inject
    Instance<BananaBuilder> builderInstances;

	public void processRow(ResultSet rs) {
	    BananaBuilder bb = builderInstances.get();

        ..... do something with the bananabuilder
	}
}
```

This will get a new `BananaBuilder` on each invocation of the
`builderInstances.get()`, achieving what we wanted. Note that the
`BananaBuilder` needs to have `@Dependent` scope, which is the default
scope if you don't annotate your bean with a specific scope.

=== Conclusion

Using CDI to make a new builder inside a loop is not too difficult, but
it was a bit hard to discover documentation explaining this.
