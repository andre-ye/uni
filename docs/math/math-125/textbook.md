---
layout: default
title: Textbook Notes
parent: MATH 125
grand_parent: Mathematics
nav_order: 2
---

# Textbook Notes

MATH 125
{: .fs-6 .fw-300 }

---

## Navigation

---

## 5.1: Areas and Distances
- When we find the area under a curve or the distance traveled over time, we end up with a special type of limit.
- Measure by using areas, Riemann sums.

$$\lim_{n\to\infty} \sum^n_{i = 1} f(x_i^*} \Delta x = \lim_{n\to\infty} \left[ f(x_1^*) \Delta x + f(x_2^*) \Delta x + ... + f(x_n^*) \Delta x \right]$$

---

## 5.2: The Definite Integral

- The definite integral of $$f$$ from $$a$$ to $$b$$ is

$$\int_a^b f(x) dx = \lim_{n\to\infty} \sum^n_{i = 1} f(x_i^*} \Delta x$$

**Precise meaning of a limit that defines the integral.**

> For every number $$\epsilon > 0$$, there is an integer $$N$$ such that for every integer $$n > N$$ and for every choice of $$x_i^*$$ in $$\left[x_{i-1}, x_i\right]$$, the following is true: $$\left| \int_a^b f(x) dx - \int^n_{i=1} f(x_i^*) \Delta x \right| < \epsilon$$.

**Theorem 3.**

> If $$f$$ is continuous on $$[a, b]$$, or if $$f$$ has only a finite number of jump discontinuities, then $$f$$ is integrable on $$[a, b]$$; that is, the definite integral $$\int_a^b f(x) dx$$ exists.

**Integral Properties**

| Integral Property |
| --- |
| $$\int_a^b c dx = c(b-a)$$ |
| $$\int_a^b [f(x) + g(x)] dx = \int_a^b f(x) dx + \int_a^b g(x) dx$$ |
| $$\int_a^b cf(x) dx = c\int_a^b f(x) dx$$ |
| $$\int_a^b [f(x) - g(x)]dx = \int_a^b f(x) dx - \int_a^b f(x) dx$$ |
| If $$f(x) \ge 0$$ for $$a \le x \le b$$, then $$\int_a^b f(x) dx \ge 0$$ |
| If $$f(x) \ge g(x)$$ for $$a\le x\le b$$, then $$\int_a^b f(x) dx \ge \int_a^b g(x) dx$$ |
| If $$m \le f(X) \le M$$ for $$a \le x \le b$$, then $$m(b-a) \le \int_a^b f(x) dx \le M(b-a)$$ |

---

## 5.3: The Fundamental Theorem of Calculus




