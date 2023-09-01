# 2D Array Practice



Consider the following code: 

``` Java
public void mystery2(int[][] data, int pos, int rows, int cols) {
    for (int i = 0; i < rows; i++) {
        int sum = 0;
        for (int j = 0; j < cols; j++) {
            sum = sum + data[pos + i][pos + j];
        }
        System.out.print(sum + " ");
    }
    System.out.println();
}
```

Suppose that a variable called `grid` has been declared as follows:

``` Java
int[][] grid = {{4, 6, 8, 8, 2, 1}, 
                {7, 4, 8, 8, 7, 7},
                {7, 8, 6, 6, 7, 2}, 
                {1, 2, 2, 7, 5, 7},
                {8, 3, 6, 6, 1, 1}, 
                {9, 7, 9, 6, 6, 1}};
```

For each call below, indicate the output that would be produced. 

**Question 1**

`mystery2(grid, 0, 2, 2);`

:::{admonition} See Answer
:class: dropdown
10 11
:::

<hr>

**Question 2**

`mystery2(grid, 2, 3, 2);`

:::{admonition} See Answer
:class: dropdown
12 9 12
:::

**Question 3**

`mystery2(grid, 1, 4, 1);`

:::{admonition} See Answer
:class: dropdown
4 8 2 3
:::