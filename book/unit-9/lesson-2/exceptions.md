# Exceptions


<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/Gh_9G2QwpCw" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 122 - PCM - Exceptions**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

As we've seen before, a very common problem when programming is considering what inputs are valid and which are invalid. Often we ask you to make assumptions about what inputs you'll receive, but assumptions can  lead to fragile code that might break if the assumption end up being true. 

In general, it is much better to write defensive code that can ensure your assumptions are met without causing some accidental error.

## 💻  Initial Program

Consider the following method that finds the maximal element of a `Queue`.

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Queue<Integer> numbers1 = new LinkedList<>();
        numbers1.add(1);
        numbers1.add(2);
        numbers1.add(3);

        System.out.println("Max of numbers1 = " + max(numbers1));

        Queue<Integer> numbers2 = new LinkedList<>();
        System.out.println("Max of numbers2 = " + max(numbers2));
    }

    // Returns the largest value in the given queue
    // Assumes the queuee is not empty
    public static int max(Queue<Integer> numbers) {
        int currentMax = numbers.remove();
        numbers.add(currentMax); // Put it back to start cycling

        for (int i = 1; i < numbers.size(); i++) {
            int number = numbers.remove();
            if (number > currentMax) {
                currentMax = number;
            }
            numbers.add(number);
        }
        return currentMax;
    }
}
```

In the second call to `max`, we end up raising an error because we try to remove from an empty queue. 

In this case, we are lucky because nothing "that bad" happened; our program just crashed. But we maybe just got lucky here, what if the assumption failing accidentally caused our code to delete everything in some database or have a user lose all of their work? 

We could say "well too bad, you broke the assumption so anything goes", but that doesn't feel very user friendly. 

Additionally, the error presented is not extremely useful. It requires understanding the internals of the method to figure out why something went wrong. It would be better if we could be more direct and tell the user exactly why this case of violating our assumption should be an error.

## ⚾ Throwing Exceptions

Instead, it is often a good idea to *defensively* protect your code from running on bad inputs. We have seen something like this before with protecting our code with `if` statements. But we can go further by making *our own error messages* that can better convey what went wrong and why. To do this in Java, we **throw an exception** where we can specify the error in more detail. 

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Queue<Integer> numbers1 = new LinkedList<>();
        numbers1.add(1);
        numbers1.add(2);
        numbers1.add(3);

        System.out.println("Max of numbers1 = " + max(numbers1));

        Queue<Integer> numbers2 = new LinkedList<>();
        System.out.println("Max of numbers2 = " + max(numbers2));
    }

    // Returns the largest value in the given queue
    // Assumes the queuee is not empty
    public static int max(Queue<Integer> numbers) {
        if (numbers.isEmpty()) {
            throw new IllegalArgumentException("numbers must be non-empty");
        }
        
        int currentMax = numbers.remove();
        numbers.add(currentMax); // Put it back to start cycling

        for (int i = 1; i < numbers.size(); i++) {
            int number = numbers.remove();
            if (number > currentMax) {
                currentMax = number;
            }
            numbers.add(number);
        }
        return currentMax;
    }
}
```

In the program above, the only "new" thing is line 20 that actually throws the exception. We surround it in an if statement to check when our assumptions have been violated, and in that case, use a special piece of `throws` syntax to cause a certain error to occur. The specific type of error is an `IllegalArgumentException` and you can pass it a message to give a more detailed description of what went wrong. Try running the program to see how much more descriptive the error is.

There are lots of types of exceptions to convey different types of errors. In our assignments, we will always tell you exactly which exception to throw and in what conditions. But to show you the scope of some of the most common exceptions:

* `IllegalArgumentException` - When a client passes in an invalid parameter

* `IllegalStateException` - When the state of the program should not be possible. For example if you had a program that a user logged into it might help to throw this exception if they are ever suddenly logged out.

* `FileNotFoundException` - If you try to read a file that is not there

* `IndexOutOfBoundsException` - If an invalid index is accessed

* ...

## 🤓 Exception Formatting

When writing code that throws exceptions, there are some pretty standard conventions used that most programmers adhere to. The fall under two general principles

### 1️⃣ Exceptions Should Happen As Early As Possible

Whenever possible, an exception check should happen before any serious work is done. You should always try to bias the placement of your exceptions to be as early in the method as possible. 

Note that sometimes it's necessary to do some work before an exception, such as if you need to prompt the user for input before you can determine if an exception is appropriate. So it doesn't necessarily need to be the first thing in a method, but it should happen as soon as you know a violation of the method's assumptions.

### 2️⃣ Exceptions Should Be Separate from "Regular" Code

Exceptions are supposed to be, well, exceptional. They are about the uncommon cases that we want to raise an error in. Generally you want your code to best reflect the logical structure of the problem. 

Generally, we want to avoid linking the conditions for exceptions with the rest of our code. That means, in most cases, you should never really connect the `if` condition of some exception with the `else` being some regular code.

```java
public static void badExample(String argument) {
    if (argument.equals("bad value")) {
        throw new IllegalArgumentException("please don't pass that value");
    } else {
        // Do any of your regular code
        System.out.println(argument);
    }
}

public static void goodExample(String argument) {
    if (argument.equals("bad value")) {
        throw new IllegalArgumentException("please don't pass that value");
    }

    // Do any of your regular code
    System.out.println(argument);
}
```

While it sounds pretty minor, it helps a lot in terms of keeping your "real" code simple and unencumbered by having extra conditionals around it.

## 🧠 Main Points

* *Defensive coding* helps us protect our code from unexpected or invalid inputs to prevent errors.

* We use *exception handling* to smoothly deal with errors. Rather than letting our program crash, we will throw exceptions with specific feedback so users get meaningful feedback on the cause of the error.

* In Java, we throw exceptions by using the `throw` keyword. 

    * We can specify a type of exception e.g. `IndexOutOfBoundsException` and a descriptive error message e.g. "Bad index when attempting to...". 

* Some sample built-in exceptions that Java has includes:

    * `IllegalArgumentException`: invalid parameters

    * `IllegalStateException`: invalid state of program 

    * `FileNotFoundException`: couldn't find file

    * `IndexOutOfBoundsException`: invalid index access

* We want to raise exceptions as early as possible (right when a violation occurs) and have exception logic be separate from the logic of the rest of the program so code will be simpler and more readable!