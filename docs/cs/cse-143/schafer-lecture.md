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
- Each method call contains its own local variables; method variables cannot communicate across each other.
- Private/public pairs for recursions; same name but different signature.
- Mixing looping and recursion
- Language: a set of words or symbols.
- Grammar: a description of a language that describes which sequences of symbols are allowed in the language.
- BNF grammar form
- Terminal - a fundamental symbol in the language.
- Non-terminal - a high-level symbol describing language abstractions or constructs
- Regular expressions and `.split()` to break up text

---

## Lecture 15: Exhaustive Search
- Applications of recursive programming to solve a variety of general problems.
- Backtracking/exhaustive search.
- Ordering a search via systematic ordering/process.  
- Decision trees

```java
public static void fourAB(String soFar) {
  if (soFar.length() == 4) {
    System.out.println(soFar);
  } else {
    fourAB(soFar + "a");
    fourAB(soFar + "b");
  }
}

public static void main(String[] args) {
  soFar("");
}
```

- Backtracking sequence:
  1. Choose
  2. Explore
  3. Backtrack/undo

---

## Lecture 16: More Recursive Backtracking
- Exploring all possibilities: trying every possibile outcome until something works.
- Spot and eliminate dead ends - or else you will get stack overflow errors.
- 8 queens problem

---

## Lecture 17: Sorting

---

## Lecture 18: Midterm Review

---

## Lecture 19: Midterm (No Class)

---

## Lecture 20: Binary Trees
- Trees in computer science - `TreeMap`/`Tree-Set`, folders/files, decision trees, compilers and parse trees
- Tree: Nodes linked together in some hierarchical fashion
- Binary tree: a tree where each node has at most two children
- Recursive definition - a tree is either empty or a root node with data, a left subtree, and a right subtree.
- `TreeNode`
- Node - any object containing a data value and left/right children
- Root - topmost node of a tree
- Leaf - a node that has no children
- Branch - any internal node that is neither the root nor a leaf
- Height - longest distance between the root and a node
- `IntTree` interface
- Tree traversal - preorder, postorder, inorder.
  - Difference - where the current node is being traversed.

---

## Lecture 21: Binary Search Trees
- Manually writing the addition of nodes is kind of tedious, a bit like linked list programming.
- Contains method - we either get to an empty tree, or a full tree. Worst traversal is `O(n)`.
- We can make it faster with `O(log n)` runtime.
- Applying binary search to binary search trees.
- Binary Search Trees (BSTs) - binary tree where each non-empty node R has the following properties:
  - elements of R's left subtree contain data less than R's data
  - elements of R's right subtree contain data larger than R's data
  - R's left and right subtrees are also binary search trees
- We can search BSTs very quickly due to their predisposition to binary search.
- An inorder traversal is a sorted traversal for a binary search tree.
- BSTs don't have a powerful enough tree to ensure `O(n)`
- Degenerate case - trees that are not balanced and have the worst runtime
- Method scoping
- Adding

```java
private IntTreeNode add(IntTreeNode root, int value) {
  if (root == null) {
    root = new IntTreeNode(value);
  } else if (value < root.data) { 
    root.left = add(root.left, value);
  } else {
    root.right = add(root.right, value);
  }
  return root;
}
```

---

## Lecture 22: Comparable
- Last time, finalized most content with a binary tree. Different tree traversals, writing code that builds a tree, etc.
- Binary search property
- Adding nodes that maintain the binary search property
- The `x = change(x)` pattern.
- Don't fight the recursive definition of a tree.
- Mechanics for sorting objects, like strings and points
- We need a way to communicate to Java how to compare different objects.
- `compareTo` is a replacement for `<`, `>`, `==`. `compareTo` returns a value less than 0 if it comes 'before' the `other`, a value larger than 0 if it comes 'after' the `other`, and a value equal to 0 if it is 'equal' in ordering to `other`.
- `Interface` - a promise to provide certain functions. Implementing the `Comparable` interface allows for comparison.
- Generics - `Comparable<E>`, `E` is a placeholder for objects.
- Shortcut with `int` types - simply return the difference
- Breaking ties - return alternative.
- Always use if/else unless you are working with `int`s.
- You can use `.compareTo` with Strings if you want to compare their `String` values.

