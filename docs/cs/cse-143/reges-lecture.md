---
layout: default
title: Reges Lecture Notes
parent: CSE 143
grand_parent: Computer Science
nav_order: 1
---

# Stuart Reges Lecture Notes
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


---

## Week 3 Friday - 
- Constructing a linked list with elements.
- Differentiating temperaroy/reference variables from actual nodes.
- Writing a loop to traverse the Linked List.

```java
for (int i = 0; i <= n; i++) {
  front = new ListNode(i, front);
}
```

- Write a `public void` method called `addSorted` that takes in a value and inserts it into a sorted linked list such that the sorted characteristic is maintained.
- Requires a `.next` lookahead method.
- Think about possible cases in which we run into `null`.
- Short-circuit evaluation on boolean expressions. If `x` is `false` in the expression `x && y`, then `y` is not evaluated.
- Robust test first, sensitive test second
- Handle all cases - front, end, middle, empty list.
- Inchworm technique - have two pointers.

```java
prev = current;
current = current.next;
```

---

## Week 4 Monday - Binary Search and Complexity
- Efficiency of the code you write.
- Sometimes, people may develop an unhealthy obsession with efficiency.
- Premature optimization is the root of all evil - Knuth.
- Don't obssess about efficiency before code works.
- There is no midterm question about this subject.
- `n` is the *size of the problem. 
- `indexOf` looks at all elements for a failed search.
- Linear search - `O(n)`.
- Binary search - eliminate the same proportion of the search space every iteration.
- Big-O notation: how does the algorithm scale with `n`?
- Complexity - resources required for a bit of code or an algorithm. Resource - time.
- Profilers - can count which lines of code are executed most often
- We care about what happens when `n` gets very large; we isolate deominant terms.

---

## Week 4 Wednesday - Maps
- Abstract Data Types: lists, sets, stacks, queues, maps
- Given a particular $$x$$, there is only one or no $$y$$.
- Key value pairs. A key maps to a value.
- Also known as a dictionary or an associative array.
- `TreeMap` puts its keys in increasing order, like a `TreeSet`.
- If you call `.put(k, v)` with the same key, the old value will be replaced.
- Important to make a distinction between the first time you see something and when you see it later.
- For map traversal, it is common to loop over the keys of the map rather than looping over the map itself.
- Maps become more difficult when we have a multilevel structure: mapping to/from structures.

```java
public static void addTo(Map<String, Set<String>> friends,
                         String name1, String name2) {
  if (!friends.containsKey(name1)) {
    Set<String> the Friends = new TreeSet<>();
    friends.put(name1, theFriends);
    theFriends.add(name2);
  } else {
    friends.get(name1).add(name2);
  }
}
```

---

## Week 4 Friday - Maps Cont'd
- Review of String processing
  - `"" + char` turns a character into a `String`.

```java
if (!friends.containsKey(name1)) {
  friends.put(name1, new TreeSet<>());
}
friends.get(name1).add(name2);
```

- Completing friends search program
- Homework review - use a map to store different patterns and words that satisfy that program. 

---

## Week 5 Monday - Recursion
- We think of recursion in contrast to iteration, which involves writing loops and procedural-style programming.
- Some problems lend themselves better to recursion.
- Every programming assignment we will have for the rest of the week will use recursion.
- We need to make progress each time.
- Program to write stars recursively:

```java
public void writeStars(int n) {
  if (n == 0) {
    System.out.println();
  } else {
    System.out.print("*");
    writeStars(n - 1);
  }
}
```
- Recursion Zen
- Call Stack
  - Calls from different methods are stacked on top of each other.
  - We're using the built-in call stack that Java uses to keep track of call orders.
- Tail recursion - tail recursion solutions can be written as loops.
- Some examples contain multiple recursion cases.

---

## Week 5 Wednesday - More Recursion
- Binary number system.

```java
public void writeBinary(int n) {
  if (n < 2) {
    System.out.print(n);
  } else {
    writeBinary(n / 2);
    System.out.print(n % 2);
  }
}
```

- The recursion programming question on the midterm exam often has low scores.
- We add additional parameters in a recursive solution to accoutn for local variables in an iterative solution.
- Recursive solution for computing the cumulative sum of an array:

```java
public int sum(int[] list) {
  return sum(list, 0);
}

private int sum(int[] list, int index) {
  if (index = list.length()) {
    return 0;
  } else {
    return list[index] + sum(list, index+1);
  }
}
```

