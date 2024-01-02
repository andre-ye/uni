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

New Groups from Old