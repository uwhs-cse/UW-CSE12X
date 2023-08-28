# Returns

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/GStAcMsqOAk?si=4-ZrKn3g5ITwo97T" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: Returns Video Walkthrough**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

## 🔍 About Returns
If parameters send values <ins>into</ins> a method, returns can send values <ins>out</ins> of a method. **Return statements** are used to "return" values after the block of code prior to the return statement has been executed. You can return all different data types when using a method. 

## 📗 Return Syntax
Go ahead and run this to see what happens!
```java
public class Example {

    public static void main(String[] args) {
        /// check this out:
        int val = 2;
        String result = print(val);
        System.out.println("The result returned:");
        System.out.println(result);
        val = 20; 
        System.out.println("Val has been updated");
        result = print(val);
        System.out.println("The result returned:");
        System.out.println(result);
    }

    public static String print(int age) {
        System.out.println("We are inside the print method with input of " + age);
        String result = "I am " + age + " years old"; 
        return result;
    }
  
}
```

* **`public static String`**
    * Previously we have been utilizing `public static void`. Prior to this point, we place `void` in the place of the return type in the method header since we did not need to return a value for those methods. 
    * If you want to return a value of a particular type, you place the type after `static` in the method header and before the method's name.
        * e.g. `public static boolean yesOrNo()`
        * e.g. `public static int guessFavoriteNumber()`
        * e.g. `public static double fractionToDecimal()`
    * If you "promise" (or list) a return type in your method header, you <ins>**must**</ins> return a value of that type. Failure to do so will result in compiler errors! 🚨
    * `String` indicates that we are expecting to return a `String`. 
* **`return result`**;
    * Here we have the key word `return` followed by `result` which is the variable holding the value we want to return. 
    * You can return a literal value (e.g. `return 6;`, `return "hello!";` ) <ins>or</ins> you can return a variable (e.g. `return result;` , `return num;` )
    * Make sure that whatever value / variable you return in your method matches the type "promised" or listed in the method header.

:::{note}
You can return all different data types we have discussed so far: `int`, `String`, `double`, etc. 
:::

## 🧠 Why Returns? 
Returns allows us to have access to more information and provide us more flexibility in our programs. As mentioned earlier, returns enable us to send information out of one method and into the scope of another method.

You might want to utilize returns to return the result of a calculation, a message, etc.

```java
public class Example {

    public static void main(String[] args) {
        System.out.println("First we call our method: myMethod");
        int val = 40; 
        int age = myMethod(val);
        System.out.println("our returned value is: " + age);
        
        // now we can use the age (the returned information)
        // to our advantage!
        System.out.println("Next we call our method: print");
        String result = print(age);
        System.out.println("The result returned from print method:");
        System.out.println(result);
    }

    public static int myMethod(int val) {
        System.out.println("Then update value inside myMethod");
        val = val + 2; 
        return val;
    }

    public static String print(int age) {
        String result = "I am " + age + " years old"; 
        return result;
    }
}
```

## 🐞 Try this out! 

**Example 1:**
```java
public class Example {

    public static void main(String[] args) {
        int val = myMethod();
        System.out.print("our returned value is: " + val);
    }

    public static int myMethod() {
        int val = 4; 
        val = val + 2; 
        System.out.print("this is before the return statement.");
        return val;

        // This will not print!!
        System.out.print("this is after the return statement.");
    }
}
```

:::{error}
**NOTE:** This block of code gives you an error on line 13. 
:::

The error states that line 13 is an "unreachable statement". This means as it claims that line 13 will never be reached and thus an **important aspect of returns is that it will abort and exit the method right after return.** 

Another important rule of return statements for Java is that we can **<ins>only</ins> have one value returned**. This means that we must be careful and creative as to not lose any data we might be keeping track of or need access to. 

**Example 2**
:::{note}
Before running the program, try going through the `main` method and predict what the output should be.
:::

```java
public class Example {
    public static void main(String[] args) {
        int value = 6;
        System.out.println("value of variable before method call: " + value);
        performCalculation(value);
        // should print that value is 60
        System.out.println("value of variable after method call: " + value);

    }

    public static int performCalculation(int num) {
        num = ((num + 7) / 2) * 10;
        return num;
    }

}
```

If you run this program, notice that we start with `value = 6;` and we report the value of the variable before the method call in line 5. We then call `performCalculation()` inside `main`, which takes an integer parameter and performs some calculation on the parameter. After those calculations, the value is returned.

But even if the value is returned, the output on line 7 doesn't reflect those changed.

This happens because we don't **catch the return**—to be able to save the information being sent as a return from another method, we need to <ins>catch</ins> that value, or store the return in a variable. This way, we are able to keep track of the updated information in main.

:::{note}
On line 5, try changing the line to `value = performCalculation(value)` , then run the program again. See how the output changes after "catching the return" inside the `value` variable.
:::

## Main Points

* In Java, you can use return statements to send values out of a method. These values can be of various data types like `int`, `String`, `double`, etc.
* To specify that a method should return a value, you replace **`void`** (which means no return) in the method signature with the desired data type (e.g., **`int`**, **`String`**, etc.).
* Use the `return` keyword followed by a value or a variable to return a value from a method. For example, **`return 17;`** or **`return result;`**
* To use the value returned by a method, you should assign it to a variable. For example, `int age = myMethod(val);`. This way, you can retain and utilize the returned value.
* Returning values allows you to access and use the results of calculations or data generated within a method in other parts of your program!