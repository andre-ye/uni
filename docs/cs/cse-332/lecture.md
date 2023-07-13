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
  
---

## Lecture 6: Tree Recurrence Method, Dictionary ADT
Last time -- algorithmic analysis of recursive code
  1. Write recurrences
  2. Solve recurrences
  3. Perform asymptotic analysis or find big-theta.
- Unrolling method: keep on substituting until a pattern emerges. 
- Closed form: get to the very base case and then rewrite it in terms of some $$n$$.
- 'Binary sum' recurrent relation:

$$T(n) = \begin{cases} c_0, & \text{ for} n=1 \\ c_1 + 2 T\left(\frac{n}{2} \right), & \text{ otherwise} \end{cases}$$

- Be careful: if you have something like `return 2 * binarySum(arr, lo, mid)` -- the resulting recursive relation is not `2 \cdot T\left(\frac{n}{2})`, because `2` is just a constant factor: it is actually just `T\left(\frac{n}{2})` because we are only doing the computation once.
- Tree method: you want to find the general formula and then the closed form.
- General formula
  1. Intiailize table
  2. Draw actual tree
  3. Add miscellaneous details -- recrsive calls, # nodes, sum work, etc.
  4. Find the base case
  5. Do work calculation
- The sum work is the number of nodes at each recursive level multiplied by the amount of work at each node

$$\sum_{i=0}^m x_i = \frac{1 - x^{m+1}}{1 - x}$$

Common recurrences

| Common recurrence relation | Order of growth | Example |
| --- | --- | --- |
| $$T(n) = T(n/2) + c$$ | $$\log n$$ | binary search |
| $$T(n) = 2T(n/2) + n$$ | $$n \log n$$ | merge sort |
| $$T(n) = T(n/2) + n$$ | $$n$$ | |
| $$T(n) = 2 T(n/2) + c$$ | $$n$$ | recursive binary sum |
| $$T(n) = T(n-1) + c$$ | $$n$$ | recursive sum |
| $$T(n) = T(n - 1) + n$$ | $$n^2$$ | |
| $$T(n) = 2T(n-1) + c$$ | $$2^n$$ | |

Dictionary ADTs
- ADTs so far: stack, queue, priority queue
- Dictionary/map: one of the most important ADTs
- A set of unique key-value pairs -- the keyset must be unique
- A set ADT is similar to a dictionary ADT without any values
- A set: does a key exist or not? (no duplicates)

Dictionary runtimes with primitive data structures

| | insert | find | delete |
| unsorted linked list | $$\mathcal{O}(n)$$ | $$\mathcal{O}(n)$$ | $$\mathcal{O}(n)$$ |
| unsorted array | $$\mathcal{O}(n)$$ | $$\mathcal{O}(n)$$ | $$\mathcal{O}(n)$$ |
| sorted linked list | $$\mathcal{O}(n)$$ | $$\mathcal{O}(n)$$ | $$\mathcal{O}(n)$$ |
| sorted array | $$\mathcal{O}(n)$$ | $$\mathcal{O}(\log n)$$ | $$\mathcal{O}(n)$$ |


---

## Lecture 7: Binary Search Trees
- Dictionary ADT: set of unique key-value pairs.
- Lazy deletion -- instead of deleting the physical element in the array, include an extra bit in each field indicating whether the element is deleted or not.
  - Advantages: simpler, can remove in batches, just unmark if re-added
  - Disadvantages: extra space, wastes space, $$\log m$$ time where $$m \ge n$$
- Height is noramlly $$\log n$$, but we need guaranteed balancing of search trees to present worst case linear time.
- Trees offer speedups because of branching factors
- We can improve worst-case to $$\log n$$ for all operations (search, add, delete) by using a binary search tree
- We need a data structure which uses a binary search mechanism
- Binary tree is either a root, a left subtree, or a right subtree. It is data with a left pointer and a right poitner. For a dictionary, the data will be a key-value pair.
- For a binary tree of height $$h$$,
  - the maximum number of leaves is $$2^h$$
  - maximum number of nodes is $$2^{h+1} - 1$$
  - minimum number of leaves is $$1$$
  - minimum number of nodes is $$h + 1$$
- Height: distance from root to the furthest leaf -- recursive code to check left and right child
- Pre-order, in-order, post-order
  - Pre-order: root, left, right
  - In-order: left, root, right
  - Post-order: left, right, root
