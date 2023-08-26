# Value vs. Reference Semantics

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/qiZcTMz-k-k" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: Value vs. Reference Semantics Video Walkthrough**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

Remember this diagram from when we first talked about arrays? 

![The text "int[] arr = new int[4];" above a grey box with the label "name: arr (int[])" underneath it. There is an arrow coming out the grey box and pointing to a row of 4 blue boxes, with 0's in each one and numbers 0, 1, 2, 3 underneath the boxes in order from left to right.](images/array.png)

We drew it this way on purpose, making sure to include that arrow pointing to the `int` array.  This is important because it turns out array variables work a little bit differently than variables that hold **primitive values** (as a reminder, these are types that are built into Java like `int`, `double`, `boolean`, and `char`). 

## 📦 Value Semantics

It turns out that that that variables holding primitive values obey what we call **value semantics**.  Recall that we've talked about thinking of variables as *boxes*.  When we're dealing with variables using value semantics, the *actual values* are stored in these boxes.  This means that when we use primitive variables to *assign* to other variables, when we pass them as parameters, and when we return them from methods, we're really making copies of these values and using them.  

Walk through the code in your mind and predict the output you expect to see before you run it! 

``` Java
public class ValueSemantics {
    public static void main(String[] args) {
        int a = 3;
        int b = a;
        System.out.println("a: " + a);
        System.out.println("b: " + b);

        a = 99;
        System.out.println("after assignment to a:");
        System.out.println("a: " + a);
        System.out.println("b: " + b);
    }
}
```

Go ahead and run the code above!  Is the output what you expected to see?  Let's talk about it step by step:

1. `int a = 3;` - This line creates a new `int` variable named `a` and stores the value `3` in it.  

2. `int b = a;` - Here, we look at the value in `a`, make a copy of it, and store it in a new `int` variable named `b`.   

3. `a = 99;` - Next, we replace the value that was in the variable `a` with the value `99`.  

When you first learned about variables, you may have expected to see `b`'s value change as well when we assigned 99 to `a` because of the line `int b = a;`.  However, you learned that that line didn't tie `a` and `b` together -- all it did was take `a`'s value, make a copy of it, and put that copy into `b`. So changing the value in `a` later on has absolutely no effect on `b` because `b` is dealing with a totally separate *copy* of the value! 

You can see a visual representation of these steps by clicking "Expand" below (note that the slides below are purely a visual representation of the steps described above). 

:::{admonition} Expand
:class: dropdown

<div style="position: relative; width: 100%; height: 0; padding-top: 56.2500%;
 padding-bottom: 48px; box-shadow: 0 2px 8px 0 rgba(63,69,81,0.16); margin-top: 1.6em; margin-bottom: 0.9em; overflow: hidden;
 border-radius: 8px; will-change: transform;">
  <iframe loading="lazy" style="position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; padding: 0;margin: 0;"
    src="https:&#x2F;&#x2F;www.canva.com&#x2F;design&#x2F;DAFLwBD7IG8&#x2F;view?embed" allowfullscreen="allowfullscreen" allow="fullscreen">
  </iframe>
</div>
<a href="https:&#x2F;&#x2F;www.canva.com&#x2F;design&#x2F;DAFLwBD7IG8&#x2F;view?utm_content=DAFLwBD7IG8&amp;utm_campaign=designshare&amp;utm_medium=embeds&amp;utm_source=link" target="_blank" rel="noopener"></a>
:::


## ➡️ Reference Semantics
 
Now let's talk about **reference semantics**.  These semantics apply whenever we are dealing with a variable that has an object type.  Let's start by thinking about some of the objects we've seen so far this quarter: `Turtle`, `Scanner`, `File`, `PrintStream`, and arrays!  Each of these objects is rather big and complicated - much more so than any of the primitive types. Because of this, an object variable doesn't actually store the object itself, but instead stores what we call a **reference** to the object.  You can think of a reference as a "way to find" the object that exists somewhere else on your computer, like a set of directions to get to its address.  Let's look at a program similar to the one above that instead deals with array variables and thus, reference semantics.  

Walk through the code in your mind and predict the output you expect to see before you run it! 

``` Java
import java.util.*;

public class ReferenceSemantics {
    public static void main(String[] args) {
        int[] list1 = {4, 8, 15, 16, 23};
        int[] list2 = list1;
        System.out.println("list1: " + Arrays.toString(list1));
        System.out.println("list2: " + Arrays.toString(list2));

        list1[1] = 99;
        System.out.println("after assignment to list[1]:");
        System.out.println("list1: " + Arrays.toString(list1));
        System.out.println("list2: " + Arrays.toString(list2));
    }
}
```

Go ahead and run the code example above.  What is different between the output of this code snippet and the previous one?  Let's break down what's happening here...

1. `int[] list1 = {4, 8, 15, 16, 23};` - This line creates a new array *somewhere on your computer*, then creates an `int[]` variable named `list1` that contains a *reference* (indicated by the arrow) to the array.

2. `int[] list2 = list1;` - Here, we look at the reference in `list1`, make a copy of it, and store it a new `int[]` variable named `list2`.  This means that `list2` also contains a *reference* to the exact same array!  

3. `list[1] = 99;` - Next, we follow the reference in `list1` (which remember, is the same *reference* that is in `list2`) to assign `99` to the compartment at index 1 in the array.  

You can see a visual representation of these steps by clicking "Expand" below (note that the slides below are purely a visual representation of the steps described above). 

<details>
<summary>Expand</summary>

<div style="position: relative; width: 100%; height: 0; padding-top: 56.2500%;
 padding-bottom: 48px; box-shadow: 0 2px 8px 0 rgba(63,69,81,0.16); margin-top: 1.6em; margin-bottom: 0.9em; overflow: hidden;
 border-radius: 8px; will-change: transform;">
  <iframe loading="lazy" style="position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; padding: 0;margin: 0;"
    src="https:&#x2F;&#x2F;www.canva.com&#x2F;design&#x2F;DAFLxmqnRb0&#x2F;view?embed" allowfullscreen="allowfullscreen" allow="fullscreen">
  </iframe>
</div>
<a href="https:&#x2F;&#x2F;www.canva.com&#x2F;design&#x2F;DAFLxmqnRb0&#x2F;view?utm_content=DAFLxmqnRb0&amp;utm_campaign=designshare&amp;utm_medium=embeds&amp;utm_source=link" target="_blank" rel="noopener"></a>
</details>

When we print out the contents of `list1` and `list2` afterwards, the array that is printed out is exactly the same because both `list1` and `list2` contain references to the same array!  This means that, even if we modified the array by following `list1`'s reference, printing the array using `list2`'s reference will still reflect that change because they both just contain directions to the exact same location!  

:::{tip}

Notice that the steps for assigning a variable to another variable (as in `b = a;` and `list2 = list1;`) are really the same!  
- We look at the variable on the right
- Make a copy of its contents (regardless of whether it contains a value or a reference)
- Put that copy into the variable on the left
:::

## 🤯 Using Parameters and Returns

Now, how do value and reference semantics affect parameters and returns?  Let's start by reviewing how they work with value semantics.  

### 📘 Value Semantics with Parameters and Returns

Take a moment to read through the code below where the method `flipValue()` accepts a `boolean` parameter (remember that `boolean` is a primitive type, so this parameter uses value semantics).  

``` Java
public class ValueSemanticsInfoFlow {
    public static void main(String[] args) {
        boolean test = true;
        flipValue(test);
        System.out.println("value of test after call: " + test);
    }

    public static void flipValue(boolean b) {
        /*
        if (b == true) {
            b = false;
        } else {
            b = true;
        }
        */
        // this is equivalent to the code above, but is a lot cleaner!
        // Remember that the ! operator negates the boolean value 
        // (so F becomes T, and T becomes F)
        b = !b;
    }
}
```

Take a moment to think about what you expect the output to be before running it.  You'll notice that the `test` variable's value in main doesn't change when the parameter `b` in the `flipValue()` method is negated.  This is because, due to value semantics, the parameter that `flipValue()` accepts is a *copy* of the `test`'s value, and when that copy is negated, it doesn't have any effect on the `test` variable in `main`'s scope.  

Let's break down what's happening here step-by-step: 

1. `boolean test = true;` - This line creates a `boolean` variable in `main`'s scope that holds the value `true`. Remember, `boolean`s are primitive types, and so they obey value semantics! 

2. `flipValue(test);` - Here we begin to execute the `flipValue()` method call, passing in a copy of the value held in the `test` variable (which is `true`) to `flipValue()`'s parameter `b`. 

3. `b != b;` - Here, we look at the value in `b` (which is `true`), negate it with the `!` operator (making it `false`), and then store it back into the parameter `b` in `flipValue()`'s scope. 

4. `System.out.println(... + test);` - Here we return to `main`'s scope, and print out some text along with the value stored in `test`. This value hasn't been changed since its initialization, so we print out the value `true`. 

  - Recall that we made a copy of the value in `test` before passing it into `flipValue()`'s parameter, so when we modified `b` in `flipValue`'s scope, `test` remained **unchanged**. 

You can see a visual representation of these steps by clicking "Expand" below (note that the slides below are purely a visual representation of the steps described above). 

<details>
<summary>Expand</summary>

Notice how b and test are represented with completely separate boxes in the visual below.

<div style="position: relative; width: 100%; height: 0; padding-top: 56.2500%;
 padding-bottom: 48px; box-shadow: 0 2px 8px 0 rgba(63,69,81,0.16); margin-top: 1.6em; margin-bottom: 0.9em; overflow: hidden;
 border-radius: 8px; will-change: transform;">
  <iframe loading="lazy" style="position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; padding: 0;margin: 0;"
    src="https:&#x2F;&#x2F;www.canva.com&#x2F;design&#x2F;DAFLxmzOPKY&#x2F;view?embed" allowfullscreen="allowfullscreen" allow="fullscreen">
  </iframe>
</div>
<a href="https:&#x2F;&#x2F;www.canva.com&#x2F;design&#x2F;DAFLxmzOPKY&#x2F;view?utm_content=DAFLxmzOPKY&amp;utm_campaign=designshare&amp;utm_medium=embeds&amp;utm_source=link" target="_blank" rel="noopener"></a>
</details>

:::{tip}

You may have run into this issue when you first started working with returns! When dealing with value semantics, if we wanted `test` to hold the updated value from `flipValue()`, we'd need to **`return`** the value in the `flipValue()` method body and catch the return by storing it in `test` in main with `test = flipValue(test);`!
:::

### 📗 Reference Semantics with Parameters and Returns

Read through the following code which is similar to the code above, but instead deals with arrays (which obey the rules of reference semantics).  

``` Java
import java.util.*;

public class ReferenceSemanticsInfoFlow {
    public static void main(String[] args) {
        boolean[] tests = {true, true, false, true, false, false};
        flipValues(tests);
        System.out.println("value of test after call: " + Arrays.toString(tests));
    }

    public static void flipValues(boolean[] b) {
        for (int i = 0; i < b.length; i++) {
            b[i] = !b[i];
        }
    }
}
```

Take a moment to think about what you expect the output to be before running it. This time, you will see that the values in `tests` are affected by the call to `flipValues()` even though there is no `return`, due to the beauty of reference semantics!  `tests` holds a reference to the array, so it passes a copy of that reference (which points to the same array) to `flipValues()`'s parameter `b`.  Then, inside of `flipValues()`, `b` is used to update the values in that array and when we return to `main`, `tests` will see those updated values!  Notice how the separate `tests` and `b` boxes both have arrows pointing to the **same** array in your computer! 

Let's break down what's happening here step-by-step: 

1. `boolean[] tests = {true, true, false, true, false, false};` - This line creates an array of `boolean` values stored somewhere on your computer, and *stores a reference to the array* in the variable `tests`. 

2. `flipValues(tests);` - Here we call the method `flipValues()` and pass in a copy of the reference stored in `tests`, which refers to the same array of `boolean` values stored on your computer.  

3. `for (...) { b[i] = !b[i]; } `- Next, inside of the `flipValues()` method, we *traverse* the array whose reference is passed in as a parameter and negate each of its elements (turning `true` elements to `false`, and `false` elements to `true`). Remember, our program has only created one array and otherwise has just made copies of references to it! 

4. `System.out.println(... + Arrays.toString(tests));` - This line prints out some text along with the String representation of the array referenced by `tests` (using the `Arrays.toString` method call). Note that this array reflects the changes made in the `flipValues()` method, even though it did not return anything! 

You can see a visual representation of these steps by clicking "Expand" below (note that the slides below are purely a visual representation of the steps described above). 

<details>
<summary>Expand</summary>

<div style="position: relative; width: 100%; height: 0; padding-top: 56.2500%;
 padding-bottom: 48px; box-shadow: 0 2px 8px 0 rgba(63,69,81,0.16); margin-top: 1.6em; margin-bottom: 0.9em; overflow: hidden;
 border-radius: 8px; will-change: transform;">
  <iframe loading="lazy" style="position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; padding: 0;margin: 0;"
    src="https:&#x2F;&#x2F;www.canva.com&#x2F;design&#x2F;DAFLx0fCQok&#x2F;view?embed" allowfullscreen="allowfullscreen" allow="fullscreen">
  </iframe>
</div>
<a href="https:&#x2F;&#x2F;www.canva.com&#x2F;design&#x2F;DAFLx0fCQok&#x2F;view?utm_content=DAFLx0fCQok&amp;utm_campaign=designshare&amp;utm_medium=embeds&amp;utm_source=link" target="_blank" rel="noopener"></a>
</details>

:::{tip}

Click to 13:26 in the walkthrough video to see an explanation of each step of the `flipValue()` and `flipValues()` methods! 
:::