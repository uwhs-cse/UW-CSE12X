# Expressions Practice

These questions are to assess your understanding of Java expressions.

For each question, answer with the value that would result from fully evaluating that expression.  Remember some of the tricky aspects of expressions in Java: 

- [!] [P] [MMD] [AS] [<><=>=] [== !=] [&&] [||] precedence!  
    * When there are multiple operations at the same level of precedence, they are executed **left to right in order.**

- Keep track of the type of each subexpression as you work through each problem!  

- Watch out for that pesky `int` division!  

:::{admonition} Note
:class: note
Make sure your answer conveys the appropriate type of the result in each answer. For double results, include the decimal point (even if the answer is a whole number, such as 7.0 instead of 7).  For String results, surround the value with double-quotes (such as "hi 23").  
:::

**Questions 1**

`3 * 10`

:::{admonition} See Answer
:class: tip
:class: dropdown
**30**
:::

---

**Question 2**

`"cat" + "dog"`

:::{admonition} See Answer
:class: tip
:class: dropdown
**"catdog"**

Remember that, when dealing with `String`s, the `+` operator performs ***concatenation***! Also keep in mind that concatenation won't add any spacing for you— since neither **String** contains any space characters, the ending result doesn't have any space characters either, which is why we get `"catdog"` rather than `"cat dog"`! 
:::

---

**Questions 3**

`11 % 3`

:::{admonition} See Answer
:class: tip
:class: dropdown
**2**

The mod operator (`%`) gives us the *remainder* after dividing `11` by `3`.  `3` fits into `11` three times evenly, which leaves a remainder of `2`!  
:::

---

**Question 4**

`(2 + 3 * 6) % 3`

:::{admonition} See Answer
:class: tip
:class: dropdown
**2**

Let's break this down! The <ins>underlined</ins> subexpression indicates the next step of evaluating the entire expression. Each step is performed on its own line. 

(2 + <ins>3 * 6</ins>) % 3 \
(<ins>2 + 18</ins>) % 3 \
<ins>20 % 3</ins> \
2

:::

---

**Questions 5**

`12 / 5 + 8 / 4`

:::{admonition} See Answer
:class: tip
:class: dropdown
**4**

Remember that pesky `int` division! 

The <ins>underlined</ins> subexpression indicates the next step of evaluating the entire expression. Each step is performed on its own line. 

<ins>12 / 5</ins> + 8 / 4 \
2 + <ins>8 / 4</ins> \
<ins>2 + 2</ins> \
4
:::

---

**Question 6**

`(14 / 5 + 7 * 3) % 8 > 4`

:::{admonition} See Answer
:class: tip
:class: dropdown
**true**

Now we're also dealing with a relational operator! Remember your order of operations and take things one step at a time.  

The <ins>underlined</ins> subexpression indicates the next step of evaluating the entire expression. Each step is performed on its own line. 

(<ins>14 / 5</ins> + 7 * 3) % 8 > 4 \
(2 + <ins>7 * 3</ins>) % 8 > 4 \
(<ins>2 + 21</ins>) % 8 > 4 \
<ins>23 % 8</ins> > 4 \
<ins>7 > 4</ins> \
true
:::

---

**Questions 7**

`12.0 / 5`

:::{admonition} See Answer
:class: tip
:class: dropdown
**2.4**

When mixing types `int` and `double` in an expression, remember that Java will convert the `int` to a `double`, then perform the operation as if it were working with two `double`!  

`12.0 / 5 --> 12.0 / 5.0 --> 2.4`
:::

---

**Question 8**

`"hello" + 2 + 3`

:::{admonition} See Answer
:class: tip
:class: dropdown
**"hello23"**

When mixing types `int` and `String` in an expression, Java will convert the `int`s to `String`s, then perform the operation as if it were working with two `String`s! 

The <ins>underlined</ins> subexpression indicates the next step of evaluating the entire expression. Each step is performed on its own line. 

<ins>"hello" + 2</ins> + 3 \
<ins>"hello" + "2"</ins> + 3 \
<ins>"hello2" + 3</ins> \
<ins>"hello2" + "3"</ins> \
"hello23"
:::

---

**Question 9**

`2 + 3 + "hello"`

:::{admonition} See Answer
:class: tip
:class: dropdown
**"5hello"**

Since we have two `+` operators that share the same level of precedence, Java will perform each operation **left to right** in order!  And when mixing types `int` and `String` in an expression, Java will convert the `int`s to `String`s, then perform the operation as if it were working with two `String`s! 

The <ins>underlined</ins> subexpression indicates the next step of evaluating the entire expression. Each step is performed on its own line. 

<ins>2 + 3</ins> + "hello" \
<ins>5 + "hello"</ins> \
<ins>"5" + "hello"</ins> \
"5hello"
:::
