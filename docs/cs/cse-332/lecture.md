---
layout: default
title: Lecture Notes
parent: CSE 332
grand_parent: Computer Science
nav_order: 2
---

# Lecture Notes
{: .no_toc }

CSE 332
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

## Lecture 1: Intro, Stacks, and Queues
Data structures
- A clever way to organize information to enable efficient computation over that information
  - Accessing elements in array -- `O(1)`
  - Accessing elements in linked list -- `O(n)`
  - Adding element at the front of a linked list -- `O(1)`
  - Adding element at the front of an array -- `O(n)`
  - Binary search tree, find max element -- `O(log n)`
- Abstract Data Type (ADT) -- mathematical description of a thing and set of oeprations
- Data structure -- specific organization of data and algorithms for implementing an ADT
- Implementation -- actual code implementation of a data structure
- Stack ADT -- push, pop, isEmpty, etc. 
  - LIFO -- last in first out
- Queue
  - FIFO -- first in first out
  - Operations: enqueue, dequeue, isEmpty, etc.
  - Circular array queue data structure -- enqueue and dequeue are `O(1)`
  - Can also use a doubly linked list

---

## Lecture 2: Algorithmic Analysis
- What do we care about?
  - Correctness
  - Performance: speed (time complexity) and memory (space complexity)
- How to compare two algorithms? A lot of variability, doesn't capture worst-case; what if $$n$$ grows?
  - We want to evaluate the algorithm rather than the implementation specifically used

Counting basic code constructs
- Assume basic operations take the same amount of time

| Code Construct | Time |
| --- | --- |
| consecutive statement | sum of times |
| loops | num iterations $$\times$$ loop body time |
| condiitionals | time of condition $$+$$ slowest branch |
| method calls | time of function's body |
| recursion | solve recurrence relation |

- Two scenarios: worst-case and best-case complexity
- Usually focus on worst-case complexity -- max # steps the algorithm takes for the most challenging input of size $$n$$; assume $$n$$ is big.
- Why not use the 'average' case? Not sure what this means.
- Amortized-case complexity, e.g. resizing an array. 
- Asymptotic analysis: getting the big-O
  - Eliminate all low-order terms and eliminate constant coefficients.
