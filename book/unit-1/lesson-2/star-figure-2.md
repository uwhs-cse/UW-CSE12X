# Star Figure 2

Write a complete program called `StarFigures` that generates the output shown. Use `print` and `println` statements to produce the following output where each statement only outputs spaces or "*"s. In other words, do not print spaces and "*"s in the same print statement.

e.g `print("*****")` , `println("  ")`

```text
*****  // line 1
*****  // line 2
 * *   // line 3
  *    // line 4
 * *   // line 5
       // line 6
  *    // line 7
  *    // line 8
  *    // line 9
*****  // line 10
*****  // line 11
 * *   // line 12
  *    // line 13
 * *   // line 14
```

## Starter Code

```java
public class StarFigures {
  public static void main(String[] args) {
    // TODO: Your Code Here
  }
}
```

:::{admonition} See Solution
:class: tip
:class: dropdown

```java
// Philip J. Fry, CSE 142, Autumn 3097, Section AX
// This program draws several repeated figures of stars.

public class StarFigures {
    public static void main(String[] args) {
        // First figure
        System.out.println("*****");
        System.out.println("*****");
        System.out.print(" ");
        System.out.print("*");
        System.out.print(" ");
        System.out.println("*");
        System.out.print("  ");
        System.out.println("*");
        System.out.print(" ");
        System.out.print("*");
        System.out.print(" ");
        System.out.println("*");

        System.out.println();

        // Second figure
        System.out.print("  ");
        System.out.println("*");
        System.out.print("  ");
        System.out.println("*");
        System.out.print("  ");
        System.out.println("*");
        System.out.println("*****");
        System.out.println("*****");
        System.out.print(" ");
        System.out.print("*");
        System.out.print(" ");
        System.out.println("*");
        System.out.print("  ");
        System.out.println("*");
        System.out.print(" ");
        System.out.print("*");
        System.out.print(" ");
        System.out.println("*");
    }
}
```

**Explanation**
Recall that `println` moves the cursor to the next line while `print` does not! This means that when we want to print everything on the same line (when mixing spaces and "*"s for this problem), we use `print` . Then, we use `println` when the line ends so we print on a new line for the next time we print.
:::

## Video Walkthrough

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/uU0Cq_FXFWU?si=UnTD55nvUkY1dZJm" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>