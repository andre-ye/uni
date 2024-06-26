---
layout: default
title: Textbook Notes
parent: CSE 143
grand_parent: Computer Science
nav_order: 50
---

# Textbook Notes

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

## Chapter 9: Classes

### 9.1: Inheritance Basics
> Code Reuse: writing program code once and using it in many contexts.

- Software has become more complicated. Teams were writing larger and more complex programs in the 1970s and encountered common problems.
- Software Crisis: program maintenance. Companies spent too much time not writing new code but instead modifying and maintainign existing code (legacy code).
- Inheritance - allows us to write programs with hierarchies of related object types.
- Key ieas:
  - It's useful to specify a broad set of rules that applies to many related groups.
  - It's also useful to specify a smaller set of rules specific to a particular group.

- *Inheritance*: a programming technique that allows a derived class to extend the functionality of a base class, inheriting all of its states and behaviors.
- *Superclass*: the parent class in an inheritance relationship.
- *Subclass*: the child class in an inheritance relationship.

```java
public class <name> extends <superclass> {
  ...
}
```

- The subclass can add new behavior not present in the superclass.
- The subclass can override superclass behavior by writing new versions of the relevant methods.

### 9.2: Interacting with the Superclass
- You also want to inherit more complex functionality from the superclass.

Writing code for a legal secretary, which earns 5000 more than a general employee:
```java
public double getSalary() {
  return super.getSalary() + 5000;
}
```

- An inheriting class cannot access private data from a superclass, but you can create accessor or mutator methods to access or change values; these are accessible to subclasses.
- Constructors, unlike other behaviors, are not inherited.
- Use the keyword `super` to initialize fields for access:

```java
public DividendStock<String symbol) {
  super(symbol);
  dividends = 0.0;
}
```
- The call to the superclass constructor must be the first statement in a constructor.
- You only need to use `super` when you are accessing overridden methods or constructors from the superclass.
- The `Object` class is the ultimate superclass for all Java classes; the compiler writes `extends Object` for declared classes during compilation. Methods include `clone`, `equals`, `finalize`, `getClass`, `hashCode`, `toString`, `notify`, `notifyAll`, `wait`
- You can accept any class by referring to the `Object`:

```java
public static void myMethod(Object o) {
  ...
}
```
- Casting an object is a promise to the compiler
- Using `instanceof`:

```java
public boolean equals(Object o) {
  if (o instanceof Point) {
    Point other = (Point) o;
    return x == other.x && y == other.y;
  } else {
    return false;
  }
}
```

### 9.3: Polymorphism
- Inheritance allows client code to treat different kinds of objects in the same way.
- Polymorphism - ability for the same code to be used with several diff. types of objects.
- The type of a reference variables doesn't need to exactly match the type of the object it refers to.
- Late binding, virtual binding, dynamic dispatch - whent he program reaches a particular call to an object's method, it examines the object to see which method to call.
- When you send messages to an object sstored in a variable of superclass type, you can only call methods known to the superclass.
- Inheritance & polymorphism can introduce complex new mechanics.
- Method call tables - have each method as a row and each class as a column; write out the output.

### 9.5: Interfaces
- Inheritance enables polymorphism and code sharing. However, it is very limited.
- A class can only extend one superclass.
- *Interface* - a common supertype between several classes without code sharing.
- An interface contains only method headers without bodies.
- An interface is a 'professional certification'.

```java
public interface Shape {
  public double getArea();
  public double getPermimeter();
}
```

General implementation for declaring an inteerface:
```java
public interface <name> {
  public <type> <name>(<type> <name>, ..., <type> <name>);
  public <type> <name>(<type> <name>, ..., <type> <name>);
  ...
  public <type> <name>(<type> <name>, ..., <type> <name>);
}
```

An interface itself cannot be instantiated. However, you can create other classes that implement the interface that can be instantiated.

```java
public class Rectangle implements Shape {
  private double width;
  private double height;
  
  public Rectangle(double width, double height) {
    this.width = width;
    this.height = height;
  }
  
  public double getArea() {
    return width * height;
  ]
  
  public double getPerimeter() {
    return 2.0 * (width + height);
  }
}
```
If a method claiming to implement an interface does not have the required methods, an error is thrown and the code does not compile.

> "Additive, not invasive"


---

## Chapter 10: ArrayLists

