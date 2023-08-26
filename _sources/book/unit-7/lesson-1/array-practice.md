# Array Practice

These questions are to assess your understanding of arrays.

**Question 1**

True or False: If you create an array of length 5, you can change your mind later and add a sixth element. 

:::{admonition} See Answer
:class: dropdown
False. Once you specify the length of an array, it cannot change! An array created with length 5 will **always** have exactly 5 elements inside of it. 
:::

<hr>

**Question 2**

True or False: The code below will execute without error: 
``` Java
String[] stuff = {"hello", "pickle juice", "nineteen", "balloon"};
stuff[2] = 19;
```

:::{admonition} See Answer
:class: dropdown
False. Arrays can only hold values of a specific type! The `stuff` array is declared to be of type `String[]` so its elements can only be of type `String` (and 19 is not!).  
:::

<hr>

**Question 3**

True or False: The code below will execute without error: 
``` Java
String[] otherStuff = {"19.8", "puzzles", "b3st fr13nD"};
```

:::{admonition} See Answer
:class: dropdown
True. Even though 19.8 is a `double`, because we've surrounded it in quotes its type is `String`! So all of the elements of the `otherStuff` array have the appropriate type. 
:::

<hr>

**Question 4**

True or False: The code below will execute without error: 
``` Java
int[] nums = {4, -88, 1095, 7.2, 365};
```

:::{admonition} See Answer
:class: dropdown
False. Because `nums` is declared to be of type `int[]`, it can only hold values of type `int` (and 7.2 is not!).  
:::

<hr>

**Question 5**

True or False: The code below will execute without error: 
``` Java
double[] otherNums = {-8.77, 4.96, 100, 98.6};
```

:::{admonition} See Answer
:class: dropdown
True. Even though 100 can be interpreted as an `int` and `otherNums` can only hold `double`, Java will automatically convert it to a `double` before storing it into the `otherNums` array!   
:::

<hr>

**Question 6**

True or False: The code below will execute without error: 
``` Java
boolean[] tests = new boolean[3];
tests[0] = true;
```

:::{admonition} See Answer
:class: dropdown
True. The `tests` array has length 3, so its valid indices are 0, 1, and 2!  
:::

<hr>

**Question 7**

True or False: The code below will execute without error: 
``` Java
String[] words = new String[5];
words[5] = "corgi";
```

:::{admonition} See Answer
:class: dropdown
False. The `words` array has length 5, so its valid indices are 0, 1,2, 3, and 4, but not 5!   
:::

<hr>

**Question 8**

Write the output that would be produced by the following code: 
``` Java
String[] colors = {"red", "orange", "yellow", "green", "blue", "purple"};
for (int i = 0; i < colors.length; i++) {
    String nextColor = colors[i];
    System.out.print(nextColor.length() + " ");
}
```

:::{admonition} See Answer
:class: dropdown
The output is
``` text
3 6 6 5 4 6 
``` 
This is a standard array traversal where we are examining each element of the `colors` array, and for each element we print out the length of the `String` (using the `String`'s `length()` method). 
:::