- Recursion Zen: don't end a recursion early - let it run further towards the end.


---

## Week 5 Friday - Grammars and Regular Expressions
- Regular expressions will be used in the homework assignment.
- RE: descriptions of patterns in strings.
- `-w` - need whole words.
- `zing` - requires `zing` to appear somewhere in the text.
- `.` - matches any letter. `.....` - searches for all five-lettered words.
- `|` - 'plumbing'/piping operation, feed output into another operation.
- To combine conditions, pipe condition outputs into new filters.
- `.split()` in Java takes in a regular expression and splits the input by the regular expression, returning an array of stinrgs.
- Delimeter - indicator of how to separate tokens. The normal delimeter is a space.
- Regular expression form - put a `+` after something to indicate 'one or more': e.g. ` +` to indicate any number of spaces.
- Tabs are not spaces; they are special characters. `\t` represents tab as well.
- For multiple or conditions: `[ -]+` indicates 'match any sequence of ` ` or `+`'.
- `[A-Za-z]` filters all lowercase and uppercase letters. `[^A-Za-z]` filters all letters that are not uppercase or lowercase letters.




- Homework assignment - will be working with grammar files using BNF grammar.
- Method of describing patterns in language.
- Terminals vs non-terminals.
  - Terminals: actual words in the language.
  - Nonterminals: variables we use to describe the grammar.

```
<s> ::= <np> <vp>
```

- Left-hand side: one non-terminal.
- Non-terminals are things that have rules associated with them.
- `::=` means "is composed of".
- A  sentence `<s>` must be composed of a noun phrase `<np>` and a verb phrase `<vp>`.
- A vertical bar `|` indicates 'or'.

---

## Week 6 Monday - Inheritance
- Inheritance - modeling different hierarchies between objects. 
- You want to be albe to add and modify/override specificity for subclasses in the object hierarchy.
- Maintaining multiple copies is tedious; by using inheritance hierarchies, we can better manage object relationships.
- Code reuse
- When you have an inheritance relationship, you automatically inherit the parent class' state and behavior.
- Another possible approach besides 'is a' is 'can substitute for'.
- `public class TypeB extends TypeA { ... }`.
- Every class in Java (except for one) extends something. When you don't extend something explicitly, Java will implicitly fill in `extends Object`.
  - `Object` is the most generic object. It is the only class that doesn't inherit from another class.
- Interfaces are an 'obligation'; inheritance is a 'gift' - all the state and behavior of the inherited class are present in the inheriting class.
- Java does not allow recursive or mutually dependent inheritance.
- Superclass vs subclass.
- `TypeA x = new TypeB();` / `TypeB y = new TypeA()` - what is going on here?
  - Remember what's going on with the variable (declared type) vs the object (actual type)
  - `TypeA x = new TypeB();` is valid.
  - `TypeB x = new TypeA();` is invalid.
  - You cannot instantiate a subclass as a superclass.
- If you have a specialized method `bOnlyMethod`, then `x.bOnlyMethod()` from `TypeA x = new TypeB();` would be invalid.
  - You can only call methods that are in the `TypeA` class.
  - Role/contract in object oriented programming: different objects can fulfill certain types of roles.
- Casting: you can cast a variable to another type. `((TypeB) x).bOnlyMethod()` - renegotiating the contract. This redirects the compiler's attention to look at the cast type rather than the declared type.
  - Casting temporarily does not change the type of `x`; `x` is still `TypeA`.
- Three steps:
  1. Compiler check. Does the role include the method that you're calling?
    - The compiler looks only at the cast type.
  3. Runtime check. Does the object that a variable refer to fill the given role? **Only when there is a cast involved.**
    - The cast type must be a valid relationship between the object type and the cast type.
  5. Execute the method. None of the stuff matters; all that matters is the object itself. Objects always behave in the same way.
- Always draw an inheritance hierarchy
- Optionally, write out a table:

| Method | `m1` | `m2` | `m3` |
| --- | --- | --- | --- |
| One | "One1" | - | - |
| Two | "One1" | - | "Two3" |
| Three | "One1" | "Three2", `m1()` | - |
| Four | "Four1", "One1" | "Three2", `m1()` | "Four3" | 

