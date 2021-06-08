![Maven Parent POMs](https://github.com/craterdog/maven-parent-poms/blob/master/docs/images/DNA.jpg)

### Maven Parent POMs
[Apache Maven](https://maven.apache.org/) is a popular dependency management system that makes it easier to build software projects. Maven defines a "project object model" file called `pom.xml` for each project. It defines the dependencies that that project has on other projects and plugins. One of the nice features of Maven is the ability to inherit dependencies from a parent `pom.xml` file.

This open source Maven multi-module project provides a starter set of parent `pom.xml` files for use in creating new, open source ready, Maven projects. Each one includes a typical set of dependencies related to a specific type of project. For a tutorial on how to use these parent `pom.xml` files to "jump start" your maven/java based open source project, click [here](https://github.com/craterdog/maven-parent-poms/wiki/Jump-Starting-Your-Maven-Java-Open-Source-Project).

### Highlighted Components
The following highlights the parent pom.xml file that this project provides:

 * *root* - the root parent pom.xml file for all other parent pom.xml files
 * *java-aggregator* - defines dependencies needed by multi-module maven projects
 * *java-api* - defines dependencies needed by projects that only define Java interfaces and
purely declarative classes (no methods)
 * *java-pojo* - defines dependencies needed by projects that define "plain old Java objects" (POJOs)
 * *java-component* - defines dependencies needed by projects that depend on the Java Spring Framework
 * *java-web-service* - defines dependencies needed by web resources

### Quick Links
For more detail on this project click on the following links:

 * [Apache Maven - Introduction to the POM](https://maven.apache.org/guides/introduction/introduction-to-the-pom.html)
 * [wiki](https://github.com/craterdog/maven-parent-poms/wiki)
 * [release notes](https://github.com/craterdog/maven-parent-poms/wiki/releases)
 * [website](https://craterdog.com)

### Getting Started
To get started using these parent POM files, include something like the following dependency in your
maven pom.xml file:

```xml
    <parent>
        <groupId>com.craterdog.maven-parent-poms</groupId>
        <artifactId>java-component</artifactId> <!-- or whichever is right for your project -->
        <version>x.y</version>
    </parent>
```

The parent pom.xml file artifacts for this project are available from the *Maven Central Repository*.

### Recognition
_Crater Dog Technologies™_ would like to recognize and thank the following
companies for their contributions to the development and testing of various
components within this project:

 * _Blackhawk Network_ (https://blackhawknetwork.com)

