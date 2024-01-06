# Exercise

Create a new terminal in vscode. Under the workspace folder, create a maven project using the `mvn` command under the workspace folder.

```
mvn archetype:generate -DgroupId=com.example \
-DartifactId=Demo2 \
-DarchetypeArtifactId=maven-archetype-quickstart \
-DinteractiveMode=false
```

Tasks:

* Modify the App.java to print "Java is fun!"
* Modify the `pom.xml` (Refer to Maven Java Project section for the sample pom.xml file).
* Compile and execute the project using the `mvn`  command.

Sample output:

<div align="left">

<figure><img src=".gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

</div>
