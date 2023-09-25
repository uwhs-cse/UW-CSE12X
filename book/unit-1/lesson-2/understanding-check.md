# Check your understanding!

These questions are meant to check your understanding of **printing** as covered lectures and sections so far! 

**Question 1**

Larry is attempting to write his first-ever Java program. Help him write the outer structure for his program. He wishes to name his program, "WordProcessing". 

1. ```java 
    public WordProcessing {

    }
   ```
2. ```java 
    	
    public static WordProcessing {

    }
   ```
3. ```java 
    public class WordProcessing {

    }
   ```
4. ```java 
    public static class WordProcessing {

    }
   ```

:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 3** is the correct answer!
:::


**Question 2**

Jasmine wishes to write the main method for the program. Can you help her with that?

1. ```java 
    public void static main(args String[]) {

    }
   ```
2. ```java 
    public static void main(String[] args) {

    }
   ```
3. ```java 
    public static void main() {

    }
   ```
4. ```java 
    void main public static(String[] args) {

    }
   ```

:::{admonition} See Answer
:class: tip
:class: dropdown
**Option 2** is the correct answer!
:::


**Question 3**

Which of the following lines of code will produce the following output? 
``` text
I'm Harry. Harry Potter.
```
*Hint: Notice that there is only one line! After printing this line, the cursor will stop after the period (.)!*


1. ```java 
    System.out.println("I'm Harry. Harry Potter.");
   ```
2. ```java 	
    System.out.print("I'm Harry. Harry Potter.");
   ```
3. ```java 
    System.out.print("I'm Harry. ");
    System.out.print("Harry Potter.");
   ```
4. ```java 
    System.out.println("I'm Harry. "); 
    System.out.println("Harry Potter.");
   ```

:::{admonition} See Answer
:class: tip
:class: dropdown
**Options 2 and 3** are both correct!

The hint provided reminds us that the printed-out statement is a single line only and there is no blank line after the printed statement. Single line printing can happen using `System.out.print` statements.  As such, Option B should be one of the correct choices. 

Remember that `System.out.print` statement prints out the corresponding statement and then moves the cursor to the right of the printed statement. So, in option C, it would print `I'm Harry`.  and then place the cursor after the space. Then, it would execute the second print statement. And since the cursor is next to what has already printed, the next part, `Harry Potter`. gets added to that line. 

As such options 2 and 3 are correct. 
:::