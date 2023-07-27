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
  - Array, obv
- AVL has worst-case $$\mathcal{O}(\log n)$$, but it's not cache-friendly
- B-trees are better for large dictionaries, e.g. over 1 GB
- Disk to memory: block size, page size. Memory to cache: line size. 
- Array benefits from linked list because of contiguous memory accessing
- BSTs: looking things up in binary search trees is log-*n*, but still disk accesses matter. The tree might not be able to fit entirely in memory even if the tree is very shallow.
- We want a balanced tree even shalower than AVL trees so we can minimize disk accesses and exploit disk block size by *increasing the branching factor*
- We have a search tree with a branching factor M and an array of sorted children; M is chosen to fit nicely into the disk block such that we have 1 access per array.
- Say that you have block size $$d$$, pointer size $$p$$, key size $$k$$, key-value pair size $$v$$. You need an internal node to fit in the block:

$$(M - 1) \cdot k + M \cdot p \le d$$
$$M \le \frac{d + k}{p + k}$$
$$M = \lfloor \frac{d + k}{p + k} \rfloor$$$$

$$v \cdot L \le d \to L = \lfloor \frac{d}{v} \rfloor$$

- `find` requires $$\log_M(n)$$ finds
- If it's balanced, the runtime is actually $$\mathcal{O}(\log_2 M \log_M n$$ 
  - $$\log_M n$$ is the height we traverse
  - $$\log_2 M$$ is finding the correct child branch to take using binary search among the M options

---

## Lecture 10: Hashing
- Dictionary data structures: unsorted linked list, unsorted array, sorted linked list, sorted array, balanced tree
- Hash table: giant array. Fit as many key-value pairs as possible.
- A hash function converts a key into an integer. Modding it by the table size gives me my index.
- What if mutliple kye pairs match to the same value? This is a collision. We want to avoid collisions when possible. It is unavoidable to have coillissions though.
- How do we resolve collisions?
- Hash table worst runtimes are all going to be `O(1)`, assuming few collisions
- We can no longer implement findMin, findMax, predecessor, successor, sort, etc. as opposed to trees
- Typically the size is smaller than possible key space

Hash Function
- An ideal hash function is fast to compute and rarely hashes two used keys to the same index
- Hash tables are generic
- The client implements the hash function, implementer mods it
- Using prime numbers for table size is common
- Client should aim for different ints for expected items, e.g. avoid wasting any part of E or the 32 bits for `int`
- What to hash? We will focus on ints and strings
- Identifying fields should contribute tot he hash function to avoid collisions
- But don't add too many to lengthen the hash function time too much
- Hashing time vs collision avoidance trade-off
- Simple hash function: `h(x) = x`, library `g(x) = h(x) % TableSize`
- Technique for prime: real-life data tends to follow a pattern, so we want to avoid that pattern
- What if the key is not an int?
- Strings: sum of ASCII, or sum of ASCII times the power of sum number to avoid permutation case
- JDK hashcode value: 31 exponent plus the ascii value, again using 31 as a prime number
- Use all 32 bits, which includes negative numbers
- If keys are known ahead of time, choose a perfect hash
- You can hash each of the fields and combine with a string-like formula
- Linear probing: if there is a collision, go to the next available spot
- Quadratic probing: if there is a collision, go to the next available spot, but skip by a quadratic function
- Double hashing: if there is a collision, go to the next available spot, but skip by a function of the key
- Separate chaining: all keys mapping to the same table location are kept in a list
- Some data structure engineering can improve constant factors, such as move-to-front or linked list or array, etc.
- Lambda: load factor, $$\lambda = \frac{n}{m}$$ where $$n$$ is the number of items and $$m$$ is the table size
- Unsuccessful `find` compares against $$\lambda$$ items, successful `find` compares against $$\frac{\lambda}{2}$$ items (on average)
- To keep runtime constant, resize TableSize to keep $$\lambda$$ constant

---

