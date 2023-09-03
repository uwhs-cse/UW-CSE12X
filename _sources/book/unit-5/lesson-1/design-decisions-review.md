# Design Decisions Review

These questions are designed to assess your current understanding of design decisions with conditionals!

**Questions 1**

Say that I wanted to write some code that, when given a day of the week as a `String`, it would tell me if it was a weekday or weekend.

What kind of conditional structure should I use?

1. `if`
2. `if/else`
3. `if/else if`
4. `if/else if/else if`

:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 2** is correct!

We would want to use an `if/else` structure here!

Again, note that in an `if/else` structure, exactly **one branch** will be entered. We'll be in the case where we either have a weekend or a weekday, not both!
:::

---

**Questions 2**

Say that I wanted to write some code that, when given an `int` representing a place in a race (1st, 2nd, 3rd, 4th, etc.), it would a unique message (e.g. `"You got first place!"` or `"You got second place!"`) only if it was 1st, 2nd, or 3rd place.

What kind of conditional structure should I use?

1. `if`
2. `if/else`
3. `if/else if`
4. `if/else if/else if`

:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 4** is correct!

We would want to use an `if/else if/else if` structure here!

Note that in a general `if/else if` structure, either **0 or 1 branches** will be entered.

We only want to produce output *if* the value indicates 1st, 2nd, or 3rd place. If we have a value other than those, then we don't want to produce output.
:::

---

**Questions 3**

Say that I wanted to write some code that, when given an `int` value, would only print to the console if the value was divisible by 3. 

What kind of conditional structure should I use?

1. `if`
2. `if/else`
3. `if/else if`
4. `if/else if/else if`

:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 1** is correct!

We would want to use just an `if` statement here!

Note that we only want to produce output if the value is divisible by 3. If we are not in that case, then we don't want to do anything else!
:::