- `super.` is a call on a superclass method; we want to have access to the original.
- The same command can be interpreted in different ways.
- Polymorphism
- The compiler looks only at the cast type.
- Section will be useful.


---

## Week 6 Wednesday - Sorting
- Exam for this lecture section is on Friday. Do not lose points by stopping late.
- Do not forget to reset `size` for ArrayIntList problems.
- Desired mean of about 75%.
- Selection Sort - iteratively find the smallest element in an array, remove it, and continue until the array is empty. An intuitive, classic sorting routine. $$O(N^2)$$ time.
- Bubble Sort - look at elements next to each other; if two elements are out of order, you switch it. $$O(N^2)$$ time.
- Bogo Sort - just guess it every time. 
- Insertion Sort - an intuitive sort in which we insert at each point that preserves structure. $$O(N^2)$$ time.
- Bucket/radix sort
- Quick Sort
- Merge Sort. Has $$O(N \log N)$$ time.
- `.compareTo`
- Stable Sort: preserves the relative order of 'ties'.

---

## Week 7 Monday - Backtracking and Exhaustive Search
- Backtracking is a very specific algorithm.
- In some sense, you'll be told exactly what code to write.
- Regardless, the backtracking assignment is conceptually difficult. Conceptually difficult, but you write very little code that does something very interesting.
- Exhaustive search - generate every possibility.
- Use recursion to accomplish exhaustive search - more scalable. 
- Anthropromorphize backtracking - imagine people changing what card is showing.
- Mechanical counters.
- Decision tree - a visualr epresentation of how different chioces can be made at each point.
- You can explore the decision space in any way, but we generally explore the space using a depth-first-search (DFS) style operation.
- Backtracking - going to when we last had a choice/could proceed.
- Typically, we do not need to write code to force it to backtrack.
- Dead-ends - problems that are not worth exploring any further.
  - i.e. we sometimes decide to stop exploring
- 8 Queens problem - try to place 8 queens on a chess board such that no 8 queens challenge each other.
- Erasure/undoing of a move.
- With backtracking, it can be easy to get lost in the low-level details.
- Rule of thumb: write supporting code to deal with the low-level details for you.
- Recursion Zen
- Backtracking pattern:
  1. Choose
  2. Explore
  3. Unchoose
- Essence of backtracking.
- Often, there isn't a cleanup task to do - but there sometimes is one, in which you must explicitly write code to unchoose.


---

## Week 7 Wednesday - More Backtracking
- More on the 8 Queens Problem.
- Recursion Zen - we often let things go a little bit further - we have robots that do things and pass it on to the next, but maybe another robot that determines a victory.
- Anagram solver homework
- Explore the dictionary that you're given; at each recursive call, you pick a word.- 
- We will be using the Letter Inventory class to keep track of the words.
- Efficiency improvements

---

## Week 7 Friday - Binary Trees
- This year's students performed much worse on the midterm than the 2020 cohort.
- Regrade policy page
- Sometimes, requesting a regrade yields a poorer performance then before - the TAs may make mistakes in or against your favor.
- Last major topic of the quarter - two programming assignments involving binary trees.
- Four different final exam questions on binary trees.
- A lot of people enjoy the elegance of binary trees.
- Binary tree code tends to be very short because they are generally recursively handled.
- Nodes - a structure composed of individual bits of data, each which is in a node.
- Root, branches, leaves.
- Parent-child relationship
- A binary tree is either an empty tree or a root node with left and right subtrees.
- Branch node constructor, leaf node constructor.
- Overall root
- Traversal - it's not necessarily clear what comes first.
  - Process everything in a lefthand subtree
  - Process everything in a righthand subtree
  - Where to process the root?
  - Inorder tree traversal - left, root, right.
  - Postorder tree traversal - left, right, root.
  - Preorder tree traversal - root, left, right.
  - One of the four final exam questions
- Sailboat method
- Write methods - traversal methods nad other methods to explore a binary tree.
- All exam questions will be in the form of working with an `IntTree`.
- 10 pt. traversal, 20 pt. re-arrangement of the tree.
- Every node introduces two trees; given $$N$$ nodes, there are $$2N+1$$ trees.

---

