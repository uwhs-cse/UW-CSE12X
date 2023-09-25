# MyProgram

The following program contains **three** errors. Correct the errors and submit a working version of the program.

::: {note}
The entire `MyProgram` class is given, but you only need to modify the code in **three** places to make it compile and output code from the `println` statements
:::

``` java
public MyProgram {
    public static void main(String[] args) {
        System.out.println("This is a test of the")
        System.out.Println("emergency broadcast system.");
    }
}
```

:::{admonition} See Solution
:class: tip
:class: dropdown

```java
public class MyProgram {
    public static void main(String[] args) {
        System.out.println("This is a test of the");
        System.out.println("emergency broadcast system.");
    }
}
```

**Explanation**
1. Missing `class` keyword on line 1

2. Missing semicolon on line 3

3. Uppercase `Println` instead of lowercase `println` on line 4

:::