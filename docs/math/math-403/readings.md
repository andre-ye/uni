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

---

## Chapter 8: Normal Subgroups and Quotient Groups

### 8.1: Congruence and Lagrange's Theorem
- In the integers, $$a \equiv b \mod n$$ iff $$n \vert (a - b)$$, or $$a - b \in n\mathbb{Z}$$.

Definition.
Let $$K$$ be a subgroup of a group $$G$$ and let $$a, b \in G$$.
Then $$a$$ is congruent to $$b$$ modulo $$K$$, written $$a \equiv b \mod K$$, if $$a^{-1}b \in K$$.

**Theorem 8.1.**
Let $$K$$ be a subgroup of a group $$G$$.
Then the relation of congruence modulo $$K$$ is
1. reflexive: $$a \equiv a \mod K$$
2. symmetric: if $$a \equiv b \mod K$$, then $$b \equiv a \mod K$$
3. transitive: if $$a \equiv b \mod K$$ and $$b \equiv c \mod K$$, then $$a \equiv c \mod K$$

- If $$K$$ is a subgruop of a group $$G$$ and if $$a \in G$$, the congruence class of $$a$$ mod $$K$$ is the set of all elemetns of $$G$$ congruent to $$a$$ modulo $$K$$>

$$\{ b \in G \vert b \equiv_K a \} = \{ b \in G \vert ba^{-1} \in K \} = \{b \in G \vert b^{-1} = k, k \in K \}$$

Noting that $$b = ka$$, we get

$$\{ b \in G \vert b = ka, k \in K \} = \{ ka \vert k \in K \} = Ka \text{ (right coset)}$$

- Right coset also denoted $$K + a$$

**Theorem 8.2.**
Let $$K$$ be a subgroup of a group $$G$$ and let $$a, c \in G$$.
Then $$a \equiv_K c$$ iff $$Ka = Kc$$.

**Corollary 8.3.**
Let $$K$$ be a subgroup of a group $$G$$.
Then two right cosets of $$K$$ are either disjoint or identical.

Lagrange's Theorem

**Theorem 8.4.**
Let $$K$$ be a subgroup of a group $$G$$.
Then
1. $$G$$ is the union of the right cosets of $$K$$: $$G = \bigcup_{a \in G} Ka$$
2. For each $$a \in G$$, there is a bijection $$f : K \to Ka$$. Consequently, if $$K$$ is finite, any two right cosets of $$K$$ contain the same number of elements.

- If $$H$$ is a subgroup of a group $$G$$, the number of distinct right cosets of $$H$$ in $$G$$ is the index of $$H$$ in $$G$$ and denoted $$[G : H]$$.
- If $$G$$ is a finite group, then $$[G:H]$$ is finite

**Theorem 8.5. Lagrange's Theorem**
If $$K$$ is a subgroup of a finite group $$G$$, then the order of $$K$$ divides the order of $$G$$.
In particular, $$\vert G \vert = \vert K \vert [ G : K]$$.

- Shows us there are limited possibilities for subgroups of a finite group
- A subgroup of a group of order 12 must have order 1, 2, 3, 4, 6, or 12

**Corollary 8.6.**
Let $$G$$ be a finite group.
1. If $$a \in G$$, then the order of $$a$$ divides the order of $$G$$.
2. If $$\vert G \vert = k$$, then $$a^k = e$$ for every $$a \in G$$

The Structure of Finite Groups
- Major goal of group theory is to classify all finite groups up to isomorphism

**Theorem 8.7.**
Let $$p$$ be a positive prime integer.
Then every group of order $$p$$ is cyclic and isomorphic to $$\mathbb{Z}_p$$.

**Theorem 8.8.**
Every group of order 4 is isomorphic to either $$\mathbb{Z}_4$$ or $$\mathbb{Z}_2 \times \mathbb{Z}_2$$.