## Week 8 Wednesday - Binary Search Tree
- Added 5 points to Hunter
- Over 23% scored 90% or higher
- Binary Search Tree
- Built-in TreeSet class uses a binary search tree, doesn't allow duplicates.
- 4 Binary Tree questions on the exam
- An inorder traversal of a binary search tree gives a sorted order.
- Always use public/private pairs for binary tree problems
- Reference semantics and local variables
- We can change the state of the object by 'talking to it' with a method call, but we can't change the reference.
- Pattern: `x = change(x)`.
- It does a lot of assigning as it 'comes back out', but the only one that has any effect is the last one.


---

## Week 8 Friday - Comparable Interface and Generic BST
- `private` does not mean private to the object, but rather private to the class.
- In the Linked List problem, often you have one linked list manipulate a second linked list.
- Most points for writing a class are standard - defining fields, a `toString` method, etc.
- Little things - e.g. minutes going over 60 in an `add` method for a time class.
- De Morgan's law - when you have 'something and something and something', negation becomes 'not something or not something or not something'.
- Class invariant - reasoning about invariance. There may be relationships we guarantee will always be maintained.
  - A condition remains true at initialization and at every modification.
- Stuart loves mod!
- Comparing custom classes.
- `compareTo` method required to implement the `Comparable` Interface.

```java
public class Angle implements Comparable<Angle> {...}
```

- Comparing: return -1 for less-than, 0 for equal, 1 for greater-than.
- Casting to `Comparable<E>` interface to address symbol not found errors for comparison.
- New syntax - constraint on the 'types' of Es that can be used.

```java
public class SearchTree<E extends Comparable<E>> {...}
```

---

## Week 9 Monday - Abstract Classes
- Cases in which we're dealing with a double difference - you cannot simply cast into an int.
- When you're dealing with a double rather than an int, do not use casting ints; just write a series of logic if/else statements. 
- You'll be better off calling a method rather than using an expression in the `compareTo`.
- Object oriented design and class hiearchy.
- Using a class vs interface - if all we need is knowing some information, then we can use an interface - if something *can* be done with an interface,  it *should* be done w ith an interface. Each subclass can only have one inheritance relationship.
- When an interface is related to another interface, you use `extend` instead of `implement`. 
- Interface solution to the problem - use an interface `Shape` and make all classes implement.
- Concrete classes - methods and states with a concrete body and filled commands. An interface is all abstract - all hollow, nothing is filled in.
- We're looking for something in between - an abstract class. We get some things filled in, and some things not filled in.
- `public abstract <type> <name> ()` for methods; `public abstract class <name> implements <interface> {...}`
- Abstract classes have a constructor, even though we can't construct an instance of an abstract class.
- The first thing that every constructor does is to call a superclass constructor.
- Accessing private fields of a superclass - we can't accesss
- Good OOP - talk about what is special - only say or express what is different from what is already written.
- Reges believes - square should not extend rectangle. The "is/a" vs the "can substitute for" relationship debate. A square cannot substitute for a rectangle, and therefore, it should not extend rectangle.
- Other things we could explore - the keyword `final` does not allow subclasses to override superclasses.
- Classes can be final too - `public final ...`.

---

## Week 9 Wednesday - Huffman Coding
- 1880 census took almost 8 years to complete; who could do something better?
- Hollerith - came up with a scheme of punched cards. Data processing equipment.
- System involving working with punched cards and machines; the government did the 1890 census in less time than the 1880 census.
- Merged with other companies into IBM.
- Attempt in the early 1960s as an alternative to IBM: ASCII, American Standard Code for Information Interchange.
- 128 possible values - 7 bits.
- ASCII doesn't work well for non-American characters.
- 8th bit for ASCII was often used as a parity bit - perform a calculation on the parity to detect corruption in data.
- International committee - defines Unicode.
- UTF-8 encoding. A code with variable lengths - some of the codes are 1-byte, some as 2-byte, 4-byte, etc. There is more space in unicode to have longer codes.
- ASCII characters are one byte long in UTF-8.
- Zipping and compression
- Common letters - letters that appear frequently. Look at the frequency of characters and deal with individual characters.
- Huffman Coding
- Create several nodes, and combine the two with the lowest frequency underr a new node with a frequency as the sum of frequencies.
- Priority Queue - has an operation that removes the smallest value from the queue.
- Your Node Class must implement the `Comparable` interface so the priority queue can 'sort'/find the 'min'.
- Prefix Property - no code in the list is the prefix of another code.
- `BitInptuStream` and `BitOutputStream` - will use classes as part of the solution.
  - `BitOutputStream` has a challenge - bits tend to come in bytes of 8
