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





