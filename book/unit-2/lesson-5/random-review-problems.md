# Random Revie Problems

**Question 1**
Which `import` statement must be placed at the beginning of our program to use `Random`?
1. `import java.util;`

2. `import java.util.*;`

3. `import java.io;`

4. `import java.io.*;`

:::{admonition} See Answer
:class: tip
:class: dropdown
**`import java.util.*`** is needed for our programs to use `Random`.
:::

---

**Question 2**
Write a line of code that will properly construct a `Random`:

:::{admonition} See Answer
:class: tip
:class: dropdown
Any of the following options are valid! Remember that the name of the `Random` variable is up to you, but all other parts of the construction code should match:

```java
Random rand = new Random(); 

Random r = new Random(); 

Random random = new Random(); 

Random randy = new Random();
```
:::

---

**Question 3**
Which line will give back a random value in the range of `0` (inclusive) to `5` (exclusive)?

1. `int num = rand.nextInt(4);` 

2. `int num = rand.nextInt(5);`

3. `int num = rand.nextInt(6);`

:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 2** is correct!

Remember that calls to `nextInt(int max)` will give you a random value in the range of `0` and `max - 1` (max-exclusive).
:::

---

**Question 4**
Which line will give back a random value in the range of `1` (inclusive) to `6` (inclusive)?

1. `int num = rand.nextInt(4) + 1;` 

2. `int num = rand.nextInt(5) + 1;`

3. `int num = rand.nextInt(6) + 1;`

:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 3** is correct!

Remember that calls to `nextInt(int max)` will give you a random value in the range of `0` and `max - 1` (max-exclusive). So in this case, a call to `rand.nextInt(6)` would give back a random value from the range of `0` (inclusive) to `5` (inclusive). 

By adding `1`, we are shifting that range from between `0` and `5`,  to between `1` and `6`.
:::

---

**Question 5**
Which line will give back a random value in the range of `5` (inclusive) to `15` (inclusive)?

:::{admonition} **Hint**
:class: hint
`nextInt(range) + min`, where `range = max - min + 1`
:::

1. `int num = rand.nextInt(11) + 5;` 

2. `int num = rand.nextInt(15) + 5;`

3. `int num = rand.nextInt(10) + 5;`

:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 1** is correct!

Remember that calls to `nextInt(int max)` will give you a random value in the range of `0` and `max - 1` (max-exclusive). So in this case, a call to `rand.nextInt(11)` would give back a random value from the range of `0` (inclusive) to `10` (inclusive). 

By adding `5`, we are shifting that range from between `0` and `10`,  to between `5` and `15`.
:::