# While Loops

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/YMh6lgdQTsE?si=x80fTZ269v3_IML2" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: While Loops Video Walkthrough**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

By now, we've worked a lot with `for` loops to simplify tasks that are repeated a set number of times. We will typically use `for` loops for what we call **definite loops**, meaning that when we write a `for` loop, we will write it in such a way that we know exactly how many times the loop should run. For example, we would use a `for` loop to print the word "Hello" 10 times, or print all numbers between 1-100. 

However, suppose you want to implement a task that repeats, but don't know in advance how many times to repeat it. What then? 

For example, I want to write a loop that keeps generating random values (using `Random`) until we hit a particular value. For example, let's say I want to keep generating random values until I generate the number 6. If the number 6 is generated, I want to end the loop. In this example, we don't know after how many tries it'll take to generate 6, so we <ins>can't</ins> use a definite loop. 

 

## Indefinite (`while`) Loops ⛔

Luckily for us, we have a programming construct called the `while` loop. A `while` loop is a type of **indefinite loop**, meaning that it's a loop that <ins>runs **until** some condition is met</ins>. When writing a `while` loop, we will define a test, which when evaluated to false ends the loop. 

## `while` Loop Syntax 📗

![Image of the while loop syntax: while(text){body (statements to be repeated)}](images/while-loop-code.png)

The `while` loop contains two key elements:

1. The **test** (within the parentheses) – in this step, we are checking whether or not to continue iterating in the `while` loop by way of a *continuation test*. This should take the form of some statement that can be evaluated as **true** or **false**. When we look at the test, we must determine whether the relationship of the two values is true or false, which will help us determine if we should continue in the loop. Just like a `for` loop, once the test evaluates to false, we no longer execute the body of the loop!
2. The **body** (within the brackets)– this is the set of controlled statements that will be *executed* or run every time we take another iteration in the while loop.

Like `for` loops, there is an initialization and update step, but these are not part of the `while` loop syntax! The initialization usually occurs right before the `while` loop, and the update usually occurs within the `while` loop (most likely at the end), as shown in the example below.

```java
// example while loop
int n = 5;
while (n < 50) {
    n *= 5;
}
System.out.println(n);
```

## ✏️ Writing a `while` Loop

Let's go back to our example of writing a loop that keeps prompting generating random values until 6 is generated. We can break this problem down into the following steps:
1. Use a `Random` variable to generate a random value in some range, and store it into a variable (**initialization + body**)
2. Check if the number is 6 (**test**)
    * If it is, end the loop!
    * If not, generate another random value and repeat steps 1, 2

This process of repeating steps an indefinite number of times is where the while loop comes in! Let's see this in code ⬇️ 
```java
import java.util.*;

public class WhileLoops {
    public static void main(String[] args) {
        // create Random variable and use it to generate a random value
        Random rand = new Random();
        // generate a random value in the range of 1 (inclusive) to 10 (inclusive)
        
        int randomValue = rand.nextInt(10) + 1; // initialization
        
        // Check if the number is 6, and repeat if not!
        while (randomValue != 6) { // test: repeat until the number is 6
            System.out.print(randomValue + " ");
            randomValue = rand.nextInt(10) + 1;  // update
        }
        System.out.println();
        System.out.println("generated 6!");
    }
}
```

Notice that just like a `for` loop, a functional `while` loop contains some sort of initialization, test, and update. This ensures that we don't run an *infinite loop*.

## `for` loops vs. `while` loops ⚔️ 

Now that we've learned about `for` loops and `while` loops, you might see a lot of similarities between the two: they both contain initializations, tests, and updates, and they both repeat some process until some test evaluates to `false`. 

But the main overall difference between the two is how they are being used: as `definite` and `indefinite` loops. When you're thinking through design decisions when writing a program using a loop, consider the following:
- Do you know exactly how many times you need to iterate in your loop before you run your loop?
    * If **YES ➡️ use a for loop!** A `for` loop is specifically meant to be used when you know how many times you need to iterate.
    * If **NO ➡️ use a while loop!** A `while` loop is specifically meant to be used in a situation where you don't know exactly how many times you need to iterate, all you know is that some process must be repeated until some condition is met.



`while` Loop Control Flow 🔁 

How do all of these elements come together? Check out the **`while` loop control** flow diagrammed below:

![Diagram of the while loop control flow: Perform the initialization once at the beginning. Is the test true? If yes, execute the statements inside the while loop body, then perform the update. Repeat until the condition is no longer true. Once the condition is false, execute the statmeents that are immediately after the loop body.](images/while-loop-control-flow.png)

We will first perform the initialization once at the beginning. If the test is **true**, then we execute the statements inside the while loop body and perform the update before checking if the test is true again. However, if the test is **false**, we exit the while loop and execute the statements that are immediately after the while loop body.

You might notice that this control structure is very similar to that of the `for` loop! There is an initialization, a test, and an update.

## Main Points

- `while` loops are a type of **indefinite** loop, meaning that the loop runs for as long as some condition (the **test**) is met.
    * This is opposed to `for` loops which are a kind of **definite** loop, meaning we know exactly how long the loop will run for just by looking at its first line.
- We want to use `while` loops when we do not know how many times a while loop will run for, but we know we want it to run for until we reach some condition.
* (e.g. keep generating Random numbers until we generate the number 6, or keep adding 1 to a variable until its value is 17).
- `while` loops consist of two main elements: 
    1. The **test**, which evaluates to **true** or **false** and tells us whether we should continue with the contents of the loop, and
    2. The **body**, which is a set of controlled statements that will execute if the **test** evaluates to **true**
- Just like `for` loops, `while` loops also consist of an **initialization** and **update** step.
    * Unlike `for` loops, the **initialization** occurs before the `while` loop runs, and the **update** occurs sometime within the loop (likely at the end!)