# Array Traversal Pattern

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/hzCYTCL5sE4" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: Array Basics & Traversal Pattern Video Walkthrough**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

Now that we've talked about some of the mechanics of arrays, let's dig into one of the most common code patterns you will use when working with arrays: the **array traversal**.  Many computations involving arrays require the programmer to examine each element of the array individually, which is exactly what a traversal is made for!  Here is an example of what it looks like: 

``` Java
public class ArrayTraversals {
    public static void main(String[] args) {
        String[] groceries = {"bananas", "frozen blueberries", "nilla wafers", "instant ramen"};
        for (int i = 0; i < groceries.length; i++) {
            String item = groceries[i];
            System.out.println(item);
        }
    }
}
```

To break this down, the `for` loop variable `i` takes on all of the *valid indices* of `groceries`: 0, 1, 2, ..., all the way up to `groceries.length - 1` which is the last valid index of the array.  In the body of the `for` loop, for each value of `i`, we pull out the element at that index and then *do something* with it (in this case, we are just printing it out to the console).  

![Table with left column header "i" and right column header "groceries[i]" with rows 0, "bananas"; 1, "frozen blueberries"; 2, "nilla wafers"; 3, "instant ramen". To the right there is labeled output "bananas frozen blueberries nilla wafers instant ramen" with each item on their own line, and underneath is a row of boxes with "bananas", "frozen "blueberries", "nilla wafers", and "instant ramen" inside with the labels 0, 1, 2, and 3 underneath.](images/groceries.png)

:::{tip} 

You might notice that an array traversal looks very similar to the `String` traversal that you saw earlier this quarter! This is because `String`s and arrays share many of the same properties (and secretly, `String`s are actually arrays under the covers!)
:::

In general, you can replace the body of the for loop with whatever operation you need to perform on each element of the array! Here are a few more examples: 

``` Java
import java.util.*;

public class ArrayTraversals {
    public static void main(String[] args) {
        String[] groceries = {"bananas", "frozen blueberries", "nilla wafers", "instant ramen"};
        for (int i = 0; i < groceries.length; i++) {
            String item = groceries[i];
            System.out.println(item);
        }

        double[] nums = {14.8, 99.8, -4.0, 93.41};
        double sum = 0;
        for (int i = 0; i < nums.length; i++) {
            sum += nums[i];
        }
        System.out.println("nums array: " + Arrays.toString(nums));
        System.out.println("total sum of elements: " + sum);

        int[] importantNumbers = {4, 8, 15, 16, 23, 42};
        for (int i = 0; i < importantNumbers.length; i++) {
            int nextNum = importantNumbers[i];
            if (nextNum % 2 == 0) {
                System.out.println(nextNum + " is even!");
            } else {
                System.out.println(nextNum + " is odd!");
            }
        }
    }
}
```

:::{note}

While a *typical* array traversal uses a `for` loop variable that starts at `i = 0` and has a test that looks like `i < array.length`, it doesn't have to! You may see some array traversals where the loop variable starts at `1` and/or may have a test like `i < array.length - 1`. There are lots of variations of the array traversal pattern, so think carefully about how the bounds of your loops affect the overall algorithm! 
:::

Revisit the "groceries" example above.  What if we wanted to print out the elements in the `groceries` array in reversed order?  Take a moment to think about how you would write the `for` loop for the traversal differently before clicking "Expand" below! 

:::{admonition} Expand
:class: dropdown

``` Java
public class ArrayTraversals {
    public static void main(String[] args) {
        String[] groceries = {"bananas", "frozen blueberries", "nilla wafers", "instant ramen"};
        for (int i = groceries.length - 1; i >= 0; i--) {
            String item = groceries[i];
            System.out.println(item);
        }
    }
}
```
:::