### 10.1: ArrayLists
- Lists should be dynamic, flexible. We want to list to grow and shrink over time as we add or remove values.
- We are considering a list abstraction.
- Java provides the `ArrayList` that provides the same fast random access as an array while letting you make simple requests to add or remove values.
- `ArrayList<E>` is the generic class in Java. `E` is short for Element.


- The `Arraylist` is part of the `java.util` package; import it before the program.
- `ArrayList<String> list = new ArrayList<String>();`
- `.size()` can be used to access the number of elements in the `ArrayList`.

Basic `ArrayList` Methods:

| Method | Description |
| --- | --- |
| `add(value)` | Adds a value to the end of the list. |
| `add(index, value)` | Adds a value to the specified index. |
| `clear` | Removes all elements from list. |
| `get(index)` | Gets item at specified index. |
| `remove(index)` | Removes a value at the specified index. |
| `set(index, value)` | Replaces the value at the given index with the current value. |
| `size()` | Returns the current number of elements in the list. |

`ArrayList` Searching Methods:

| Method | Description |
| --- | --- |
| `contains(value)` | `true` if item value appears in list, `false` otherwise. |
| `indexOf(value)` | Returns the index of the 1st occurrence of the given value, and `-1` if not found. |
| `lastIndexOf(value)` | Returns the index of the last occurrence of the given value, and `-1` if not found. |

You can use a `for-each` loop to iterate over elements of an `ArrayList` directly instead of using for-loop indexing.

```java
for (<type> <name> : <structure>) {
  <statement>
}
```

This is equivalent to the Python

```python
for name in structure:
  statement
```

However, you cannot modify an ArrayList while you are iterating through it using the `for-each` method.

Because `ArrayList<E>` can only store objects, it cannot store primitive types (`int`, `double`, `char`, `boolean`, etc.). Java defines wrapper classes that 'wrap' around primitive data.

```java
int x = 38;
Integer y = new Integer(38);
int number = y.intValue();

ArrayList<Integer> list = new ArrayList<Integer>();
list.add(13);
list.add(47);
```

Boxing: automatic conversion from primitive data to a wrapped object of the appropriate type, like `int` boxed to form `Integer`.

Common Wrapper Classes:

| Primitive Type | Wrapper Class |
| --- | --- |
| `int` | `Integer` |
| `double` | `Double` | 
| `char` | `Character` |
| `boolean` | `Boolean` |

### 10.2: THe `Comparable` Interface
- Boxing vs unboxing.
- testing object equality is not as simple as testing for equality in primitives.
- Natural ordering: the order imposed on a type by its comparison function. Not all types have natural orderings.
- `compareTo` method is the comparison function for the type. Three possible answers: negative number for less than, 0 for equality, positive number for greater-than relationship.
- When we implement a `Comparable` interface, use `public class Name implements Comparable<T>`.
- Implement a `public int compareTo(type other) {...}` method.

---

## Chapter 11: Java Collections Framework

### 11.2: Sets
- Limitation to linked and array lists: searching takes a long time.
- *Set* abstract data type: a collection that cannot contain duplicates, and thus is faster to search.
  - Sets also easily eliminate duplicates.
- Two primarily implementations: `HashSet` and `TreeSet`. The former is the general-purpose set class.

```java
Set<String> names = new HashSet<String>();
names.add("Adam");
names.add("Eve");
names.add("Steve");
names.add("Adam"); // will not be added
```

- The `Set` interface provides all operations from the `Collection` interface, like `add`, `contains`, and `remove`.
- `contains` in `ArrayList` and `LinkedList` examines every element in the collection until it finds the target value.
- `HashSet`s use a hash table, which places elements in specific positions based on integers called hash codes; this allowed for fast addition, rmeoval, and search.
  - However, the hashing technique forces elements to be arranged in an unpredictable order.
  - `LinkedHashSet` is almost as fast as `HashSet`, but stores elements in the order they were inserted.
- `HashSet` can also accept another collection and puts unique elements into a `Set`. This can be used to find if a `List` has any duplicates by comparing sizes of the original list and the set of unique values:

```java
public static boolean hasDuplicates(List<Integer> list) {
  Set<Integer> set = new HashSet<Integer>(list);
  return set.size() < list.size();
}
```
- `HashSet` does not support indexing; to iterate, use one of the following two methods:
  - *Iteration*. `Iterator<String> itr = set.iterator(); while (itr.hasNext()) {...}`
  - *For-each*. `for (String item: set) {...}`