**Theorem 8.9.**
Every group of order 6 is isomorphic to either $$\mathbb{Z}_6$$ or $$S_3$$.

| order | isomorphic to |
| --- | --- |
| 1 | $$\{e\}$$ |
| 2 | $$\mathbb{Z}_2$$ |
| 3 | $$\mathbb{Z}_3$$ |
| 4 | $$\mathbb{Z}_4$$ or $$\mathbb{Z}_2 \times \mathbb{Z}_2$$ |
| 5 | $$\mathbb{Z}_5$$ |
| 6 | $$\mathbb{Z}_6$$ or $$S_3$$ |
| 7 | $$\mathbb{Z}_7$$ |

### 8.2: Normal Subgroups
- Suppose $$G$$ group and $K$$ subgroup.
- Create a new group whose elements are right cosets of $$K$$ in $$G$$.
- Left coset $$aK$$: $$\{ak \vert k \in K\}$$
- a subgroup $$N$$ of a group $$G$$ is normal if $$Na = aN$$ for every $$a \in G$$.
- Every subgroup of an abelian group is normal.
- Note that $$Na = aN$$ does not imply that $$na = na, \forall n \in N$$

**Theorem 8.10.**
Let $$N$$ be a normal subgroup of a group $$G$$.
If $$a \equiv_N b$$ and $$c \equiv_N d$$< then $$ac \equiv_N bd$$.

**Theorem 8.11.**
The following conditions on a subgroup $$N$$ of a group $$G$$ are equivalent:
1. $$N$$ is normal in $$G$$
2. $$a^{-1} N a \subseteq N$$ for every $$a \in G$$, where $$a^{-1} N a = \{a^{-1}na \vert n \in N\}$$
3. $$aNa^{-1} \subseteq N$$ for every $$a \in G$$, where $$aNa^{-1} = \{ana^{-1} \vert n \in N\}$$
4. $$a^{-1} N a = N$$ for every $$a \in G$$
5. $$aNa^{-1} = N$$ for every $$a \in G$$

### 8.3: Quotient Groups
- $$G / N$$ denotes the set of all right cosets of $$N$$ in $$G$$.

**Theorem 8.12.**
Let $$N$$ be a normal subgroup of a group $$G$$.
If $$Na = Nc$$ and $$Nb = Nd$$ in $$G / N$$, then $$N ab = N cd$$.

**Theorem 8.13.**
Let $$N$$ be a normal subgroup of a group $$G$$.
Then
1. $$G / N$$ is a group under the operation defined by $$(Na)(Nc) = Nac$$.
2. If $$G$$ is finite, then the order of $$G / N$$ is $$[G : N]$$.
3. If $$G$$ is abelian, then $$G / N$$ is abelian.

If $$K$$ is the cyclic subgroup $$\langle n \rangle$$ of $$\mathbb{Z}$$, then $$\mathbb{Z} / K = Z_n$$.

### 8.4: Quotient Groups and Homomorphisms

**Definition.**
Let $$\phi: G \to H$$ be a homomorphism from a group $$G$$ to a group $$H$$.
Then the kernel of $$\phi$$ is the set of all elements of $$G$$ that are mapped to the identity of $$H$$.

- Kernels are normal subgroups

**Theorem 8.16.**
Let $$f : G \to H$$ be a homomorphism of groups with kernel $$K$$.
Then $$K$$ is a normal subgroup of $$G$$.

- The kernel of a homomorphism $$f$$ measures how far $$f$$ is from being injective.

**Theorem 8.17.**
Let $$f : G \to H$$ be a homomorphism of groups with kernel $$K$$.
Then $$K = \langle e_G \rangle$$ iff $$f$$ is injective.

**Theorem 8.18.**
If $$N$$ is a normal subgroup of a group $$G$$, then the map $$\pi G \to G / N$$ given by $$\pi(a) = Na$$ is a surjective homomorphism with kernal $$N$$.

