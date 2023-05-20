# For Loops for String Traversals

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/uM8T9Z8av3c" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

On the left hand side, you'll see there's a lesson titled For ***CSE 121: Loops for String Traversals [Video Walkthrough]***. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

## String Traversals

A lot of computations involve processing a String one character at a time. Often, they start at the beginning, select each character in turn, do something to it, and continue until the end. This pattern of processing is called a *String traversal*. To repeat some specific action on each character in the String, we can use a `for` loop along with the String methods we've seen above! Try running the code below to look at the output

``` Java
public class StringTraversals {
    public static void main(String[] args) {
        String message = "Hello";
        for (int i = 0; i < message.length(); i++) {
            char letter = message.charAt(i);
            System.out.println(letter);
        }
    }
}
```

There are a lot of parts to this code so let's break it down:

1. We start with creating the variable `message` with the value `"Hello"` on line 3

2. On line 4, we have the `for` loop header `for (int i = 0; i < message.length; i++)` 

    1. Notice that we start the counter variable at 0 and set the test to check that `i < message.length`. Remember that for Strings, we are dealing with **zero-based indexing**.

    2. To access all the characters in a String from beginning to end, we have to make sure we are looking through all legal indexes, starting with 0. Remember that `length()` will give us the number of characters in the String. So the test `i < message.length()` will successfully loop through all characters

3. On line 5, we look at a single character in the String (`char letter = message.charAt(i);`)

    1. Like mentioned above, because of the way we set up the for loop bounds, `i` will equal 0, 1, 2, 3, 4 as we iterate through the loop.

    2. By passing `i` as the parameter into `charAt()`, for each iteration of the for loop, we can access the character at whatever `i` is at the time. When `i` equals 0, we will get `'H'`, when `i` equals 1 we will get `'e'`, and so on.

4. On line 6, we just print the current letter to the console (`System.out.println(letter);`). 