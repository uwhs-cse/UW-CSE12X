# User Input (Scanner) Review

These questions are designed to assess your current understanding of using `Scanner`s to read in user input!

**Question 1**
Which of the following code snippets shows the correct way to construct a `Scanner` that takes user input from the console?

1. `scanner input = new Scanner(System.in)`
2. `Scanner input = Scanner(System.in)`
3. `Scanner input = new Scanner(System.in);`
4. `Scanner input = new Scanner();`

:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 3** is correct!

In order to create a `Scanner`, we must declare the `Scanner` type, give it a name, and have the correct `Scanner` construction code, which is `= new Scanner(System.in);`.
:::

---

**Question 2**
How many tokens are listed below?

```text
hello!          I love 
       computer        Science!
1 2 3
```

:::{admonition} See Answer
:class: tip
:class: dropdown
**8**

Remember that **tokens** are any unit of input separated by white space (e.g. a space, tab, etc.).
:::

---

**Question 3**
Which statement do we need at the very top of our program so that we can use `Scanners`?

1. `import java.util;`
2. `import java.io.*;`
3. `import java.util.*;`
4. `import java.io;`

:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 3** is correct!
:::

--- 

**Question 4**
What `Scanner` methods can you use to read in this token of user input? 
`hello`

*Select all methods that could apply*

1. `next()`
2. `nextDouble()`
3. `nextInt()`
4. `nextLine()`
5. Error!

:::{admonition} See Answer
:class: tip
:class: dropdown
**Options 1 and 4** are correct!

The input hello can only be read as a string (“hello”). Trying to read in with `nextInt()` or `nextDouble()` would result in an **exception**, which is like an error. 

**Note:** while both `next()` and `nextLine()` will read in this token of user input as a string, it's better design to use the method that matches the input you expect <ins>closest</ins>. If you are expecting to only take in one token of user input, `next()` might be the best method to use here!
:::

---

**Question 5**
What `Scanner` methods can you use to read in this token of user input? 
`3.0`

*Select all methods that could apply*

1. `next()`
2. `nextDouble()`
3. `nextInt()`
4. `nextLine()`
5. Error!

:::{admonition} See Answer
:class: tip
:class: dropdown
**Options 1, 2 and 4** are correct!

The input `3.0` can be read in as a `double` (`3.0`) or a `String` (`“3.0”`).
:::

---

**Question 6**
What `Scanner` methods can you use to read in this token of user input? 
`3`

*Select all methods that could apply*

1. `next()`
2. `nextDouble()`
3. `nextInt()`
4. `nextLine()`
5. Error!

:::{admonition} See Answer
:class: tip
:class: dropdown
**Options 1, 2, 3, and 4** are correct!

The input `3` can be read in as an `int` (`3`), a `double` (`3.0`), or a `String` (`“3”`)!
:::

---

**Question 7**
If I were to write a program to prompt the user asking them for their <ins>age</ins>, what `Scanner` method should I use to get that input?

*Select all methods that could apply*

1. `next()`
2. `nextDouble()`
3. `nextInt()`
4. `nextLine()`

:::{admonition} See Answer
:class: tip
:class: dropdown
**Options 4** is correct!

Since age is a value that is a <ins>whole</ins> number, we would want save that information as an `int` and use `nextInt()` to get that value.

`nextDouble()` could also work, but it's not the best style: Because we typically represent age as a whole number, it would make the most sense to read that information in as an `int`.
:::

--- 

**Question 8**
If I were to write a program to prompt the user asking them for their <ins>favorite season</ins> (e.g. winter, summer, autumn, or spring), what `Scanner` method should I use to get that input?

*Select all methods that could apply*

1. `next()`
2. `nextDouble()`
3. `nextInt()`
4. `nextLine()`

:::{admonition} See Answer
:class: tip
:class: dropdown
**Options 1** is correct!

Since a user's favorite season will be <ins>one</ins> word, we should use `next()` to read in that single token as a `String`. 
:::