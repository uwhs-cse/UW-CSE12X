# Scanner Methods and Processing Tokens

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/9Xf784OJWAo" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: Reading From a File & Scanner Methods and Processing Tokens Video Walkthrough**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

## Dealing with `FileNotFoundException`s

There's one issue we've run into that we haven't discussed yet. What if the file we are trying to read from doesn't exist? For now, we can just assume that we will always give our `Scanner` a file that does exist, but Java doesn't necessarily know that. If we try to make a `Scanner` over a file given our current knowledge of Java, the compiler will throw an error on our `Scanner` creation for an "unreported `FileNotFoundException`". 

Notice that it says "unreported". Importantly, this means that if we tell, or "report", to Java that we are aware our method can throw this exception and we want the code to execute regardless, then the compiler will not throw this error. In order to do this we need to add two words to the end of our method header: `throws FileNotFoundException`. With the addition of these 2 words, we have reported the possible exception to Java, and stated that we accept the possibility of it being thrown. In practice our method headers now look something like this: 

``` Java
public static void fileReadingMethod() throws FileNotFoundException {
```

:::{admonition} Note
:class: note

Note that this is only required in the method headers of methods that create a `Scanner` over a `File`. The creation of a `File` or a `Scanner` alone does not require the inclusion of the `throws FileNotFoundException` in the method header in order to successfully run.
:::

## Scanner Methods

Now that we have our `File` `Scanner` set up, let's take a look at what methods we can use with it. Given a `Scanner` with the following creation:

``` Java
Scanner fileScan = new Scanner(new File("inputFile.txt"));
```

We can use its methods as such:

- `fileScan.hasNext() `

  - Returns `true` if the `Scanner` contains another token of input, returns `false` otherwise.

- `fileScan.hasNextLine()`

  - Returns `true` if the `Scanner` contains another line of input, returns `false` otherwise.

- `fileScan.next()`

  - Scans and returns the next token of input from this `Scanner`.

- `fileScan.nextLine() `

  - Scans and returns the next line of input from this `Scanner`.

- `fileScan.nextInt() `

  - Scans and returns the next token of input from this `Scanner` as an `int`.

- `fileScan.nextDouble() `

  - Scans and returns the next token of input from this `Scanner` as a `double`.

- `fileScan.hasNextInt()`

  - Returns `true` if the `Scanner`'s next token of input is an `int`, returns `false` otherwise.

- `fileScan.hasNextDouble()`

  - Returns `true` if the `Scanner`'s next token of input is a `double`, returns `false` otherwise.

Now, `Scanner`s do have more methods associated with them, you can google the Java `Scanner` documentation to see more, but these are the methods that will be relevant for this course and the 12x sequence as a whole. 

## What is a Token?

We tossed the word "token" around a lot in those method definitions above, but what exactly is that? A **token** is the smallest component of something being read that has meaning to the thing reading it. For our purposes however, we can consider a "token" to be a chunk of input. A token as defined by a Java `Scanner` reading from a file, happens to be a word or number separated by whitespace. **Whitespace** is defined as any space which separate tokens (e.g. spaces, tabs, newlines), and so each token of input in Java should have some form of space separating it from the rest. 

Note that you do not need a space before the first token in a line or after the last, as the beginning and end of each line is a *de-facto* whitespace character, the latter via the newline. That means if a `Scanner` was processing token by token a file that contained the text `"To be or not to be\nThat is the question"`, each individual word would be read in as its own token, e.g. `"To"` `"be"` `"or"` `"not"` `"to"` `"be"` `"That"` `"is"` `"the"` `"question"`.

## Processing a File Token by Token

The last problem we have to solve is how do we know how many times to read in a token given an arbitrary file? There's no easy way to tell how many tokens are in a file, so we can't use a `for` loop to process the file token by token like we might in order to process a `String` character by character. That leaves us with the `while` loop as an iterative structure to process tokens, and it turns out that the `Scanner`'s `hasNext()` and `hasNextLine()` methods work perfectly in conjunction with a `while` loop. On each iteration of the `while` loop, we can ask the `Scanner` if there is something to read in with either the `hasNext()` or `hasNextLine()` methods, and if there is we can process it accordingly!

We now know all that we need to set up a basic `Scanner` over an input `File`! On the next slide we have a code challenge for you to test these new skills. Make sure to read the description on the left side of the screen for information on what to do before starting the challenge.