- `TreeSet` uses an internal linked data structure called a binary search tree to store elements in sorted order.
  - Efficient for adding, removing, and searching, albeit slower than `HashSet`.
  - `TreeSet` can be applied to data with a *natural ordering* specified by a `Comparable` interface, like `Integer` or `String`.
  - Do not use `TreeSet` with objects without a natural ordering/unspecified comparator.

*Common set operations given sets `A` and `B`*:

| Set Operation | Method | Description |
| --- | --- | --- |
| union | `addAll` | Set of all elements in A, B, or both |
| intersection | `retainAll` | Set of all elements that are in both A and B |
| difference | `removeAll` | Set of all elements in A but not in B |
| superset/subset | `containsAll` | Returns if A is a superset of B |

- Set operations modify existing sets rather than creating new ones.

### 11.3: Maps
- In many data processing tasks, we want to link pairs of objects.
- A map is a collection that allows you to create one-way associations between pairs of objects.
- A map is a collection that associates keys with values.
- A key can map to only one value, but multiple keys can map to the same value.
- `HashMap` and `TreeMap` - maps and sets have similar internal implementations.
  - `HashMap` is a more general purpose map
  - `TreeMap` stores comparable keys in sorted order
- Map constructed with two type parameters separated by a comma - type of keys and values.

```
Map <String, Double> salaryMap = new HashMap<String, Double>();
salaryMap.put("Bobess", 6.0);
salaryMap.put("Aliceski von Aliski", 12.0);
```

- Look up values using `.get(key)`.
- You can use `.containsKey(key)` to check if a key is present in the salary map.
- `keySet()` returns a `Set` of all keys in the map
- `values()` returns a `Collection` of all values in the map

Map views
- Maps don't have an `iterator` method. Maps have a pair of methods claled `keySet` and `values` instead, which return a `Set` of all keys in a map and a `Collection` of all values in the map.
- Collection views of a map - each collection exists conceptually within the map.

```java
for (<type> item : map.keySet()) {
  doSomething(item);
}
```

- `EntrySet` returns key/value pairs.
- `HashMap` is slightly faster than `TreeMap`, but keys are stored in somewhat haphazard order. `TreeMap` stores comparable data and performs operations slightly slower while keeping it in order.
- `HashMap` is generally used over `TreeMap`.

---

## Chapter 12: Recursion

### 12.1: Thinking Recursively
- In classic iteration, actions are repeated via a loop.
- In recursion, actions are repeated using a method that calls itself.
- Instead of having one object work to count all entities, have each entity do a little part of the work and pass it on to the next piece.

Simple program to print out a line ofs tars:
```java
public static void writeStars(int n) {
  if (n == 0) {
    System.out.println();
  } else {
    System.out.println("*");
    writeStars(n-1);
  }
}
```

- Every recursive solution must have a base case and a recursive case.

### 12.2: A Better Example of Recursion
- Recursive programming - thinking about cases. What is the simplest file to reverse?
- Think about the call stack - how elements are stacked, addressed, and removed.

### 12.3: Recursive Functions and Data
- Recursive functions can be used to iteratively compute a result.

```java
public static int pow(int x, int y) {
  if (y == 0) {
    return 1;
  } else {
    return x * pow(x, y - 1);
  }
}
```

- We can improve the program by further factoring out repititions:
```java
public static int pow(int x, int y) {
  if (y == 0) {
    return 1;
  } else if (y % 2 == 0) {
    return pow(x * x, y / 2);
  } else {
    return x * pow(x, y - 1);
  }
}
```

- Greatest Common Divisor of two integers recursively using the Euclidean formula:

```java
public static int gcd(int x, int y) {
  int (y == 0) {
    return x;
  } else {
    return gcd(y, x % y);
  }
}
```

- Helper methods: an additional method used to help solve a recursive problem.

### 12.4: Recursive Graphics
- Fractal geometry

### 12.5: Recursive Backtracking
- Most programming problems (that professors in CSE 143 give students on exams) can be solved by systematically searching a set of possibilities
  - tic-tac-toe
  - maze navigation
- Recursive backtracking: a gneeral algorithm for finding solutions to a problem by exploring a candidate solution, abandoning/backtracking once the candidate is found unsuitable
- Decision tree representation of possible move space; functionally this is a depth-first search (DFS) using the internal call stack
- 8 Queens puzzle
- Solving Sudoku puzzles
- 

