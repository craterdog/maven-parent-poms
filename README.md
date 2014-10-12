#Maven Parent POMs
These maven POM projects provide a starter set of parent pom.xml files for use in creating new, open source ready, maven projects. Each one includes a typical set of dependencies related to a specific type of project.

##Root Parent POM
The *root* project provides a root level pom.xml file that is inherited by all other parent pom.xml files that are provided by this git repository. This root pom.xml file defines dependencies on the following projects:

 * Plugins
   * maven-source-plugin (with attach source)
   * maven-javadoc-plugin
   * maven-scm-plugin
   * maven-release-plugin (autoversionsubmodules)
   * maven-deploy-plugin
   * maven-gpg-plugin (only when a passphrase is passed)

To use it to create a new parent pom.xml file, simply include the following block in your new parent pom.xml file:

    <parent>
        <groupId>com.craterdog.maven-parent-poms</groupId>
        <artifactId>root</artifactId>
        <version>3.4</version>
    </parent>

##Java API Parent POM
The *java-api* project provides a parent pom.xml file that can be inherited by Java projects that define only interfaces and entities that contain no testable methods. This parent pom.xml file defines dependencies on the following projects:

 * Spring Framework
   * spring-core (commons-logging excluded)
   * spring-expression
   * spring-beans
   * spring-aop
   * spring-context
 * Logging
   * slf4j-api
   * slf4j-simple
   * slf4j-ext
   * jcl-over-slf4j
   * logback-classic
   * logback-core
 * Miscellaneous
   * joda-time
   * oval
 * Plugins
   * maven-compiler-plugin (java 1.8, show deprecation, Xlint args)

To use it as the parent POM for this type of project, simply include the following block in the pom.xml file for your Java API project:

    <parent>
        <groupId>com.craterdog.maven-parent-poms</groupId>
        <artifactId>java-api</artifactId>
        <version>3.4</version>
    </parent>

##Java POJO Parent POM
The *java-pojo* project provides a parent pom.xml file that can be inherited by Java projects that define only "plain old Java objects" or POJOs.  These projects typically contain Java classes that will be used as beans within a Spring application. This parent pom.xml inherits the dependencies defined above for the java-api pom.xml file and also defines dependencies on the following additional projects:

 * Spring Framework
   * spring-context-support
 * Apache Commons
   * commons-lang
   * commons-codec
   * commons-io
 * AOP
   * cglib
   * aspectjtools
   * aspectjweaver
 * Unit Testing
   * junit
   * easymock
   * spring-test

To use it as the parent POM for this type of project, simply include the following block in the pom.xml file for your Java POJO project:

    <parent>
        <groupId>com.craterdog.maven-parent-poms</groupId>
        <artifactId>java-pojo</artifactId>
        <version>3.4</version>
    </parent>

Note, the pom.xml file for the *java-pojo* project actually inherits from the pom.xml file for the *java-api* project and shares all of its definitions and dependencies.

##Java Web Service Parent POM
The *java-web-service* project provides a parent pom.xml file that can be inherited by Java projects that define only RESTful web service resources. This parent pom.xml inherits the dependencies defined above for the java-api and java-pojo pom.xml files and also defines dependencies on the following additional projects:

 * Spring Framework
   * spring-web
 * Apache CXF
   * cxf-rt-frontend-jaxrs (with multiple exclusions)
 * Jackson
   * jackson-jaxrs-json-provider
   * jackson-jaxrs-xml-provider
 * Plugins
   * jetty-maven-plugin

To use it as the parent POM for this type of project, simply include the following block in the pom.xml file for your Java web service project:

    <parent>
        <groupId>com.craterdog.maven-parent-poms</groupId>
        <artifactId>java-web-service</artifactId>
        <version>3.4</version>
    </parent>

Similarly, the pom.xml file for the *java-web-service* project actually inherits from the pom.xml file for the *java-pojo* project and shares all of its definitions and dependencies.

## Using Parent POMs in Multi-Module Maven Projects
Often a project will be structured as a mulit-module maven project so that each subproject is maintained and released together. If the subprojects are of different types they each require a different parent pom.xml file containing the dependencies that are appropriate for that type of project.  The parent pom.xml files listed above can be used as the parent pom.xml files for subprojects as well with one important addition to the declaration. For example, if one of the subprojects defines Java POJOs, the following should be used to define its parent POM:

    <parent>
        <groupId>com.craterdog.maven-parent-poms</groupId>
        <artifactId>java-pojo</artifactId>
        <version>3.4</version>
        <relativePath/>
    </parent>

The empty "relativePath" attribute tells maven that the parent POM is not the *aggregator* POM from the multi-module project but, instead, should be searched for in the central maven repository. Without this attribute in the declaration, maven will generate a warning similar to the following:

    [INFO] Scanning for projects...
    [WARNING] 
    [WARNING] Some problems were encountered while building the effective model for com.craterdog.example:example-beans:jar:1.0-SNAPSHOT
    [WARNING] 'parent.relativePath' points at com.craterdog.example:aggregator instead of com.craterdog.maven-parent-poms:java-pojo, please verify your project structure @ line 25, column 13
    [WARNING] 
    [WARNING] It is highly recommended to fix these problems because they threaten the stability of your build.
    [WARNING] 
    [WARNING] For this reason, future Maven versions might no longer support building such malformed projects.
    [WARNING] 

