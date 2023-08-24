# String Scanners and Line Based Processing

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/yBnYapHLuvY" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: Reading From a File & Scanner Methods and Processing Tokens Video Walkthrough**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

In the example we gave on the previous slide, despite our file containing multiple separate lines of input, our output was all on a single line. One thing to pay attention to when scanning a file token by token is that we cannot easily tell when we have crossed onto a new line, making it hard to tell when to print on a new line and maintain the structure of our input file. 

One way we can get around this is by using the `nextLine()` `Scanner` method to scan in an entire line from the file at a time. Given we then have the whole line as a variable, we can process it in its entirety and print it on its own line. We still might want to process this line token by token though, and so this is when making a `Scanner` over a `String`, as mentioned earlier in the lesson, becomes useful. 

## String Scanners

When creating a `Scanner`, if you pass a `String` as the argument into the `new Scanner()` call, you actually create a `Scanner` over that `String`, allowing you to process the tokens within that `String` as if they were in a `File` or coming from the console. For example, you might create a `Scanner` over a `String` like this:

``` Java
String lineOfText = "Four score and seven years ago";
Scanner lineScan = new Scanner(lineOfText);
```

Just like with the previous `Scanner`s we've looked at in this course, we can use all of the usual methods to process the `String`. Now that we have a third type of `Scanner` that could exist in the same program as the others, our variable naming schema is even more important. We suggest giving this `Scanner` a name such as `"lineScan"`, as we are processing a line of text, or `"stringScan"` etc... .  In general, the more obvious the name, the better. 

## Maintaining Line Structure While Reading From a File

:::{admonition} Note
:class: note

For the following section, `fileScan` refers to a `Scanner` created over a `File` in the following manner:

``` Java
Scanner fileScan = new Scanner(new File("inputFile.txt"));
```

And `lineScan` refers to a `Scanner` created over a `String` in the following manner:
``` Java
String line = fileScan.nextLine();
Scanner lineScan = new Scanner(line);
```
:::

By using `fileScan.nextLine()` and creating a `Scanner` over the resulting `String`, we can now process `File`s line by line, as opposed to token by token, and maintain line structure when printing from a `File`. In practice, our program will look quite different now. We will still need a `while` loop to check for existing lines using `fileScan.hasNextLine()`, and a call to `fileScan.nextLine()` to read said line in if it exists, but inside that loop we will need a new `while` loop to process the line we've just scanned in token by token. We can use our previous knowledge of token based processing to do this though, and the same principals of using `lineScan.hasNext()` and `lineScan.next()` to process the line token by token apply.

It is worth noting that you do not need to process a `File` in this mixed line and token based approach. We now have the tools to approach reading from a `File` in 3 general ways:

1. Token by Token. We can use the `.hasNext()` and `.next()` methods from a `Scanner` to ignore line breaks and pull a File apart token by token.

2. Line by Line. We can use the `.hasNextLine()` and `.nextLine()` methods from a `Scanner` to ignore the individual tokens and simply process each line as a whole.

3. Hybrid. As explained in this slide, by combining the methods and techniques from both previous approaches to `File` handling we can process a `File` token by token while still maintaining the contents and structure of each line from our `File`.

We now know all that we need to read a `File` token by token while still maintaining the structure of each line! On the next slide we have a code challenge for you to test these new skills. Make sure to read the description on the left side of the screen for information on what to do before starting the challenge.