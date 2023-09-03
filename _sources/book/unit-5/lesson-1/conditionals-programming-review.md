# Conditionals Programming Review

# Challenge Problem [Optional]

`Download starter code`

Complete the static method called quadrant that takes as parameters a pair of real numbers representing an (x, y) point and that returns the quadrant number for that point. Recall that quadrants are numbered as integers from 1 to 4 with the upper-right quadrant numbered 1 and the subsequent quadrants numbered in a counter-clockwise fashion:

![Image of the four quadrants of the conditional plane. Quadrants 1 has positive x and y values. Quadrant 2 has negative x and positive y values. Quadrant 3 has negative x and y values. Quadrant 4 has positive x and negative y values.](images/quadrants.png)

Notice that the quadrant is determined by whether the x and y coordinates are positive or negative numbers. If a point falls on the x-axis or the y-axis, then the method should return 0. 

:::{attention}
Think about which conditional structure is stylistically most appropriate for this program!
:::

## Starter Code
**Quadrant.java:
```java
public class Quadrant {
    public static void main(String[] args) {
        System.out.println(quadrant(12.4, 17.8));
        System.out.println(quadrant(-2.3, 3.5));
        System.out.println(quadrant(-15.2, -3.1));
        System.out.println(quadrant(4.5, -4.5));
        System.out.println(quadrant(0.0, 0.0));
        System.out.println(quadrant(12.5, 0.0));
        System.out.println(quadrant(0.0, 2.3));
    }

    /* TODO */
    // Finish the method with the most appropriate 
    // conditional structure using the pseudocode below 
    public static int quadrant(double x, double y) {
        // if x is positive and y is positive
            // the point is in quadrant 1

        // if x is negative and y is positive
            // the point is in quadrant 2
        
        // if x is negative and y is negative
            // the point is in quadrant 3

        // if x is positive and y is negative
            // the point is in quadrant 4

        // HINT: is there any case we're missing?
    }
}
```