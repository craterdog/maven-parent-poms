#Maven Parent POMs
These maven POM projects provide a starter set of parent pom.xml files for use in creating new, open source ready, maven projects.Each one includes a typical set of dependencies related to a specific type of project.

##Root Parent POM
The *root* project provides a root level pom.xml file that is inherited by all other parent pom.xml files that are provided by this git repository. To use it to create a new parent pom.xml file, simply include the following block in your new parent pom.xml file:

    <parent>
        <groupId>com.craterdog.maven-parent-poms</groupId>
        <artifactId>root</artifactId>
        <version>3.0</version>
    </parent>

##Java API Parent POM
The *java-api* project provides a parent pom.xml file that can be inherited by Java projects that define only interfaces and entities that contain no testable methods. To use it as the parent POM for this type of project, simply include the following block in the pom.xml file for your Java API project:

    <parent>
        <groupId>com.craterdog.maven-parent-poms</groupId>
        <artifactId>java-api</artifactId>
        <version>3.0</version>
    </parent>

##Java POJO Parent POM
The *java-pojo* project provides a parent pom.xml file that can be inherited by Java projects that define only "plain old Java objects" or POJOs.  These projects typically contain Java classes that will be used as beans within a Spring application. To use it as the parent POM for this type of project, simply include the following block in the pom.xml file for your Java POJO project:

    <parent>
        <groupId>com.craterdog.maven-parent-poms</groupId>
        <artifactId>java-pojo</artifactId>
        <version>3.0</version>
    </parent>

Note, the pom.xml file for the *java-pojo* project actually inherits from the pom.xml file for the *java-api* project and shares all of its definitions and dependencies.

##Java Web Service Parent POM
The *java-web-service* project provides a parent pom.xml file that can be inherited by Java projects that define only RESTful web service resources.  To use it as the parent POM for this type of project, simply include the following block in the pom.xml file for your Java web service project:

    <parent>
        <groupId>com.craterdog.maven-parent-poms</groupId>
        <artifactId>java-web-service</artifactId>
        <version>3.0</version>
    </parent>

Similarly, the pom.xml file for the *java-web-service* project actually inherits from the pom.xml file for the *java-pojo* project and shares all of its definitions and dependencies.

