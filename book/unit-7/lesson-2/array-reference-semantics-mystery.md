# Array Reference Semantics Mystery

These questions are to assess your understanding of the differences between value and reference semantics in Java.

What values are stored in the array at the comment in main? Note that the incrementAll method returns void, but does take an int[] parameter.

``` Java
public static void main(String[] args) {
    int[] nums = {2, 4, -1, 3};
    incrementAll(nums);

    // HERE!
}

public static void incrementAll(int[] data) {
    for (int i = 0; i < data.length; i++) {
        data[i]++;
    }
}
```

:::{admonition} See Answer
:class: dropdown

The elements are 3, 5, 0, 4.

``` text
nums[0] = 3
nums[1] = 5
nums[2] = 0
nums[3] = 4
```
:::