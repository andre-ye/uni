---
layout: default
title: Lecture Notes
parent: CSE 431
grand_parent: Computer Science
nav_order: 1
---

# Lecture Notes
{: .no_toc }

CSE 431
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

## Lecture 1: Introduction, Models of Computation

- Part of computer science that tries to address the big questions
    - What can we compute and not compute? Is there an algorithm for everything?
    - Is it possible to speed up every sequential algorithm with parallelism?
- Ask philosophical questions and answer them with mathematics.
- We need definitions to say what words mean? What is a good model for computation?
- What is computation?
    - Function: takes something coming from a domain and mapping it to a range
    - But what is the function? What are the steps? What steps are you allowed? How do you mesaure if it's efficient?
- Assumptions: mostly talking about computing functions, but assume that the domain is $$\{0, 1\}^*$$ (all binary strings) or $$\{0, 1\}^n$$ (binary strings of length n) and the range is a single bit $$\{0, 1\$$
- Finite automata: there is a start vertex, and from every vertex there is an outgoing edge (0, 1), and there an accept vertex which is a 1.
    - Don't like this model: does not compute easy things, e.g. palindromes or matching parentheses
    - No resource to see how efficient the function is -- the length is just dependent on the input, something is missing -- there's no way to say if some functions are hard and if some are easy
    - No good complexity measure 
- Branching programs: there's a start vertex with a zero and one edge coming out of it; it has a bunch of layers and two edges coming out of every vertex, but every edge has to go forward to the next layer. It maps the $$n$$-bit inputs; you can talk about a branching program for it. You can also read it in any ordedr.
    - Different metrics: time (length) and width (roughly, amount of memory you need when you execute the program)
    - Parallel time is related to the depth of width 5 of branching programs.
        - Every function can be computed with a width-5 branching program.
    - You can start asking interesting questions about the model. Does this model give a complexity measure to every function? Can you compute every function with such an object? Yes -- you can use the width to remember the entire input.
    - Every function can be computed with length $$n$$ and width $$2^n$$
    - Trade-off between memory and time
- Boolean circuits: you have different inputs, and then gates that compute things from the variables, you might have and, or, negation, etc.
    - Can be interpreted as writing programs in a very simple programming language.
    - You can measure the size as the number of gates, or the number of execution sets. THis corresponds exactly to the running time.
    - You can also measure the depth -- the length of the longest path. Corresponds to the time to execute this in parallel.
    - Rephrasing the parallelism question: Can every circuit of size $$s$$ be simulated in depth $$O(\log s)$$?
- Theorem 1: If $$f$$ is computed with width 5 and length $$2^d$$, you can compute $$f$$ in depth $$O(d)$$.
- Theorem 2: If $$f$$ is computed with depth $$d$$, then $$f$$ is computed in width $$5$$ and length $$4^d$$.







