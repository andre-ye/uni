---
layout: default
title: Lecture
parent: MATH 208
grand_parent: Mathematics
nav_order: 1
---

# Lecture Notes
{: .no_toc }

MATH 208
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

## Week 1 Wednesday
- Homework - two parts, WebAssign and conceptual problems. Exams are modeled on conceptual problems.
- Three large sides of linear algebra
  - Solving linear equations - generalizing linear equation solving across dimensions and number of equations.
  - Linear transformations
  - Data
- Why does mechanical/computational arithmetic on linear equation systems work? Because transformations preserve the equality of their solutions: lines are transfered into vertical and horizontal forms through repeated manipulation.
- In $$n$$ dimensions, we need $$n$$ hyperplanes to define a point; each point cuts down on one dimension.

## Week 1 Friday

Problem: A bag is thrown from a bridge at 5 m/sec; after 3 sec; the bag is 25.9m from the water with velocity -34.4 m/sec and acceleration -9.8 m / sq-sec. Find a formula for $$H(t)$$ height at time $$t$$.

Solving: Take derivatives and create a triangular system; solve with back-substitution.

- Generally, we write triangular systems with the empty space at the bottom left.
- When you impose a condition, you do not allow everything to come into play; you cut down one dimension.
- Every condition which is imposed decreases the dimensionality by 1, unless they are parallel.

> Theorem: A system of linear equations has either no solution, one solution, or an infinite number of solutions.

- Gaussian elimination - generalizing the original elimination algorithm.
- Elementary row operations (which will not change the solution space):
  - interchange equations
  - Multiply an equation by a number
  - Add a multiple of an equation to another.
- 























