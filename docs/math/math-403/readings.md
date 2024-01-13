---
layout: default
title: Reading Notes
parent: MATH 403
grand_parent: Mathematics
nav_order: 1
---

# Reading Notes
{: .no_toc }

MATH 403
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

Textbook: *Abstract Algebra, an Introduction.* Thomas Hungerford. [Internet Archive link](https://archive.org/details/abstractalgebrai0003hung/page/2/mode/2up){:target="_blank"}

## Chapter 7: Groups

- Algebraic systems like $$\mathbb{Z}$$ and $$\mathbb{Z}_n$$ have two operations
- Groups have a single operation

### 7.1: Definition and Examples of Groups
- The integers form a group under addition but not multiplication
- Nonzero rational numbers form a group under multiplication but not addition
- Study of permutations: most historically important
- A permutation is an ordering of elements in a set $$T$$
- A permutation is a bijective function from $$T$$ to $$T$$
- Every bijection has an inverse function

A group is a nonempty set $$G$$ equipped with a binary operation $$*$$ that satisfies the following axioms:
1. Closure: $$a*b \in G$$ for all $$a,b \in G$$
2. Associativity: $$(a*b)*c = a*(b*c)$$ for all $$a,b,c \in G$$
3. Identity: there exists an element $$e \in G$$ such that $$a*e = e*a = a$$ for all $$a \in G$$
4. Inverses: for each $$a \in G$$ there exists an element $$a^{-1} \in G$$ such that $$a*a^{-1} = a^{-1}*a = e$$

A group is abelian if $$a*b = b*a$$ for all $$a,b \in G$$ (i.e. commutativity).

- The order of a group is the number of elements it has.
- $$S_n$$: the symmetric grup on $$n$$ symbols with order $$n!$$.
- $$A(T)$$ is the set of all permutations of $$T$$ (all bijective functions $$T \to T$$. $$A(T)$$ is a group under the operation of composition of functions.
- Dihedral group / group of symmetries of the square.

Groups and Rings

**Theorem 7.1.**
Every ring is an abelian group under addition.
A nonzero ring $$R$$ is never a group under multiplication.

**Theorem 7.2.**
The nonzero elements of a field $$F$$ form an abelian group under multiplicaiton.

- A ring $$R$$ with identity always has at least one subset that is a group under multiplication

**Theorem 7.3.**
If $$R$$ is a ring with identity, then the set $$U$$ of all units in $$R$$ is a group under multiplication.

**Theorem 7.4.**
Let $$G$$ with an operation $$*$$ and $$H$$ with operation $$\diamond$$ be groups.
Define an operation $$\square$$ on $$G \times H$$ by

$$(g, h) \square (g', h') = (g * g', h \diamond h')$$

Then $$G \times H$$ is a group under $$\square$$.
If $$G$$ and $$H$$ are abelian, then $$G \times H$$ is abelian.
If $$G$$ and $$H$$ are finite, then $$G \times H$$ is finite and $$|G \times H| = |G| \cdot |H|$$.


### 7.2: Basic Properties of Groups
- Standard multiplicative notation: write $$ab$$ instead of $$a * b$$.

**Theorem 7.5.**
Let $$G$$ be a group and let $$a, b, c \in G$$. Then
1. $$G$$ has a unique identity element
2. Cancelation holds in $$G$$: if $$ab = ac$$, then $$b = c$$; if $$ba = ca$$, then $$b = c$$
3. Each element of $$G$$ has a unique inverse.

**Corollary 7.6.**
If $$G$$ is a gruop and $$a, b \in G$$, then
1. Order of inverse application: $$(ab)^{-1} = b^{-1}a^{-1}$$
2. Canceling of inverses: $$(a^{-1})^{-1} = a$$

**Theorem 7.7.**
Let $$G$$ be a group and let $$a \in G$$.
Then for all $$m, n \in \mathbb{Z}$$, $$a^m a^n = a^{m+n}$$ and $$(a^m)^n = a^{mn}$$.	

- Element $$a$$ has finite order if $$a^k = e$$ for some positive integer $$k$$.
- The order of $$a$$ is the smallest positive integer $$k$$ such that $$a^k = e$$.
- Order of $$a$$ denoted $$\vert a \vert$$
- Element has infinite order if $$a^k \neq e$$ for all positive integers $$k$$.

**Theorem 7.8.**
Let $$G$$ be a group and let $$a \in G$$.
1. If $$a$$ has infinite order, then the elements $$a^k$$, $$k \in \mathbb{Z}$$, are all distinct.
2. If $$a^i = a^j$$ with $$i \neq j$$, then $$a$$ has finite order.

**Theorem 7.9.**
Let $$G$$ be a group and $$a \in G$$ an element of finite order $$n$$.
Then:
1. $$a^k = e$$ iff $$n \vert k$$
2. $$a^i = a^j$$ iff $$i \equiv_n j$$
3. If $$n = td$$, with $$d \ge 1$$, then $$a^t$$ has order $$d$$

**Corollary 7.10.**
Let $$G$$ be an abelian group in which every element has finite order.
If $$c \in G$$ is an element of largest order in $$G$$, then the order of every element of $$G$$ divides $$\vert c \vert$$.


### 7.3: Subgroups

A subset of $$H$$ of a group $$G$$ is a subgroup of $$G$$ if $$H$$ is itself a group under the operation of $$G$$.

The trivial subgroup of $$G$$ is $$\{e\}$$.

It is never necessary to check associativity for a subset $$H$$ of a group $$G$$ to be a subgroup of $$G$$.

**Theorem 7.11.**
A nonempty subset $$H$$ of a group $$G$$ is a subgroup of $$G$$ iff
1. if $$a, b \in H$$, then $$ab \in H$$
2. if $$a \in H$$, then $$a^{-1} \in H$$

**Theorem 7.12.**
Let $$H$$ be a nonempty finite subset of a group $$G$$.
If $$H$$ is closed under the operation in $$G$$, then $$H$$ is a subgroup of $$G$$.

The center of $$G$$ is $$Z(G) = \{a \in G \vert ag = ga \text{ for all } g \in G\}$$.
An element of $$G$$ is in $$Z(G)$$ iff it commutes with every element of $$G$$.

**Theorem 7.13.**
The center of a group $$G$$ is a subgroup of $$G$$.

**Theorem 7.14.**
If $$G$$ is a group and $$a \in G$$, then $$\langle a \rangle = \{ a^n \vert n \in \mathbb{Z} \}$$ is a subgroup of $$G$$.

$$\langle a \rangle$$ is the cyclic subgroup generated by $$a$$.
If $$\langle a \rangle = G$$, then $$G$$ is cyclic.
Every cyclic group is abelian.

**Theorem 7.15.**
Let $$G$$ be a gruop and let $$a \in G$$.
1. If $$a$$ has infinite order, then $$\langle a \rangle$$ is an infinite subgroup consisting of the distinct elements $$a^k, k \in \mathbb{Z}$$.
2. If $$a$$ has finite order $$n$$, then $$\langle a \rangle = \{e, a, a^2, \dots, a^{n-1}\}$$ is a finite subgroup of $$G$$ with order $$n$$.

**Theorem 7.15 (Additive Version).**
Let $$G$$ be an additive group and let $$a \in G$$.
1. If $$a$$ has infinite order, then $$\langle a \rangle$$ is an infinite subgroup consisting of the distinct elements $$ka, k \in \mathbb{Z}$$.
2. If $$a$$ has finite order $$n$$, then $$\langle a \rangle = \{0, a, 2a, \dots, (n-1)a\}$$ is a finite subgroup of $$G$$ with order $$n$$.

**Theorem 7.16.**
Let $$F$$ be any one of $$\mathbb{Q}, \mathbb{R}, \mathbb{C}, or \mathbb{Z}_p$$, where $$p$$ is prime. ($$F$$ is a field.)
Then $$F^* = F \setminus \{0\}$$ be the multiplicative group of nonzero elements of $$F$$. If $$G$$ is a finite subgroup of $$F^*$$, then $$G$$ is cyclic.

**Theorem 7.17.**
Every subgroup of a cyclic group is itself cyclic.

**Theorem 7.18.**
Let $$S$$ be a nonempty subset of a group $$G$$.
Let $$\langle S \rangle$$ be the set of all possible products, in every order, of elements of $$S$$ and their inverses.
Then
1. $$\langle S \rangle$$ is a subgroup of $$G$$ that contains the set $$S$$
2. If $$H$$ is a subgroup of $$G$$ that contains the set $$S$$, then $$H$$ contains the entire subgroup $$\langle S \rangle$$.

- Shows that $$\langle S \rangle$$ is the smallest subgroup of $$G$$ containing $$S$$.
- In the case where $$S = \{a\}$$, $$\langle S \rangle = \langle a \rangle$$.
- $$S$$ generates $$G$$

### 7.4: Isomorphisms and Homomorphisms
- Isomorphic groups have the same structure

Definition of an isomorphism.
Let $$G, H$$ be gruops with the group operation $$*$$. 
$$G$$ is isomorphic to $$H$$ if there is a function $$\phi: G \to H$$ such that
1. $$\phi$$ is a bijection ($$\phi$$ is injective and surjective)
2. $$\phi(a * b) = \phi(a) * \phi(b)$$ for all $$a, b \in G$$

- If $$G$$ is abelian and $$H$$ is nonabelian, then $$G$$ is not isomorphic to $$H$$.
- If $$\phi$$ is an isomorphism, then $$a$$ and $$\phi(a)$$ have the same order
- $$\phi: G \to G$$ is an automorphism if $$\phi$$ is an isomorphism from $$G$$ to $$G$$.

**Theorem 7.19.**
Let $$G$$ be a cyclic group.
- If $$G$$ is infinite, then $$G$$ is isomorphic to $$\mathbb{Z}$$.
- If $$G$$ is finite of order $$n$$, then $$G$$ is isomorphic to $$\mathbb{Z}_n$$.

Definition of a homomorphism.
Let $$G, H$$ be groups with the group operation $$*$$.
A homomorphism from $$G$$ to $$H$$ is a function $$\phi: G \to H$$ such that
$$\phi(a * b) = \phi(a) * \phi(b)$$ for all $$a, b \in G$$.

**Theorem 7.20.**
Let $$G, H$$ be groups with identity elements $$e_G, e_H$$.
If $$\phi: G \to H$$ is a homomorphism, then
1. $$\phi(e_G) = e_H$$
2. $$\phi(a^{-1}) = \phi(a)^{-1}$$ for all $$a \in G$$
3. $$\text{Im}(f)$$ is a subgroup of $$H$$
4. If $$f$$ is injective, $$G \cong \text{Im}(f)$$

**Theorem 7.21. Cayley's Theorem.**
Every group $$G$$ is isomorphic to a group of permutations.

**Corollary 7.22.**
Every finite group $$G$$ of order $$n$$ is isomorphic to a subgroup of $$S_n$$.

A homomorphism from $$G$$ to a group of permutation is a representation of $$G$$.
Group theory can be reduced to the study of permutation groups.

### 7.5: The Symmetric and Alternating Groups
- Cycle notation
- Two cycles are disjoint if they have no elements in common

**Theorem 7.23.**
If $$\sigma = (a_1 a_2 \hdots a_k)$$ and $$\tau = (b_1 b_2 \hdots b_r)$$ are disjoint cycles in $$S_n$$, then $$\sigma \tau = \tau \sigma$$.

**Theorem 7.24.**
Every permutation in $$S_n$$ is a product of disjoint cycles.

**Theorem 7.25.**
The order of a permutation $$\tau$$ in $$S_n$$ is the LCM of the lengths of the disjoint cycles whose product is $$\tau$$.

- A 2-cycle is a transposition.
- Every transposition is its own inverse.
- If $$\sigma_1 \sigma_2 \sigma_3 \hdots \sigma_{n}$$ are transpositions, then the inverse is $$\sigma_{n} \sigma_{n-1} \hdots \sigma_2 \sigma_1$$.
- Note that $$(1) = (12)(12)$$, $$(123) = (12)(23)$$, and $$(1234) = (12)(23)(34)$$

**Theorem 7.26.**
Every permutation in $$S_n$$ is a product of (not necessarily disjoint) transpositions.
- A permutation is even if it is a product of an even number of transpositions.
- A permutation is odd if it is a product of an odd number of transpositions.
- No permutation is both even and odd.

**Lemma 7.27.**
The identity permutation in $$S_n$$ is even and not odd.

**Theorem 7.28.**
No permutation in $$S_n$$ is both even and odd.

The set of all even permutations in $$S_n$$ is the alternating group $$A_n$$.

**Theorem 7.29.**
$$A_n$$ is a subgroup of $$S_n$$ of order $$n! / 2$$.

