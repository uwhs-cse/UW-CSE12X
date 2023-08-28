# Parameters Review

These questionss are designed to asssess your current understanding of parameters!

**Questions 1**

What is the output?

```java
public static void main(String[] args) {
   repeat(2, "banana bread is delicious");
   repeat(3, "I love rubber band balls");
}

public static void repeat(int times, String phrase) {
   for (int i = 1; i <= times; i++) {
      System.out.println(phrase);
   }
}
```

1. ```text 
    banana bread is delicious
    banana bread is delicious
    I love rubber band balls
    I love rubber band balls
    I love rubber band balls
   ```
2. ```text 	
    banana bread is delicious banana bread is delicious
    I love rubber band balls I love rubber band balls I love rubber band balls
   ```
3. ```text 
    banana bread is delicious
    I love rubber band balls
   ```
4. ```text 
    2
    3
   ```

:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 1** is correct!

In the method `repeat` the parameter `times` is utilized in the `for` loop to loop and print the parameter `phrase`, `times` number of times. 
:::

---

**Question 2**

True or False: There is an error in the following code.

```java
public static void main(String[] args) {
    String star = "*";
    int value = -5;
    print(value, star);
}

public static void print(String shape, int n) {
    System.out.println("I have " + n + "number of " shape);
}
```

:::{admonition} See Answer
:class: tip
:class: dropdown
**True**!

There is an error on line `print(value, star);`  because the order of parameters do not match for what the method print is expecting, which is a `String` then an integer. 
:::

---

**Question 3**

What is the output? 

```java
public static void main(String[] args) {
    int val = 1;
    mOne(val);
    val = -1; 
    mTwo(val);
    mThree(val);
}

public static void mOne(int val) {
    System.out.println("One " + val);
}

public static void mTwo(int val) {
    val = val * 2;
    System.out.println("Two " + val);
}

public static void mThree(int val) {
    mOne(val);
    val = val + 3;
    System.out.println("Three " + val);
}
```

1. ```text 
    One 1
    Two -2
    One 1
    Three 4
   ```
2. ```text 	
    One 1
    Two 2
    One 1
    Three 4
   ```
3. ```text 
    One 1
    Two -2
    One -1
    Three 2
   ```
4. ```text 
    One 1
    Two -2
    One 2
    Three 5
   ```

:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 3** is correct!

First we call `mOne()` and pass a `val` of value `1`.

Second we call `mTwo()` and pass the updated `val` of value `-1`. Then print the updated `val` inside `mTwo()`.

Third we call `mThree()` and again pass the `val` of value `-1`, inside which we call `mOne()` and pass `val` of value `-1` as well. Then print the updated `val` inside `mThree()`.
:::

---

**Question 4**

Find the error(s): multiple options may be correct.

```text
1    public static void main(Strings[] args) {
2        String name = "Min"
3        int val = 25; 
4        findErr(name);
5        findErr(name, val);
6        findErr(val, name);
7        findErrTwo();
8    }
9    
10    public static void findErr(String name, int val) {
11        System.out.println("hello " + val + " age is " + name " ?");
12    }
13    
14    public static void findErrTwo() {
15        System.out.println("Yikes");
16        findErr();
17    }
```

1. line 2
2. line 5, line 6
3. line 4, line 6
4. line 7
5. line 16

:::{admonition} See Answer
:class: tip
:class: dropdown
**Options 1, 3, and 5** are correct!

line 2: missing semicolon

line 4: missing a parameter

line 6: the parameter types do not match what findErr() is expecting

line 16: missing a parameter
:::

---

**Question 5**

What is the output? 

```java
public static void main(String[] args) {
    String playerOne = "Ninda"; 
    String playerTwo = "Rita";  
    
    gameOne(playerTwo, playerOne);
    gameTwo(playerOne, 5);
}

public static void gameOne(String playerOne, String playerTwo) {
    System.out.println(playerOne + " has won!");
    System.out.println(playerTwo + "has lost!");
}

public static void gameTwo(String player, int lives) {
    System.out.println(player + " has " + lives * 2 + " lives.");
}
```

1. ```text 
    Ninda has won!
    Rita has lost!
    Ninda has 5 lives.
   ```
2. ```text 	
    Rita has won!
    Ninda has lost!
    Ninda has 5 lives.
   ```
3. ```text 
    Ninda has won!
    Rita has lost!
    Ninda has 10 lives.
   ```
4. ```text 
    Rita has won!
    Ninda has lost!
    Ninda has 10 lives.
   ```

:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 4** is correct!

Option 4 is the answer because, `gameOne`'s first parameter passed is "Rita" and the second is "Ninda", thus the order of parameters passed is more important that the variable name. For the last line, the parameter `lives` is multiplied by 2.
:::

