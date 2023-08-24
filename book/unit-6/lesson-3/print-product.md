# Print Product

`Download starter code`

Write a static method `printProduct` that accepts a `Scanner` reading input from a file containing a series of integers and calculates their product, printing the result to an output `PrintStream` parameter. For example, if the input file numbers.txt contains: 

```text
1 6 2 3 5 4 
```

Then your method could be called in the following way: 

```java
Scanner input = new Scanner(new File(“numbers.txt”)); 
PrintStream output = new PrintStream(new File(“output.txt”)); 
printProduct(input, output); 
```

And it would calculate the product of all the numbers and output the following to output.txt: 

```text
1 * 6 * 2 * 3 * 5 * 4 = 720 
```

How could you use this method to print the result to the console instead of an output file?