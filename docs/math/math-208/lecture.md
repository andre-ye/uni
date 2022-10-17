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


---

## Week 3 Monday
- Linear independence: second important concept (+ span).
- If a vector is a linear combination of other vectors, then that vector depends on the vectors whose linear combination constitutes that vector.
- How to check for linear dependence computationally? 
- A vector set is linearly dependent iff:
  - some vector is in the span of the authors
  - some vector is a linear combination of the others
  - the system $$\sum_{i=1}^m u_i x_i = 0$$ has a nonzero solution (infinitely many solutions)
- Otherwise, the vectors are linearly independent.
- A system of vectors is always linearly dependent when the zero-vector is present or if the dimensionality of the vectors is less than the number of the vectors.

---

## Week 3 Friday
- Matrix - rectangular array of numbers. 
- Size - given as rows first by column count.
- $$\mathbb{R}^{n \times m}$$ refers to all matrices of size $$3 \times 2$$.
- Operations - addition, scalar multiplication. Properties: commutativity, associativity, distributivity
  - Commutativity is a rare property among algebras.
  - Associativity is more common
- Important matrix:
  - Zero matrix, denoted $$0_{m \times n}$$.
  - Identity matrix, denoted $$I_n$$. Always square.
- Matrix multiplication by a vector: make a linear combination of the columsn of the matrix.
- Matrix multiplication by a matrix: perform matrix-by-vector multiplication columnwise.
- Another interpretation of matrix multiplication: dot product between rows of the first matrix and columns of the second matrix.
- The dot product measures the angle between two vectors.
- Matrix multiplication is not commutative.
- Two nonzero matrices can be multiplied to yield the zero matrix.
  - Vectors are perpendicular; the dot product is zero.
  
---

## Week 4 Monday
- All linear transformations can be represented with matrices.
- $$\LaTeX: \mapsto`.
- Let $$T : \mathbb{R}^m \to \mathbb{R}^n$$ such that $$T(c x) = cT(x)$$ and $$T(a + b) = T(a) + T(b)$$. These properties are rare and not true of all maps. Then $$T$$ is a linear transformation.
- Translation is not a linear transformation - it won't keep the origin at the origin.
- To construct a transformation, stack column vectors corresponding to the novel positions of the basis vectors from the original space.
- All vectors are positioned by the given basis vectors, as scaled transformations.