---

## Chapter 13: Searching and Sorting

### 13.1: Searching and Sorting in the Java Class Libraries
- To search an `ArrayList` or `LinkedList`, you generally call the `indexOf` method.
- Sometimes, you'll want to search through elements of an array that are already in sorted order.
- Binary search looks at sorted data much faster than sequential search.
- Binary search examines the center array and selects the half that contains the element, then recursively repeats.

*Binary search on an array.*
```java
int index = Arrays.binarySearch(arr, target);
```

*Binary search on an `ArrayList`.*
```java
int index = Collections.binarySearch(list, target);
```

*Various methods to sort data*
```java
Arrays.sort(arr);
Arrays.parallelSort(arr);
Collections.sort(list);
```

- Parallel sort takes advantage of computer architectures with multiple processors or multi-core processors.
- An array must implement the `Comparable` interface to be sorted.

*Various methods to shuffle data*
```java
Collections.shuffle(list);
```

- Comparators are implemented as classes that implement the interface `Comparator` in the `java.util` package.

```java
public class customComparator implements Comparator<E> {
  public int compare(obj obj1, obj obj2) {
    return value;
  }
}

Arrays.sort(array, new customComparator());
```

### 13.2: Program Complexity
- We want algorithms that can solve problems quickly and efficiently.
- Complexity - techncial term for an algorithm's runtime.
- Time complexity - dependent on the task.
- Empirical algorithm analysis - actually timing program outputs.
  - Not necessarily reliable because of varying processor speed and memory, etc.
- Instead, examine code or pseudocode and roughly cout the statements executed. Mathematically approximate the performance of applying techniques.
- Use loops as a multiplier or exponential
- It's important to create algorithms that don't loop over data unnecessarily.
- Drop the least 'important' or 'significant' term in complexity analysis.

*Complexity class*

| Name | Notation | Examples |
| --- | --- | --- |
| Constant | $$O(1)$$ | Don't depend on input size. Numerical functions. |
| Logarithmic | $$O(\log N)$$ | Divide the problem space by a certain proportion repeatedly until the problem is solved. Binary search |
| Linear | $$O(N)$$ | Algorithms process each element of the data. Count, sum, average, maximum. |
| Log-Linear | $$O(N \log N)$$ | A combination of logarithmic and lienar operations. Merge sort |
| Quadratic | $$O(N^2)$$ | Runtimes proportional to the square of the input size. Programs that construct a matrix from a one-dimensional array. |
| Cubic | $$O(N^3)$$ | Runtimes proportional to the cube of the input size. Make triply nested passes over the data. |
| Exponential | $$O(2^N)$$ | If the input siz increases by one, the lagorithm will take roughly twice as long. Print power set of a dataset. |

### 13.4: Merge Sort
- The merge sort algorithm stems from the observation that you can easily merge two sorted subarrays into a single sorted array.
- Merge sort pseudocode:

```
split the array into two halves
sort the left half
sort the right half
merge the two halves
```

- To perform merging, simply compare the two 'top' values of the two sorted subarrays and stack.
- We can write recursive merge sort.

```java
 1 // This program implements merge sort for arrays of integers.
 2 import java.util.*;
 3
 4 public class MergeSort {
 5 public static void main(String[] args) {
 6 int[] list = {14, 32, 67, 76, 23, 41, 58, 85};
 7 System.out.println("before: " + Arrays.toString(list));
 8 mergeSort(list);
 9 System.out.println("after : " + Arrays.toString(list));
10 }
11
12 // Places the elements of the given array into sorted order
13 // using the merge sort algorithm.
14 // post: array is in sorted (nondecreasing) order
15 public static void mergeSort(int[] a) {
16 if (a.length > 1) {
17 // split array into two halves
18 int[] left = Arrays.copyOfRange(a, 0, a.length / 2);
19 int[] right = Arrays.copyOfRange(a, a.length / 2,
20 a.length);
21
22 // recursively sort the two halves
23 mergeSort(left);
24 mergeSort(right);
25
26 // merge the sorted halves into a sorted whole
27 merge(a, left, right);
28 }
29 }
30
31 // Merges the given left and right arrays into the given
32 // result array.
33 // pre : result is empty; left/right are sorted
34 // post: result contains result of merging sorted lists;
35 public static void merge(int[] result, int[] left, int[] right) {
36 int i1 = 0; // index into left array
37 int i2 = 0; // index into right array
38 for (int i = 0; i < result.length; i++) {
39 if (i2 >= right.length || (i1 < left.length &&
40 left[i1] <= right[i2])) {
41 result[i] = left[i1]; // take from left
42 i1++;
43 } else {
44 result[i] = right[i2]; // take from right
45 i2++;
46 }
47 }
48 }
49 }
```
- Merge sort is an $$O(N \log N)$$ algorithm. 

