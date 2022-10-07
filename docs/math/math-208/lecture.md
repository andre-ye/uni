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

## Week 2 Monday
- Homogenous systems - contain the origin as a solution, have at least one solution.
- You can only tell the number of free variables in a linear system using Gaussian elimination.
- If a system is inconsistent, Gaussian elimination will yield an impossible equation.

```
 x - 2y - 3z = -1
 x -  y - 2z =  1
-x + 3y + 5z =  2

  1 -2 -3 -1
  1 -1 -2  1
 -1  3  5  2
 
  1 -2 -3 -1
  0  2  3  3
  0  1  2  1
  
  1 -2 -3 -1
  0  1  1  2
  0  0 -1  1
  
  z = -1
  y =  3
  x = 2
  ```
  
  ## Week 2 Wednesday
  - Vectors - can add and scale
  - Solving a linear system is equivalent to adding or manipulating vectors.
  - We can interpret solving a linear equation as determing the combination of scailng factors by which different coefficient column vectors are added to reach a particular point.
  - Span - the reachable set of points given linear combinations of existing sets of vectors.
  - Questions one can ask about span:
    - Is a vector in the span? Solve for the equations and try to derive a solution.
    - What is the span of a set of vectors? Derive a solution to prove which vectors have solutions reachable as linear combinations of the existing vectors.
 
---

## Week 2 Friday
- Span - set of all linear combinations of a given set of vectors

*Problem*: Compute the span of $$\{(\langle 2, 1, 1\rangle, \langle 1, 2, 3 \rangle, \langle 9, 1, -1 \rangle\}$$

*Solution*:

$$\begin{pmatrix} a // b // c \end{pmatrix} = \begin{pmatrix} 2, 1, 1 \end{pmatrix} x_1 + \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix} x_2 + \begin{pmatrix} 9 \\ 1 \\ -1 \end{pmatrix} x_3$$

$$a = 2x_1 + x_2 + 9x_3$$

$$b = x_1 + 2x_2 + x_3$$

$$c = x_1 + 3x_2 - x_3$$

Perform Gaussian elimination on the corresponding augmentation matrix. Yes, the span is $$\mathbb{R}^3$$.

- Another type of possible problem: given a set of vectors, find another vector which is not part of the span.
















