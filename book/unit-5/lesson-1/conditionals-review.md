# Conditionals Review

These questionss are designed to asssess your current understanding of conditionals!

```java
public static void mystery(int n) {
    System.out.print(n + " ");

    if (n < 0) {
        n = n + 7;
    } else {
        n = n * 2;
    }
    
    System.out.println(n);
}
```

Consider the following method. For each call below, indicate what output is produced.

**Questions 1**

`mystery(8)`

:::{admonition} See Answer
:class: tip
:class: dropdown

**8 16**
:::

---

**Questions 2**

`mystery(-3)`

:::{admonition} See Answer
:class: tip
:class: dropdown

**-3 4**
:::

---

**Questions 3**

`mystery(1)`

:::{admonition} See Answer
:class: tip
:class: dropdown

**1 2**
:::

---

**Questions 4**

`mystery(0)`

:::{admonition} See Answer
:class: tip
:class: dropdown

**0 0**
:::