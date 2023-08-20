# Data Types

<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/PWoC6F2ldgw" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 121: Data Types Video Walkthrough**.The video and the reading both have the same information. You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

Aside from displaying text to the console, one of the most important needs for a programmer is the ability to store information. Whether it's storing the name of a user, the balance of a bank account, or the current year, it is very useful to be able to give information a label, and reference it. We can do this in Java using **variables** (more on *variables* in the next lesson).

## 🧠 Data Types

When deciding what information to store, you first need to decide what *type* of data it should be so that Java can be prepared for what you want to give it. This could be something like a number, word, or letter! Java has formal names for each of these types.

:::{admonition} Note
:class: note

We'll see examples on how to use these data types in the next section!
:::

### Integers

**Integers** are *whole numbers* such as 1, 2, 3, 0, -1, -50, etc. We can tell Java that we want to store an integer using the `int` keyword. Integers are useful for representing quantities like the number of people in a room, your age, or other discrete (whole number) quantities.

:::{admonition} Caution
:class: caution

✅ **Valid Integers:** 121, 2022, 10, 75

❌ **Not Valid Integers:** 3.14, 0.5, "Hello", "10000" (even though the last example is an integer, note it has quotes!)
:::

### Doubles

**Doubles** are decimal numbers such as 0.25, -3.56, 3.14, 500.0, etc. We can tell Java that we want to store a decimal number using the `double` keyword. Doubles are useful for representing quantities like money (dollars and cents), weight, and so on. Doubles are typically used in situations where we need more precision than simple integers (whole numbers). 

:::{admonition} Caution
:class: caution

✅ **Valid Doubles:** 9.81, 98.6, 1.0,10.5772984

❌ **Not Valid Doubles:** "Hello", "10.5" (even though the last example is a double, note it has quotes!)
:::

### Strings

**Strings** represent text such as "Hello", "Bye", "CSE 121", etc. You can think of strings as a collection of letters, digits, or other characters that are strung together to form a word or a sentence. We can tell Java that we want to store text using the `String` keyword (notice the capital S), typically with double quotes around the text. 

:::{admonition} Caution
:class: caution

✅ **Valid Strings:** "java-!", "a longer string"

❌ **Not Valid Strings:** 10000 (notice no quotes)
:::

### Booleans

A **boolean** is a data type that has only two possible values: `true` or `false`. Booleans are intended to represent the output of a *logical* calculation. We can tell Java that we want to store a `true`/`false` value using the `boolean` keyword.  You probably won't use boolean values much for now, but as we continue to build on our Java knowledge, they will indeed become more useful! 

:::{admonition} Caution
:class: caution

✅ **Valid Booleans:** true, false (these are the only two values that a boolean can be)

❌ **Not Valid Booleans:** "true", "false", 10, 100.5, "hi"
:::

## Main Points

- We've learned about 4 *data* types in Java: integers (`int`) which represent whole numbers, doubles (`double`) which represent real numbers, strings (`String`) which represent text or a sequence of characters, and booleans (`boolean`) which represent truth value (i.e., `true` or `false`). 