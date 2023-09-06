# Sum

`Download starter code`

This problem has two primary tasks:

## Task 1 - buildQueue

Write a method called `buildQueue` that takes a number `n` as a parameter and returns a `Queue` of integers with the value `1` at the front and `n` at the end.

For example, `buildQueue(5)` should return the queue

```java
[1, 2, 3, 4, 5]
```

If `n` is less than 1, an empty queue should be returned.

## Task 2 - Sum

Write a method called `sum` that takes a `Queue` of integers as a parameter and returns the sum of all of the values in the queue.

So for example if you had the queue

```java
[1, 2, 3, 4, 5]
```

Your method should return `15`