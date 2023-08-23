# Methods

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/y3Hd2wpYzqs?si=bJxyURFODkJsis5i" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: Methods Video Walkthrough**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

## 🔍 What are Methods? 

Methods allow us to *define our own commands*, which also allows us to compartmentalize our logic and thus our code. Methods also help us reduce redundancies to write concise and clear code that is readable for others as well. This way we are not dumping all our code into the main method.  

For example we have already been calling a method:  `System.out.println`. This is a method that the Java developers wrote to print some text to the console, and we are able to **call** it each time we want to print something out! 

This means that we don't have to understand or repeat all that is involved in printing to the console every time we want to produce some output - we can just use this method to do exactly that, clearly and concisely! 



## 🤔 Why methods? 

Methods allow us to "pull" some code out of the `main` method and into individual method bodies instead. This leaves `main` only containing the high-level details of the program. We often like to think about `main` as a table of contents. 

From reading through `main` you should be able to get a high-level idea of what the program does without getting into the specifics of exactly how each method is written. This is similar to how you can get an idea of what a book contains from the table of contents, without getting into all of the information which is stored in the chapters! 

Methods also allow us to package several lines of code into a single "command", which can help us reduce redundancy in our programs. 

Take a look at the following program that makes good use of static methods to pull tasks out of `main` and reduce redundancy: 

```java
public class BakeCookies {
    public static void main(String[] args) {
        makeDough();
        bake();
        bake();
        bake();
    }

    public static void makeDough() {
        System.out.println("Cream the butter and sugar together");
        System.out.println("Add eggs and vanilla extract");
        System.out.println("Combine dry ingredients separately");
        System.out.println("Add dry ingredients to wet ingredients slowly");
        System.out.println("Fold in chocolate chips");
    }

    public static void bake() {
        System.out.println("Scoop spoonfuls of dough and place on cookie sheet");
        System.out.println("with about 2 inches of separation");
        System.out.println("Bake for about 8 minutes");
        System.out.println("Wait a few minutes and transfer to rack to cool completely");
    }
}
```

## 📗 Method Syntax

**Part 1: Creating a Method**

```java
public static void myMethod() {
    /***
    Your code here
    **/
}
```

- **public static void**
    * Similar to our main method we call public static so that our method can be used. You do not need to know why this is needed at the moment. Rather as the quarter progresses you will come to understand the meaning and necessity.  

- **myMethod**
    * This is the name of our method, similar to how we call the main method "main". But unlike the main method we can name methods we create anything we want. 
    * We will use this method header to identify and use this method, so the name needs to be unique!

- **()**
    * We do not need to worry about this right now and it will be introduced at a later point.

**Part 2: Calling a Method** 

When we **call** a method, we are executing a block of code in the order it is written in our method.

```java
public static void main(String[] args) {
    myMethod(); // here we call our method
}
```

- **myMethod();**
    * In order to "call" our method (i.e. utilize it), we have the name of our method followed by the open and closed parentheses. 
    * We have a naming convention in Java where all of our methods use **camelCasing** 🐪. Specifically, this means that the first letter of every word **after the first** is uppercased.
    * All methods in a program should be uniquely named so as to not cause confusion to the programmer nor Java. More on this later.

## 🧠 Try this out!

```java
public class Before {
    public static void main(String[] args) {
        // What we have seen
        System.out.println("Hello World");
        System.out.println("I hope you have a great day");
        System.out.println();
        System.out.println("Good night World");
        System.out.print("It was a great day");
    }
}
```

Now we can create our own methods to help us reuse logic and reduce redundancies. Note below how creating our own methods has compartmentalized our code to look cleaner and easier to read. 

The Java program above <ins>exhibits the same behavior</ins> as the program below:

```java
public class After {
    public static void main(String[] args) {
        // After 
        printHello();
        printGoodNight(); 
    }

    public static void printHello() {
        System.out.println("Hello World");
        System.out.println("I hope you have a great day");
        System.out.println();
    }

    public static void printGoodNight() {
        System.out.println("Good night World");
        System.out.print("It was a great day");
    }
}
```

:::{adominition} **Note:**
:class: note
NOTE: We do not have to always call our methods inside `main`, we can call methods in other methods too! But in order for anything to happen we need to call at least something in `main` to get things started. 
:::

## **Main Points:**

- Avoid repeating the same code over and over again. Instead of writing the same stuff multiple times, you can create a method and just call it whenever you need that code to run.

- Method syntax involves creating a method with a unique name and optionally passing parameters (arguments).

- Calling a method executes the block of code defined within the method, providing a way to reuse logic throughout the program.

- Utilizing methods helps keep the main method clean and allow you to share code across your program.
    * Your main method becomes a high-level overview of how your program functions! 