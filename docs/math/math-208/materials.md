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

---

## Week 2: Vector and Span

### Section 2.1: Vectors
- Vector - a convenient way to record values, and algebraically useful.
$$\mathbb{R}^n$$ - denotes the set of all vectors with $$n$$ entries.
- Vectors are often denoted in boldface $$\mathbf{u}$$.
- Column vector - vector in vertical form; row vector - row in horizontal form. Generally column form is used.
- Linear combinations and systems of equations - vectors can be linearly combined by taking weighted sums. Constitutes another way to express linear equations by arranging the coefficients across the same variable in a column vector and using scalar multiplication against the corresponding variable.
- Solutions can be expressed in vector form.
- Vectors can be understood geometrically as a direction and a magnitud

### Section 2.2: Span
- The span of a set of vectors is the plane where every point can be expressed as a linear combination of the vectors.
- Span generalizes to higher dimensions. You can determine if a vector is in the span of another two vectors by determining if there are coefficients of the span equation that make it equal to the original vector.
- For $$\mathbb{R}^d$$, no $$d - 1$$ vectors can span $$\mathbb[R}^d$$; but $$d$$ vectors can.
- If a vector is in the span of an existing set of vectors, then this span is equal to the span of the union between that set and the new vector.
- The span of vectors in $$\mathbb{R}^n$$ is $$\mathbb{R}^n$$ when there is a pivot position in every row of the corrsponding echelon-form matrix.

---

## Week 3: Linear Dependence

### Section 2.3: Linear Independence
- If the solution to $$x_1u_1 + x_2u_2 + ... + x_3u_3 = 0$$ has a trivial solution $$x_1 = x_2 = ... = x_m = 0$$, the set of vectors $$u_1, u_2, ..., u_m$$ is linearly independent; if the solutions are nontrivial, the set is linearly dedependent.
- Having 0 in any set of vectors guarantees the set will be linearly dependent.
- Two sets are linearly dependent iff vectors are scalar multiples of each other (i.e. if they point in the same direction). 
- If the vector dimensionality is smaller than the number of vectors in the set, the set is linearly dependent.
- A set of vectors is linearly dependent iff one of the vectors in the set is in the span of the other vectors.
- Any linear system can be expressed as $$Ax = b$$; this is a homogeous linear system, which has either one solution or infinitely many.
A set of vectors is linearly independent iff the homogenous linear system $$Ax = 0$$ has only the trivial solution.
- A system $$Ax = b$$ is nonhomogenous for $$b \neq 0$$; the associated homogenous system is $$Ax = 0$$. The only difference is a constant vector.
- $$x_p$$ is a particular solution to the system $$Ax = b$$. Then all solutions to $$Ax = b$$ can be expressed as $$x_p + x_h$$, where $$x_h$$ is the solution to the associated homogenous system.
- Theorem - the following are equivalent.
  - The set $$\mathbf{a}$$ is linearly dependent.
  - The vector equation $$\sum_{i=1}^m x_i\mathbf{a}_i = \mathbf{b}$$ has at most one solution for every $$\mathbf{b}$$.
  - The linear system corresponding to $$\[ \mathbf{a}_1 \mathbf{a}_2 ... \mathbf{a}_m \vert \mathbf{b} \]$$ has at most one solution for every $$\mathbf{b}$$.
  - The equation $$A \mathbf{x} = \mathbf{b}$$, with $$A = \[ \mathbf{a}_1 \mathbf{a}_2 ... \mathbf{a}_m\]$$, has at most one solution for every $$\mathbf{b}$$.

### Section 3.1: Linear Transformations
- Linear transformations
- Domain - input vectors. Codomain - output vectors.
- $$T(\mathbf{u})$$ for a domain vector $$\mathbf{u}$$ is the image of $$\mathbf{u}$$ under $$T$$.
- The range of $$T$$ is a subset of the codomain of $$T$$.
- A function is a linear transformation if it obeys $$\forall u, v, r : (T(u + v) = T(u) + T(v)) \wedge (T(ru) = rT(u))$$
- Not all functions $$T : \mathbb{R}^m \to \mathbb{R}^n$$ are linear transformations.
- Square matrix - rows and columns are the same in quantity
- If $$T(x) = Ax$$ for a matrix $$A$$, then $$T : \mathbb{R}^m \to \mathbb{R}^n$$ is a linear transformation.
  - The range is the span of all the vectors constituting $$A$$.
