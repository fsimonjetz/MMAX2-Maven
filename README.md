## Mavenized MMAX2

### General

This is an attempt to convert the [MMAX2](https://github.com/nlpAThits/MMAX2)
soruce code into a structure that allows compiling
and packaging into a single `.jar` using [Apache Maven]
(https://maven.apache.org/). The dependencies of the project have
been included into the `pom.xml`, i.e., they are pulled by `Maven`
when building or packaging the project. However, this didn't work for
the [jakarta oro](http://jakarta.apache.org/oro/) tools that are used by MMAX2
for their regex capabilities. The library has been deprecated since
2010 and should probably be replaced by something more recent, but for the time
being, it is included via a local dependency solution.

### Building the .jar

After updating code it can be tested and deployed
by `cd`-ing to the source directory of the
repository (where the `pom.xml` is located) and
running `mvn package`. This will generate several
files under the `target` directory, including
`mmax2-0.0.1-jar-with-dependencies.jar`, which
should work on
its own without additional files.

This was tested on a MacBook running macOS 10.13.6,
Java 8 and Maven 3.6.0.
