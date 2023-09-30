---
layout: default
title: Reading Notes
parent: MATH 402
grand_parent: Mathematics
nav_order: 1
---

# Reading Notes
{: .no_toc }

PHIL 402
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

## Chapter 1: Arithmetic in $$\mathbb{Z}$$ Revisited
- Algebra grows out of arithmetic and depends heavily on it

### 1.2: Divisibility

> Let $$a$$ and $$b$$ be integers with $$b \neq 0$$. $$b \vert a$$ (divides $$a$$) if $$a = bc$$ for some integer $$c$$.

- An important case of division happens when the remainder is zero
- $$a$$ and $$-a$$ have the same divisors
- $$a$$ and $$b$$ are not both 0; then, their GCD exists and is unique. It is also larger than or equal to one.

**Theorem 1.2.** Let $$a$$ and $$b$$ be integers, not both zero, and let $$d$$ be their greatest common divisor. Then there exist (not necessarily unique) integers $$u$$ and $$v$$ such that $$d = au + bv$$.

Proof:
1. Let $$S$$ be the set of all linear integral combinations of $$a, b$$: $$S = \{ am + bn \vert m, n \in \mathbb{Z} \}$$
2. Find the smallest positive element of $$S$$.
  1. $$a^2 + b^2 = aa + bb$$, $$aa + bb \in S$$, $$a^2 + b^2 \ge 0$$. 
  2. $$S$$ must contain a smallest positive integer by the Well-Ordering Axiom.
  3. Let $$t = au + bv$$ be the smallest positive element of $$S$$
3. Prove that $$t = GCD(a, b)$$
  1. Prove $$t \vert a$$ and $$t \vert b$$
    1. By the Division Algorithm, $$\exists q, r \in mathbb{Z} : a = tq + r$$, where $$0 \le r < t$$.
    2. Therefore, $$r = a - tq$$
    3. Substituting: $$r = a - (au + bv)q$$
    4. We get $$a - aqu - bvq$$ by expanding
    5. Rearranging into linear combination: $$r = a(1 - qu) + b(-vq)$$
    6. $$r \in S$$ because it is a linear combination of $$a, b$$
    7. $$r < t$$, the smallest positive element of $$S$$
    8. $$r \ge 0$$, so the only possibility is that $$r = 0$$
    9. Therefore, $$t \vert a$$. Repeat argument to show $$t \vert b$$. 
    10. $$t$$ is a common divisor of $$a$$$ and $$b$$.
  2. Prove $$c \vert a$$ and $$c \vert b$$ implies $$c \vert t$$
    1. Let $$c$$ be any common divisor of $$a$$ and $$b$$.
    2. Then $$a = ck$$ and $$b = cs$$, where $$k, s \in \mathbb{Z}$$
    3. Therefore, $$t = au + bv = (ck)u + (cs)v = c(ku + sv)$$
    4. We know from this that $$c \vert t$$ 
    5. $$c \le \vert t \vert$$: every divior of a nonzero integer $$a$$ is less than or equal to $$\vert a \vert$$
    5. However, $$t$$ is positive.
    6. Therefore, $$c \le t$$.
    7. Therefore, $$t$$ is the greatest common divisor.

**Corollary 1.3.** Let $$a$$ and $$b$$ be integers, not both 0, and let $$d$$ be a positive integer. Then $$d$$ is the greatest common divisor of $$a$$ and $$b$$ if and only if $$d$$ satisfies these conditions:
- $$d \vert a$$ and $$d \vert b$$
- $$(c \vert a \wedge c \vert b)$$ implies $$c \vert d$$

**Theorem 1.4.** If $$a \vert bc$$ and $$(a, b) = 1$$, then $$a \vert c$$.

Proof:
1. Since $$(a, b) = 1$$, $$au + bv = 1$$ for some $$u, v \in \mathbb{Z}$$
2. Multiply by $$c$$: $$acu + bcv = c$$
3. Since $$a \vert bc$$, $$bc = ar$$ for some $$r \in \mathbb{Z}$$
4. Therefore,

$$c = acu + bcv = acu + (ar) v = a(cu + rv)$$

5. This shows $$a \vert c$$

### 1.3: Primes and Unique Factorization

- Every nonzero integer has four distinct divisors.
- Integers with only four divisors are important:

