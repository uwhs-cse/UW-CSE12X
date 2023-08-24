# Printing to a File

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/uHjLYOhnzn4" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: Printing to a File Video Walkthrough**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

## Printing With `PrintStream`

So far our view of file processing has been very one-sided in that we've only been taking data from files, and not putting any data into them. Java has a construct though that allows us to print to a `File` using the same syntax that we use to print to the console, with a construction similar to that of a `Scanner`. Given a file `"output.txt"` that we want to print to, we would construct a `PrintStream` like this:

:::{admonition} Note
:class: note

Just like when creating a `Scanner` over a `File`, we do need to include a `throws FileNotFoundException` on the headers of methods that create a `PrintStream`.
:::

``` Java
PrintStream output = new PrintStream(new File("output.txt"));
```

Notice that, similarly to with `Scanner`s, you pass a Java `File` construct representing the file you wish to print to into the `new PrintStream()` call. `PrintStream`s can actually be made by just passing in the name of the `File` as a `String`, but creating the `File` construct is the preferred method of `PrintStream` creation in this class. 

## `PrintStream` methods

The `PrintStream` construct conveniently implements the `print` and `println` methods for us to use. Given the `PrintStream` created above, we would use the methods as such:

- `output.print()`

  - Prints the given value

- `output.println()` 

  - Prints the given value and then terminates the line

As an example of these methods in use, here is a basic program that prints increasing digits from 1 to 10 on new lines to a file named `"output.txt"`:

``` Java
import java.io.*;

public class ExampleProgram {
    public static void main(String[] args) {
        PrintStream output = new PrintStream(new File("output.txt"));
        
        for (int i = 1; i <= 10; i++) {
            output.println(i);
        }
    }
}
```

:::{admonition} Caution
:class: caution

Notice the `import` statement at the top of the program. The `PrintStream` and `File` constructs are both from the `java.io` library, and so we must import said library before we can use constructs from it.
:::

The program above would produce the following output in a text file named `output.txt` in the same directory as the program is located:

``` text
1
2
3
4
5
6
7
8
9
10
```

We now know all that we need to set up a `PrintStream` and print output to a `File`! On the next slide we have a code challenge for you to test these new skills. Make sure to read the description on the left side of the screen for information on what to do before starting the challenge.