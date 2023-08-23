# Printlns

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/2v3YzZGF4TA" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled For ***CSE 121: Printlns Video Walkthrough***. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

Imagine you're writing an essay in a text editor, like Google Docs, but you don't have access to the arrow keys or the mouse. You can type any text, but you can't move around the document or freely type anywhere you want! 

This idea of typing without arrow keys or a mouse is how Java behaves when we *print* (i.e. display) text to the screen. 

There are <ins>two</ins> such **methods** (i.e. commands) that we use to display content to the screen. Namely, they are:
- `System.out.print`
- `System.out.println`

:::{admonition} Note
:class: note
The only thing that's different between the two methods is the extra **`ln`** in `System.out.print`**`ln`**
:::

## `System.out.println` ✏️

The `System.out.println` method "*prints*" some text to the screen and <ins>moves to a new line</ins>. (This second part is very important!) We refer to this "move to a new line" as a new-line character. 

:::{tip} Tip
It might help to remember this by reading `println` as "print line"
:::

What does this mean and how do we use this method? Suppose we wanted to display the text "Welcome to CSE 121!" on the screen, we would do so with the following statement:

``` java 
System.out.println("Welcome to CSE 121!"); 
```


Let's see this in the context of a full Java program. Press the "Run" button on the code block below to run the program and see the output.

``` java
public class Welcome {
    public static void main(String[] args) {
        System.out.println("Welcome to CSE 121!");
    }
}
```

:::{warning} Watch out!
Don't forget the double quotes inside the `println` statement! We <ins>**always**</ins> need quotes when we're printing out text, otherwise your program won't run 😢 More on why the quotes are necessary soon!
:::

The text inside the quotes can be anything! Try changing the text inside the `System.out.println` method above to say "Hello, world!" instead of "Welcome to CSE 121!". The expand snippet below has a possible solution for this!

``` java
public class Welcome {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}
```

We can stack multiple `System.out.println` methods, to display multiple sentences to the console. Try running the following program and examine its output.

``` java
public class Welcome {
    public static void main(String[] args) {
        System.out.println("Welcome to CSE 121!");
        System.out.println("Hope you have a great time");
    }
}
```

Using `println` statements makes the output prints on two separate lines! Let's break this down:

Remember that

- The `System.out.println` method "*prints*" some text to the screen and moves to a new line
- So, if we look at the first time we're using the `System.out.println` method (on line 3), we display the text "Welcome to CSE 121!" and **move our cursor to the next line**
- We then display the text "Hope you have a great time" starting on the next line!

Looking at this example, we can see that the `println` method acts like typing text to the screen and then hitting the enter (or return) key on your keyboard!

## `System.out.print`

The `System.out.print` method also "*prints*" some text to the screen. This feels just like the `System.out.println` method... 🤔 What's different? Sometimes, you want to have finer-grained control of how your printing is formatted. `print` operates just like `println` but does <ins>**not**</ins> include a new-line at the end. Let's see this in practice:

``` java
public class Welcome {
    public static void main(String[] args) {
        System.out.print("Welcome to CSE 121!");
    }
}
```

Try running the program above. Now, scroll back up to where we printed the same message using the `println` statement. Why aren't there any differences in the output between the `print` and the `println` method? Shouldn't the `println` command move to the next line... Well it did! <ins>We just can't see it</ins> on our screen, because we haven't printed anything new on that next line 😦 

Maybe we'll notice the difference if we display two sentences on the screen using the `print` command. Let's use the same sentences that we tried previously with our `println` command. Run the code block below to see what happens. 

``` java
public class Welcome {
    public static void main(String[] args) {
        System.out.print("Welcome to CSE 121!");
        System.out.print("Hope you have a great time");
    }
}
```

So what's happening here? Why do these sentences display on the same line? Let's break this down: 

- Remember that > The `System.out.print` method "prints" some text to the screen, but does <ins>**not**</ins> include a new-line at the end
- So, if we look at the first time we're using the `System.out.print` method (on line 3), we *print* the text "Welcome to CSE 121!" and stay on the same line
- We then *print* the text "Hope you have a great time" starting at the same place we ended our last sentence, and again stay on the same line!

This method behaves exactly like how text editors do! You type a sentence, and you don't automatically to a new line; you start typing the next sentence exactly where you left off with your previous sentence. 

Notice that there are no spaces after each thing printed, since `print` doesn’t include any trailing characters. If you would want the program to have spaces between calls of `print`, you must <ins>include the spaces yourself</ins> in the text you are printing.

## Mixing `print` and `println` ✏️ 

It is completely possible to mix your use of both `print` and `println` to format your output how you want! This will make more sense when later in the course, but for example you could write a program like the following. <ins>Note that each call to `print` prints the text exactly while each call to `println` prints the text and then moves to the next line.</ins>

``` java
public class Printing {
    public static void main(String[] args) {
        System.out.print("A");
        System.out.print("A");
        System.out.println("A");
        System.out.print("B");
        System.out.println("B");
        System.out.println("C");
    }
}
```

## Main Points:
`System.out.println` is a command that prints out the specified text, and then moves to a new line. 
`System.out.print` is a command that prints out the specified text without moving to a new line. 