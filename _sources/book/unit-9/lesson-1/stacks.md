# Stacks



<div style="position: relative; padding-bottom: 62.5%; height: 0;">
    <iframe src="https://www.youtube.com/embed/yQ3JvLsR9UM" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

:::{admonition} Note
:class: note

Above, you'll see there's a video titled **CSE 122 - PCM - Stacks**. The video and the reading both have the same information! You're not required to go through both the video and the reading, as the video just walks through the reading to help contextualize it!
:::

Another example of a different ADT could work better in different situations: Consider the web browser you use (e.g., Chrome,  Firefox, Safari, Arc, ...) and the core feature of a back button. Every time you visit a new link, a new website is added to your history. 

When you press the back button, you go back to the previously visited page, and it's removed from the set of pages that the back button will take you to (pressing back again takes you to the page before that one).

What if we tried to use a queue to represent this? Well every time we visited a site we would add it to the back of the queue. But what if the user presses the back button? We, unfortunately, can't easily remove the value from the back of the queue since we can only remove from the front! So a queue wouldn't be a good choice of an ADT to represent the back-button history.

![There is a horizontal black arrow pointing to the left. At the top of the arrow, there's a text labeling it "front" and below, the words "peek" and "remove" are there. It's connected to 4 blue boxes aligned horizontally next to each other. First box on the left is named "CSE 122 Website", 2nd is named "Twitter", 3rd is named "Ed", and the 4th is named "Youtube". To the right of the boxes, there's another horizontal black arrow pointing to the boxes. Above the arrow, it's labeled "back" and below, the text "add" exists. ](images/queue-example.png)

In this example, we have a queue with the CSE 122 Website at the front (where we can peek at an element or remove it), followed by Twitter, Ed, and then YouTube at the back (where we can add another element). If we represent our website exploration with a queue, then the very first website we visited, the CSE 122 Website, will be the one that we remove or present to the user. 

## 💌 Stacks

So let's introduce one different ADT that will be helpful here: **Stack**. A Stack is somewhat similar to a Queue in that it limits where a user can add/remove values. A Stack operates like a stack of plates. Every time you add a value it goes on top of the Stack. 

When you remove a value, you also remove from the top; like the easiest plate to grab from a stack of plates is the one at the top.  We call stacks a *Last In, First Out* (LIFO) structure where the we are always adding/removing from the top.

:::{admonition} Note
:class: note

A good way of thinking about stacks is trays in a cafeteria. When you take a tray, you take it from the top of the stack of trays, and when you put a tray back, you also put it back on the top of the stack of trays.
:::

Visually, our browser example would look like the following with a Stack. Every time we visit a page it's added to the top. When the user presses back we remove the last visited page from the top of the stack.

![There are 4 vertical blue boxes stacked on top of each other. Near the bottom of the stack, there's a text on the left labelling it "bottom" and near the top of the stack, there's another label "top". Starting from the box on the bottom, the first box is labelled "CSE 122 Website", the 2nd is "Twitter", the 3rd is "Ed", and the 4th is "Youtube". There are two vertical arrows at the top of the stack: the one on the left side points down to the stack and the one on the right side points away from the stack. Near the left side of the left arrow, there's a text "push". Near the right side of the right arrow, there's text "pop" and below that "peek". ](images/stack.png)

In this pictorial representation of our Stack, the CSE 122 website was the one we visited first, so it is at the bottom of the Stack, and then increasing from bottom to top we have the Twitter, Ed, and YouTube websites. The YouTube website is at the top of the Stack, and we can push, pop, and peek at the top of the Stack. Therefore, since we visited YouTube most recently out of all the websites, we will see YouTube when we hit the back button.

## 📥 `Stack` interface/implementation?

Unfortunately, the Stack in Java is designed a bit less well when compared to Queue. There is no Stack interface and a separate implementation. Instead, we just have a `Stack` class without an interface. To make a `Stack`, we write

```java
Stack<String> stack = new Stack<>();
```

`Stack`'s have the following methods. There are technically more methods in Java's `Stack`, but in CSE 122, we will ask you only to use these methods.

* `push(value)`  - Adds a value to the top of the stack

* `pop()` - Removes and returns the value from the top of the stack

* `peek()` - Returns the value from the top of the stack without removing it. Useful for inspecting what is at the top.

* `size()` - Returns the number of elements in the stack

* `isEmpty()` - Returns `true` if the stac is empty, `false` otherwise.

Take a look at this runnable example of a `Stack` in action below:

```java
import java.util.*;

public class ExampleStack {
    public static void main(String[] args) {
        String[] plates = {"plate 1", "plate 2", "plate 3", "plate 4"};

        Stack<String> s = new Stack<>();

        System.out.println("Pushing onto stack:");
        for (int i = 0; i < plates.length; i++) {
            String plate = plates[i];
            s.push(plate);
            System.out.println("   " + plate + " (state of s=" + s + ")");
        }
        System.out.println();

        System.out.println("Size of stack: " + s.size());
        System.out.println("Contents of stack:");
        System.out.println("   " + s);
        System.out.println();

        System.out.println("Popping from stack:");
        while (!s.isEmpty()) {
            String plate = s.pop();
            System.out.println("   " + plate + " (state of s=" + s + ")");
        }
    }
}
```

Note that when printing the `Stack` it displays the values from the bottom on the left to the top on the right.

## 🧠 Main Points

* When trying to implement a back button on a web browser, we realized that implementing it via a `Queue` wouldn't allow us to access the website we most recently visited. Thus, we needed a new ADT to represent a web browser's back button - a `Stack`.

* A `Stack` is an ADT that is a *Last In, First Out* (LIFO) structure. It's just like a stack of plates - when we add a value, it goes on top, and when you remove a value, we also remove it from the top.

* We create `Stack`s using the following syntax: `Stack<Type> stack = new Stack<>();`

    * Java has a `Stack` class but no separate `Stack` interface.

* `Stack`s come with many methods we can use, including :

* When traversing through a `Stack`, we will repeatedly use the `.pop()` method until our `Stack` is empty so that we can process elements in a *LIFO* manner.