# Design Decisions

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/eaCAdzKWTWY?si=8hXY7jpWY0ZBzBFq" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: Design Decisions Video Walkthrough**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

## 🤔  When to use each conditional structure?

Now that we've learned about `if`, `if/else`, and `if/else if` conditional structures, we should know in what case we should be using each of them!

As mentioned in the previous reading, though these structures generally all evaluate some test(s) and execute some statement(s) of code based on that test, they all have slightly different semantics in how exactly they work.

## 💡 You should use an if statement when...

...you only want to execute a certain block of statement(s) in **one particular case**. 

Say that I wanted to write a method that takes in an `int` parameter and prints to the console if the parameter is less than 100 and/or less than 0.

Note that this method could take in any `int` value, but I want to print to the console in the case the parameter is less than 100 and/or less than 0. Check out the example method calls below as well as the expected output:

```java
evaluateNumber(-10):
-10 is less than 100
-10 is less than 0
finished evaluating the parameter.

evaluateNumber(30):
30 is less than 100
finished evaluating the parameter.

evaluateNumber(101):
finished evaluating the parameter.
```

Note that these tests are *independent* of each other! We can test for individual conditions.

Try **running** the code below! 
:::{note}
Compare the output of the three method calls!
:::
```java
public class Example {
    public static void main(String[] args) {
        evaluateNumber(-10);
        System.out.println();
        evaluateNumber(30);
        System.out.println();
        evaluateNumber(101);

    }

    // this method will take in an integer parameter and prints
    // a line to the console if the parameter is less than 100,
    // and prints another line to the console if the parameter is 
    // less than 0
    public static void evaluateNumber(int number) {
        if (number < 100) {
            System.out.println(number + " is less than 100");
        }
        if (number < 0) {
            System.out.println(number + " is less than 0");
        }
        System.out.println("finished evaluating parameter.");
    }
}
```

:::{tip}
In short: with an `if` statement, you could execute **0, 1, or many `if` statements**.
:::

## 💡 You should use an `if/else` statement when...

...you are dealing with one of two cases. You can think of it like "this OR that"! 

Say I wanted to write a method that would take an `int` parameter and output to the console if the number was even or odd. Note that we our parameter can only fall into one of two cases, it'll either be positive or negative – never both!

Note that these tests are **mutually exclusive** – meaning that we cannot execute more than 1 of the structure's branches at once.

So in this case, it would be appropriate to utilize an `if/else` structure in this method:
```java
public class Example {
    public static void main(String[] args) {
        determineEvenOrOdd(2);
        determineEvenOrOdd(17);
        determineEvenOrOdd(-35);
        determineEvenOrOdd(0);
    }

    // this method reads in an int parameter and prints to the console
    // if the parameter is even or odd
    public static void determineEvenOrOdd(int number) {
        if (number % 2 == 0) { // if the number is even
            System.out.println(number + " is even!");
        } else { // number is odd
            System.out.println(number + " is odd!");
        }
    }
}
```

:::{dropdown} Expand
:open:
How did we know to use `% 2` to check for evenness?

Remember that modulo (`%`) provides the remainder when you divide two integers. When we take some `num % 2`, there are only two possible values we could get: `0` or `1`.

If we have some `num % 2` equal to `0`, that means there is no remainder when we divide `num` by 2. This means the value is even

If we have some `num % 2` equal to `1`, that means there is a remainder of `1` when we divide `num` by 2. This means the value is odd.
:::

:::{tip}
In short: with an `if/else` structure, you execute the statements of exactly **one branch**.
:::

## 💡 You should use an `if/else if` statement when...

...you want to evaluate specific cases, not just one or the other. 

Say that I wanted to implement a method that would take an `int` parameter and determine if it was positive or negative. I could use an `if/else` structure, but what if my parameter was 0 (a value that is neither positive nor negative)?

If my parameter was 0, I don't want to incorrectly report that the value is positive. So by using an `if/else if` structure, I can look for cases specifically where a value is positive (greater than 0) or negative (less than 0).

Note that these tests are **mutually exclusive** – meaning that we cannot execute more than 1 of the structure's branches at once.

Try **running** the code below!
:::{note}
Compare the output for the three method calls! Notice that the method call with the parameter of 0 doesn't have any output!
:::

```java
public class Example {
    public static void main(String[] args) {
        determinePosOrNeg(29);
        determinePosOrNeg(-763);
        determinePosOrNeg(0);
    }

    // this method reads in an int parameter and prints to the console
    // if the parameter is positive or negative
    public static void determinePosOrNeg(int number) {
        if (number < 0) {
            System.out.println(number + " is negative!");
        } else if (number > 0) {
            System.out.println(number + " is positive!");
        } 
    }
}
```

:::{tip}
In short: with an `if/else if` structure, you could enter **0 or 1 branch**.
:::

## 💭 Summary

```text
// using separate if statements can execute 0, 1, or many paths (independent tests)
if (test1) {
    statement(s) 1;
}
if (test2) {
    statement(s) 2;
}

// using an if/else structure will execute exactly 1 path (mutually exclusive)
if (test1) {
    statement(s) 1;
} else if (test2) {
    statement(s) 2;
} else {
    statement(s) 3;
}

// using an if/else if structure will execute 0 or 1 paths (mutually exclusive)
if (test1) {
    statement(s) 1;
} else if (test2) {
    statement(s) 2;
} else if (test3) {
    statement(s) 3;
}
```

## Main Points
While different types of conditionals have similarities in their meaning, different conditionals are used for different purposes.
- Use `if statements` if you only want to execute a certain block of statement(s) in **one particular case**.
    * ```java
        String date = "October-31";
        System.out.println("Hello!");
        if (date.equals("October-31")) {
            System.out.println("Happy Halloween!")
        }
        ```
- Use `if/else statements` if you are dealing with **one of two cases** (this OR that).
    * ```java
        String date = "October-31";
        System.out.println("Hello!");
        if (date.equals("October-31")) {
            System.out.println("Happy Halloween!")
        } else {
            System.out.println("Today is not Halloween...");
        }
      ```
- Use `if/else if statements` if you want to **evaluate specific cases**, not just one or the other.
    * ```java
        String date = "October-31";
        System.out.println("Hello!");
        if (date.equals("October-31")) {
            System.out.println("Happy Halloween!")
        } else if (date.equals("January-1")){
            System.out.println("Happy New Year!");
        } else if (date.equals("February-14")) {
            System.out.println("Happy Valentine's Day!");
        }
      ```