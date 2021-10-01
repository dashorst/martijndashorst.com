---
layout: post
status: draft
published: false
title: "Compiled in 60 seconds"
---

# Compiled in 60 seconds

Make your Maven build go fast!

"I feel the need... the need for speed!"

Did you know you can make your Maven build quite faster by switching your Java compiler?

Here we have a real life Maven module that has just under 7000 classes. When I compile this module with the standard compiler from Java 11 it ... takes a while.

Building this module takes about 60 seconds when starting from a Maven clean. In this the resources are copied (2200 of them), XJC generates sources from XSDs and the `maven-compiler-plugin` compiles using the default Java compiler that comes with your JDK: `javac`.

```
[INFO] --- maven-compiler-plugin:3.8.1:compile (default-compile) @ iridium-sis-core ---
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 6869 source files to /Users/dashorst/Workspaces/vscode/iridium/sis/core/target/classes
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  01:02 min
[INFO] Finished at: 2021-09-11T16:44:33+02:00
[INFO] ------------------------------------------------------------------------
```

When you split these durations per plugin you get this:

##### Table 1: Execution times using javac for compilation

Plugin execution	Duration
org.apache.maven.plugins:maven-compiler-plugin:3.8.1:compile {execution: default-compile}	51.48 s
net.alchim31.maven:yuicompressor-maven-plugin:1.5.1:compress {execution: default}	3.022 s
org.apache.maven.plugins:maven-resources-plugin:3.2.0:resources {execution: default-resources}	1.842 s
org.codehaus.mojo:jslint-maven-plugin:1.0.1:jslint {execution: default}	1.413 s
org.jvnet.jaxb2.maven2:maven-jaxb23-plugin:0.14.0:generate {execution: default}	1.217 s
org.apache.maven.plugins:maven-enforcer-plugin:1.4.1:enforce {execution: default}	295.4 ms
org.codehaus.mojo:build-helper-maven-plugin:3.2.0:add-source {execution: add-source}	97.59 ms
org.codehaus.mojo:properties-maven-plugin:1.0.0:set-system-properties {execution: default}	15.37 ms

51 seconds, or 83% of the time building the module goes to the compiler. Can this be sped up?

Oh my yes it can!

The **Eclipse Compiler for Java** (ECJ) improves the compilation speed almost two fold!

The total time for a clean build of this module using ECJ is just under 40 seconds:

```
[INFO] --- maven-compiler-plugin:3.8.1:compile (default-compile) @ iridium-sis-core ---
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 6869 source files to /Users/dashorst/Workspaces/vscode/iridium/sis/core/target/classes
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  39.162 s
[INFO] Finished at: 2021-09-11T16:41:04+02:00
[INFO] ------------------------------------------------------------------------
```

##### Table 2: Execution times using ecj for compilation

Plugin execution	Duration
org.apache.maven.plugins:maven-compiler-plugin:3.8.1:compile {execution: default-compile}	27.85 s
net.alchim31.maven:yuicompressor-maven-plugin:1.5.1:compress {execution: default}	3.057 s
org.apache.maven.plugins:maven-resources-plugin:3.2.0:resources {execution: default-resources}	1.899 s
org.codehaus.mojo:jslint-maven-plugin:1.0.1:jslint {execution: default}	1.419 s
org.jvnet.jaxb2.maven2:maven-jaxb23-plugin:0.14.0:generate {execution: default}	1.291 s
org.apache.maven.plugins:maven-enforcer-plugin:1.4.1:enforce {execution: default}	312.2 ms
org.codehaus.mojo:build-helper-maven-plugin:3.2.0:add-source {execution: add-source}	101.3 ms
org.codehaus.mojo:properties-maven-plugin:1.0.0:set-system-properties {execution: default}	18.08 ms

Compilation time for 6869 classes went from 51.48s to 27.85s! That is a 1.8x improvement.

Because there's other overhead in the project, the total speed improvement clocks in at about an awesome 1.5x! Does that speed improvement translate onto performing a build across multiple modules?

## Total impact on the larger project

So in this unusually large module the impact is quite large. But does that impact carry over to the rest of the project? How much difference does changing the compiler make on building all the 72 modules of this project?

With javac the total time of one run is 132 seconds. With ECJ the total time of one run is 102 seconds. So the total impact is lessened, but a 29% speed improvement of running the compilations on the project is quite exciting!

It is of course normal that the impact of changing just the compiler on a total build would be smaller when Maven needs to do so much more. Still I don't think you can scoff at a 29% improvement overall. How can you get this improvement for your projects?

## Use the Eclipse Compiler for Java

All you need to do to start using the ECJ as your java compiler is to update your maven-compiler-plugin configuration.

The plugin definition below instructs the maven-compiler-plugin to use ECJ instead of javac:

```
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-compiler-plugin</artifactId>
    <version>3.8.1</version>
    <configuration>
        <compilerId>eclipse</compilerId>
    </configuration>
    <dependencies>
        <dependency>
            <groupId>org.codehaus.plexus</groupId>
            <artifactId>plexus-compiler-eclipse</artifactId>
            <version>2.8.8</version>
        </dependency>
    </dependencies>
</plugin>
```

The versions may have been updated since writing this blog post, so you might want to search for updates when you want to implement this.

## Conclusion

Speed up your Maven build considerably substituting javac with ECJ. With just a minor adjustment to your project configuration you can gain tens of seconds or more when building it. Life is too short to wait for `javac`.