- Injective - one to one $$\forall$$ ones. Surjective - many to one $$\forall$$ ones.
- A linear transformation is injective.
- A transformation is one-to-one iff columns of $$A$$ are linearly independent.
- A linear transformation must be represented as a matrix multiplication.
- Linear transformations transform lines in the domain to lines in the range.

### Section 3.2: Matrix Algebra
- Two matrices are equal if they have the same size and if their entries are all individually equal.
- $$AB = [AB_1 \vert AB_2 \vert \hdots \vert AB_m]$$
- Each cell in the resulting matrix is the dot product of the appropriate row and column of the argument matrices.
- Identity matrices - do not affect the result.
- Matrix multiplication is not necessarily commutative.
- The zero product property does not necessarily apply to matrix multiplication.
- Tranpose of a matrix - interchanging the rows and columns.
- $$(AC)^T = C^T A^T$$.
- A matrix is symmetric if it is equal to its transpose.
- We get the same result regardless of how we organize products.
- Diagonal matrix - only values along the diagonal axis. Raising these matrices to powers amounts to a per-element powering
- Triangular matrices remain triangular after being raised to a pwoer.
- We can perform any row operation by operating on the identity matrix (yielding an elementary matrix), then multiplying the identity matrix by the new matrix.
- Matrices can be partitioned.

### Section 3.3: Inverses
- A one-to-one and onto linear transformation pairs each vector in the domain to each vector in the codomain; the inverse is a pairing from the codomain to the domain.
- The inverse of a linear transfomration is also a linear transformation.
- The inverse of $$B$$, $$A$$, is such that $$AB = I_n$$. Then, $$BA = I_n$$.
- A transformation can only have an inverse if the domain and codomain are of the same dimensionality.
- A matrix which is invertible is nonsingular. A matrix which does not have an inverse is singular.
- How to compute the inverse of a matrix? Begin with $$\[A \vert I_n \]$$ and transform to $$\[ I_n \vert A^{-1} \]$$.
- Invertibility is related to solutions of linear systems: if a matrix does not have an inverse, then Gaussian elimination will yield at least one zeroed row-vector, and indeed there is a multiplicity of solutions here.
  - The following statements are equivalent: $$A$$ is invertible, $$Ax = b$$ has a unique solution $$\forall b$$, $$Ax = 0$$ has only the trivial solution (i.e. column vectors are linearly independent).
- The 2-by-2 matrix has a quick formula: $$A$$ has an inverse when $$ad - bc \neq 0$$ and is given by

$$A^{-1} = \frac{1}{ad - bc} \begin{bmatrix} d && -b \\ -c && a \end{bmatrix}$$.

---

## Week 4

### 4.1: Introduction to Subspaces
- A subset of $$\mathbb{R}^n$$ is a subspace if $$S$$ contains the zero vector, obeys $$(\mathbf{u} \in S \wedge \mathbf{v} \in S) \to (\mathbf{u} + \mathbf{v} \in S)$$, and obeys $$(r \in \mathbb{R} \wedge \mathbf{u} \in S) \to (r \mathbf{u} \in S)$$.
- A subset is closed under addition and scalar multiplication: performing these operations on vectors produces other vectors in the subspace.
- A space is its own subspace.
- If a subspace is formed by the span, then it is the subspaced spanned or generated by the vector set.
- The set of solutions to a homogenous linear system forms a subspace
- If $$A$$ is an $$n \times m$$ matrix, the set of solutions to the system $$A \mathbf{x} = \mathbf{0}$$ forms a subspace of $$\mathbb{R}^m$$.
  - This set of solution sis the null space, and is denoted as $$\text{null}(A)$$.
  The kernel of $$T$$ is the set of vectors such that $$T(\mathbf{x}) = \mathbf{0}$$.
- A linear transformation $$T$$ is bijective only if its kernel is equal to the set $$\{ \mathbf{0} \}$$.

