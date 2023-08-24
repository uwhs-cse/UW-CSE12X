# negativeSum

`Download starter code`

Finish the method `negativeSum` that accepts a `Scanner` as a parameter reading input from a file containing a series of integers, and determines whether the sum starting from the first number is ever negative. The method should print a message indicating whether a negative sum is possible and should return `true` if a negative sum can be reached and `false` if not. 

For example, if the file contains the following text, your method will consider the sum of just one number (38), the sum of the first two numbers (38 + 4), the sum of the first three numbers (38 + 4 + 19), and so on up to the sum of all of the numbers:

:::{admonition} Tip
:class: tip
`Scanner.nextInt()` can process a negative number! Scanning in `"-27"` will return the integer `-27`
:::

```text
38 4 19 -27 -15 -3 4 19 38
```

None of these sums is negative, so the method would produce the following message and return `false`:

```text
no negative sum
```

If the file instead contains the following numbers, the method finds that a negative sum of `-8` is reached after adding 6 numbers together (14 + 7 + -10 + 9 + -18 + -10):

```text
14 7 -10 9 -18 -10 17 42 98
```

It should output the following and return `true`, indicating that a negative sum can be reached:

```text
-8 after 6 steps
```

Notice that after the sum becomes negative you stop processing the file and return your result. Even if the sum would become positive again later in the sequence, and possibly negative again afterwards, as soon as you reach the first negative sum you can return from the method. 

You can also assume that the file only contains valid `int`s, each separated by valid whitespace. As such you may use the `.hasNextInt()` or `.hasNext()` methods on your `Scanner` to check for further input.