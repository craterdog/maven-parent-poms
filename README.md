# Maven Parent POMs

## The Gist
These maven POM projects provide a starter set of parent pom.xml files for use in creating new, open source ready, maven projects. Each one includes a typical set of dependencies related to a specific type of project.

## Highlighted Components
The following highlights the parent pom.xml file that this project provides:

 * *root* - the root parent pom.xml file for all other parent pom.xml files
 * *java-api* - defines dependencies needed by projects that only define Java interfaces and
purely declarative classes (no methods)
 * *java-pojo* - defines dependencies needed by projects that define "plain old Java objects" (POJOs)
 * *java-web-service* - defines dependencies needed by web resources

## Quick Links
For more detail on this project click on the following links:

 * [Apache Maven - Introduction to the POM](http://maven.apache.org/guides/introduction/introduction-to-the-pom.html)
 * [wiki](https://github.com/craterdog/maven-parent-poms/wiki/Crater-Dog-Technologies%E2%84%A2-Maven-Parent-Poms)
 * [website](http://craterdog.com)

## Getting Started
To get started using these POM files, include something like the following dependency in your maven pom.xml file:

```xml
    <parent>
        <groupId>com.craterdog.maven-parent-poms</groupId>
        <artifactId>java-pojo</artifactId> <!-- or whichever parent POM project is right for your project -->
        <version>3.6</version>
    </parent>
```

Or, if your project is a subproject of a *multi-module* maven project, you will need to add a `<relativePath/>`
attribute as follows:

```xml
    <parent>
        <groupId>com.craterdog.maven-parent-poms</groupId>
        <artifactId>java-pojo</artifactId> <!-- or whichever parent POM project is right for your project -->
        <version>3.6</version>
        <relativePath/>
    </parent>
```

See the [wiki](https://github.com/craterdog/maven-parent-poms/wiki/Crater-Dog-Technologies%E2%84%A2-Maven-Parent-Poms#using-parent-poms-in-multi-module-maven-projects)
for details on why this is necessary.
