---
layout: default
title: Reges Lecture Notes
parent: CSE 143
grand_parent: Computer Science
nav_order: 1
---

# Stuart Reges Lecture Notes

CSE 143
{: .fs-6 .fw-300 }

---

## Navigation

Week 1
- [Monday - `ArrayIntList` Add, Remove, toString Methods](#week-1-monday---arrayintlist-add-remove-tostring-methods)
- [Wednesday - `ArrayIntList` Methods](#week-1-monday---arrayintlist-methods)
- [Friday - Interfaces and Sets](#week-1-monday---interfaces-and-sets)

Week 2


---

## Week 1 Monday - ArrayIntList Add, Remove, toString Methods
- CSE 143 centers around data structures (linked lists, binary trees, Collections classes), as well as recursion for control.
- Riel's perspective of an objective: external vs internal views.
  - External: client side, *what* an object does
  - Internal: implementation, *how* an object works
- Running data structure: `ArrayList<E>`. `ArrayList` that can store different types of elements.
- Ideally, you should work in a programming environment. Recommended environment is JGrasp.

`ArrayList` review:

```java
ArrayList<String> list = new ArrayList<>();
list.add("four");
list.add("score");
list.add("seven");
list.add("years");
list.add("ago");
list.add(2, "and");
```
Appends items to the end at default. If an index is provided, inserts at that index.

*How is this done?* The `ArrayList` can be thought of as growing and shrinking, but it's not actually growing and shrinking inside.

Two numbers to think about: capacity and size.
- A variable size is used to keep track of how many 'things' are currently inside the structure.
- Arrays have a certain associated capacity

**Let's think about implementing the internal representation for `ArrayIntList`.**

Initializing the class fields:
```java
public class ArrayIntList {
  int[] elementData;
  int size;
}
```

> Style Issue Notice (!)

Never initialize values outside of a constructor function.
```java
public class ArrayIntList {
  int[] elementData = new ...;
  int size = ...;
}
```
Instead, use a constructor function:
```java
  public ArrayIntList() {
    elementData = new int[100];
    size = 0;
  }
```

The `ArrayIntList` object should include a method to add new elememnts. We rely upon the internal state of `size` to determine which slot in `elementData` to use.
```java
  public void add(int value) {
    this.elementData[size] = value;
    this.size++;
  }
```

You want to have a `toString()` method in your function to display the desired representaiton when `System.out.print` is called.

Next lecture -- it will be important to use the keyword `private` for fields.

---

## Week 1 Wednesday - ArrayIntList Methods

CSE Grades by Lectures Watched from Spring 2021:

| Lectures Watched | # Students | Avg Grade |
| --- | --- | --- |
| 90-100% | 121 | 3.32 |
| 80-90% | 113 | 3.06 |
| 70-80% | 31 | 2.88 |
| 60-70% | 24 | 2.86 |
| 0-60% | 126 | 1.97 |

In this class, many resources are presented (lecture, section, textbook). You do not need to utilize all of them.


`toString()` methods allow us to print a representation of the method. When calling `System.out.println(obj)`, the `toString` method of `obj` is implicitly called. The same occurs with String arithmetic: `"hello " + obj`.

**Use this class' `ArrayIntList` as an example for Homework 1.**

> OOPSLA: An object encapsulates state and exposes behavior.

- *State*: represents by fields, the data an object keeps track of.
- *Behavior*: represented by methods.
- *Encapsulation*: the client cannot 'reach right in'; the internal functionalities and operations are kept protected/encapsulated. We can utilize the `private` keyword for object fields to achieve encapsulation.

*Make sure to look at style issues for a particular homework.*

While the client should not be able to *modify* certain fields, we can create *getter methods* that return the value of a field.

Contract with the client: `pre/post` format.
```java
// contract
// pre : index >= 0 and index < size
// post: returns the value at a given index

public int get(int index) {
  if (index < 0 || index < size) {
    throw new ExceptionType(message);
  }
  return elementData[index];
```

Overloading: two different constructors.

Adhere to Boolean Zen: directly return the result of a conditional if a Boolean output is desired.

`private` means accessible to the class, including all instances of that class.

---

## Week 1 Friday - Interfaces and Sets
- Now, we are beginning to discuss content relevant to Homework 2.
- Monday and Wednesday were about making different methods work - implementing data structures.
- Now, we are going to be the client of a data structure.
- **Abstraction**: an important concept in computer science.
  - Separating the essential properties of something from the unimportant details.
  - Essence of Computer Programming - controlling complexity.
  - We create incredibly complex software products.
- Space Needle Assessment in CSE142 - while there are many details involved in drawing the ASCII art (for loops, ifs, repetition, etc.), we are fundamentally drawing different components - the base, the needle, etc.
- **Interface**: list of behaviors (API)
- Various relevant methods: setting, getting, obtaining the size, removing, adding, clearing, contains-checking.
- **Diamond operator**: inferencing the object type instead of repeating it.

```java
ArrayList<String> list = new ArrayList<>();
```

- **You must use the appropriate interface**:
  - ...when declaring variables
  - ...when declaring parameters to a method
  - ...when introducing fields into a class
  - ...when using a return type for a method

```java
// correct usage

// as a variable
List<String> list = new ArrayList<>();

// as a parameter
public void doSomething(List<E> list) {
  ...
}

// as a return type
public List<E> do Something(...) {
  ...
}

// as a field
private list<E> data;
```

- We use the `List` interface, but when we are actually creating the object via `new`, we use `ArrayList` to be more explicit/specific.
- Write your code in a method that suits the *desired function/behavior* rather than the specific implementation.
- `List` can refer to an `ArrayList`, `LinkedList`, etc.: any list that implements an interface.
- `ArrayList` traversal: could use `for (int i = 0; i < list.size(); i++) {...}`.
- `foreach` loop (we have an affair between Microsoft, Sun, Java, C++, and C# to thank for this): allows for simple traversal if you desire only to get elements of a list rather than indexes. Is a read-only operation; you cannot change values in the structure.

```java
for (String s : list) {
  ...
}
```

- `Iterator`: a special kind of object used to perform a traversal.

Three key `Iterator` functions:

| Method | Function |
| --- | --- |
| `hasNext()` | Are there any elements left to see? |
| `next()` | Returns the next value and moves to the next element. |
| `remove()` | Removes the value most recently returned by `next()`. |

- Limitations: you cannot call `remove` directly after initialization, or twice consecutively without calling `next()`.
- Ask Java to create an iterator from a List for you.

```java
Iterator<String> iter = list.iterator();
while (iter.hasNext()) {
  String next = iter.next();
}
```

- Primitive types in Java are all lowercase; Java does not allow you to use a primitive type in declaring a list of `E`.
- Wrapper classes are classes of objects that have only one purpose: to wrap up a primitive into a non-primitive version.

```java
List<Integer> list = new ArrayList<>();
Set<Integer> set = new TreeSet<>();
```

- **Sets**: the client is not able to choose the order of a set (for `TreeSet`).
- When using `.remove` with sets, the parameter is the *value* rather than the index. There is no concept of index in a set.
- A `foreach` loop works with set traversal, but no modification is possible.
- If you desire to loop through while modifying, use an `Iterator`.
- When using a structure, do not 'talk' to the structure; the *iterator* is supposed to talk to the structure. Interact with the structure via the iterator.


---

## Week 2 Monday - Queues and Stacks
- We'll be looking at content relevant to Week 2.
- In CSE 142 - emphasized control abstraction about the flow of control through methods.
- In CSE 143 - data abstraction.
- Abstract Data Types (ADT) - quite old abstraction ideas.
- Java gives us interfaces as methods to capture ADTs.
- ADTS: list, set, stacks, queues.
- Why use a stack or queue when you can use a list? Understand that stacks and queues are simpler and operate within certain restrictions.
- Good experience to work with a limited data structure.
- FIFO - First In, First Out. LIFO - Last In, First Out.
- Don't use the `peek()` operation on exam operations, but you may use it on the homework.
- There is no interface for `Stack`; it is its own class.
- Make sure to use `import java.util.*`.
- You can have objects that implement multiple interfaces; for instance `LinkedList` implements both `List` and `Queue`.
- Pay attention to **reference semantics**
- Never use comparators for equality with Booleans; this violates Boolean zen.
- Important queue technique: take something from the front, do something with it, and put it back at the end.m
- Make sure in a for loop that you account for changes in the counter and the condition.

---

## Week 2 Wednesday - Interfaces and Arrays of Objects
- In CSE 143, a common approach to reducing redunancy is simply to write a new method.
- Overloading - two versions of the same method that tkae in different sets of parameters/have a different signature.
- HDMI port as an interface analogy.

```java
public interface IntList {
  public int size();
  public int get(int index);
  public String toString();
  public int indexOf(int value);
  public void add(int value);
  public void add(int index, int value);
  ...
}
```

- An interface is a list of required behaviors (methods).
- A 'certification' 
- Must indicate that a method implements an interface in the method header.
- When you construct an array, Java will initialize all items to the '0' equivalent - `false`, `0`, `null`.
- When you implement an interface, it is a minimum set of methods; however, a variable declared with an interface is *restricted to the methods outlined in the interface* (even if the other object has additional methods).

---

## Week 2 Friday - Linked Lists
- Need to recognize the difference between data and a reference to data. *Reference semantics*.
- We have been looking at array storage.
- Arrays have random access - we can quickly jump around the structure. Linked Lists have sequential access.
- If we want to remove values, we need to shift values down; `ArrayList` is not used to implement the `Queue` interface because everything needs to be shfited down.
- Linked Lists are slow for traversal.
- Singly and doubly linked lists.
- Recursive structure - defined in terms of itself.
- Reference - "Java is a language without pointers". Pointers and references are the same thing.
- References are memory locations, an address in memory.
- Difference between a variable and an actual node; things come into existence when you call `new`.
- `.` - dereferencing operator. Goes inside the object.
- Circular linked list
- To write generalized linked lists, we need to use loops.
- Garbage collector - looks for stray references that are unreachable; memory space is reclaimed.
- If you want to keep part of a list, you need to create a temporary variable to store it.
- Temporary variables are not nodes - they are references to actual nodes.
- Understand comparison between `current.next != null` and `current != null`
- Make sure to check for edge cases - null or low-element list








