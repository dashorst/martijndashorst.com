---
layout: post
status: publish
published: true
title: "Quarkus with JPA model on the test class path"
---
I'm working on an application for €€€ day job, and I want to use Quarkus because the plugins provide pretty good support for what I am wanting to achieve.
The application is a CLI application that will merge the contents of two tenant databases (same schema) into one databse.
For this functionality I want to write some unit tests (yeah, I know).
To generate a test model and database schema I want to use JPA (Hibernate) to quickly create and fill the schema.

I put the JPA entities on the test class path:

```
src/main/java/banana/CliCommand.java
src/test/java/banana/model/Tenant.java         <|-- Entity
src/test/java/banana/model/TenantAccount.java  <|-- Entity
```

Unfortunately when I start Quarkus in dev mode, Hibernate complains that it can't find any entities, so it disables itself:

```
WARN  [io.qua.hib.orm.dep.HibernateOrmProcessor] (build-27) Hibernate ORM is disabled because no JPA entities were found
```

I tried googling for this, but couldn't come up with an answer, so I asked the [question on Stack Overflow][question], and within [30 minutes or so I got the answer][answer]:

> Just put the `io.quarkus:quarkus-hibernate-orm-panache` dependency on the `<scope>test</scope>` scope, and everything will work as you intended.

And that works!

[question]: https://stackoverflow.com/q/76771938/611274
[answer]: https://stackoverflow.com/a/76772363/611274