## Lecture 11: More Hashing
- Hashing has very fast average runtimes -- an array is a hash table, use a hash function
- A lot of different choices: hash function, tabl size, collision resolution strategy
- Open addressing with linear probing: try the next available spot mod table size
- Open addressing: resolve collisions by trying a sequence of other positions in the table 
- Probe function $$f$$: `i`th probe is `(h(key) + f(i)) % TableSize`
- Open addressing does poorly with a high load factor $$\lambda$$
- For the `find` operation, we store values with keys, and we keep going along the probe sequence until we hit an empty slot
- For `delete`, we risk pausing the `find` probe early with empty slots. Use lazy deletion to mark there used to be a key there
- LInear probing is a bad idea because it tends to form clusters, which lead to long probe sequences. Also called primary clustering. Each insert operation either appends to the end of a cluster or creates a new cluster.
- Quadratic probing: $$f(i) = i^2$$
- You might end up with an infinite loop though
- Proof: use a prime TableSize, so quadratic probing will find an empty slot in at most Table Size divided by 2 probes. SO if lambda is less than half, no need to detect cycles.
- Quadratic probing does not resolve collisions between keys that initially hash to the same index: secondary clustering
- Double hashing: $$f(i) = i \cdot h'(key)$$ where $$h'$$ is a second hash function. If two keys hash to the same index, it is unlikely that they will follow the same probe sequence.
- While we prevent secondary hashing (possibly), we run the risk of infinite cycles
- We no longer have a convenient theorem for double hashing
- Some functions `h` and `g` have proven resistance to infintite cycles
- As lambda approaches 1, resize the table because you don't want to do too much probing
- Advantage is less memory allocation -- less chaining, it's just in one array
- Separate chaining is more intuitive and easier to implement, also linear rather than exponentially increasing as lambda approaches one
- Can optimize the structure of storage within a single bucket
- Rehashing: when you resize the table, you need to rehash all the keys
  - Separate chaining: you can decide what too full means, probably keeping the load factor reasonable
  - Open addressing: half full is a good rule of thumb
- Good idea to double. But you should choose a prime if you can.

---

## Lecture 12: Comparison Sorts
- Why sorting? -- common to need data to be sorted
- Goals: stable (preserve original ordering in the case of ties), in-place (no extra memory), fast (typically $$\mathcal{O}(n \log n)$$)
- Insertion sort: beginning is sorted, end is unsorted, loop through and find the best way to put it
- Selection sort: find the smallest element and append it to the end of the sorted part.
  - Stable and in place, but not fast -- best case and worst case are both $$\mathcal{O}(n^2)$$
- Selection sort, most work is done in the unsorted part (selecting)
- Insertion sort, most work is done in the sorted part (inserting)
- Bubble Sort -- pretend it doesn't exist, really bad asymptotic complexity and bad constant factors, literally should not be used ever.
- Heap Sort -- use a heap, put all element into a heap with build-heap ($$O(n)$$) and then remove elements one by one and put them back in the heap ($$O(n \log n)$$)
  - This is stable: treat the initial array as a heap, when you delete the `i`th element, you put it in `arr[n-i]`. When you `deleteMin`, there's always an empty block at the beginning, because heaps are a complete tree.
- AVL Sort: not good, insert all elements into balanced tree and then do an in-order traversal. It's not in-place and also has worse constant factors, with all the balancing etc. -- holding an entire data structure just to sort something. Heap sort is just better than AVL sort.
- Merge sort: sort the left half of the elements recursively, sort the right half of the elements recursively, merge the two sorted halves into a sorted whole (linear-time). Runs in $$\mathcal{O}(n \log n)$$
  - Stable, not in-place
  - Merge step is linear time
  - Recursive calls are $$\mathcal{O}(n \log n)$$
  - Merge sort is asymptotically optimal for comparison sorts
  - Use 3 pointers and 1 more array and copy into an array, and then copy from the array back to the original. 
  - Stable? Yes, prioritize left array.
  - In place? No, $$O(n)$$ space.
  - Fast? Yes, it has worse constant factors though. Copying, merging, etc.
  - Why is it $$O(n \log n)$$? The merge sort case, we have $$2T(n/2) + c_1 n + c_2$$. 
