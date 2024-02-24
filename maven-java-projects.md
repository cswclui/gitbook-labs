# Maven Java Projects

## Overview

Maven is a tool for building and managing your Java-based projects.

* Simplify the build process. For instance, your Java project may consist of many classes and depend on different class libraries.
* Define and manage the dependencies/libraries used by the project.

If you run the `mvn -v` command, you will get some output about your current environment, including your version of Java.&#x20;

Start a terminal in the VSCode workspace folder.

<div align="left">

<figure><img src=".gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

</div>

&#x20;Check that `maven` is installed in the operating system.

<div align="left">

<figure><img src=".gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

</div>

## Create a Maven Project

In VSCode, press Ctrl+Shift+P. Search for **Java**.  Select **Create Java Project ...**.

<div align="left">

<figure><img src=".gitbook/assets/image (95).png" alt=""><figcaption></figcaption></figure>

</div>

Alternatively, if you already have the Java Project Panel opened In the Explorer tab in VSCode. you may Click **`+`** under the Java Project Panel.

<div align="left">

<img src=".gitbook/assets/image (134).png" alt="">

</div>

Choose **Maven**.&#x20;

<div align="left">

<img src=".gitbook/assets/image (73).png" alt="">

</div>

Select the Archtetype `maven-archetype-quickstart`.

<div align="left">

<figure><img src=".gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

</div>

For version, select 1.4.

<div align="left">

<figure><img src=".gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

</div>

Accept the default group id (which will become the package name), artifact id (which will become the base folder name of the project) and the workspace folder as the base path.

<div align="left">

<img src=".gitbook/assets/image (101).png" alt="">

</div>

<div align="left">

<img src=".gitbook/assets/image (62).png" alt="">

</div>

<div align="left">

<figure><img src=".gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

</div>

Accept the default when asking for the following parameters (Press enter).

<div align="left">

<img src=".gitbook/assets/image (130).png" alt="">

</div>

Examine the Maven project structure.

<div align="left">

<figure><img src=".gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

</div>

Open `App.java` under `/src/main/java/com/example`.&#x20;

If you see errors in your code, you may refresh the VSCode page to refresh the VSCode `Java extension.`

<div align="left">

<figure><img src=".gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

</div>

Click **Ctrl+Shift+P**. Select **Developer: Reload Window**.

<div align="left">

<figure><img src=".gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

</div>

Execute the project by clicking the **Run** button above the main function. ().

<div align="left">

<figure><img src=".gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

</div>



Maven encourages better software development practices by providing a standard convention for how source and test code should be organized. By default, Maven expects that

* Your source code to be located at `/src/main/java` + `groupId`(we have accepted the default value `com.example`in the previous step).&#x20;
* Your test classes with test cases to be located in `/src/test/java` + `groupId`



Open a new VScode terminal in the workspace folder. Change to the `demo` folder (if you are not in the folder).

```
cd demo
```

Compile the project

```
mvn compile
```

The default project may generate the following error as the configuration for the Java version in the project is not correct.

<div align="left">

<figure><img src=".gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

</div>



The `pom.xml` Project Object Model (POM) is the core of a project's configuration in Maven. You can define metadata about your project, dependencies, plug-ins, and control things like build process and package management.

The file `pom.xml` is an XML file that contains information about the project and configuration details used by Maven to build the project. Click the file `pom.xml` to view its content. and replace it with the following contents. Save the change.

```xml

<?xml version="1.0" encoding="UTF-8"?>

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>

  <groupId>com.example</groupId>
  <artifactId>demo</artifactId>
  <version>1.0-SNAPSHOT</version>

  <name>demo</name>
  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <maven.compiler.source>18</maven.compiler.source> <!-- modified -->
    <maven.compiler.target>18</maven.compiler.target> <!-- modified -->
    <exec.mainClass>com.example.App</exec.mainClass> <!-- added-->
  </properties>

  <dependencies>
    <dependency>
        <groupId>junit</groupId>
        <artifactId>junit</artifactId>
        <version>4.11</version>
        <scope>test</scope>
    </dependency>
  </dependencies>

  <build> <!-- added-->
      <plugins>
          <plugin>
          <!-- Build an executable JAR -->
          <groupId>org.apache.maven.plugins</groupId>
          <artifactId>maven-jar-plugin</artifactId>
          <version>3.1.0</version>
          <configuration>
            <archive>
              <manifest>
                <addClasspath>true</addClasspath>
                <classpathPrefix>lib/</classpathPrefix>
                <mainClass>com.example.App</mainClass>
              </manifest>
            </archive>
          </configuration>
        </plugin>
      </plugins>
  </build>
</project>

```



**Exercises:** &#x20;

Use Copilot to explain the highlighted lines in pom.xml.

<div align="left">

<figure><img src=".gitbook/assets/image (147).png" alt=""><figcaption></figcaption></figure>

</div>

Open a new VScode terminal in the workspace folder. Change to the `demo` folder (if you are not in the folder).

```
cd demo
```

Compile the project

```
mvn compile
```

<figure><img src=".gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

The Maven `exec` plugin provides an option _**exec:java**_ to run a main class program of your java project.&#x20;

Execute the following command to execute your project.

```
mvn exec:java
```

Sample output for successful execution of the program.

<div align="left">

<figure><img src=".gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

</div>

A Maven plugin is like a tool or an add-on for Maven, which is a tool used to build and manage Java projects.  For example, there are plugins that can compile your Java code, create files that package your code (like JAR or WAR files), run tests on your code, generate documentation for your code, and more.

The `clean` Plugin in Maven is used when you want to remove files generated at build time in a project's directory. Execute the following command to delete all previously compiled `Java .class` files so that we can start from a clean state.

```
mvn clean
```

<div align="left">

<figure><img src=".gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

</div>

Check that the previously compiled class (if any) will be removed.

&#x20;![](<.gitbook/assets/image (123).png>)









