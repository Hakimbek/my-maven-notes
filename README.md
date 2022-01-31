# Maven
Maven is a powerful project management tool that is based on POM (project object model). It is used for projects build, dependency and documentation.

## Understanding the problem without Maven
There are many problems that we face during the project development. They are discussed below:

1. Adding set of Jars in each project: In case of struts, spring, hibernate frameworks, we need to add set of jar files in each project. It must include all the dependencies of jars also.
2. Creating the right project structure: We must create the right project structure in servlet, struts etc, otherwise it will not be executed.
3. Building and Deploying the project: We must have to build and deploy the project so that it may work.

## What it does?
Maven simplifies the above mentioned problems. It does mainly following tasks.

- It makes a project easy to build
- It provides uniform build process (maven project can be shared by all the maven projects)
- It provides project information (log document, cross referenced sources, mailing list, dependency list, unit test reports etc.)
- It is easy to migrate for new features of Maven

# Maven Repository
A maven repository is a directory of packaged JAR file with pom.xml file. Maven searches for dependencies in the repositories. There are 3 types of maven repository:

- Local Repository
- Central Repository
- Remote Repository

Maven searches for the dependencies in the following order:

**Local repository** then **Central repository** then **Remote repository**.

## 1) Maven Local Repository
Maven local repository is located in your local system. It is created by the maven when you run any maven command.

## 2) Maven Central Repository
Maven central repository is located on the web. It has been created by the apache maven community itself.

## 3) Maven Remote Repository
Maven remote repository is located on the web. Most of libraries can be missing from the central repository such as JBoss library etc, so we need to define remote repository in pom.xml file.

# Maven pom.xml file
POM is an acronym for Project Object Model. The pom.xml file contains information of project and configuration information for the maven to build the project such as dependencies, build directory, source directory, test source directory, plugin, goals etc.

Maven reads the pom.xml file, then executes the goal.

Before maven 2, it was named as project.xml file. But, since maven 2 (also in maven 3), it is renamed as pom.xml.

## Elements of maven pom.xml file

| Element |	Description |
| ------- | ----------- |
| project |	It is the root element of pom.xml file. |
| modelVersion |	It is the sub element of project. It specifies the modelVersion. It should be set to 4.0.0. |
| groupId |	It is the sub element of project. It specifies the id for the project group. |
| artifactId |	It is the sub element of project. It specifies the id for the artifact (project). An artifact is something that is either produced or used by a project. Examples of artifacts produced by Maven for a project include: JARs, source and binary distributions, and WARs. |
| version |	It is the sub element of project. It specifies the version of the artifact under given group. |

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"   
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">  
  
  <modelVersion>4.0.0</modelVersion>  
  <groupId>com.javatpoint.application1</groupId>  
  <artifactId>my-app</artifactId>  
  <version>1</version>  
  
</project>  
```

## Maven pom.xml file with additional elements
Here, we are going to add other elements in pom.xml file such as:

| Element |	Description |
| packaging |	defines packaging type such as jar, war etc. |
| name |	defines name of the maven project. |
| url |	defines url of the project. |
| dependencies |	defines dependencies for this project. |
| dependency |	defines a dependency. It is used inside dependencies. |
| scope |	defines scope for this maven project. It can be compile, provided, runtime, test and system. |

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"   
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">  
  
  <modelVersion>4.0.0</modelVersion>  
  <groupId>com.javatpoint.application1</groupId>  
  <artifactId>my-app</artifactId>  
  <version>1</version>  
 
  <name>Maven Quick Start Archetype</name>  
  <url>http://maven.apache.org</url>  
  
  <dependencies>  
    <dependency>  
      <groupId>junit</groupId>  
      <artifactId>junit</artifactId>  
      <version>4.8.2</version>  
      <scope>test</scope>  
    </dependency>  
  </dependencies>  
  
</project>  
```

# How to build the maven project or how to package maven project?
The mvn package command completes the build life cycle of the maven project such as:

- validate
- compile
- test
- package
- integration-test
- verify
- install
- deploy

# Maven Plugins
The maven plugins are central part of maven framework, it is used to perform specific goal.

According to Apache Maven, there are 2 types of maven plugins.

- Build Plugins
- Reporting Plugins

## Build Plugins
These plugins are executed at the time of build. These plugins should be declared inside the \<build> element.

## Reporting Plugins
These plugins are executed at the time of site generation. These plugins should be declared inside the \<reporting> element.

## Maven Core Plugins
A list of maven core plugins are given below:

| Plugin | Description |
| ------ | ----------- |
| clean | clean up after build. |
| compiler | compiles java source code. |
| deploy | deploys the artifact to the remote repository. |
| failsafe | runs the JUnit integration tests in an isolated classloader. |
| install | installs the built artifact into the local repository. |
| resources | copies the resources to the output directory for including in the JAR. |
| site | generates a site for the current project. |
| surefire | runs the JUnit unit tests in an isolated classloader. |
verifier	verifies the existence of certain conditions. It is useful for integration tests.
