# For Loop Review

These questionss are designed to asssess your current understanding of `for` loops!

**Questions 1**

True or False: **For loops** are typically used as **definitive loops.**

:::{admonition} See Answer
:class: tip
:class: dropdown
True!
:::

---

**Question 2**

Let's write a for loop header! Say I'm writing a for loop that should loop <ins>six times</ins>. Which test(s) ensures my code will loop six times?

1. ```java 
    for (int num = 1; num <= 5; num++) {
   ```
2. ```java 
    for (int num = 1; num < 6; num = num + 1) {
   ```
3. ```java 
    for (int num = 1; num <= 6; num++) {
   ```
4. ```java 
    for (int num = 1; num < 7; num += 1) {
   ```

:::{admonition} See Answer
:class: tip
:class: dropdown
Options **3** and **4** are correct! Both of these tests will cause our loop to run **six times**! Try going through the control flow of this for loop header for practice.
:::

---

**Question 3**

How many hearts will the following for loop print?

```java
for (int hearts = 1; hearts <= 25; hearts += 1) {
    System.out.println("<3");
}
```

:::{admonition} See Answer
:class: tip
:class: dropdown
This for loop will execute 25 times.
:::

---

**Question 4**

What is the output of this for loop?

Write the output in quotation marks. For example: "Hello!"

:::{admonition} **Hint**
:class: note
Watch out for trailing whitespace... 👀

What is trailing whitespace? Trailing whitespace is <ins>any whitespace</ins> after the last non-whitespace character in a line until the newline character, if any.
:::

```java
for (int counter = 0; counter <= 5; counter++) {
    System.out.print(counter + " ");
}
```

:::{admonition} See Answer
:class: tip
:class: dropdown
The for loop runs a total of six times, each time printing out the variable `counter` as it's incremented. Note there is a trailing whitespace! If you copied the output and put it in a string variable, it would look as such: `String var = "0 1 2 3 4 5 ";`
:::

**Question 5**

[Challenge] Ho many stars ill be printed by the folloing for loop?

```java
for (int stars = -5; stars <= 0; stars = stars + 1) {
    System.out.print("***");
}
```

:::{admonition} **Hint**
:class: note
Try following the control flow of the for loop and writing out how the value of `stars` changes as we progress.
:::

:::{admonition} See Answer
:class: tip
:class: dropdown
**18** stars will be printed! 

Note that we are starting with `stars` being equal to `-5` and we are continuing on until `stars` is greater than `0`!
:::

---

**Question 6**

[Challenge] What is the output of this for loop?

```java
for (int loop = 10; loop >= 0; loop -= 2) {
    System.out.print(loop + " ");
}
```

:::{admonition} See Answer
:class: tip
:class: dropdown
The output is

`10 8 6 4 2 0`

Note that this time our update steps subtracts `2` from the `loop` variable at each iteration, rather than the usual `1` we have seen so far. 
:::