- We use $$\mathcal{O{$$ on a function to mean the set of functions with asymptotic behavior less than or equal to $$f(n)$$.
- Suppose $$f: \mathbb{N} \to \mathbb{R}, g: \mathbb{N} \to \mathbb{R}$$ are two functions. Then,

$$f(n) \in \mathcal{O}(g(n))  \equiv \exists_{c \in \mathbb{R}_{>0, n_0 \in \mathbb{N}} \forall_{n \in \mathbb{N} \ge n_0} f(n) \le c \cdot g(n)$$

- $$n_0$$ represents the threshold at which a function truly exceeds the other for the rest of the positive domain. 
- Technically, $$\log n \in \mathcal{O}(n)$$ is correct. But we want a tighter bound: $$\log n \in \mathcal{O}(\log n)$$
- We want to remain invariant to differences in scaling, so we have a $$c$$.

---

## Lecture 3: Algorithmic Analysis II, Amortization
- Counting code constructs
- How to show that $$f(n) \in \mathcal{O}(f(n))$$? Pick $$c$$ to account for constant factors and $$n_0$$ to cover lower-order terms
- Informal way to understnd big O is in terms of droppable terms which characterize class (invariant to scaling)
- Big omega -- same as Big-Oh, but with $$f(n) \ge c \cdot g_n$$. Therefore $$f(n)  \in \Omega (g(n))$$ iff $$f(n)$$ eventually constitutes a lower bound.
- Tight bound $$\Theta$$

$$f(n) \in \Theta(g(n)) \equiv f(n) \in \mathcal{O}(g(n)) \wedge f(n) \in \Omega(g(n))$$

- Little oh and omega: no 'equals to'
- Big Theta -- a function is in $$\Theta(g(n))$$ if there is a tight bound, it is being squeezed between big oh and big omega.
- Worst and best -- all about case / scenario
- Assuming a particular scenario, what happens as $$n \to \infty$$?
- Big-Oh: what's the worst growth rate this algorithm could have?
- Big-Omega: what's the best growth this algorithm could have?
- Although these two are technically incorrect.
- Usually concerned with worst and amortized for tight or upper asymptotic analysis
- Mtovation: the worst case is too pessimistic. 
- Amortization: max total # steps an algorithm takes on $$M$$ most challenging consecutive inputs of size $$n$$ divided by $$m$$: averages the running times of operations in a worst-case sequence over that sequence

---

## Lecture 4: Priority Queues
- "Highest priority, first out"
- Operations:
  - `insert` (adds item at the end, enqueue equivalent)
  - `deleteMin` (finds, returns, and removes minimum element in priority queue, dequeue equivalent)
    - Break ties arbitrarily
- Implemented by a heap
- Holds comparable data, in the sense that every element has a priority

| | `insert` | `deleteMin`
| unsorted array | `O(1)` | `O(n)` |
| unsorted linked list | `O(1)` | `O(n)` |
| sorted circular array | `O(n)` | `O(1)` |
| sorted linked list | `O(n)` | `O(1)` |
| binary search tree | `O(n)` | `O(n)` |
| binary min heap | `O(log n)` | `O(log n)` |

- We pay for functionality needed
  - Don't want to scan all the items, but we also maintain a full sorted list
  - Visualize heap as a tree
- Height: count arrows from node to deepest descendent
- Depth: count the arrows from root to node
- Binary tree: every node has at most 2 children
- n-ary tree: every node has at most $$n$$ children
- Complete tree: every row is completely full except for the bottom row, bottom row is filled left to right
- Perfect tree: every row is completely full
- Height is $$\mathcal{P}(\log n)$$

$$n = \sum_{i = 0}^h 2^i = 2^{h+1} - 1$$

$$\log n = \log 2^{h+1} - 1$$

- Binary min heaps
  - Smallest element is at the root
  - A complete binary tree
  - Heap order priority: every non-root node has a priority value greater than or equal to its parent
- Strategy for every operation:
  - Preserve complete tree structure property
  - May break heap order property
  - Percolate to restore heap order property
- Percolate up: swap with the parent until you reach the root or the heap order property is fulfilled
- Deletion:
  - Grab minimum element (root) and delete it
  - Only option is to move the bottom-rightmost element as the root
  - This probably breaks heap order quality, so percolate down to restore heap order property
  - When percolating down, swap with the *smallest child*

- Array representation of heap
  - Root at index 1, children at $$2i$$ and $$2i + 1$$ for any $$i$$
  - Parent is given by `i / 2` (integer division) 
- Array implementation:
  - Minimal wasted space -- using tree node objects requires pointers, which are expensive
  - Fast lookups: index is very nice
  - Resizing is an issue, but not by that much.
- Increase and decrease priority operations: change index value and then percolate up or down
  - Can conceive of deleting any particular keep as decreasing key by infinity and then percolating to top, and then delete min.

## Lecture 5: `buildHeap` and Recurrences
- Scenario: $$n$$ elements into a blank heap. Calling insert $$n$$ times gives $$n \log n$$.
- We can do better with Floyd's `buildHeap` (linear time)
  1. Put $$n$$ elements in the array, any order is OK
  2. Percolate down, starting from the lowest non-leaf  node not in the last row, and working up to the root. (Leaves are already in the correct ordering.)
- Runtime efficiency calculations
  - Given completeness, the total loop iterations is $$\frac{n}{2}$$
  - For half of its iterations (bottom full row), percolate at most 1 step; $$\frac{1}{2}$$ cost
  - For a quarter of its iterations (second to bottom full row), percolate at most 2 steps, $$\frac{2}{4}$$ cost
  - Summed cost: $$\frac{1}{2} + \frac{2}{4} + \frac{3}{8} + ...) = 2$$
  - $$2 \cdot \frac{n}{2} \in \mathcal{O}(n)$$
- Intuition for correctness: build a hierarchy of nodes that we promise are going to be correct.

Couhnting recursive code
- Analogy: performing computation recursively on a list of size $$n$$
- Each recursive call performs some non-recursive work $$w(n)$$ and then calls the method on a smaller resource $$T(n - 1)$$
- We reach a base case with work $$b(n)$$
- Total work is given by $$T(n) = w(n) + T(n-1)$$, $$T(1) = b(n)$$
- Recurrence function / relation: piecewise function which mathematical models the runtime of a recursive algorithm
- Unrolling method
  - Expand via substitution
  - Find the closed form -- find when the base case occurs and get to the base case.
  