- 8.16. states that every kernel is a normal subgroup, but every normal subgroup is also a kernel

**Lemma 8.19.**
Let $$ : G \to H$$ be a group homomorphism with kernel $$K$$.
Let $$a, b \in G$$.
Then $$f(a) = f(b)$$ iff $$Ka = Kb$$.

**Theorem 8.20. First Isomorphism Theorem.**
Let $$f : G \to H$$ be a surjective homomorphism of groups with kernel $$K$$.
Then the quotient group $$G / K$$ is isomorphic to $$H$$.

From the first isomorphism theorem, we have a lot of interesting results:
- Let $$N = \{ a + bi \vert a^2 + b^2 = 1 \}$$. Then $$\mathbb{C} / N \cong \mathbb{R}^+$$.
- Let $$K = \{1, -1\}$$. Then $$\mathbb{R}^* / K \cong \mathbb{R}^+$$.

**Theorem 8.21.**
Let $$N$$ be a normal subgroup of a group $$G$$ and let $$K$$ be any subgroup of $$G$$ that contains $$N$$.
Then $$K / N$$ is a subgroup of $$G / N$$.

**Theorem 8.22. Third Isomorphism Theorem**
Let $$K, N$$ be normal subgroups sof a group $$G$$ with $$N \subseteq K \subseteq G$$.
Then $$K / N$$ is a normal subgroup of $$G / N$$, and the quotient group $$(G / N) / (K / N)$$ is isomorphic to $$G / K$$.

**Corollary 8.23.**
Let $$N$$ be a normal subgroup of a group $$G$$ and let $$K$$ be any subgroup of $$G$$ that contains $$N$$.
Then $$K$$ is normal in $$G$$ iff $$K / N$$ is normal in $$G / N$$.

**Theorem 8.24.**
If $$T$$ is any subgroup of $$G / N$$, then $$T = H/N$$, where $$H$$ is a subgroup of $$G$$ that contains $$N$$.

- Classification of finite groups: every finite group is isomorphic to one group on the list
- A group is simple if its only normal subgroups are $$\langle e \rangle$$ and $$G$$ itself

**Theorem 8.25.**
$$G$$ is a simple abelian group iff $$G$$ is isomorphic to the additive group $$\mathbb{Z}_p$$ for some prime $$p$$.

- Nonabelian simple groups are rare: only five of order les than 1k and 56 of order less than 1m.
- Alternating groups: large class of nonabelian simple groups.
- Simple groups are the basic building blocks for all groups
- If $$G$$ is a finite group, it only has finitely many normal subgroups other than itself.
- Let $$G_1$$ be a normal subrgroup that has the largest possible order: $$G / G_1$$ is simple.
  - Suppose $$G / G_1$$ had a proper normal subgroup; it would have form $$M / G_1$$, where $$M$$ is a proper normal subgroup of $$G$$ properly containing $$G_1$$. But then $$M$$ would be the largest normal subgroup of $$G$$, a contradiction.
  - If $$G_1 \neq \langle e \rangle$$, let $$G_2$$ be a normal subgroup of $$G_1$$ of largest possible order. We know $$G_1 / G_2$$ is simple. And we can continue until we reach some $$G_n$$ that is the identity subgroup, so you get a sequence of ;groups $$\langle e \rangle = G_n \subset G_{n-1} \subset \hdots \subset G_3 \subset G_2 \subset G_1 \subset G_0 = G$$
  - Each $$G_i$$ is a normal subgroup of its predecessor; each quotient group $$G_i / G_{i + 1}$$ is simple. These simple groups are the composition factors of $$G$$
  - Composition factors of a finite group $$G$$ are independent of the choice of the subgroups $$G_i$$: you can choose different $$G_i$$ but the simple quotient groups would be isomorphic
  - The composition factors of $$G$$ totally determine the structure of $$G$$
- Classification problem strategy: classify all simple groups and show how the composition factors of an arbitrary group determine the structure of the group




