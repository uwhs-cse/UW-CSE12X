# Methods Review

These questionss are designed to asssess your current understanding of methods!

**Questions 1**

What is the output of this method?

```java
public static void order() {
    System.out.println("I am number four");
    System.out.println("I am number one");
    System.out.println("I am number three");
    System.out.println("I am number two");
}
```

:::{admonition} See Answer
:class: tip
:class: dropdown
```text
I am number four
I am number one
I am number three
I an number two
```

When a method is called, the code is executed in the order it is written inside. 
:::

---

**Question 2**

What is the output of executing this `main` method?

```java
public static void main(String[] args) {
    mTwo();
    mThree();
}

public static void mOne() {
    System.out.print("One ");
}

public static void mTwo() {
    System.out.print("Two ");
}

public static void mThree() {
    mOne();
    System.out.println("Three ");
}
```

1. ```text 
    Two Three
   ```
2. ```text 
    One Two Three
   ```
3. ```text 
    Two One Three
   ```
4. ```text 
    One Three
   ```

:::{admonition} See Answer
:class: tip
:class: dropdown
Options **3** is correct:

First the method `mTwo()` is called which prints "Two ", then we call `mThree()` which <ins>first</ins> calls `mOne()` inside itself <ins>and then</ins> prints "Three ". 

So our result is `Two One Three`.
:::

---

**Question 3**

True or False: The code below is possible.

```java
public static void main(String[] args) {
    methodOne();
}

public static void methodOne() {
    System.out.println("I am first");
}

public static void methodOne() {
    System.out.println("I am second");
}
```

:::{admonition} See Answer
:class: tip
:class: dropdown
**False!**

These two are not acceptable because Java cannot differentiate between the two as they have the same name. It is good practice to name methods that reflect the purpose or action of the method in a concise manner.
:::

---

**Question 4**

Select the <ins>two best</ins> lists of methods for the following requirements: 

We have a two-part game and ending:

- Part one of the game prints all integer numbers between 1 and 10, and then prints out "This is part one." with a newline.

- Part two of the game prints out "This is part two." and then prints all integer numbers between 1 and 10 with no newline at the end. 

- At the end we have an outro saying "Thanks for playing!" with a newline. 

:::{admonition} **Hint**
:class: note
Look for a selection of methods with the least amount of redundancy within their logic, and which exhibit the least necessary amount of methods to complete the game task. 
:::

1. ```java
    for (int counter = 0; counter <= 5; counter++) {
        System.out.print(counter + " ");
    }
    ```
2. ```java
    for (int counter = 0; counter <= 5; counter++) {
        System.out.print(counter + " ");
    }
    ```
3. ```java
    for (int counter = 0; counter <= 5; counter++) {
        System.out.print(counter + " ");
    }
    ```
4. ```java
    for (int counter = 0; counter <= 5; counter++) {
        System.out.print(counter + " ");
    }
    ```

:::{admonition} See Answer
:class: tip
:class: dropdown
**A** is the best answer, because it has the least amount of redundant logic. 

**B** contains repeated for loop logic.

**C** has unnecessary methods, `printOne()` and `printTwo()`. 

**D** is the second best answer to A.
:::

**Question 5**

Select and order the following text blocks to match the output of the program below:

```java
public static void main(String[] args) {
    gameTwo();
    gameOne();
}

public static void gameOne() {
    System.out.println("playerOne has won!");
    gameTwo();
    
}

public static void gameTwo() {
    System.out.print("playerTwo has lost! ");
}
```

1. `playerOne has lost! playerTwo has won!`
2. `playerTwo has lost!`
3. `playerOne has won!`
4. `playerTwo has lost! playerOne has won!`

:::{admonition} See Answer
:class: tip
:class: dropdown
The correct order is:
```text
playerTwo has lost! playerOne has won!
playerTwo has lost!
```
Note the we use a `System.out.print()` (no new line) method in `gameTwo()` , making `gameOne()`'s first printed output be on the same line. 
:::