---

## Lecture 23: Priority Queues and Huffman Encoding
- Priority Queue: a collection of ordered elements that provides fast access to the minimum or maximum element.
- Instead of being FIFO, pulls things based on a priority.
- Implements the `Queue` interface.
- Removes with the highest priority (e.g. lowest comparative value)
- Compression - the process of encoding information so that it takes up less space.
- Compression - WinZip, WinRar, zip
- Strategy of making a file smaller without losing information.
- Lossy information - loses some marginal information.
- Lossless compression - do not lose any data at all.
- ASCII - American Standard Code for Information Interchange. Standardized code for mapping characters to integers. Allows characters to be represented in binary so computers can read them.
- Every character is represented by a byte - 8 bits.
- Huffman's Insight: use variable length encodings for different characters to take advantage of frequencies in which characters appear.
- ASCII is trying to be very general, but that can lead to redundancy/waste.
- We have a new encoding scheme for each new file.
- Create a Huffman Tree that gives a good binary representation for each character.
- The path from the root to a character leaf is the encoding for that character; left means 0, right means 1.
- Steps for encoding:
  1. Count the occurrences for each character in the file.
  2. Create a Priority Queue with Huffman Nodes that are in ascending order with respect to frequency.
  3. Run the Huffman Tree merge algorithm. Remove two nodes and combine them into a node such that the left of the new node is one node and the right of the new node is the other node. The frequency of the new node is the sum of the two child node frequencies. Add this node back to the priority queue.
  4. Save the tree to a file to save the encodings for the characters we made. Perform a tree traversal to output the tree structure.
- What is the relationship between frequency in the file and binary representation length? The more frequently occuring characters have shorter paths to the root node.
- Prefix property - no prefix for one code is the prefix of another code.
- To rebuild the tree, read two lines of input at a time. Build a tree by following the file information.
- `BitInputStream` - works like a `Scanner` for bits

---

## Lecture 24 - Inheritance
- Inheritance - form new classes based on existing ones.
- Superclass - parent class being extended.
- Subclass - child class inheriting behavior from superclass.
  - Gets a copy of every field and method from the superclass
- is-a relationship - each object of the subclass also "is a(n)" object of the superclass and can be treated as one.
  - One-way relationship
- Example:

```java
public class A {
  public void m1() {
    m2();
    S.o.pln("A1");
  }
  
  public void m2() {
    S.o.pln("A2");
  }
}

public class B extends A
  public void m2() {
    S.o.pln("B2");
  }
}

// what is the output of
B b = new B();
b.m1();

// output: B2 / A1
```

- What relationships are or are not allowed?
- Type systems, casting, compiler checking

```java
PromiseType variable = new ActualType();
```

- Object: automatically is extended from every object.

```java
SuperClassType variable = new SubClassType();
```

- Methods are always called on the actual type - not the promised type. Promises are nothing in execution.
- Casting to access certain subclass methods
- Casting can get 'around' the Java compiler, renegotiating a contract. Casting creates a temporary new 'interpretation'.
- Super calls are non polymorphic calls.

---

## Lecture 25 - ArrayIntList, Iterators, Resizing
- Compile time - check if the cast type or promised type has the method
- Run time - if compiles and involved casting, check if actual type can actually be cast to cast type
- If no compile time or run time error, call the method on the actual type


- `ArrayList` - we started trying to understand how the `ArrayList` works.
- Extending the size of an array when the maximum capacity is reached: the significant cost (the heavy cost of copying over) is amortized across an increasing number of cheap costs
- Iterators - the iterator is an interface with a certain set of methods - `hasNext()`, `next()`, and `remove()`
- The iterator is like the 'pharmacist' at a pharmacy: they navigate the backroom.
- Static - makes things applicable to the class rather than the object.

---

## Lecture 26 - Collections and Abstract Classes
- Organize a collection of collections
- Interfaces - you define which elements you need
- Abstract classes - the best of both worlds between interfaces and classes.
- Interfaces can implement interfaces via extension















