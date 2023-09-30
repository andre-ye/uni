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