- Recursing through left subtree, root, right subtree
- A lot of code with trees is done through recursion
- Structure (each node has 2 or less children) and order (all keys in the left subtree are less than the node's key, and all keys in the right subtree are larger)
  - Keys must be comparable
  - No duplicates are allowed
  - No less than or equals to
- `find` method: recursive. If key is less than root key, return find for left subtree. If key is greater than root key, return find for right subtree. If key is equal to root key, return root.
  - Minimum node: keep on going left until you hit a null node
  - Maximum node: keep on going right until you hit a null node
- `insert`: each insert is inserting a leaf node. Call `find`, and then create a new leaf node.
- `delete`: 3 cases. Important thing is to keep the ordering property met.
  1. Node is a leaf node: just delete it
  2. Node has one child: replace node with child
  3. Node has two children: replace node with successor (minimum of right subtree) or predecessor (maximum of left subtree)
- Balancing conditions which both don't work because you can carry on with linked-list problem
  - Left and right subtree of just the root have the same number of nodes
  - Left and right subtree of just root have the same height
- Balancing conditions -- every node has the same number of nodes or every node has the same height, this is TOO STRONG -- because it requires only perfect trees. Certain numbers of elements don't even work.
- Instead, we meet in the middle. Left and right tree heights differ by at most one for every node.

AVL balance property:
$$\left| \text{height of left subtree} - \text{height of right subtree} \right| \le 1$$

- Always ensures that the root height is $$\log n$$, and is efficient to maintain -- $$\Theta(1)$$ rotations.
- AVL Tree stands for Adelson-Velskii and Landis
- AVL tree is a BST which is balanced
- With an AVL Tree node, we also add a height field into our node so we can keep our field value.

---

## Lecture 8: AVL Trees
- Use B-Trees and Quicksort sorting presented in class
- AVL Tree is a BST which is balanced
- P is the problme node where an imbalance occurs. There are four cases.
  - Left-left: left child of left subtree
  - Left-right: right child of left subtree
  - Right-right: right child of right subtree
  - Right-left: left child of right subtree
- Cases 1 and 3 are solved by a single rotation; cases 2 and 4 are solved by a double rotation
- When going back up, use backtracking and rebalance the deepest imbalanced node
- Single-rotation (left left and right right):
  1. Move the child of p to the position of p
  2. p becomes the 'other' child
  3. Other subtrees move based on what BST allows

Left-left:
```
    p          A
   / \        / \
  A   Z  ->  X   p
 / \            / \
X   Y          Y   Z
```
Right-right:
```
  p              A
 / \            / \
Z   A    ->    p   X
   / \        / \
  Y   X      Z   Y
```

- Double rotation (left-right and right-left)
  - Rotate p's child and grandchild
  - Rotate p and p's new child

```
  p       p
   \       \          X
    A  ->   X   ->   / \
   /         \      p   A
  X           A
```

- AVL efficiency:
  - find is in $$\mathcal{O}(\log n)$$
  - insert is in $$\mathcal{O}(\log n)$$
    - rotation is in $$\mathcal{O}(1)$$
    - Deepest descendant is in $$\mathcal{O}(\log n)$$
  - buildTree is in $$\mathcal{O}(\log n)$$
  - Lazy and nonlazy deletion are both in $$\mathcal{O}(\log n)$$
- DSA is all about maintaining invariants / assumptions
- Pros of AVL Trees:
  - All operations are worst-case because trees are always balanced
  - height balancing adds no more than a constant factor
- Cons of AVL Trees:
  - Difficult to program and debug
  - MOre space needed for the height field
  - Asymptotically faster, but rebalancing does take time
  - Mot large searches are done in data-base systems, where the data is stored on disk. Disk access is slow, so we want to minimize the number of disk accesses. AVL trees are not good for this because they are not cache-friendly.
- B-trees try to exploit the fact that disk access is slow with high branching and use block sizes (accessing contiguous chunks of memory at a time)

---

## Lecture 9: B-Trees
- Disk accesses are expensive, how can we minimize disk accesses?
- Moving data up the memory hierarchy is slow because of latency
- Nearby memory is sent because it's easy and will be asked for soon, esp in the context of arrays
- Temporal locality -- lcoaity in time
- Spatial locality -- locality in sapce
- Arrays vs linked list, which can better take advantage of the spatial locality?














