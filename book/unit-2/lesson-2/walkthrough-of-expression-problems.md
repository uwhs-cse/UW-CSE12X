# 👣 Walkthrough of Expression Problems

To help you get comfortable with all of these complicated rules, let's walk through the evaluation of a couple of complex Java expressions step by step.  

## ⭐ Expression 1

```
2 + 2 + "hello" + 3 * 5 / 10
```

### () — **P**arentheses

There are no parentheses in this particular expression, so we can move on! 

### % * / — **M**odulo, **M**ultiplication, **D**ivision

We have a few subexpressions with operators at this level of precedence (specifically the `*` and `/`), so we must carefully execute them in order from **left to right**.  In this order, first we deal with the multiplication by evaluating `3 * 5`: 

```
2 + 2 + "hello" + 3 * 5 / 10
2 + 2 + "hello" + 15 / 10
```

Note that because we were dealing with an `int` times an `int`, we also get an `int` result (`15`, as opposed to `15.0` or `"15"`).  Now, there is only one operation left at this level of precedence—the subexpression `15 / 10`:

```
2 + 2 + "hello" + 15 / 10
2 + 2 + "hello" + 1
```

Again, we are dealing with two `int` operands so we produce an `int` result and we are dealing with `int` division (or "truncating division")!  So instead of getting a result of `1.5` (that you maybe would have expected from typical mathematics), we get `1` because 10 fits evenly into 15 exactly 1 time.  (That 5 remainder would be the result of `15 % 10`!)

### + - — **A**ddition, **S**ubtraction

Finally, we only have `+` operators left which are all at the same level of precedence.  So once again, we will dutifully execute them in order from **left to right**.  Let's start with the leftmost subexpression `2 + 2`:

```
2 + 2 + "hello" + 1
4 + "hello" + 1
```

Both operands are `int`, so we produce an `int` result which produces a (hopefully unsurprising) `4`.  Let's keep going by evaluating the next leftmost subexpression at this level: `4 + "hello"`! 

```
4 + "hello" + 1
"4hello" + 1
```

This time, we have one `int` operand (`4`) and one String operand (`"hello"`) so Java converts the `int` to a `String` (making it `"4"` instead of `4`) and then we do typical `String` concatenation, squishing the two `String`s together to create `"4hello"`. We're almost done - just `"4hello" + 1` remaining!

```
"4hello" + 1
"4hello1"
```

Here, we repeat the exact same logic! One of the operands is an `int` while the other is a `String`, so the `int` operand is converted to a `String` before we concatenate the two `String`s together, and we have our final result! 🥳 

Video walkthrough of this problem below (click "Expand"). 

<details>
<summary>Expand</summary>

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.loom.com/share/8024130794224184b56d8afaea2038fa" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

</details>


## ⭐ Expression 2

177 % 100 % 10 / 2

### () — **P**arentheses

There are no parentheses in this particular expression, so we can move on! 

### % * / — **M**odulo, **M**ultiplication, **D**ivision

*All* of the operators in this expression are at this level of precedence, so let's move across the expression one subexpression at a time **left to right**, starting with `177 % 100`.  

```
177 % 100 % 10 / 2
77 % 10 / 2
```

Remember that the modulo operator gives us the *remainder* after dividing the left operand by the right operand (so 177 divided by 100 gives us 1, remainder 77).  Next up is `77 % 10`:

```
77 % 10 / 2
7 / 2
```

Same process: 77 divided by 10 gives us 7, with 7 left over! And finally `7 / 2`:

7 / 2
3

We return to our very favorite `int` division which gives us 3 (because 2 divides evenly into 7 **three** times, with 1 remainder).  

### + - — Addition, Subtraction

No addition or subtraction - we're done! 🏁 

Video walkthrough of this problem below (click "Expand"). 

<details>
<summary>Expand</summary>

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.loom.com/share/e8bb25d232284cdd8f460e14aed168a7" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

</details>


## ⭐ Expression 3

```
(2.5 + 3.5) / 2
```


### () — **P**arentheses

Let's start with the subexpression in the parentheses: `2.5 + 3.5`

```
(2.5 + 3.5) / 2
6.0 / 2
```

Notice that we wrote `6.0`, not `6`.  Even though this value *could* be represented by an `int`, we must carefully follow Java's rules about types. Both operands in this subexpression are `double`s, so we get a `double` result! Now, we only have one operator to deal with...

### % * / — Modulo, Multiplication, Division

Now we just need to evaluate `6.0 / 2`

```
6.0 / 2
3.0
```

Again, you may have expected the result to be `3`, but we have `double` and `int` expression so Java converts the `int` to a `double` before performing `double` division! Moral of the story: **type matters**!  

### + - — **A**ddition, **S**ubtraction

No addition or subtraction, we're done! 

Video walkthrough of this problem below (click "Expand"). 

<details>
<summary>Expand</summary>

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.loom.com/share/cec22b0510d745e48a004772a7d39a2e" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

</details>


## ⭐ Expression 4

```
(6.7 > 25) && 9 > 2 && !(8.2 < 5)
```


### () — **P**arentheses

Let's start with the subexpression in the first set of parentheses: `6.7 > 25`

```
(6.7 > 25) && 9 > 2 && !(8.2 < 5)
false && 9 > 2 && !(8.2 < 5)
```

Now we have a subexpression in one more set of parentheses to handle before moving on: `8.2 < 5`

```
false && 9 > 2 && !(8.2 < 5)
false && 9 > 2 && !false
```

### ! — **Logical Not**

Remember that logical NOT just takes whatever the boolean value is, and flips it to the opposite!  So in this case !false becomes true.

```
false && 9 > 2 && !false
false && 9 > 2 && true
```

### % * / — **M**odulo, **M**ultiplication, **D**ivision

No mod, multiplication or division! 

### + - — **A**ddition, **S**ubtraction

No addition or subtraction! 

### < > <= >= — **Relational Operators**

We've already dealt with some of the relational operators that were in the original expression when we evaluated the parenthesized expressions, but there is one left: `9 > 2`

```
false && 9 > 2 && true
false && true && true
```


### == != — **Equality Operators**

No equality operators! 

### && — **Logical And**

We have multiple subexpressions using `&&` so we evaluate them left to right. Remember, `false && true` results in `false`!

```
false && true && true
false && true
false
```

### || — **Logical Or**

No logical OR, so we're done! 

Video walkthrough of this problem below (click "Expand").

<details>
<summary>Expand</summary>

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.loom.com/share/4ccd49b5f48d414e9367916087beea00" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

</details>