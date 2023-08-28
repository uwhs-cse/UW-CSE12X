# Returns Review

These questionss are designed to asssess your current understanding of returns!

Refer to this block of code to answer the following questions: 

```java
public static void main(String[] args) {
    int val = 2; 
    val = mOne(val);          // Line 3
    val = -1;                 
    val = mOne(val);          // Line 5
    String state = mTwo(val); // Line 6
    val++;                    
    state = mTwo(val);        // Line 8
}

public static int mOne(int currNum) {
    currNum = currNum * -1;
    return currNum;
}

public static String mTwo(int num) {
    return "our number is " + num;
}
```

**Questions 1**

What is `val` after line 3 has been executed? 

:::{admonition} See Answer
:class: note
:class: dropdown
**-2**

We pass in `val`—which is initialized to `2`—into `mOne()`. Then we multiply the input inside `mOne()` by `-1`. 

Thus, `2 * -1` is `-2`.
:::

---

**Question 2**

What is `val` after line 5 has been executed? 

:::{admonition} See Answer
:class: tip
:class: dropdown
**1**

We pass in `val`—which is now updated to `-1`—into `mOne()`. Then we multiply the input inside `mOne()` by `-1`. 

Thus `-1 * -1` is `1`. 
:::

---

**Question 3**

What is `state` after line 6 has been executed? 

:::{admonition} See Answer
:class: tip
:class: dropdown
**False!**
**"our number is 1"**

After line 5 has been executed, `val` is `1`. Then `val` is passed into `mTwo()`. 
:::

---

**Question 4**

What is state after line 8 has been executed? 

:::{admonition} See Answer
:class: tip
:class: dropdown
**"our number is 2"**

After line 7 has been executed, `val` is `2`. Then `val` is passed into `mTwo()`.
:::