- Quick sort: Pick a pivot element, which is hopefully the median element. Divide the elements into 2 halves, less than pivot and greater than pivot, and recursively sort the two halves.
  - The pivot you pick can make the difference between $$O(n^2)$$ and $$O(n \log n)$$
  - Warning, many different versions of quick sort on the internet.
  - How do we pick a good pivot? This is the majority of the runtime.
    - Pick lowest or highest element. This can be disasterous. Fast but likely worst-case
    - Ideally we want to picka  random element, but pseudorandomness is actually very expensive in terms of constant factors.
    - In practice we use median of 3, choose the median of the low, middle, and high index of the array. 
  - Parittioning issue -- given a pivot, how do you split the array into two? This is a problem -- ideally we want it to be fast $$\mathcal{O}(n)$$ linear time and for it to also be an in-place operation. Of course linear time runtime is more important. 
  - "Hoare" partitioning approach: swap pivot with `arr[lo]`, move it out of the way. Use two pointers `l` and `r` starting at `lo + 1` and `hi - 1`. Move `l` and `r` such that `arr[l]` should be on the right of the pivot and `arr[r]` should be on the left of the pivot. 
  - Quicksort is not stable because of the partitioning set -- doing a bunch of swaps where we don't know where elements end up at
  - In term sof asymptotics, kind of -- best case and average case is $$\mathcal{O}(n \log n)$$, worst case is $$\mathcal{O}(n^2)$$
  - Worst constant factors but in practice it's faster and used often, e.g. in Python

---

