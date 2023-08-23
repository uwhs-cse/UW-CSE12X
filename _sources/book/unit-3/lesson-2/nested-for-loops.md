# Nested For Loops

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/Godft3qzkLM?si=6cL_N2oWxcnXajps" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: Nested For Loops Video Walkthrough**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

**For loops** are a powerful construct in computer science, allowing programmers to repeat lines of code for a definite amount of times. This allows us to control exactly how many times we want to repeat a particular process. 

Note that sometimes, we're not just programming to complete a singular repetitive process. Sometimes we'll repeat a task with repetition.

Say that I wanted to write some code to print this figure made of ASCII characters:

``` java
******************************
******************************
******************************
******************************
******************************
```

The figure above consists of 5 lines of 30 asterisks/stars.

Not only are we just printing 5 lines repeatedly, but we are also repeatedly printing 30 asterisks/stars within one line! This is an example of repeating a task (printing one asterisk 30 times) with repetition (doing this for 5 lines), or in other words, repeating a task that already has repetition in that very task.

When we are repeating a task with repetition, we are able to solve this by putting a for loop inside a **for loop**, often called a **nested loop**. Using nested for loops allow for further flexibility in writing code and layers of repetition.

If I were to write a program to code this without using nested for loops, it would probably look something like this:

```java
public class Example {
    public static void main(String[] args) {
        for (int line = 1; line <= 5; line++) {
            System.out.println("******************************");
        }
    }
}
```

When we **run** the program, it works and provides the output we want! However, if we look further, not only are we repetitively repeating lines of asterisks (5 times), but there's another repetitive process as well. For each line we are printing, we are repetitively printing 30 asterisks!

We'll come back to this example after reviewing nested for loop syntax.

## Nested For Loop Syntax

There's no new syntax when writing a nested for loop, we're just simply putting a for loop <ins>inside</ins> another for loop:

```java
public class Example {
    public static void main(String[] args) {
        // example for loop

        // the outer loop that will run 5 times
        for (int outerLoop = 1; outerLoop <= 5; outerLoop++) {
            
            // the inner loop that runs 3 times
            for (int innerLoop = 1; innerLoop <= 3; innerLoop++) {
                int product = outerLoop * innerLoop;
                System.out.println(outerLoop + " * " + innerLoop + " = " + product);
            }
    
        } // CHALLENGE! can you determine the output when this loop runs?
    }
}
```

Note that both the inner and outer for loops contain the four main elements of a for loop – *initialization, test, update*, and *body*. 

Remember that every time we iterate in any for loop, we are going to execute the entire of body of controlled statements that comes after the for loop header. 

## Nested For Loops & Scope 🔭

Try running the code below!

```java
public class Example {
    public static void main(String[] args) {

        // outer loop
        for (int outerLoop = 1; outerLoop <= 5; outerLoop++) {
            System.out.println("outer loop iteration #" + outerLoop);
            for (int innerLoop = 1; innerLoop <= 3; innerLoop++) {
                System.out.println("    inner loop iteration #" + innerLoop);
            }
            // at this point, innerLoop is OUT OF SCOPE!
            System.out.println(innerLoop);
        }
    }
}
```

Notice that you get an <ins>error</ins> on line 11 saying that the compiler could not find the symbol **`innerLoop`**. 

This has to do with the concept of **scope** (which we will get into more later in the course). You can think about scope as being limited in where you can use particular variables in your code depending on where you're writing code. 

Just know for now that the counter variable we create in the initialization step of a particular for loop is only available to use <ins>inside</ins> that particular for loop.

Once we end running the **for loop** and execute the statements of code after its closing curly brace, that variable no longer exists!

:::{admonition} Warning
:class: warning
Try deleting line 11 from the code block above and running it!
:::

## Application to Example 🔁

Let's apply what we've learned in this pre-lecture lesson to the example presented at the beginning with the following output! 
```
******************************
******************************
******************************
******************************
******************************
```

:::{admonition} Expand
:class: note
:class: dropdown
Code to write the above output using nested for loops:
```java
// outer for loop that will print our five lines
for (int i = 0; i < 5; i++) {
    // inner for loop that will repeatedly print 30 asterisks for each line
    for (int j = 0; j < 30; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```
:::

:::{admonition} Tip
Check out the video walkthrough at **08:42** to see this nested for loop written!
:::

## Main Points:

- We've learned about **nested for loops**, which are used when we need to repeat a task (inner loop) multiple times within another repetition (outer loop).

- **Nested for loop** syntax involves placing a for loop <ins>inside</ins> another for loop, similar to any regular for loop structure. Both the inner and outer loops have initialization, test, update, and body sections.

- When using nested for loops, be careful about variable **scope**. Variables declared in the inner loop are not accessible outside of that inner loop's body.