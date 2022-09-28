---
layout: default
title: Materials
parent: MATH 208
grand_parent: Mathematics
nav_order: 2
---

# Materials Notes
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

## Week 1: Topic

### Section 1.1: Lines and Linear Equations
- A linear equation has the form $$a_1x_1 + a_2x_2 + ... + a_nx_n = b$$.
- A solution $$s$$ is an ordered set of $$n$$-numbers ($$n$$-tuple)$$ such that setting $$x_i = s_i$$ satisfies the linear equation.
- Solution set - the set of all solutions to the equation.
  - The solution set $$S$$ of all $$n$$-tuples for $$n \ge 4$$ is a hyperplane.
- A system of linear equations is a collection of equations with the same $$n$$ (but possibly zero-coefficients).
  - A system has $$m$$ equations and $$n$$ unknowns.
- A linear system is consistent if $$\|S\| \ge 1$$; therwise it is inconsistent.
  - If a consistent linear system has an infinite number of solutions, it should be written as a general solution with a free parameter.
- A triangular system cn be solved using back substitution: values can be iteratively found by moving backwards to uncover new solution values.
  - **Leading variable** - a variable which appears as the first term in at least one equation.
  - In triangular systems, every variable is a leading variable in some equation.
- Back substitution can be applied to some systems in which a variable is a leading variable for at most one equation.
- **Echelon form**: a system is organized into a descending stair-step pattern from left to right, such that the indices of the leading variables strictily increase.
  - All triangular systems are in echelon form.
  - Every variable is the leading variable of at most one equation.
  - The number of solutions $$\in {0, 1, \infty}$$.
  - Nonleading variables are *free variables*.
  - To solve:
    1. Set each free variable equal to a free parameter.
    2. Back substitute to solve for the leading variables (in terms of the free variables).
- A system of linear equations may contain a falsity (e.g. $$0 =3$$), in which case no solutions are possible.
  - If a system has no free variables, there will be 1 solution.
  - If a system has $$\ge 1$$ free variables, then there will be an infinite number of solutions.

### Section 1.2: Linear Systems and Matrices
- Systems of linear equations rarely come nicely in echelon form. We want to transform any linear system into echelon form such that it is solvable with back substitution.
- Elementary operations:
  1. Interchange of equation position.
  2. Multiply an equation by a nonzero constant.
  3. Add a multiple of one equation to another.
- To convert to echelon form, begin with $$i=1$$ and use multiplication to cancel out $$x_i$$ in all equations of index $$> i$$; then increment $$i$$.
- We can simplify notation by arranging coefficients in a matrix. An augmented matrix contains all the coefficients of a linear system (including the constant terms on the RHS).
- We can find elemetnary row operation correlates for matrices:
  1. Interchange two rows.
  2. Multiply a row by a nonzero constant.
  3. Replace a row with the sum of that row and the scalar multiple of another row.
- Two matrices are equivalent if a matrix can be transformed into another through elemetnary row operation compositions.
- Echelon form: every leading term is in a column to the left of the leading term of the row below it; any zero rows are at the bottom of the matrix.
- Pivot position: the position of a leading term. Pivot column: the column with a pivot position. Pivot: a nonzero number in a pivot position.
- All echelon forms of a given matrix have the same pivot positions.
- Gauss-Jordan elimination: multiply every nonzero row by the reciprocal value of the pivot such that the new pivots are all ones. Make sure all entires above each pivot have zeros. This produces reduced echelon form: leading variables appear only in the equation they lead.
  - Forward phase: Gaussian elimination & echelon form transformations; Backward phase: transformation to reduced echelon form.

> Theorem: A given matrix is equivalent to a unique matrix that is in reduced echelon form. There are not multiple possible matrices, like in echelon form.

- Linear equation: homoegenous if has form $$a_1x_1 + a_2x_2 + ... + a_nx_n = 0$$. Homogenous linear systems are comprised of homogenous linear equations. There is always one easy solution: $$\forall i; x_i = 0$$. This is a trivial solution.

## Week 2:
























