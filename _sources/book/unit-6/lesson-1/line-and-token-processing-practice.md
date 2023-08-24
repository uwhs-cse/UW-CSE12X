# Combining Line and Token Processing

`Download starter code`

These questions are to assess your understanding of file processing in Java and different approaches to processing a file.

To the right, we have again provided some code that attempts to read from a `File` and print to the console, this time maintaining the line structure present within the `File`. We've also again conveniently forgotten to include some parts of the code, and have left them as an exercise to you. The three parts of the code you must adapt are marked by `/* YOUR CODE HERE */` comments. You must first successfully scan in a line of input from the file, you must then pass the correct variable into the `new Scanner()` call to create a `Scanner` over the line from the `File`. You must finally, choose the correct bound for the `while` loop; remember that we are processing this line token by token! Similarly to the last code challenge, you should follow each token with a space, " ". You do not need to remove any trailing whitespace from the end of the lines that you print.