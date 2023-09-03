# While Loops Review

These questions are to assess your understanding of the `while` loops.

**Question 1**

**`while` loops** are typically used as **definite loops**.

:::{admonition} See Answer
:class: tip
:class: dropdown
**False**

We will typically use `while` loops for what we call **indefinite loops**, meaning that when we write a while loop, we will write it in such a way that it runs till a condition is `false`.
:::

---

**Question 2**

Let's write a `while` loop header! Say I'm writing a `while` loop that should loop until some variable `x` has value `-1`. Which test ensures my code will loop correctly?

1. `while (x == -1)`
2. `while (x > -1)`
3. `while (x != -1)`
4. `while (x < -1)`

:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 4** is correct!

The loop when end when `x == -1`. Try going through the control flow of this for loop header for practice.
:::

---

**Question 3**

What is the output of the following program:

```java
int num = 1; // initialization
while (num <= 200) { // test
    System.out.print(num + " "); // body
    num = num * 2; // update
}
```

1. ```text 
   1 2 4 8 32 64 128
   ```
2. ```text
   1
   2
   4
   8
   16
   32
   64
   128
   ```
3. ```text
   1 2 4 16 32 128 200
   ```
4. This will run forever and never stop


:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 1** is correct!

We keep multiplying `num` by `2` until the number is bigger than `200`
:::