### 4.2: Basis and Dimension
- A vector set is a basis for a subspace $$S$$ if it spans $$S$$ and is linearly independent.
- The zero subspace does not have a subspace, since the set is not linearly independent.
- Every vector in a subspace can be expressed in exactly one way as a linear combination of vectors in a basis vector set.
- If $$A$$ and $$B$$ are equivalent matrices, the subspace spanned by the row vectors of $$A$$ is the same as that of the rows of $$B$$.
- To find a basis for a vector set: use the vectors to form rows of a matrix, convert it into echelon form, and read the nonzero rows. Alternatively, arrange into columns of the matrix.
- If two matrices are equivalent, the linear dependence of states is retained.
- The derived bases mayb e different.
- If $$S$$ is a subspace of $$\mathbf{R}^n$$, then every basis of $$S$$ has the same number of vectors.
- If $$S$$ is a subspace of $$\mathbb{R}^n$$, then every basis of $$S$$ has the same number of vectors.
- The dimension of a vector space is the number of vectors in any basis of $$S$$.
- The zero subspace $$S$$ has no basis and has dimension 0.
- Standard basis - orthogonal vectors
- If a vector set is linearly independent, then it is the basis for $$S$$ or additional linearly independent vectors can be added to form the basis for $$S$$.
- If a vector set spans $$S$$, then it is the basis for $$S$$ or vectors can be removed to form a basis for $$S$$.
- Nullity of a matrix: the dimension of the null space.
- Let a vector set be a set of $$m$$ vectors in a subspace $$S$$ of dimension $$m$$. If the vector set is linearly independent or spans $$S$$, the vector set is the basis for $$S$$.

### 4.3: Row and Column Spaces
- Row vectors come from viewing the rows of a matrix as vecotrs.
- Column vectors come from viewing the columns of a matrix as vectors.
- Taking the span of the row or column vectors yields the row and column space.
- The dimension of the row space equals the dimension of the column space.
- The rank of a matrix is the dimension of the row or column space of $$A$$.
- The vectors in the general solution form a basis for the null space; the size of this set can be used to calculate the nullity
- Rank-nullity theorem: the sum of the rank and the nullity equals the dimensionality of the codomain.
- A system $$Ax = b$$ is consistent iff $$b \in \text{col}(A)$$. This solution is unique iff the columns of $$A$$ are linearly independent; the column space has the same dimensionality as the number of columns.

### 4.4: Change of Basis
- The coordinate vector contains the coefficients needed to express a vector as a linear combination of the vectors in some provided basis.
- Change of basis matrix - switch from a basis to the standard basis. The inverse switches from the standard basis to the basis.
- Composit basis matrices and theri inverses to switch from one basis to another.

---

## Week 8

### 5.1: The Determinant Function
- Determinant of a square matrix - produces a single real number.
- A matrix is invertible only if the determinant is not equal to zero.
- The determinant of a $$2 \times 2$$ matrix is $$ad - bc$$.
- Shortcut method - draw down-left arrows as minus and down-right arrows as plus. 
- Pipes around a matrix indicate the determinant.
- $$M_{ij}$$ - the smaller matrix we can get by removing the row and column containing $$a_{ij}$$. The determinant of this is the minor of $$a_{ij}$$.
- Cofactor of $$a_{ij}$$: $$C_{ij} = (-1)^{i+j} \text{det}(M_{ij})$$
- General definition of determinant: The determinant of $$A$$ is $$a_{11}C_{11} + a_{12}C_{12} + \hdots + a_{1n} C_{1n}$$
- Recursively defined function
- $$n \ge 1 \implies \text{det}(I_n) = 1$$
- Cofactor expansions - can expand across any row or column.
- If $$A$$ is triangular, the determinant is the product of the terms along the diagonal.
- The determinant of a matrix and its transpose are equivalent.
- If $$A$$ has a row or column of zeros, or has two identical rows or columns, then the determinant is zero.
- $$det(AB) = det(A) det(B)$$
- Computing determinants is a slow and difficult process.

---

## Week 9

### 5.2: Properties of the Determinant
- Convert the matrix into echelon form and multiply terms along the diagonal.
- Properties of a square matrix:
  - Interchanging two rows negates the determinant.
  - Multiplying a row by a constant multiplies the determinant by the reciprocal.
  - Adding a multiple of a row to another does not change the determinant. 
  - This applies to columns as well.
  
  Page 223