---

## Chapter 14: Stacks and Queues

- Fundamental abstract data types: stacks and queues.
- Programming equivalent of drawers and shelves.

### 14.1: Stack/Queue Basics
- Stacks: LIFO. Last-in, First-out.
- Queues: FIFO. First-in, first-out.
- *push*: an adding operation.
- *pop*: a removing operation.

Useful methods in the `Stack` class:

| Method | Description |
| --- | --- |
| `push(value)` | Pushes value to top of stack |
| `pop()` | Removes value at top of stack |
| `isEmpty()` | Returns `true` if stack contains no values |
| `peek()` | Returns value at top of stack without removing it |
| `size()` | Returns number of values in the stack

```java
Stack<String> s = new Stack<String>();
for (String str : data) {
  s.push(str);
}
while (!s.isEmpty()) {
  s.pop();
}
```

Useful methods in the `Queue` Interface:

| Methods | Description |
| --- | --- |
| `add(value)` | Adds given value to back of queue | 
| `remove()` | Removes value at front of queue |
| `isEmpty()` | Returns `true` if queue contains no values |
| `peek()` | Removes value at front of queue without removing it |
| `size()` | Returns number of values in queue |

```java
Queue<String> q = new LinkedList<String>();
for (String str : data) {
  q.add(str);
}
while (!q.isEmpty()) {
  q.remove();
}
```

### 14.2: Common Stack/Queue Operations
- We use a `Queue<Integer>` interface, even though the specific implementation is `LinkedList`. Should be used in return types, parameters, and variable initializations.

*Sample code: generating a random Queue parametrized by number of elements added (`size`).*

```java
public static Queue<Integer> makeRandomQueue(int size) {
  Queue<Integer> q = new LinkedList<Integer>();
  Random r = new Random();
  for (int i = 0; i < size; i++) {
    q.add(r.nextInt(100));
  }
  return q;
}

// client code:
Queue<Integer> q = makeRandomQueue(10);
System.out.println("q = " + q);
```

- **To transfer all values from a queue to a stack**, we need a loop that will remove values from the queue until there are no more left; we can use `while(!queue.isEmpty()) { type var = queue.remove(); ... }`. 

```java
public static void queueToStack(Queue<Integer> q, Stack<Integer> s) {
  while (!q.isEmpty()) {
    s.push(q.remove());
  }
}

public static void stackToQueue(Stack<Integer> s, Queue<Integer> q) {
  while (!s.isEmpty()) {
    q.add(s.pop());
  }
}
```

- **To find the sum of values in a queue** without destroying the contents of the queue, we add items to the end of the queue that have been taken from the front. Since the size remains constant, we cannot use `while (!q.isEmpty()) {...}` but rather `for (int i = 0; i < q.size(); i++) {...}`.

```java
public static int sum(Queue<Integer> q) {
  int sum = 0;
  for (int i = 0; i < q.size(); i++) {
    int n = q.remove();
    sum += n;
    q.add(n);
  }
  return sum;
}
```

- **To find the sum of a stack**, we cannot use the same approach as a queue because of the stack's FIFO nature. We use another stack as an *auxiliary structure* and put things in the aux. stack as we take them out of the original stack, then transfer items from the aux. queue back into the stack.

### 14.3: Complex Stack/Queue operations

**Removing a value from a queue**.
> Thought process: cycle through and only add back if the value is not the value desired to be removed. However, we need to make sure we adapt to the queue size and loop through the entire range only once.

```java
public static void removeAll(Queue<Integer> q, int value) {
  int oldSize = q.size();
  for (int i = 0; i < oldSize; i++) {
    int n = q.remove();
    if (n != value) {
      q.add(n);
    }
  }
}
```

**Comparing two stacks for similarity**
- When comparing, make sure you restore stacks and queues if you obtain values through popping and removing.
- Comparing the parity pattern of two stacks:

```java
public static boolean sameParityPattern(Stack<Integer> s1,
  Stack<Integer> s2) {
  if (s1.size() != s2.size()) {
    return false;
  } else {
    Stack<Integer> s3 = new Stack<Integer>();
    boolean same = true;
    while (same && !s1.isEmpty()) {
      int num1 = s1.pop();
      int num2 = s2.pop();
      if (num1 % 2 != num2 % 2) {
        same = false;
    }
    s3.push(num1);
    s3.push(num2);
    }
    while (!s3.isEmpty()) {
      s2.push(s3.pop());
      s1.push(s3.pop());
    }
    return same;
  }
}
```

---

## Chapter 15: Implementing a Collection Class

### 15.1: Single ArrayIntList
- Clients don't want to understand all the internal class details.
- Contract - specification telling the client how an object behaves without describing the implementation details.
- `ArrayIntList` - we use an unfilled array in which some of the elements are filled.
- Distinguish between occupied and vacant cells with a `size` variable.


We can write a `print`/`toString` method that displays the internal contents of the list:

```java
public void toString() {
  if (size == 0) {
    System.out.println("[]");
  } else {
    System.out.print("[" + elementData[0]);
    for (int i = 1; i < size; i++) {
      System.out.print(", " + elementData[i]);
    }
    System.out.println("]");
  }
}
```
To allow the user to access the size, we can write an accessor method:
```java
public int size() {
  return size;
}
```
To remove an item at a given index, we shift all values after the index down by one position.
```java
public void remove(int index) {
  for (int i = index; i < size – 1; i++) {
    elementData[i] = elementData[i + 1];
  }
  size– –;
}
```
To insert an item at a given index, we go in the other direction and shift all values after the index up by one position.
```java
public void add(int index, int value) {
  for (int i = size; i >= index + 1; i– –) {
    elementData[i] = elementData[i – 1];
  }
  elementData[index] = value;
  size++;
}
```
To set a default capacity size in addition to offering parameter inputs, we define two separate methods. These have different *signatures* (one takes arguments, one does not).
```java
public ArrayIntList() {
  this(100);
}

public ArrayIntList(int capacity) {
  elementData = new int[capacity];
  size = 0;
}
```

### 15.2: A More Complete ArrayIntList

We can make preconditions explicit by throwing errors with optional error messages:
```java
if (capacity < 0) {
  throw new IllegalArgumentException("capacity: " + capacity);
}
```

Common exception types:

| Exception Type | Description |
| --- | --- |
| `NullPointerException` | A `null` value has been used in a case that requires an object. |
| `ArrayIndexOutOfBoundsException` | A passed index is illegal. |
| `IndexOutOfBoundsException` | A passed index to a nonarray object is illegal. |
| `IllegalStateException` | A method has been called in an illegal time. |
| `IllegalArgumentException` | A value passed to a method is illegal. |
| `NoSuchElementException` | A call was made to a `next` method when no such value exists. |

Common convenience methods:

| Method Name | Description |
| `indexOf` | Searches for the index of a value in the array. |
| `contains` | Returns a Boolean indicating the presence of a value in the array. |
| `isEmpty` | Returns whether the array is empty or not; i.e. `return size==0`. |
| `set` | Directly sets an index to a new value, rather than using `remove`, then `add`. |
| `addAll` | Adds all elements from anohter `ArrayIntList`.

### 15.3: Advanced Features
- Resizing when necessary: creating a larger array when capacity is exceeded; capacity grows to accmodate new values.
- Expense is amortized over additional calls until the resized capacity is filled.
- The `ArrayList` impementation increases capacity by about 50% each time.
- Block copy operation - optimized to run quickly for transferring elements.
- Adding an iterator: the collections framework often uses an iterator to traverse a collection. The iterator must have three basic operations: `hasNext()`, `next()`, and `remove()`.

