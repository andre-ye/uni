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

---

## Week 4 Wednesday
- Linear transformations - mappings between Euclidean spaces.
- All linear transformations can be written as matrix transformations - this is the complete class of linear transformations.
- We can prove this by writing properties as a matrix.
- You can construct a linear transformation just by understanding how the unit basis vectors are transformed.
- You can invert a linear transformation by setting up a system of equations.
- There is nothing sacred about our standard Euclidean space
  - e.g. Fourier series - working with sinusoidal waves as the basis space
- Rotation - arbitrary degrees.
- Matrix operations are not always commutative - order matters.
- Function composition - you can repeatedly multiply by different matrices to obtain a composite effect.

---

## Week 5 Monday
- Linear transformation - a map from one Euclidean space to another. Sends a vector $$x$$ to $$Ax$$, where $$A$$ is some matrix.
- The set of matrices $$n \times m$$ is exactly the same set of linear transformations $$\mathbb{R}^m \mapsto \mathbb{R}^n$$.
- Matrices as equations and linear transformations
- A linear combination represented as a matrix can be derived by understanding where the various basis vectors go to.
- You can derive function compositions by multiplying matrices.
- The range is everything in the codomian which can be reached by the linear transformation $$T$$ from the domain.
- The range of a linear transformation given by a matrix is the span of the column vectors.
- The range is equal to the codomain only if there is a pivot in every row of the echelon form matrix form of $$\[A \vert b \]$$.
- A function is one-to-one if $$(T(x) = T(y)) \implies (x = y)$$
- Projection - decreasing dimension
- Bijection does not imply surjection
- Isomorphism - you can have a forwards and backwards map between two sets.
- To check if something is one to one, assert that the transformation forces two vectors to be mapped to the same point given an input.

---

## Week 5 Wednesday
- Range and span
- A transformation is onto if the range is equal to the codomain.
- A linear transformation represented by $$A$$ is onto if there is a pivot in every row in the echelon form.
  - Equivalent to do the column vectors span the range.
- A vector is bijective if it has a pivot on in every column.
- Kernel of the matrix - the set of solutions to $$At = 0$$.
- All points parallel to the kernel are mapped to the same value in the codomain.
- To be one to one, then the krnel must be the origin - there's nothing to collapse. $$At = 0$$ to test.
- If the domain is higher in dimensionality than the codomain, the kernel is always nonzero.
- Bijective and surjective: reflection across $$x$$-axis
- Not bijective and not surjective: send all to the origin
- Bijective but not surjective: not possible.
- Not bijective but surjective: not possible.

---

## Week 5 Friday
- Mean - 74%
- All exams will be cumulative 
- Inverse transformations - we want to be able to undo a transformations. 
- Composing an inverse transformation and the original transformations should yield the identity transformation.
- The original transformation must be bijective and surjective. Therefore, the original transformation must be square.
- The inverse of reflection is itself. This is provable - multiplying it by itself yields the identity matrix.
- Pseudoinverse - used for rectangular matrices.
- $$BA = I_{n \times n} \implies AB = I_{n \times n}$$, $$B = A^{-1}$$.
- Multiplying a row vector by a matrix gives a linear combination of the rows. Multiplying a matrix by a column vector gives a linear combination of the columns.
- Vectors are always column vectors - horizontal vectors / row vectors should be considered the transpose of a column vector.
- $$B \[ A \vert I \] \to \[ BA \vert B \] \to \[ I \vert B\]$$. Converting to $$\[ I \vert \vdots \]$$ gives us $$B$$ automatically.

---

## Week 6 Monday
- Not all matrices can be inverted, even if they are square (the transformation is not bijective or not surjective).
- We are trying to find combinations of rows which are equal to the identity.
- $$(BA = I \wedge AC = I) \implies (B = C)$$ - the inverse doesn't matter whether if it is multiplied from the left or the right
- Properties of invertible matrices, for two invertible $$A$$ and $$B$$.

