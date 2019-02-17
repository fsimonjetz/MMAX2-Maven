## Mavenizing MMAX2

### General

The original directory structure of the `MMAX2` source code made it
difficult to make changes, missing an obvious way to build the source
code. The new structure is a more standard one and allows compiling
and packaging the source code as a single `.jar` using [Apache Maven]
(https://maven.apache.org/). The dependencies of the project have
been included into the `pom.xml`, i.e., they are pulled by `Maven`
when building or packaging the project. However, this didn't work for
the `jakarta` tools that are used by MMAX2 for their regex
capabilities. The library has been [deprecated since
2010](http://jakarta.apache.org/oro/) and
should be replaced by something more recent, but for the time being,
it is included via a local solution.

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
