# Overview: Abstract Data Types



## 🤔 Collections

In the previous lessons, we learned about the `ArrayList` datatype and its applications. This serves as our first look at a larger set of related datatypes, known as `Collections`. A `Collection` simply represents a group of objects that we refer to as its *elements*; in other words, a `Collection` is a group of individual objects which are represented as a single unit.

The `ArrayList` functions as a `Collection` very similarly to the arrays that we have been dealing with for a while now, allowing us to access any element via its index. The main difference is that the `ArrayList` is a dynamic structure that allows us to freely change its size / the number of elements within it, whereas an array is static and must have its final size declared upon initialization.

It turns out that `ArrayList` is just one example of a data structure, and we will learn many more in this class. One important concept when we consider data structures is separating out the specification implementation of a data structure and the set of behaviors we would like to use it for. 

The idea is that we might have some abstract notion of what a list is -- an indexed sequence of values we can add/remove dynamically -- and the `ArrayList` is just one possible implementation of that idea, and other different implementations might exist.

## 🧩 Abstract Data Types

This leads to the concept of an **abstract data type** or **ADT**,  which is a description of the behaviors a data structure can do. For example, we can consider the **List ADT** as an indexed sequence of values that dynamically grows/shrinks as values are added/removed. 

This inspired the `List` interface in Java that we learned last time. We will discuss interfaces later this quarter, but essentially an interface is a description of what methods an object must have. However, interfaces do not provide a concrete implementation.

Because an interface does not provide a concrete implementation, *other objects* can implement these behaviors differently, just like how two students can write different solutions to the same programming assignment. In Java, there is another implementation of the `List` interfaced called a `LinkedList`. So, for example, you could make a `List` using the `LinkedList` implementation with the following line of code:

```Java
List<String> list = new LinkedList<>();
```

## ❓ ArrayLists vs LinkedLists

Thankfully because of this separation of a List ADT as the `List` interface, you already know how to use a `LinkedList`. It has all of the methods of `ArrayList` that you are familiar with, such as `add(value)`, `remove(index)`, `get(index)`, and so on. 

You might be wondering:  If `ArrayList` and `LinkedList` have all the same methods, why use one over another? This is subtle question that we will actually explore more in CSE 123. The high-level idea is that the different implementations are optimized so that certain operations on one are more efficient while certain operations on the other are more efficient. If you want to learn more about that, you should take CSE 123! 

The reason we introduce the concept of an ADT now is that we will see this pattern of having an interface for something describing what an object can do and potentially various implementations of those interfaces. We will introduce more such ADTs and implementations in this course.

## 🤓 Recap of Terms

* **Abstract Data Type** or **ADT**: A description of the idea of a data structure including what operations are available on it and how those operations should behave. For example, the English explanation of what a list should be.

* An **interface** is a Java construct that lets programmers specify what methods a class should have. For example the `List` interface in java.

* An **Implementation** of an interface is concrete code that meets the specified interface. For example, the `ArrayList` and `LinkedList` classes that implement the `List` interface.

## 🧠 Main Points

* `Collections` represent a group of objects, and each object within the `Collection` is referred to as an **element**. 

    * `Collections` allow us to manage and manipulate multiple objects as a single unit.

* `Abstract Data Types (ADTs)` describe the behaviors and operations that a data structure can perform. For example, the List ADT represents an indexed sequence of values that can dynamically grow or shrink as elements are added or removed.

* `Interface`s specify what methods an object must have without providing a concrete implementation. For example, the List interface defines the methods that a list-like data structure should support, such as adding, removing, and accessing elements.

* There can be multiple `implementation`s from one `interface`. For example, both ArrayList and LinkedList are implementations of the List interface. Different implementations can have different advantages and disadvantages that will be further discussed in CSE 123!