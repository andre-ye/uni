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

**Corollary 1.3.** Let $$a$$ and $$b$$ be integers, not both 0, and let $$d$$ be a positive integer. Then $$d$$ is the greatest common divisor of $$a$$ and $$b$$ if and only if $$d$$ satisfies these conditions:
- $$d \vert a$$ and $$d \vert b$$
- $$(c \vert a \wedge c \vert b) \to c \vert d$$

