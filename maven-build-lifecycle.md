# Maven Build Lifecycle

A phase is a step in the [build lifecycle](https://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html) (which is an ordered sequence of phases). The default lifecycle comprises the following phases:

* `validate` - validate the project is correct and all necessary information is available
* `compile` - compile the source code of the project
* `test` - test the compiled source code using a suitable unit testing framework. These tests should not require the code be packaged or deployed
* `package` - take the compiled code and package it in its distributable format, such as a JAR.
* `verify` - run any checks on results of integration tests to ensure quality criteria are met
* `install` - install the package into the local repository, for use as a dependency in other projects locally
* `deploy` - done in the build environment, copies the final package to the remote repository for sharing with other developers and projects.

When a phase is given, Maven executes every phase in the sequence up to and including the one defined.

In the VSCode terminal, under the demo folder created in previous section.

Use following command will validate and compile the project.

```
mvn compile
```

<div align="left">

<img src=".gitbook/assets/image (77).png" alt="">

</div>

This will create a directory called `target/` that contains all of your compiled code (e.g. `app.class)` in the `classes` directory.&#x20;

![](<.gitbook/assets/image (111).png>)

When you are ready to share your application with others, you can build and package it.

The following command will validate, compile, test, and package the project to generate a jar file for it.

```
mvn package
```

<div align="left">

<figure><img src=".gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

</div>

You can find the `.jar` file under the `target` folder.

![](<.gitbook/assets/image (57).png>)

A JAR (Java ARchive) is a package file format typically used to aggregate many Java class files and associated metadata and resources (text, images, etc.) into one file for distribution.&#x20;

Inside the demo folder, execute the project jar file by executing

```
java -jar target/demo-1.0-SNAPSHOT.jar 
```

<div align="left">

<img src=".gitbook/assets/image (108).png" alt="">

</div>

In VSCode's `Explorer` tab, you can also right-click on the `demo` project under the Maven tab.&#x20;

![](<.gitbook/assets/image (49).png>)

Select the phase so that Maven can execute up to the corresponding phase.

<div align="left">

<img src=".gitbook/assets/image (132).png" alt="">

</div>