> An integer $$p$$ is prime if $$p \neq 0, \pm 1$$ and the only divisors of $$p$$ are $$\pm 1$$ and $$\pm p$$.

- Becuase an integer $$p$$ has the same divisors as $$-p$$, $$p$$ is prime iff $$-p$$ is prime.
- If $$p$$ and $$q$$ are prime and $$p \vert q$$, then $$p = \pm q$$

**Theorem 1.5.** Let $$p$$ be an integer with $$p \neq 0, \pm 1$$. Then $$p$$ is prime iff whenever $$p \vert ab$$, $$p \vert b$$ or $$p \vert c$$.

Proof.
1. Suppose $$p$$ is prime and $$p \vert bc$$.
  1. $$(p, b)$$ must be a positive divisor of the prime $$p$$.
  2. If $$(p, b) = \pm p$$, $$p \vert b$$
  3. If $$(p, b) = \pm 1$$, then $$p \vert c$$
2. Suppose $$p \vert bc$$ implies $$p \vert b$$ or $$p \vert c$$.
  1. ...

**Corollary 1.6.** If $$p$$ is prime and $$p \vert a_1 a_2 ... a_n$$, then $$p$$ divides at least one of $$a_i$$.

**Theorem 1.7.** Every integer $$n$$ except $$0, \pm 1$$ is the product of primes.

Proof: Let $$S$$ be the set of integers greater than 1 that are not a product of primes. Show that $$S$$ is the empty set. Since there are no integers in $$S$$, every integer greater than 1 is a product of primes.

1. Suppose $$S$$ is not empty.
2. By the Well-Ordering Principle, $$S$$ has a smallest element, call it $$n$$.
3. $$n$$ is not prime, so $$n = ab$$ for some integers $$a, b$$, where $$1 < a, b < n$$.
4. Since $$n$$ is the smallest element of $$S$$, $$a$$ and $$b$$ are not in $$S$$.
5. Therefore, $$a$$ and $$b$$ are products of primes.
6. Therefore, $$n$$ is a product of primes.
7. This contradicts the assumption that $$n$$ is not a product of primes.
8. Therefore, $$S$$ is empty.

**Theorem 1.8 (The Fundamental Theorem of Arithmetic).**  Every integer $$n$$ except $$0, \pm 1$$ is a product of primes. The prime factorization is unique:

$$(n = p_1 p_2 ... p_n) \wedge (n = q_1 q_2 ... q_n) \implies p_1 = \pm q_1, p_2 = \pm q_2, ..., p_n \pm q_n$$

Proof: 
1. Eery integer $$n$$ except $$0, \pm 1$$ is a product of primes by Theorem 1.7.
2. Suppose $$n$$ has two prime factorizations. Then,

$$n = p_1 p_2 ... p_n = q_1 q_2 ... q_n$$

3. We know that $$p_1 \vert q_1 q_2 ... q_n$$.
4. $$p$$ must divide one of the $$q$$.
5. After reordering, $$p_1 \vert q_1$$.
6. Since $$p_1$$ and $$q_1$$ are prime, $$p_1 = \pm q_1$$.
7. Therefore, replacing on the LHS:

$$\pm q_1 p_2 p_3 ... p_n = q_1 q_2 q_3 ... q_n$$

8. Dividing both sides by $$q_1$$ gives

$$\pm p_2 p_3 ... p_n = q_2 q_3 ... q_n$$

9. Continuing to eliminate one prime at each step, we get totaly equality.$$
10. The lengths of the prime factorizations must be equal. If they were not, then we would get something like

$$ \pm p_{r+1} p_{r+2} ... p_n = 1$$

10. This is a contradiction because $$p_i = \pm 1$$ but is also prime.

**Corollary 1.9.** Every integer $$n > 1$$ can be written in only one way in the form $$n = p_1 p_2 p_3 ... p_n$$, where the $$p_i$$ are primes and $$p_1 \le p_2 \le p_3 \le ... \le p_n$$.

**Theorem 1.10.** Let $$n > 1$$. If $$n$$ has no positive prime factor less than or equal to $$\sqrt{n}$$, then $$n$$ is prime.

---

## Chapter 2: Congruence in $$\mathbb{Z}$$ and Modular Arithmetic

### 2.1: Congruence and Congruence Classes
- Congruence is a generalization of the equality relation.
- Two integers are equal if their difference is zero or a multiple of zero.

---

## Chapter 3: Rings
Page 42

