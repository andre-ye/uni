---
layout: default
title: Favorite Math Results
parent: Mathematics
nav_order: 1
permalink: /docs/math/fav_math
---

# Favorite Math Results
A collection of nifty, interesting, and cool math results.

- [Calculus](#calculus)
- [Linear Algebra](#linear-algebra)
- [Abstract Algebra](#abstract-algebra)


## Calculus

**Arc length.**
The length of a curve given by the function $f(x)$ on the interval $[a, b]$ is given by the integral $$\int_a^b \sqrt{1 + (f'(x))^2} \, dx$$.

**Bolzano-Weierstrass Theorem.**
$$S$$ is compact iff every sequence of points in $$S$$ has a convergent subsequence whose limit is in $$S$$.
Or, every bounded sequence has a convergent subsequence.

**Cauchy Sequences.**
A sequence $$\{ \mathbf{x}_n \} \in \mathbb{R}^n$$ is convergent iff it is Cauchy.
A sequence is Cauchy if for every $\epsilon > 0$, there exists an $N$ such that for all $n, m > N$, $$\| \mathbf{x}_n - \mathbf{x}_m \| < \epsilon$$.

**Heine-Borel Theorem.**
If $$S$$ is a subset of $$\mathbb{R}^n$$, then $$S$$ is compact iff $$S$$ is closed and bounded.

**Connectedness, Pathwise and Not.**
A set is connected iff it cannot be written as the union of two disjoint nonempty open sets.
A set is path-wise connected iff for every pair of points in the set, there exists a continuous function that maps the interval $[0, 1]$ to the set and maps the endpoints to the given points.
If a set is path connected, then it is connected. The converse is not true: consider the Topologist's sine curve, defined as

$$S = \{ (x, \sin(1/x)) \mid 0 < x \leq 1 \} \cup \{ (0, y) \mid -1 \leq y \leq 1 \}$$

**Leibniz's proof for the derivative of a quadratic.**
If $$x$$ changes by $$\delta x$$, then $$y = x^2$$ should change by $$y + \delta y = (x + \delta x)^2 = x^2 + 2x\delta x + (\delta x)^2$$. Relabel $$\delta x, \delta y$$ as $$dx, dy$$ and as they become 'infinitely small', then $$(\delta x)^2$$ gets infinitely smaller. Also subtract $$y = x^2$$. So we get $$dy = 2x dx$$, or $$dy/dx = 2x$$.

**Riemann integrability.**
$$f$$ is integrable on $$[a, b]$$ if
for every $$\epsilon > 0$$ there is a partition $$P$$ of $$[a, b]$$ such that $$U(f, P) - L(f, P) < \epsilon$$,
where $$U(f, P)$$ is the upper sum and $$L(f, P)$$ is the lower sum.

**Zero-content.**
A bounded set is integrable even if it has a subset of zero content.
For instance, the Cantor set defined by removing the middle third of the interval $[0, 1]$ and then removing the middle third of the remaining intervals, and so on until infinity.

**Measurability.**
Any bounded set whose boundary is a finite union of pieces of smooth curves is measurable.

## Linear Algebra

**Rank-Nullity Theorem.**
For a linear transformation $T: V \to W$, the rank-nullity theorem states that $$\text{rank}(T) + \text{nullity}(T) = \dim(V)$$.

**Closed-form solution for the *n*th Fibonacci number** using matrix decomposition. 
Begin with the following definition of the Fibonacci sequence, and then raise the given matrix to the power of *n* and decompose it to find a closed-form solution for the *n*th Fibonacci number.
$$\begin{pmatrix} F_n \\ F_{n+1} \end{pmatrix} = \begin{pmatrix} 0 & 1 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} F_{n-1} \\ F_{n} \end{pmatrix}$$

## Abstract Algebra

**Isomorphisms.**
- The field $$K$$ of matrices with form $$\begin{pmatrix} a & b \\ -b & a \end{pmatrix}$$ is isomorphic to the field $$\mathbb{C}$$.
- The quotient group $$\mathbb{SL}_n(\mathbb{R}) / \mathbb{GL}_n(\mathbb{R})$$ is isomorphic to the multiplicative group $$\mathbb{R}^+$$.
    - The special linear group is the set of $$n \times n$$ matrices with determinant 1
    - The general linear group is the set of $$n \times n$$ matrices with non-zero determinant
- The quotient group $$\mathbb{C}* / \{ x \in \mathbb{C} \mid |x| = 1 \}$$ is isomorphic to the multiplicative group $$\mathbb{R}^+$$.
    - "Taking the complex numbers modulo the unit circle is the same as taking the positive real numbers."

**Bezout's Theorem.**
For any two integers $$a, b$$, there exist integers $$x, y$$ such that $$ax + by = \gcd(a, b)$$.

**Units in $$\mathbb{Z}_n$$.**
The units in $$\mathbb{Z}_n$$ are the integers $$a$$ such that $$\gcd(a, n) = 1$$.
Note that units are elements with a multiplicative inverse.

**Fields and Integral Domains.**
Every field is an integral domain, but not every integral domain is a field.
(A field is a commutative ring with every element a unit. An integral domain is a commutative ring with no zero divisors -- that is, if $$ab = 0$$, then $$a = 0$$ or $$b = 0$$.)

**Eisenstein's Criterion.**
If a polynomial $$f(x) = a_nx^n + a_{n-1}x^{n-1} + \cdots + a_0$$ has integer coefficients and there exists a prime $$p$$ such that $$p \nmid a_n$$, $$p \mid a_{n-1}, \ldots, a_0$$, and $$p^2 \nmid a_0$$, then $$f(x)$$ is irreducible over the rationals.

**Irreducibility of polynomials.**
$$p(x)$$ is irreducible in $$F[x]$$ iff $$F[x]/(p(x))$$ is a field.

**Extension field for polynomials.**
Let $$F$$ be a field and $$p(x)$$ an irreducible polynomial in $$F[x]$$. Then the field $$F[x]/(p(x))$$ is an extension field of $$F$$ containing the root of $$p(x)$$.

**First Isomorphism Theorem for Rings.**
If $$\phi: R \to S$$ is a ring homomorphism, then $$\ker(\phi)$$ is an ideal of $$R$$ and $$R/\ker(\phi) \cong \text{im}(\phi)$$.

**First Isomorphism Theorem for Groups.**
If $$\phi: G \to H$$ is a group homomorphism, then $$\ker(\phi)$$ is a normal subgroup of $$G$$ and $$G/\ker(\phi) \cong \text{im}(\phi)$$.

**Prime Ideals.**
An ideal is prime if $$ab \in I$$ implies $$a \in I$$ or $$b \in I$$.
Let $$P$$ be an ideal in a commutative ring $$R$$ with identity.
Then $$P$$ is a prime ideal iff $$R/P$$ is an integral domain.

**Maximal Ideals.**
An ideal is maximal if it is not contained in any other proper ideal.
Let $$M$$ be an ideal in a commutative ring $$R$$ with identity.
Then $$M$$ is a maximal ideal iff $$R/M$$ is a field.

**Relation between rings and groups.**
Every ring is a group under addition, and no ring is a group under multiplication.

**Abelian groups.**
Every group of order 5 or less is abelian.

**Cayley's Theorem.**
Every group is isomorphic to a subgroup of the symmetric group on the group's elements.

**Cycles.**
Every permutation in $$S_n$$ is a product of disjoint cycles.

**Lagrange's Theorem.**
If $$G$$ is a finite group and $$H$$ is a subgroup of $$G$$, then the order of $$H$$ divides the order of $$G$$: $$|G| = |H| \cdot [G:H]$$, where $$[G:H]$$ is the index of $$H$$ in $$G$$ (the number of left cosets of $$H$$ in $$G$$).

**Isomorphisms to prime modulo groups.**
Every group of prime order, with no subgroups, or simple and abelian is cyclic and isomorphic to $$\mathbb{Z}_p$$.

**Finite abelian groups.**
Every finite abelian group is isomorphic to a Cartesian product of cyclic groups of prime power order.