```java
 1 // Objects of this class can be used to iterate over an
 2 // ArrayIntList and remove values from the list.
 3
 4 import java.util.*;
 5
 6 public class ArrayIntListIterator {
 7 private ArrayIntList list; // list to iterate over
 8 private int position; // current list position
 9 private boolean removeOK; // okay to remove now?
10
11 // post: constructs an iterator for the given list
12 public ArrayIntListIterator(ArrayIntList list) {
13 this.list = list;
14 position = 0;
15 removeOK = false;
16 }
17
18 // post: returns true if there are more elements left
19 public boolean hasNext() {
20 return position < list.size();
21 }
22
23 // pre : hasNext() (throws NoSuchElementException if not)
24 // post: returns the next element in the iteration
25 public int next() {
26 if (!hasNext()) {
27 throw new NoSuchElementException();
28 }
29 int result = list.get(position);
30 position++;
31 removeOK = true;
32 return result;
33 }
34
35 // pre : next() has been called without a call on remove
36 // (throws IllegalStateException if not)
37 // post: removes the last element returned by the iterator
38 public void remove() {
39 if (!removeOK) {
40 throw new IllegalStateException();
41 }
42 list.remove(position – 1);
43 position––;
44 removeOK = false;
45 }
46 }
```



---

## Chapter 16: Linked Lists

### 16.1: Working with Nodes
- Arrays are stored in one large contiguous block of memory, so we can quickly locate any element of an array.
- However, we cannot easily insert or remove values without shifting other valeus.
- Linked List: opposite properties. Not a random access structure: you cannot jump around in the structure.
- It is easy to insert or delete values in a linked list without shifting.
- **Node**: each node contains one data value. Node is like a Lego building block.
- A node contains an item for storing a single item of data and another to store the next node in the list.
- The `ListNode` class is defined in terms of itself because it has a field of type `ListNode`; thus, it is a recursive data structure.

```java
ListNode list;
list = new ListNode();
list.data = 3;
list.next = new ListNode();
list.next.data = 7;
list.next.next = new ListNode();
list.next.next.data = 12;
list.next.next.next = null;
```
- To get rid of a node, we reassign the links.
- When no variable points to a node, Java automatically invokes a garbage collector and reclaims space.
- `NullPointerException` - caused by calling a field on a `null` object.
- Introduce temporary variables to keep track of a node.
- Basic Linked List traversal structure:

```java
ListNode current = list;
while (current != null) {
  process next value.
  move current forward.
}

// printing each element of a Linked List
ListNode current = list;
while (current != null) {
  System.out.println(current.data);
  current = current.next;
}
```

### 16.2: A Linked List Class
- We would like to define a `LinkedIntClass` instead of needing to manipulate nodes ourself.
- We want everything to be completely encapsulated when writing code to interact with a client.

```java
public String toString() {
  if (size == 0) {
    return "[]";
  } else {
    String result = "[" + elementData[0];
    for (int i = 1; i < size; i++) {
      result += ", " + elementData[i];
    }
    result += "]";
    return result;
  }
}
```

- In linked list programming, there are only two ways to change the content of a list: changing the value of `front`, or changing the value of `<variable.next`.

```java
public void add(int value) {
  if (front == null) {
    front = new ListNode(value);
  } else {
    ListNode current = front;
    while (current.next != null) {
      current = current.next;
    }
    current.next = new ListNode(value);
  }
}
```

- Important 'stop one early' method: use `while (curr.next != null) {...}` instead of `while (curr != null) {...}`.
- A linked list has sequential access rather than fast random access.

### 16.3: A Complex List Operation
- Suppose we want to write a new method to add values to the list in a way that preserves a sorted order.
- Need to write several different exceptions and index ahead.
- Remember to adjust both next and previous linkage next links when inserting.
- Sensitive test and robust test. Robust must be written first.
- *Short circuited evaluation* - if the first test evaluates to `false`, Java does not perform the second in an `&&` situation.
- Consider the following cases:
  - `middle`: the typical case
  - `back`: insert at back of list
  - `front`: insert at front of list
  - `empty`: insert into an empty list
- Inchworm approach: consider an 'inchworm' that is two nodes in length. Pointers keep track of a two-element window on the list.

### 16.4: An IntList Interface
- We can introduce an inrerface to eliminate redundancy when two kinds of list behave in the same way.
- We understand lists as being the smae kind of thing.
- Remember to write `... class name implements interfaceName`, or an error will be thrown.
- You cannot instantiate an interface.
- Variables created as interfaces are more flexible.

```java
public void add(int index, int value) {
  if (index == 0) {
    front = new ListNode(value, front);
  } else {
    ListNode current = front;
    for (int i = 0; i < index – 1; i++) {
      current = current.next;
    }
    current.next = new ListNode(value, current.next);
  }
}

public void remove(int index) {
  if (index == 0) {
    front = front.next;
  } else {
    ListNode current = front;
    for (int i = 0; i < index – 1; i++) {
      current = current.next;
    }
    current.next = current.next.next;
  }
}
```

