# String Methods Practice

These questions are to assess your understanding of the `String` methods.

Consider the following variable declarations: 

```java
String yum = "mashed potatoes";
String bestPie = "a-p-p-l-e";
String obligatoryVeg = "GREEN beanS";
```

For each of the questions below, answer with what the resulting value will be from each expression. 

**Question 1**
`yum.charAt(3 * 2 + 1)`

:::{admonition} See Answer
:class: tip
:class: dropdown
**p**

`yum.charAt(3 * 2 + 1)` will return the character located at index `7` inside of the `yum` ("mashed potatoes"), which is **p**.
:::

---

**Question 2**
`obligatoryVeg.indexOf("e")`

::::{admonition} See Answer
:class: tip
:class: dropdown
**7**

`obligatoryVeg.indexOf("e")` returns the (first) index of the character "e" inside of `obligatoryVeg` ("GREEN beanS"), which is **7**.

:::{admonition} Note
:class: note
Here `indexOf` is given a `String` ("e"), not a character. Either works for `indexOf`!
:::
::::

---

**Question 3**
`bestPie.length()`

:::{admonition} See Answer
:class: tip
:class: dropdown
**9**

The number of characters inside of `bestPie` ("a-p-p-l-e") is **9**.
:::