## Lecture 13: Non-comparison Sorts
- Insertion and selection sort have good constant time; heap sort, merge sort, and quick sort have good asymptotic time
- When the array is small, sort with insertion sort; when it is large, sort with quick sort
- $$\Omega (n \log n$$ is the best runtime for a sorting algorithm which only interacts with tis input by comparing elements.
  - Tree "proof" intuition: comparisons can be mapped to a tree structure, height and node counts contribute to $$n \log n$$ factor
- Bucket Sort / Bin Sert
  - Given an array of numbers spanning a small range of integers
  - Find the min and max value
  - Make an aux array to represent range between min and max
  - Go through original array and tally each number
  - Copy aux into original array
  - Stable: can be made stable
  - In place: no, need aux array
  - Fast: yes, $$\mathcal{O}(n + k)$$
- Radix sort
  - Intuition: exploit integer digits
  - Sort by least significant digit, then second least significant digit, etc. Works because bucket sort is stable.
  - Stable? Yes.
  - In place? No.
  - Fast? Yes, worst case is $$\mathcal{O}(d \cdot (n + k))$$

---

## Lecture 14: Introduction to Graphs
- A graph $$G$$ is a pair of sets ($$V$$, $$E$$) where
  - $$V = \{v_1, v_2, ..., v_n\}$$ is a set of vertices
  - $$E = \{e_1, e_2, ..., e_m\}$$ is a set of edges
    - where each edge is a pair of vertices $$e_i = (v_j, v_k)$$
- Undirected graphs: edges have no specific direction, edges are "two-way"

$$(v, u) \in E \to (u, v) \in E$$

- Degree of a vertex: the number of edges containing that vertex, i.e. the number of adjacent vertices
- Directed graphs: edges have a direction; a pair $$(v, u) \in E$$ means $$v$$ is the source and $$u$$ is the destination
  - In-degree: number of in-bound edges where $$w$$ is the destination
  - Out-degree: number of out-bound edges
- Self-edges: we pretend they don't exist
- Weighted graphs: each edge has a weight or a cost, typically a number

---

## Lecture 15: Graph Traversals
- A walk: a sequence of adjacent vertices
- Path, simiple path: a walk that doesn't repeat a vertex
- Cycle: a walk that doesn't repeat a vertex except the first and alst
- Length: number of edges
- Cost: sum of weights from each edge
- Undirected graph
  - Connected if for all pairs of vertices there exists a path from one to the other
  - Complete (fully-connected) of for all pairs of vertices there exists an edge from one to the other, including self edges
- Directed graph
  - Strongly connected: path from every vertex to every other vertex
  - Weakly connected if there is a path from every vertex to another ignoring direction
  - Fully connected / complete if for every vertex there is a pointer from it to every other vertex
- Every tree is a graph -- which is undirected, acyclic, and connected.
- Rooted trees -- just pick a root. So it becomes directed.
- Directed Acyclic Graphs: DAGs. A directed graph with no cycles. Come up very often in graph prolbems. Every DAG is a directed graph but not vice versa.
- Undirected: $$0 \le \vert E \vert < \vert V \vert^2$$
- Directed: $$0 \le \vert E \vert \le \vert V \vert^2$$
- Given $$\vert V \vert $$ vertices, the
  - minimum number of edges is 0
  - Maximum number of undirected edges is $$\frac{\vert V \vert (\vert V \vert - 1)}{2}$$
  - Maximum number of directed edges is $$V^2$$
- Sparse: $$\vert E \vert \in \Theta \left( \vert V \vert \right)$$, few edges
- Dense: $$\vert E \vert \in \Theta \left( \vert V \vert^2 \right)$$, many edges
- Graphs, the data structure -- many data structures na dtrade-offs, exploits graph properties
  - Common operations: is ($$v, u$$) an edge?? What are neighbors of $$v$$?
- Adjacency matrix: 2-d array of booleans
  - Better for dense graphs
  - Large space requirements: $$\Theta \left( \vert V \vert^2 \right)$$
  - Fast edge insert, delete, and search
  - Slow vertex add and delete
    - Pretty fast neighbor search
- Adjacency List
  - Assign each node a number from 0 to $$\vert V \vert - 1$$
  - Array of length $$\vert V \vert$$, each element is a linked list of neighbors
  - To decide if some edge exists, is $$\mathcal{O}(d)$$, where $$d$$ is the out-degree of the source vertex
  - Space requirements: $$\Theta \left( \vert V \vert + \vert E \vert \right)$$
  - Better for sparse graphs
- Graphs are often very sparse, so adjacency lists are often better
- Graphs: Algorithms.
  - Depth-first graph search and breadth-first graph search.
  - Shortest path
  - Topological search
- Traversals
  - In a graph, find all nodes from a node source, is there a path from the source to a specific node?
  - Basic idea: keep following nodes, mark nodes after visiting them such that it processes each node once
  - Processing (print it) vs visiting (just getting there)
  - Visiting always happens before processing

---

## Lecture 16: Graph Traversals
- Depth-First Search
  - Uses a stack
  - Recursively explore far away from the source node first
  - Add source to stack. While stock is not empty, pop from the stack, for each adjacent node, if the node is not marked, mark it as visited and push it onto the stack.
- Breadth-First Search
  - Uses a queue
  - Explore everything near the source first
  - Add source to queue. While queue is not empty, dequeue from the queue, for each adjacent node, if the node is not marked, mark it as visited and enqueue it.
- DFS tends to use less memory compared to BFS because it only needs to store nodes along the current branch. Applications in topological sorting and cycle detection.
- BFS tends to use more memory, needs to store all nodes at the current level before moving to the next level. Applications for shortest paths
- Third option: iterative deep DFS (IDDFS), uses DFS with increasing depth limits
- Traversal, savin gthe path: store the predecessor node along the path. When you're done searching, follow the predecessor backwards to where you started.
- Problem: BFS does not work because the shortest path may not have the fewest edges when you consider a weighted graph.
- Doesn't work with negative weights because if there are cycles you can have negative cost cycles or positive cost cycles
- Dijkstra's algorithm
  - Start node A has cost 0 and all other nodes have cost infinity
  - At each setep
    - Pick closest unvisited vertex V
    - Add it to a cloud of visited vertices
    - Update distances for nodes with edges from V
  - Terminate when all nodes are visited
  - Dijkstra's, comparing the current best, once you've expanded the cloud you have a lot of good information about the current best















