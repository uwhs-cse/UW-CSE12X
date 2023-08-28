# Scope

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/re-bsXtmNQM?si=4sLwPRT-B6ibkGFx" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: Scope Video Walkthrough**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

## 🔍 Importance of Scope

Scope is the idea that different values can be accessed, altered, and utilized, within a particular part of a program. Scope is important for methods and parameters as we are passing around information in between methods with different scope.



## Example 1: 

Let's look at the scope for the variable value  initialized in the main method.
```java
public class Scope {

    public static void main(String[] args) {
        int value = 2;
        printVal(value);
        System.out.println("This is still the same value: " + value);
    }

    public static void printVal(int value) {
        System.out.println("This is an external value: " + value);
        // now lets alter the input
        value = 15;
        System.out.println("This is an updated external value: " + value);
    }

}
```

:::{note}
We can see that even when the method `printVal()` is called and we changed `value` in line 12 to `value = 15;`  it does <ins>not</ins> get updated outside of the `printVal()` method like on line 6. Thus, we can see that the scope of `value` is within the main method only, where it was initialized. 
:::

## Example 2: 

Let's look at the scope for the variable `otherVal` initialized in the `printVal()` method.
```java
public class Scope {

     public static void main(String[] args) {
        printVal();
        System.out.println("Lets check the other value: " + otherVal);
    }

    public static void printVal() {
        int otherVal = 0;
        System.out.println("This is an internal value: " + otherVal);
        otherVal = 25;
        System.out.println("This is an updated internal value: " + otherVal);
    }

}
```

:::{error}
We run into an error on line 5, because the variable `otherVal` cannot be accessed through the `main` method. This is because the scope of `otherVal` is within the method `printVal()`, where `otherVal` was initialized. 
:::

## Main Points:

* **Scope** refers to the visibility and accessibility of variables within different parts of a program.
* Variables declared within a method have **scope** *limited to that method*. They cannot be accessed outside of the method in which they were declared.
* Parameters also have a limited **scope** within the method where they are defined. They can only be used within that specific method.
* Changes made to variables inside a method do not affect their values outside the method, as their **scope** is confined to the method's block.
* Variables defined within a method cannot be accessed from other methods or the main method - otherwise, we will get compile-time errors.