- Pseudo-EOF. We will need to manually add the Pseudo-EOF character to the priority queue.

---

## Week 9 Friday - Advanced `ArrayIntList`
- FInal exam resources have been posted, extra credit opportunities.
- Material we are covering today is usually covered earlier.
- `ArrayIntList` - how to make a somewhat better version.
- What else would we want in an `ArrayIntList`?
  - `set` - reassignment at a certain index
  - `removeAll`
  - `isEmpty`
  - `iterator`
  - `clear`
- Interface `Iterator<E>` - must implement a `hasNext()`, `next()`, and `remove()` method

```java
public class ArrayIntListIterator implements Iterator<Integer> {
  private int position;
  private ArrayIntList list;
  private boolean removeOK
  
  public ArrayIntListIterator(ArrayIntList list) {
    this.list = list;
    this.removeOK = false;
  }
  
  public boolean hasNext() {
    return position < list.size();
  }
  
  public Integer next() {
    if (!hasNext()) {
      throw new NoSuchElementException();
    }
    int result = list.get(position);
    position++;
    this.removeOK = true;
    return result;
  }
  
  public void remove() {
    if (!removeOK) {
      throw new NoSuchElementException();
    }
    list.remove(position - 1);
    position--;
    this.removeOK = false;
  }
}
```

- The iterator is a lightweight object
- Do not remove something in a loop, you will get a concurrent modification error. Use an iterator instead.
- We want to be able to instantiate an iterator

```java
public Iterator<Integer> iterator() {
  return new ArrayIntListIterator(this);
}
```

- Expanding capacity - if you will exceed capacity, it makes a bigger array and copies elements over to the new array.
- Amoratizing - spreading out a cost over a certain duration of period.
- Java multiplies by 1.5 - increases by 50%.
- Sample final on website
- `TreeSet` does not work on an object that does not implement `Comparable`
- `Point` does not implement `Comparable`; `Point` is often used in exams.

| This text resides on the 777th line of the markdown file used to generate this text. |

- Binary tree questions are generally not too diffiuclt - linked list problems are very difficult.
  - Simulate your code: list of length 0, length 1, length 2, etc.
 
 ---
 
 ## Week 10 Monday - `IntList` Case Study
 - ArrayList vs LinkedList - very different approaches to getting something.
 - Abstract class vs interface - which one to use?
 - We can say that an abstract class implements an IntList, and ArrayIntList and LinkedIntList inherit from AbstractIntList.
 - Abstract classes force you to extend a particular class.
 - Implement the `IntList` interface such that your code fits in.
 - Iterator techniques - often used to assist with efficient object-oriented solutions.
 - `Iterable` interface - required for `for-each`
 - Java turns for-each loops into iterator-type looping.
 - Syntactic sugar
 - Concurrent modificaiton error - if you iterate over a structure, you should not be editing it using internal methods - remove using the iterator.
- `protected` access modifier - private methods are not inherited. Public - everyone can see it, public - no one can see it. Protected - subclasses can see it.
- You can put a class inside a class - if you have an inner class, objects of the inner class automatically have access to the fields and methods of the constructing class.
- Private static classes

---

## Week 10 Wednesday - Hashing

| Structure | Add | Find | Remove |
| --- | --- | --- | --- |
| Unsorted Array | O(1) | O(n) | O(n) |
| Sorted Array | O(n) | O(log n) | O(n) |
| Unsorted Linked List | O(1) | O(n) | O(n) |
| Sorted Linked List | O(n) | O(n) | O(n) |
| Binary Search Tree | O(log n) | O(log n) | O(log n) |
| HashTabe | O(1) | O(1) | O(1) |

- The binary search tree only works on certain types of data.
- Hashing - a very clever idea with interesting applications in a lot of places.
- Hash Function - takes in data and converts it into an integer.
- We need such a function for hashing. This function is not necessarily invertible, i.e. we cannot always recover the object from the integer.
- `hashCode()` is a method in the `Object` class. Every object in Java has a hash code.
- Use mod to get to a location in the 'roomy array'
- Collision resolution
- Separate chaining - to resolve collisions, chain multiple nodes/possible values together. An array of linekd lists.
- The Hash function has to spread things out.
- $$\Lambda$$ - load factor for hash table. 0.75 is a typical example: we don't want the structure to be more than 75% full.














