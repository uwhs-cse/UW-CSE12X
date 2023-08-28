# Parameters

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/-bGkdUEkTZU?si=YOM2lEGTvLUyxFfz" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: Parameters Video Walkthrough**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

## 🔍 What are Parameters?

**Parameters** are values of different data types such as `String`, `int`, `double`, etc. that we "pass into methods" to utilize these values within the methods. This allow methods to work with data or information from <ins>outside</ins> the method, which provides greater power and flexibility in what methods can do!

## 🧠 Why Parameters? 

Parameters enable us to further organize our logic and reduce redundancies by utilizing information from outside of the method. Observe the following comparison.  

```java
public class Before {
    //// Version 1 ////

    public static void main(String[] args) {
        lineOf5();
        lineOf10(); 
    }

    public static void lineOf5() {
        for (int i = 1; i <= 5; i++) {
            System.out.print("*");
        }
        System.out.println();
    }
    
    public static void lineOf10() {
        for (int i = 1; i <= 10; i++) {
            System.out.print("*");
        }
        System.out.println();
    }

}
```

In the program above, we can see that `lineOf5()` and `lineOf10()` have similar code, notably the only difference is the code being used to print either 5 or 10 stars. Now we already have external knowledge about the number of stars. We can use to our advantage to reduce redundancies in our code through the use of parameters as show in version 2. 

```java
public class After {
    //// Version 2 ////
    
    public static void main(String[] args) {
        line(5); // prints 5 stars using the parameter
        line(10); // prints 10 stars using the parameter
    }

    public static void line(int numStars) {
        for (int i = 1; i <= numStars; i++) {
            System.out.print("*");
        }
        System.out.println();
    }

}
```

:::{note}
Note that even though the variable names `value` and `numStars` are different, we are relaying the same information.
:::

## 📗 Parameters Syntax

```java
public static void methodOne() {
    // body
}

public static void methodTwo(int value) {
    // body
}

public static void methodThree(int value, String name) {
    // body
}
```

Here are a couple of different method calls that use different numbers of parameters.

* **methodOne()**
    * "methodOne" is the name of our method followed by an open and closed parentheses, where we are not "passing in" any parameters. This means that myMethod is not accepting nor expecting external information outside of the method itself. 
* **methodTwo(int value)**
    * "(int value)" Now inside the open and closed parentheses we have some other element:
        * "int" is the data type of our parameter
        * "value" is the name we gave our parameter
* **methodThree(int value, String name)**
    * we can pass multiple parameters into our method by separating each individual parameters with a comma. For each parameter we have, we should list the type (e.g. `int` ) and the name (e.g. `value` ).

Here is how we would "call" (i.e. use) each of these methods in a separate method, such as the main method.

```java
// examples of how we would call the above methods with parameters in main
public static void main(String[] args) {
    methodOne();
    methodTwo(5);
    methodThree(4, "hello");
}
```

:::{attention}
Remember that specific syntax such as commas or semicolons matter for our code to run properly. 
:::

## Main Points:

* Parameters in programming are values of different data types (e.g., `int`, `String`) that we pass into methods to use within the methods.

* Using parameters allows methods to work with external data (such as the values we pass in to methods), making them more powerful and flexible.

* Parameters help organize logic and reduce redundancies in code by allowing us to reuse methods with different inputs.

* When defining a method with parameters, we specify the data type and name of each parameter inside the parentheses.

* Method calls with parameters involve passing specific values that match the data type and order of the parameters defined in the method signature.
    * Note: in this case we only include the value of the parameter, not the name (present in the last example of Parameters Syntax).