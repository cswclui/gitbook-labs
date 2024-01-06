# Creating and Running Java programs

In the _Explorer_ tab, create a folder `basic` under your workspace.  Inside the folder, create a Java source file `TestCircle.java`.

Define the `main` function as follows.

```java
public class TestCircle {
    public static void main(String args[]) {
        System.out.println("Hello");
      } 
}
```

![](<.gitbook/assets/image (116).png>)

Press `` Ctrl+` `` to open a terminal. To execute the program, enter the folder, compile the Java source file into bytecode.

```
cd basic
javac TestCircle.java
```

<div align="left">

<figure><img src=".gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

</div>

&#x20;Execute the Java program.

```
java TestCircle
```

You can also click the `Run` button in VSCode IDE.

<div align="left">

<figure><img src=".gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

</div>

<div align="left">

<figure><img src=".gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

</div>

Click Yes.

if your Java extension pack has been installed in VSCode, you can Run the program by clicking the button.

<div align="left">

<img src=".gitbook/assets/image (140).png" alt="">

</div>

Modify the `TestCircle.java` as follows.

```java
class Circle{
    public void draw() {
        System.out.println("I am drawing a Circle");
    }
}

public class TestCircle {
    public static void main(String args[]) {
        Circle c = new Circle();
        c.draw();
      } 
}
```

Execute the program and observe the output.

## Exercise

Modify the `TestCircle` class as follows.

* Define a private attribute `radius` for the Circle class.&#x20;
* Define a constructor function which accepts a radius (an integer) as the parameter.&#x20;
* When calling the `draw()` method, the method should print the radius of the circle.
* Define a getter method `getRadius()` which returns the radius of the circle.

To generate Setter and Getter Methods in VSCode,  in a Java source file, Right-click and select `Source Action...` .&#x20;

<div align="left">

<img src=".gitbook/assets/image (128).png" alt="">

</div>

Select `Generate Getters and Setters`.

<div align="left">

<img src=".gitbook/assets/image (96).png" alt="">

</div>

You can select `Generate Constructors...` to generate the Constructor method.



Modify the main function as follows.

```java
public class TestCircle {
    public static void main(String args[]) {
        Circle c1 = new Circle(5);
        c1.draw();  
        System.out.println(c1.getRadius());

        Circle c2 = new Circle(10);
        c2.draw();
        System.out.println(c2.getRadius());
      } 

}
```



Sample output:

<div align="left">

<img src=".gitbook/assets/image (90).png" alt="">

</div>

## References

* [https://www.guru99.com/java-tutorial.html](https://www.guru99.com/java-tutorial.html)

