# Queues



<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/ehLgJ74ld3w" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 122 - PCM - Queues**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

We will see that different situations call for different ADTs that best fit the task. Consider the example of software a hospital might use to track who is waiting in line and who should be helped next. For simplicity, assume this hospital always helps the person next in line.

Now they could use a list to do this, but a list is a little too general for the task. We've seen that a list allows programmers to insert values at any point, which in this simplified example, might not be appropriate. Sometimes having something too general for a task can be a drawback because of its extra functionality introducing room for programming error. 

To reduce the risk of errors, it's often best to use an ADT that's just general enough for task. So let's introduce a new ADT that works perfectly for situations like this hospital.

## Queues

A queue is an ADT representing a *First-In, First-Out* (FIFO) structure. This means that the first value added to the queue should be the first one removed. Conceptually we can think of a queue as a line where values are added in the back and removed from the front. 

![There is a horizontal black arrow pointing to the left. At the top of the arrow, there's a text labeling it "front" and below, the words "peek" and "remove" are there. It's connected to 4 blue boxes aligned horizontally next to each other. First box on the left is named "Miya", 2nd is named "Hunter", 3rd is named "Brett", and the 4th is named "Elba". To the right of the boxes, there's another horizontal black arrow pointing to the boxes. Above the arrow, it's labeled "back" and below, the text "add" exists. ](images/queue.png)

In this picture, we see a queue with the list of names (from front to back) being "Miya", "Hunter", "Brett", and "Elba". We are able to peek and remove from the front of the queue aka "Miya", and we can add at the back of the queue aka "Elba".

So in some sense, a queue is similar to a list in that it stores multiple elements in a sequence but differs in two major ways:

* Values can only be added to the end of the queue and removed from the front.

* There is no notion of indices in a queue, so it is not possible to access the a value at index 3.

## 🚶‍♂️ `Queue`

Java provides a `Queue` interface to represent this idea. It turns out that the `LinkedList` class is the implementation of the `Queue` interface. To make a queue, we would write:

```java
Queue<String> queue = new LinkedList<>();
```

The `Queue` interface provides the following methods. There are technically more methods in Java's `Queue`, but we'll only ask you to use the following methods in CSE 122:

* `add(value)`  - Adds a value to the end of the queue

* `remove()` - Removes and returns the value from the front of the queue

* `peek()` - Returns the value from the front of the queue without removing it. Useful for inspecting what is at the front.

* `size()` - Returns the number of elements in the queue

* `isEmpty()` - Returns `true` if the queue is empty, `false` otherwise.

:::{admonition} Note
:class: note

A useful analogy for a Queue is that of standing in line at a store, aka standing in a "queue". As new people arrive, they are told to go to the back of the line. When the store clerk is ready to help the next customer, the person at the front of the line is helped first. 
:::

Below is a code example that shows a longer program using a queue and its methods. It demonstrates a useful pattern of traversing a queue by repeatedly calling the `remove` method until the queue `isEmpty` (lines 24-27).

```java
import java.util.*;

public class ExampleQueue {
    public static void main(String[] args) {
        String[] people = {"Miya", "Hunter", "Brett", "Elba"};

        Queue<String> storeLine = new LinkedList<>();

        System.out.println("Adding to storeLine:");
        for (int i = 0; i < people.length; i++) {
            String person = people[i];
            storeLine.add(person);
            System.out.println("   " + person + " (state of storeLine" + storeLine + ")");
        }
        System.out.println();

        System.out.println("Size of storeLine: " + storeLine.size());
        System.out.println("Contents of storeLine:");
        System.out.println("   " + storeLine);
        System.out.println();

        // Queue traversal pattern
        System.out.println("Removing from storeLine:");
        while (!storeLine.isEmpty()) {
            String person = storeLine.remove();
            System.out.println("   " + person);
        }
    }
}
```

## 🧠 Main Points

* To reduce the risk of errors, we want to choose an ADT that is just general enough for the task we want to achieve (but specific enough to the task at hand). For some tasks, such as figuring out a line at a hospital, a `Queue` might be a useful ADT.

* A `Queue` is an ADT that represents a *First-In, First-Out* (FIFO) structure. The first value that we added to the `Queue` will be the first value removed, and new values are always added to the end/back of the `Queue`.

    * This is very similar to how a grocery line works - the first person who stood in line gets to check out first, and the most recent person in the line must join the back of the line.

* A `LinkedList` is one implementation of a `Queue`. Thus, to make a new `Queue`, we use the following syntax:

    * `Queue<Type> queue = new LinkedList<>()`

* `Queues` come with many methods we can use, including 

    * `add(value)`  - Adds a value to the end of the queue

    * `remove()` - Removes and returns the value from the front of the queue

    * `peek()` - Returns the value from the front of the queue without removing it. Useful for inspecting what is at the front.

    * `size()` - Returns the number of elements in the queue

    * `isEmpty()` - Returns `true` if the queue is empty, `false` otherwise.

* When traversing through a `Queue`, we will repeatedly use the `.remove()` method until our `Queue` is empty so that we can process elements in a *FIFO* manner.