---

## Chapter 17: Binary Trees

### 17.1: Binary Tree Basics
- Each different data value in a tree is a node.
- Branch nodes vs leaf nodes
- A binary tree is either an empty tree or a root node that refers to two other trees known as a left subtree and a right subtree.
- *Branch* - a node that has one or more nonempty subtrees.
- *Leaf* - a node that has two empty subtrees.
- For every node `p` that has a nonempty subtree with root node `q`, we say that `p` is the parent of `q` and `q` is the child of `p`.
  - Other ancestral relationships follow: sibling, grandparent, etc.
- Similar to Linked Lists, but with a left and right component rather than just a next field.

### 17.2: Tree Traversals
- We can't do much with a tree unless we can see what's inside.
- A tree is defined recursively, so navigating it recursively is perhaps the easiest choice.
- Preorder - process the root before you traverse either subtree
- Postorder - process the root after you traverse both subtrees
- Inorder - process the root in between traversing either subtree
- Imagine a sailboat sailing down the 'coastline' of the tree.
  - When the sailboat passes nodes on the left, you get preorder traversal
  - When the sailboat passes underneath, you get inorder traversal
  - When the sailboat passes nodes on the right, you get postorder traversal






| This text is written on the 1000th line of the markdown file used to generate this webpage. |


```java
private void printPreorder(IntTreeNode root) {
  if (root != null) {
    System.out.print(" " + root.data);
    printPreorder(root.left);
    printPreorder(root.right);
  }
}

private void printInorder(IntTreeNode root) {
  if (root != null) {
    printInorder(root.left);
    System.out.print(" " + root.data);
    printInorder(root.right);
  }
}
```
- Printing a tree:

```java
public void printSideways() {
  printSideways(overallRoot, 0);
}
private void printSideways(IntTreeNode root, int level) {
  if (root != null) {
    printSideways(root.right, level + 1);
    for (int i = 0; i < level; i++) {
      System.out.print(" ");
    }
    System.out.println(root.data);
    printSideways(root.left, level + 1);
  }
}
```

### 17.3: Common Tree Operations
- Sum of a tree: use a private/public pair, return 0 if root is null and return sum of current root data and sum of left and right subtrees if not.
- Counting levels: return 1 + the maximum depth of the left or right subtree.
  - The height of a tree is 1 less than the number of levels.
- Counting leaves: if is a leaf, return 1; otherwise, sum leaf counts of left and right subtres.

### 17.4: Binary Search Trees
- Both the `TreeMap` and `TreeSet` classes in Java are binary search trees.
- Binary Search Tree property: the values in a binary tree are guaranteed to be arranged in a way such that the values in the left subtree are all less than the root data, and the values in the right subtree are all greater than the root data.
- An inorder traversal returns a sorted array.
- `IntSearchTree`
- Reassignment doesn't work for recursive binary tree code because you are re-assigning a local variable.
- The pattern `x = change(x)`
- Binary tree complexity: `log N`
- Degenerate tree - a tree that is technically still a tree but isn't really a good one, a linked list turned on its side.

---

## Chapter 18: Advanced Data Structures

### 18.1: Hashing
- *Hashing* - technique to efficiently map data elements to indexes in an array. A collection can have add, remove, and search for elements in `O(1)`.
- Hash function - allows us to organize elemetns of our set and search it quickly.
- Idea: stpre element value $$k$$ at index $$k$$-mod-$$c$$,w here $$c$$ is the capacity.
- Hash function method - uses a hash table to govern insertion and deletion of elements. Individual indexes in the hash table: buckets.
- Collision: two values can have the same preferred index. Probing: look for another index to use if the preferred index is taken. Linear vs quadratic probing.
- Clustering - elements clumping near each other.
- If each array index can store more than one value, collissions are not a problem. We can resolve collisions by storing hash elements in lists using separate chaining.
- Most hash table implementations use a prime number for table capacity to encourage even bucketing/minimum collision.
- Rehashing: esizing a hash table to increase its capacity and enabling it to store more elements, or store them more efficiently.
- To hash non-integer data, request the `hashCode` (implemented in the `Object` object).












