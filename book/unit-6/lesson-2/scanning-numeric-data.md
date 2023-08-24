# Scanning Numeric Data From Files

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/Dj9XkYwxI_M" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: Scanning Numeric Data From Files Video Walkthrough**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

## Processing Numeric Data Types

So far each item of data that we've dealt with has been scanned in as a `String`, even tokens like `3` or `4.57` become `"3"` and `"4.57"`. What if we want to process whole or decimal numbers from a `File` and store them as `int`s or `double`s respectively? Thankfully `Scanner`s have 2 methods that do exactly that. 

Given the following `Scanner` creation:

``` Java
Scanner fileScan = new Scanner(new File("inputFile.txt"));
```

We would call these methods as such:

- `fileScan.nextInt()`

  - Scans and returns the next token of input from this `Scanner` as an `int`.

- `fileScan.nextDouble()`

  - Scans and returns the next token of input from this `Scanner` as a `double`.

Using these two methods we can expand the capabilities of our file processing greatly.

## Scanning in Multiple Data Types From a Single File

One problem does arise when incorporating integers and doubles into our current understanding of file processing. Before we scan in each token or line, our `Scanner` `hasNext()` and `hasNextLine()` calls are only checking that a next token or line exists respectively, not that said token is an integer or double value. When using `Scanner` `nextInt()` or `nextDouble()`, if not given the correct data type, Java will throw this exception:

``` sh
Exception in thread "main" java.util.InputMismatchException
```

An input mismatch occurs when a `Scanner` is expecting one data type, for instance an `int`, but is given an incompatible type, for instance a `String`. There are some complicated programmatical ways to get around this hurdle when you need to scan in data of multiple types from a file, but the way that we will get around that in this class, and by far the easiest way, is to require the data you are reading in to be of a specific format. For instance, if you are processing an IMDB style dataset you could require a format like this:

``` Text
[Rank] [Rating] [Review Count] [Name (Year)]
1        9.2       1974878     The Shawshank Redemption    (1994)
2        9.2       1352427     The Godfather    (1972)
...
```

By requiring a format like this, you as the programmer know exactly where in the line the integer and double tokens will be, and so you can read the line in with this knowledge. Here is an example program that processes a list of movies given in the above format. Notice how it processes each line in its entirety in a single loop iteration, taking advantage of knowing where the integers and doubles will fall in the line. Run the following code:

``` Java
import java.util.*;

public class ReadFile {
    public static void main(String[] args) {
        String movieList = "1	9.2	1974878	The Shawshank Redemption	(1994)\n" +
                           "2	9.2	1352427	The Godfather	(1972)\n" +
                           "3	9	936012	The Godfather: Part II	(1974)\n" + 
                           "4	9	1945677	The Dark Knight	(2008)\n" +
                           "5	8.9	551047	12 Angry Men	(1957)\n" +
                           "6	8.9	1018923	Schindler's List	(1993)\n" +
                           "7	8.9	1408534	The Lord of the Rings: The Return of the King	(2003)\n" +
                           "8	8.9	1543514	Pulp Fiction	(1994)\n" +
                           "9	8.8	586022	The Good, the Bad and the Ugly	(1966)\n" +
                           "10	8.8	1582385	Fight Club	(1999)";
        Scanner movieScan = new Scanner(movieList); // Create Scanner

        while (movieScan.hasNextLine()) {
            String line = movieScan.nextLine();
            Scanner lineScan = new Scanner(line);

            int rank = lineScan.nextInt();
            double rating = lineScan.nextDouble();
            int numberOfRatings = lineScan.nextInt();
            String name = lineScan.nextLine();

            System.out.println("The number " + rank + " ranked movie on our IMDB list is \"" + name.strip() + "\"");
            System.out.println("With a rating of " + rating  + " from " + numberOfRatings + " people.");
            System.out.println();
        }
    }
}
```

Due to technological limitations we had to process our IMDB list from a string, but since we are still using a `Scanner`, the process is the same (except for the creation of the `Scanner` of course).

It's worth noting that restricting the format of the input File in order to easily process multiple data types is both reasonable and common practice in the Computer Science community. Most data sets that you find online will have very specific and restricted formatting to make processing them more convenient. This is one case where we don't try and generalize our programs to the fullest extent we could, as the restricted option is much easier.

You don't have to restrict the format of potential input though, and Scanners do contain methods that allow us to check the exact types of each token as we read it in. Given the following Scanner creation:

``` Java
Scanner fileScan = new Scanner(new File("inputFile.txt"));
```

We could call either of these methods to check if the next token in the Scanner is of a numeric data type:

- `fileScan.hasNextInt()`

  - Returns `true` if the `Scanner`'s next token of input is an `int`, returns `false` otherwise.

- `fileScan.hasNextDouble()`

  - Returns `true` if the `Scanner`'s next token of input is a `double`, returns `false` otherwise.

You can create a complex conditional structure using these methods to check the type of each token before you read it in, but the method of requiring the `File` to be formatted in a specific way explained above is much easier. These methods can be useful in a situation where you are exclusively processing `int`s or `double`s however, and the next slide contains a code challenge where this is the case. You can go to the next slide and work on using the techniques we have developed here to process numeric data types when you are ready. 

Make sure to read the explanation on the left of the slide through fully before starting the code challenge.