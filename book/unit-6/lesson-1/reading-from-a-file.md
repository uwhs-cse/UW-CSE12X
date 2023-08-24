# Reading From a File Using Scanners

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/9Xf784OJWAo" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: Reading From a File & Scanner Methods and Processing Tokens Video Walkthrough**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

So far in this course, we have been limited as to how we can take input from the user into our program; we recently learned how to take user input from the console using `Scanner`s. What if we want to take input from a more standard, consistent source, such as a file? 

By using files, we can store and use data that outlives the run time of our program. It also allows us to manipulate data that isn't given to us by the user through the console at runtime, giving our programs much more flexibility in the kinds of tasks that they can do. As it turns out we can also use `Scanner`s and all their associated methods to read data from a file! 

## `File`s and File Scanners in Java

Let's first take a look back at how we made `Scanner`s to take input from the console:

``` Java
Scanner console = new Scanner(System.in);
```

We pass `System.in` as a parameter to our `new Scanner()` call in order to let the `Scanner` know it's reading from the console. So it would make sense if we could pass our file into the `Scanner` to let it know it's reading from said file. It turns out this is exactly what you have to do! We can't just pass the name of the file into our `Scanner` though, as this doesn't explicitly tell the `Scanner` we are processing a file (it also turns out you can make `Scanner`s over a `String`, which we will cover later in this lesson). In order to make the distinction we need to make a new variable of the datatype `File`. The syntax for making a `File` is similar to that of the `Scanner`, but with the word Scanner replaced with `File`, and the `System.in` argument replaced with the name of our file, in this case the file we will be reading from is called `"newFile.txt"`.

``` Java
File newFile = new File("newFile.txt");
```

It turns out we have to include a different import statement to access the code for the `File` object! When using `File`s we have to include the `import java.io.*;` statement as the `File` object is contained in Java's IO package, which stands for Input Output.

:::{admonition} Caution
:class: caution

We have to remember to import Java's util package when using `Scanner`s to access their code using the `import java.util.*;` statement. 
:::

Notice that we pass the filename as a `String` into the `new File()` call. Now that we have a `File`, we can make the `Scanner` to process input from the file by passing the `File` as the argument to the `new Scanner()` call:

``` Java
File newFile = new File("newFile.txt");
Scanner fileScan = new Scanner(newFile);
```

:::{admonition} Caution
:class: caution

It's very likely that a program will contain more than one type of `Scanner`. Keeping track of which `Scanner` does what can be difficult if your naming scheme is not consistent and descriptive. Try and use the same names for each type of `Scanner` across all programs that you write to minimize the confusion, and make sure their names clearly show the type of input data that the `Scanner` is processing. `console`, and `fileScan` are both good names for `Scanner`s.
:::

Now that we know how to setup our `File` and `Scanner` objects, let's take a look at putting it all together in code on the next page.