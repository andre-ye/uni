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
