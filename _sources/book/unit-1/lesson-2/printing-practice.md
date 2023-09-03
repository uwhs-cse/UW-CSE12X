# Println's Review

These questions are to assess your understanding of printing in Java.

**Question 1**

True or False: The `System.out.print` method displays text to the screen and **inserts a new line**.

:::{admonition} See Answer
:class: tip
:class: dropdown
False!
:::

<hr>

**Question 2**

Which of the following is the correct syntax to output the message "Hello, world!"?
- `System.out.println(Hello, world!);`
- `System.println("Hello, world!");`
- `System.println.out('Hello, world!);`
- `Out.system.println"(Hello, world!)";`
- `System.out.println("Hello, world!");`

:::{admonition} See Answer
:class: tip
:class: dropdown
The correct syntax to output "Hello, world!" is:
`System.out.println("Hello, world!");`
:::

<hr>

**Question 3**

What series of `System.out.print` and `System.out.println` statements would produce the following output? 

``` java
Several slashes are sometimes seen,
said Sally. I've said so. See?
```

Make sure to choose ***all*** options that produce the desired output.

*Hint*: For each `print` and `println` statement, track where your cursor is going to be at the end of that statement!

1. ```java 
    System.out.print("Several slashes are sometimes seen,");
    System.out.print("said Sally. I've said so. See?");
   ```
2. ```java 
    System.out.println("Several slashes are sometimes seen,");
    System.out.println("said Sally. I've said so. See?");
   ```
3. ```java 
    System.out.print("Several slashes ");
    System.out.print("are sometimes seen,");
    System.out.println("said Sally. I've said so. See?");
   ```
4. ```java 
    System.out.print("Several slashes ");
    System.out.println("are sometimes seen,");
    System.out.println("said Sally. I've said so. See?");
   ```

:::{admonition} See Answer
:class: tip
:class: dropdown
Options **2** and **3** are correct!
:::

<hr>

**Question 4**
What is the output of the following series of `System.out.print` and `System.out.println` statements:
```java
System.out.print("There's one thing every coder ");
System.out.println("must understand:");
System.out.println("The System.out.println command.");
```

Write it as you would see on the terminal. (i.e. no quotation marks!)

:::{admonition} See Answer
:class: tip
:class: dropdown
There's one thing every coder must understand: The `System.out.println` command.

:::{admonition} Explanation
:class: note
First, we print out `There's one thing every coder` but **stay** on the same line since it is just a print statement. Then, we print out `must understand`: on the same line and then **move** to the next line because it is a println statement. Finally, we print out `The System.out.println command.` and move to the next line.

Answer:
``` text
There's one thing every coder must understand:
The System.out.println command.
```
:::