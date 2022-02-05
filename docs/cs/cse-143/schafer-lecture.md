---
layout: default
title: Schafer Lecture Notes
parent: CSE 143
grand_parent: Computer Science
nav_order: 2
---

# Hunter Schafer Lecture Notes
{: .no_toc }

CSE 143
{: .fs-6 .fw-300 }

---

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

## Lecture 1: Syllabus and ArrayIntList
- Collection: an object that stores data, a data structure.
- Objects stored are elements
- Common operations: add, remove, store, access, etc.
- `ArrayList`; tell it what type it stores. `ArrayList<String> list = new ArrayList<String>();`.
- `.remove(index)` and `.add(index, value)`.
- *Overloading* - different versions of `.add()` depending on which sets of parameters are passed.

---

## Lecture 2: More ArrayIntLIst, Pre-Post, Exceptions
- Class vs object. Class is a program entity, defines a blueprint. Object is an entity that combines state and behavior.
- `private` keyword - client cannot mess with the internal state.
- Class design
- Getter/setter methods

---

## Lecture 3: Lists, Sets, For-Each Loop
- You can have multiple constructors that take in different version of parameters.

```java
public ArrayIntList() {
  this(INITIAL_CAPACITY);
}

public ArrayIntList(int capacity) {
  doStuffWithCapacity();
}
```
- Different types of collections: building up a series of tools
- List: a collection of elements with 0-based indexes.
  - `LinkedList`, `ArrayList`, etc.
- Abstract Data Type: general description of a collection.
- Implemented as an *interface*: a description of the generalized idea
- Minor drawback: in cases where you need a restrictive type of implementation, interfaces cause problems.
- Wrapper Classes: you cannot put primitive types in wakkas. Use wrapper types that map onto primitive types; `List<Integer> numbers = newArrayList<Integer>();`.

---

## Lecture 4: Stacks and Queues
- Never destroy queue/stack structures

---

## Lecture 5: Arrays of Objects, Interfaces
- Reference semantics
- Linked Lists are some of the more difficult parts of CSE 143: make sure you understand reference semantics.
- You need `this.var` in a parameter with `x`; using `x = x` (with `x` being a field variable) doesn't actually change the field variable value.
- Looping over data is where inefficiency comes.
- We can use a *Set*.
- `foreach` loops - you cannot modify the text.
- Syntactic Sugar: code that really is shorthand for actual code.
- Behind the scenes of the `foreach` loop, Java is using an iterator.
- Iterator is like a scanner: an interface.
  - `hasNext`
  - `next`
  - `remove`
- All collection objects have  an `.iterator()` method.
- Only use `Iterator` if you need to (i.e. to remove).

---

## Lecture 6: LinkedList Nodes
- Assymetry: left-hand side is variable, right-hand side is field. We evaluate the field, find what is inside the box. The left side is the box.

```java
list1.next = list2.next;
```

----

## Lecture 7: LinkedIntLists and Loops
- Implementing list-like operations, like adding and removing.
- To traverse a list, we make a new reference. `ListNode curr = list;` is not creating a new `ListNode`.
- Encapsulate ListNodes so the client does not need to think about it.
- To add elements to a list: go to the very end of the list and add a new node.

---

## Lecture 8: Advanced LinkedIntList
- Especially when writing Linked List code, think about edge cases and try to break your code.
- You can simplify your code, but focus on reducing objects, not necessarily variables/references
- To change, we need to stop one before and use `curr.next != null` as condition.

---

## Lecture 9: Binary Search and Complexity
- Efficiency: measure of computing resources used by code. Can be relative to speed, memory, etc. 
- We want to compare different algorithms to see which is more efficient.
- Instead of running time experimentally/empirically by manually timing - a process which is heavily influenced by computing environment factors - we define efficiency as the number of operations run, assuming each operation runs for about the same amount of time.
- Complexity class - a family of how algorithms grow together.
- When measuring complexity, we drop all terms of lower complexity.
- Report the worst possible complexity if there are multiple types.
- Binary search - locate the target value in a sorted array or list by successively eliminating half of the array from consideration.

---

## Lecture 10: Maps
- `TreeMap` vs `HashMap`
- `TreeMap` runs in `O(log N)`, `HashMap` runs in `O(1)`. `TreeMap` uses a linked binary tree, which allows for easy sorted storage.
- `.put()`, `.get()`.

---

## Lecture 11: More Maps
- Reference semantics and modification elegance

```java
Set<String> s = friends.get("Taylor");
s.add("Hunter");
friends.put("Taylor", s);

// can be written more elegantly as

friends.get("Taylor").add("Hunter");
```
- Iteration over key/value pairs by iterating over the key set and reference associated value for each key.
- Breadth-first search in graphs using self-referencing maps
- Stopping infinite recursion with checks

---

## Lecture 12: Recursion
- Recursion: solving a problem by breaking it into smaller problems and solving each. Solving self-similar tasks.
- Recursion: the definition of an operation in terms of itself.
- Recursion: see "Recursion".
- Recursive programming: writing methods that call themselves to solve problems recursively.
- Sometimes, certain patterns lean nicely into a recursive solution.
- Base case and recursive cases must be specified in a recursive function.
- The semantics of recursion are controlled in the call stack.

---

## Lecure 13: More Recursion, Public/Private Pairs