$$(A^{-1}^{-1} = B$$
$$(AB)^{-1} = **^{-1}^{-1}$$
$$(AC = AD) \implies (C=D)$$
$$(AC = 0) \to (C=0)$$
$$(Ax = b) \to (x = A^{-1}b)$$

- A matrix is invertible if the reduced echelon form of $$A$$ is $$I$$
- Chapter 4 - peak of abstraction in the class, covers many things.
- Vector sets are always subsets of a higher-diensional space.
- A subset is a vector space if the zero vector is in it and it is closed under addition and multiplication.
- The span of any vector set forms a vector space.
- Kernels are vector spaces.
- Ranges are vector spaces.
- The range/span lives in the codomain, but the kernel lives in the domain: both are vector spaces in different spaces.
- Subspace - vector space in another vector space.
- **All subspaces are either the kernel or the range of a transformation.**

---

## Week 6 Wednesday
- Multiplication is not defined across vector spaces.
- The zero vector is an example of a finite vector space.
- The requirement of scaling by a constant bars a non-one finite vector space.
- Anything which is the span or the kernel are vector spaces.
- Every vector space is both a span and a kernel.
- Range is the span of the column vectors of a matrix.
- Consider some plane $$ax + by + cz = 0$$; this is the kernel of the transformation [a b c].
- Basis of a vector sapce: a set of linearly independent vectors which spans the vector space.
- Affine spaces
- To prove that a set is a vector space, show that it is the span or the kernel of some transformation.
- The set of all quadratics is a vector space.

---

## Week 6 Friday
- A vector set $$B$$ is a basis of $$S$$ if $$B$$ spans $$S$$ and $$B$$ is linearly independent.
- The size of a basis is the dimension.
- Why can we infer the linear indendence of vector sets from the column vector pivot position status of column vectors in Gaussian reduced matrices?
- The span of row and column vectors does not chang when we perform linear reduction. They can be converted into row vectors and reduced such that the span is still the same. **They must be done as row vectors**: functions as a basis. 
- If U is linearly independent, then either U is a basis of S, or U can be extended to form a basis of S.
  - Simply add the standard basis vectors and perform reduction.
- Two algorithms to identify the basis vectors from an oversized vector set:
  - Arrange into a standard matrix, perform Gaussian elimination, identify which of the previous column vectors to use
  - Arrange into a standard matrix, transpose, perform Gaussian elimination, read the resulting row vectors
- If U spans S, then either U is a basis or a subset of U is a basis of S.
- The algorithm proves the theorem - you can extend or cut down.
- Basis is important, because it defines dimension.
- Rank - number of linearly dependent vectors along the rows
- Coordinates - always with respect to the standard basis.
- Can we change the basis and calculate the coordinates of the same location?
- Monomial basis - extremely unstable. To salve a partial differential equation, you can choose other bases - e.g. Lagrange or Chebyshev bases.

---

## Week 7 Monday
- There are many subspaces which come out of a matrix: row space, column space, null space.
- The null space is the kernel of the transformation. 
- The row space of a transformation - basis can be the nonzero rows of $$B$$.
- Row span does not change when you convert to echelon form.
- Dimension of the row space - the _row rank_
- Dimension of the column space - the _column rank_.
- The row rank and the column rank are euqal - the number of pivots.
- This number fof columns in a matrix plus the nullity is the dimension $$n$$.  
- Free variables - non pivot columns of $$A$$
- Rank-nullity theorem: $$\text{rank}(A) + \text{nullity}(A) = n$$ for $$A \in \mathbb{R}^{m \times n}$$
- How to get matrix with a certain set as its null space? Set variables and solve a system of equations.

---

## Week 7 Wednesday
- Change of basis in $$\mathbb{R}^n$$. You can perform a change of basis in other subspaces too.
- Standard unit basis
- Coordinates are always w.r.t. a basis and indicatet eha mount of the basis to travel in.
- To express as a basis: find the inverse of the matrix formed by horizontally concatenating the column vectors and multiplying by the vector in standard $$\mathbb{R}^n$$.
- We need pivots in all cases to be able to invert a matrix and change the bases.

---

## Week 8 Friday
- Determinant: maps the set of square matrices to the real numberrs. 
- Trace - sum of the diagonal elements.
- The determinant was discovered before matrices were formulated.
- Worked on mainly by Cauchy
- Determinant - a certificate for invertibility, is zero if the matrix is not invertible. 
- How to compute the determinant.
- Determinant of a two-by-two matrix: products of diagonals minus products of the up-diagonals
- If there are many zeros in a row or column, pick that for the cofactor expansion.
- The cofactor expansion is the same regardless of which row or column you choose on. 
- The determinant is the area of the parallelgogram formed by the column vectors.
- Determinant of a multi-dimensional matrix - volume spanned by the column vectors
- Recursively, you can prove that the determinant of a diagonal matrix is the product of all the elements. It is also the product of the eigenvalues in the matrix. 
- The determinnat of a triangular matrix is still the product of the diagonals.
- A diagonal or triangular matrix is only invertible when none of the numbers along the diagonal are zero.
- Laplace expansion (cofactor expansion)

---

## Week 9 Monday
- Matrix tree theorem - the determinant of a degree-based matrix representation of a graph is the number of spanning trees.
  - Degree: number of edges touching each vertex.
  - Laplacian of a graph - can tell connectivity, traversal rate, expansion, etc.
- Symmetric matrix - equal to its transpose
- What does Gaussian elimination do to deterimnants and how can we use this to create an algorithm for calculating determinants?
- Interchanging two rows negates the determinant.
- Scaling a row by a constant scales the determinant by that constant.
- Scaling an $$n \times n$$ matrix scales the determinant by $$\lambda^n$$
- Interchanging rows does not change the determinant.
- If the determinant of a matrix isn't 0, then a transformation by gaussin elimination of that matrix returnst his status.
- To find the equation of a plane: stack $$\langle x, y, z \rangle$$ with the given vectors, set determinant to zero, and solve. Need to find a $$n-1$$ dimesnional plane in $$\mathbb{R}^n$$. This is the hyperplane.

---

## Week 10 Monday
- Median - 80%
- A vector is an eigenvector of a matrix with a given eigenvalue if $$A u = \lambda u$$.
- The rotation matrix does not have real eigenvectors for values of theta other than 0 and 180 degrees.
- Eigenspace - the set of all eigenvectors
- An $$n \times n$$ matrix can have at most $$n$$ values. 
- Goal - to compute all eigenvalues and eigenspaces of some matrix. 
- Steps to derive the eigenvalue
  1. $$\lambda$$ is an eigenvalue of $$A$$ iff $$\exists u \neq 0 : Au = \lambda u = \lambda I u$$
  2. $$\exists u \neq 0 : Au - \lambda I u = 0$$
  3. $$\exists u \neq 0 : (A - \lambda I)u = 0$$ - we are finding $$u$$ in the nullspace of $$A - \lambda I$$. The rank is less than $$n$$ because the nullity is nonzero (rank-nullity theorem). This means that the matrix is not bijective and therefore that:
  4. $$\text{det} (A - \lambda I) = 0$$
- Characteristic polynomial -- has degree equal to the size of the matrix. Every polynomial in one variable is the characteristic polynomial of a matrix. (Used to compute roots to high-dimensional polynomials.)
- After the eigenvalues are derived, just compute the nullspace of $$A - \lambda I$$.
- 

---

## Week 10 Wednesday
- The Eigenspace is a subspace. It contains the zero vector and is closed under scalar multiplication and addition.
- Algorithm 1 for eigenvalues: find the determinant of $$A - \lambda I$$ and set to zero. The resulting polynomial is the characteristic polynomial of $$A$$.
- The characteristic polynomial of an $$n \times n$$ has a degree $$n$$. Therefore there will be $$n$$ complex roots (eigenvalues) for every $$n \times n$$ matrix.
- Multiplicity - the relevant degree. The multiplicity is a bound on the dimensionality of the eigenspace. Multiplicity 2 -- a plane or a line. Multiplicity 1 -- a line.
- If 0 is an eigenvalue of matrix, the determinant of the matrix is 0.
- Computers solve polynomials by computing eigenvalues.
- Suppose we are given $$x^3 - 15x^2 + 56x - 60$$. We can construct a matrix for which this polnomial is the characteristic polynomial (companion matrix of a polynomial). There are good methods of finding eigenvalues which don't rely upon solving polynomials

$$\begin{bmatrix} 0 & 0 & 0 & 60 \\ 1 & 0 & 0 & -56 \\ 0 & 1 & 0 & 15 \\ 0 & 0 & 1 & -1 \end{bmatrix}$$




































