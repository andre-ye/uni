---
layout: default
title: Reading Notes
parent: MATH 334
grand_parent: Mathematics
nav_order: 1
---

# Reading Notes
{: .no_toc }

MATH 334
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

Textbook [link](https://sites.math.washington.edu//~folland/Homepage/AdvCalc2308.pdf){:target="_blank"}

## Chapter 1: Setting the Stage
Page 13

### 1.2: Subsets of the Euclidean Space
- Sphere: set of all points whose distance from a fixed point $$\mathbf{a}$$ is a fixed number $$r$$
- Ball: set of all points whose distance from a fixed point $$\mathbf{a}$$ is less than a fixed number $$r$$

$$B(r, \mathbf{a}) = \{ \mathbf{x} \in \mathbb{R}^n \Vert \mathbf{x} - \mathbf{a} \Vert < r \}$$

- A set $$S \subset \mathbb{R}^n$$ is bounded if it is contained in some ball $$B(r, \mathbf{a})$$
- Complement of $$S$$: $$S^C = \mathbb{R}^n \setminus S$$
- A point $$\mathbf{x} \in \mathbb{R}^n$$ is an interior point of $$S$$ if all points sufficiently close to $$\mathbf{x}$$ are also in $$S$$. That is, $$S$$ contains a ball centered at $$\mathbf{x}$$.

$$S^{\text{int}} = \{ \mathbf{x} \in S : (B, r \mathbf{X}) \subset S \text{ for some } r > 0 \}$$

- A point $$\mathbf{x} \in \mathbb{R}^n$$ is a boundary point of $$S$$ if every ball centered at $$\mathbf{x}$$ contains points in $$S$$ and points not in $$S$$.

$$\partial S = \{ \mathbf{x} \in \mathbb{R}^n : \text{ every ball centered at } \mathbf{x} \text{ contains points in } S \text{ and points not in } S \}$$

- $$S$$ is open if it contains none of its boundary points
- $$S$$ is closed if it contains all of its boundary points
- Closure of $$S$$ is the union of $$S$$ and its boundary points, denoted $$\overline{S} = S \cup \partial S$$.
- Neighborhood of a point $$\mathbf{x} \in \mathbb{R}^n$$ is a set of which $$\mathbf{x}$$ is an interior point
- The boundary points of $$S$$ are the same as the boundary points of $$S^C$$.
- If $$\mathbf{x}$$ is either an interior point of $$S$$ nor an interior point of $$S^C$$, it must be a boundary point of $$S$$.
- **Proposition 1.4.** Suppose $$S \subset \mathbb{R}^n$$.
  - $$S$$ is open $$\iff$$ every point of $$S$$ is an interior points
  - $$S$$ is closed $$\iff$$ $$S^C$$ is open
- Sets defined by strict inequalities are open; sets defined by equalities or weak inequalities are closed.

### 1.3: Limits and Continuity
- $$\mathbb{C}$$ can be regarded as $$\mathbb{R}^2$$.
- $$f$$ is a real-valued function defined across $$\mathbb{R}^n$$.
- $$\lim_{x\to\mathbf{a}} f(\mathbf{x}) = L$$ is the limit of $$f(\mathbf{x})$$ as $$\mathbf{x}$$ approaches $$\mathbf{a}$$.

$$\lim_{\mathbf{x} \to \mathbf{a}} f(\mathbf{x}) = L \text{ means }\forall \epsilon_{\epsilon \in \mathbb{R}^+} \exists \delta_{\delta \in \mathbb{R}^+} : \vert f(\mathbf{x} - L \vert < \epsilon \text{ whenever } 0 < \vert \mathbb{x} - \mathbb{a} \vert < \delta$$

- In general, consider function $$f$$ which are only defined on a subset $$S$$ of $$\mathbb{R}^n$$ and points $$\mathbf{a}$$ that lie in the closure of $$S$$.

$$\lim_{\mathbf{x} \to \mathbf{a}, \mathbf{x} \in S} f(\mathbf{x})$$

- $$f$$ is continuous at $$\mathbf{a}$$ if $$\lim_{\mathbf{x} \to \mathbf{a}} f(\mathbf{x}) = f(\mathbf{a})$$
- If $$f$$ is continuous at every point of $$U \subset \mathbb{R}^n$$, then $$f$$ is continuous on $$U$$.

$$\forall \epsilon_{\epsilon \in \mathbb{R}^+} \forall \mathbf{a}_{\in U}  \exists \delta_{\delta \in \mathbb{R}^+} : \vert f(\mathbf{x}) - f(\mathbf{a}) \vert < \epsilon \text{ whenever } \vert \mathbf{x} - \mathbf{a} \vert < \delta$$

- Limits on vector-valued functions: $$\mathbf{f} : \mathbb{R}^n \to \mathbb{R}^m$$

$$\lim_{\mathbf{x} \to \mathbf{a}} \mathbf{f}(\mathbf{x}) = L \iff \lim_{\mathbf{x} \to \mathbf{a}} f_j(\mathbf{x}) = L_j \text{ for } j = 1, ..., m$$

- Limits are tricky in higher dimensions because there are many ways to approach a point.
- If $$f$$ is a continuous function, $$\lim_{\mathbf{x} \to \mathbf{a}} f(\mathbf{x}) = f(\mathbf{a})$$
- Most functions are built up from continuous functions of one variable using artihemtic operations and composition, which all preserve unity except for division.

**Theorem 1.9.** Suppose $$\mathbf{f} : \mathbb{R}^n \to \mathbf{R}^m$$ is continuous on $$U \subset \mathbf{R}^n$$ and $$\mathbf{g} : \mathbb{R}^m \to \mathbb{R}^k$$ is continuous on $$\mathbf{f} (U) \subset \mathbf{R}^m$$. Then the composite function $$\mathbf{g} \circ \mathbf{f} : U \to \mathbb{R}^k$$ is continuous on $$U$$.

**Theorem 1.10.** Let $$f_1(x,y) = x+y, f_2(x, y) = xy,$$ and $$g(x)=1/x$$. Then $$f_1$$ and $$f_2$$ are continuous on $$\mathbb{R}^2$$ and $$g$$ is continuous on $$\mathbb{R} \setminus \{0\}$$.

**Corollary 1.11.** The function $$f_3(x, y) = x-y$$ is continuous on $$\mathbb{R}^2$$, and the function $$f_4(x, y) = x / y$$ is continuous on $$\{(x, y) : y \neq 0 \}$$.

**Corollary 1.12.** The sum, product, or difference of two continuosu functions is continuous; the quotient of two continuous functions is continuous on the set where the denominator is nonzero.

**Theorem 1.13.** Suppose $$\mathbf{f} : \mathbb{R}^n \to \mathbf{R}^k$$ is continuous and $$u \subset \mathbb{R}^k$$. Let $$S = \{ \mathbf{x} \in \mathbb{R}^n : \mathbf{f}(\mathbf{x}) \in U\}$$. Then $$S$$ is open if $$U$$ is open and $$S$$ is closed if $$U$$ is closed.

### 1.5: Completeness
- The essential properties of the real number system which *underlies all of calculus*: $$\mathbb{R}$$ is a complete ordered field.
  - Field: operations of addition, subtraction, multiplication, and division are defined and subjec to usual laws of arithmetic.
  - Ordered field: field with the binary relation and antisymmetric
  - Completeness: there are no 'holes' in the real number line
- If $$S$$ is a subset of $$\mathbb{R}$$, an **upper bound** for $$S$$ is a number $$u$$ such that $$x \le u$$ for all $$x \in S$$, and a **lower bound** for $$S$$ is a number $$l$$ such that $$l \le x$$ for all $$x \in S$$.

**The Completeness Axiom.** Let $$S$$ be a nonempty set of real numbers. If $$S$$ has an upper bound, then $$S$$ has a least upper bound, the supremum of $$S$$, denoted $$\sup S$$. If $$S$$ has a lower bound, then $$S$$ has a greatest lower bound, the infimum of $$S$$, denoted $$\inf S$$. Examples:
- $$S = (0, 1]$$. $$\sup S = 1$$, $$\inf S = 0$$.
- $$S = \{ 1, 1/2, 1/3, 1/4, ... \}$$. $$\sup S = 1$$, $$\inf S = 0$$.
- $$S = \{ 1, 2, 3, 4, ... \}$$. $$\sup S = \infty$$, $$\inf S = 1$$.

If $$S$$ has an upper bound, the number $$a = \sup S$$ is the unique number such that
- $$x \le a$$ for all $$x \in S$$ ($$a$$ is an upper bound)
- For every $$\epsilon > 0$$, there exists $$x \in S$$ with $$x > a - \epsilon$$ (there is no smaller upper bound)
- **Completeness of the real number system is important in establishing the convergence of numerical sequences**
  - A sequence is **bounded** if its range is bounded
  - A sequence is **increasing** if $$x_{n+1} \ge x_n$$ for all $$n$$
  - A sequence is **decreasing** if $$x_{n+1} \le x_n$$ for all $$n$$
  - A sequence is **monotonic** if it is either increasing or decreasing

**Theorem 1.16** (Monotone Sequence Theorem). Every bounded monotone sequence in $$\mathbb{R}$$ is convergent. The limit of an increasing/decreasing sequence is the supremum/infimum of its set of values.

**Theorem 1.17** (Nested Interval Theorem).
Let $$I_1 = [a_1, b_1], I_2 = [a_2, b_2], ...$$ be a squence of closed, bounded intervals in $$\mathbb{R}$$.
Suppose that $$I_1 \supset I_2 \supset I_3 \supset ...$$ *and* the length $$b_k - a_k$$ of $$I_k$$ approaches 0 as $$k \to \infty$$.
Then there is eactly one point contained in all of the intervals $$I_k$$.
The intersection $$\bigcap_{k=1}^\infty I_k$$ is nonempty (a single point).

- A subsequence of $$\{x_k\}$$ is a sequence specified by a one-to-one map $$j \to k_j$$ from the set of positive integers into itself, e.g. $k_j = 2j$$ selected even-numbered terms.

**Theorem 1.18** (form of Bolzano-Weierstrass theorem). 
Every bounded sequence in $$\mathbb{R}^n$$ has a convergent subsequence.

- A sequence $$\{\mathbf{x}_k\} \in \mathbb{R}^n$$ is a Cauchy sequence if $$\mathbf{x}_k - \mathbf{x}_j \to 0$$ as $$k, j \to \infty$$; that is, if for every $$\epsilon > 0$$ there exists an integer $$K$$ such that $$\vert \mathbf{x}_k - \mathbf{x}_j \vert < \epsilon$$ whenever $$k > K$$ and $$j > K$$.

**Theorem 1.20.** A sequence $$\{ \mathbf{x}_k \} \in \mathbb{R}^n$$ is convergent iff it is Cauchy.

### 1.6: Compactness

- A subset of $$\mathbb{R}^n$$ is **compact** if it is closed and bounded.
- Compactness is important because it yields existence theorems for limits.

**Theorem 1.21** (Bolzano-Weierstrass Theorem).
If $$S$$ is a subset of $$\mathbb{R}^n$$, $$S$$ is compact iff every sequence of points in $$S$$ has a convergent subsequence whose limit lies in $$S$$.

- Note: every finite subset of $$\mathbb{R}^n$$ is obviously compact
- Connection between compactness and continuity

**Theorem 1.22.**
Continuous functions map compact sets to compact sets.
Suppose that $$S$$ is a compact subset of $$\mathbb{R}^n$$ and $$\mathbf{f} : S \to \mathbb{R}^m$$ is continuous at every point of $$S$$.
Then the set $$\mathbf{f}(S) = \{ \mathbf{f}(\mathbf{x}) : \mathbf{x} \in S \}$$ is also compact.

**Theorem 1.23** (Extreme Value Theorem).
Suppose $$S \subset \mathbb{R}^n$$ is compact and $$f : S \to \mathbb{R}$$ is continuous.
Then $$f$$ has an absolute minimum value and an absolute maximum value on $$S$$;
that is, there exist points $$\mathbf{a}, \mathbf{b} \in S$$ such that $$f(\mathbf{a}) \le f(\mathbf{x}) \le f(\mathbf{b})$$ for all $$\mathbf{x} \in S$$.

- $$\mathcal{U}$$ is a collection of subsets $$\mathbb{R}^n$$. It is a covering of $$S$$ if $$S$$ is contained within the union of the sets in $$\mathcal{U}$$.

**Theorem 1.24** (Heine-Borel Theorem).
If $$S$$ is a subset of $$\mathbb{R}^n$$, then $$S$$ is compact iff every open covering of $$S$$ has a finite subcovering.

- Metric spaces: general spaces equipped with a distance function.
- But Bolzano-Weierstrass and Heine-Borel may not be completely valid for other metric spaces. 

### 1.7: Connectedness

- A set in $$\mathbb{R}^n$$ is connected if it is ``all in one piece''
- A set is disconnected if it is the union of two nonempty sets, neither of which intersects the closure of the other.
- A set is connected if it is not disconnected.

**Theorem 1.25**. 
The connected subsets of $$\mathbb{R}$$ are precisely the intervals (open, half-open, or closed; bounded or unbounded).

**Theorem 1.26.**
Cotninuous functions map connected sets to connected sets.

**Corollary 1.27.** (The Intermediate Value Theorem.)
Suppose $$f : S \to \mathbb{R}$$ is continuous at every point of $$S$$ and $$V \subset S$$ is connected.
If $$\mathbf{a}, \mathbf{b} \in V$$ and $$f(\mathbf{a}) < t < f(\mathbf{b})$$ or $$f(\mathbf{b}) < t < f \mathbf{a})$$, there is a point $$\mathbf{c} \in V$$ such that $$f(\mathbf{c}) = t$$.

- A set is arcwise/pathwise connected if any two points in $$S$$ can be joined by a continuous curve in $$S$$.

**Theorem 1.28.**
If $$S \subset \mathbb{R}^n$$ is arcwise connected, then $$S$$ is connected.

**Theorem 1.30.**
If $$S \subset \mathbb{R}^n$$ is open and connected, then $$S$$ is arcwise connected.

---

## Chapter 2: Differential Calculus

### 2.1: Differentiability in One Variable
- A more useful notion of the derivative than in elemetnary calculus books
- $$f : \mathbb{R} \to \mathbb{R}$$ is differentiable at $$x = a$$ if it is approximately linear near $$x = a$$.
- That is, there exists a linear function $$l(x) = mx + b$$ satisfying $$l(a) = f(a)$$, i.e. $$l(x) = f(a) + m(x-a)$$.
  - The linear approximation $$f(x) - l(x)$$ must go to zero faster than $$x - a$$ as $$x \to a$$ (i.e. faster than $$x$$ approaches $$a$$), so we have

$$\frac{f(x) - l(x)}{x - a} \to 0, x \to a$$

- Let $$h = x - a$$. Then

$$f(x) - l(x) = f(a + h) - f(a) - mh$$

- We have the error function $$E(h) = f(x) - l(x) = f(a + h) - f(a) - mh$$, which is the difference between the function and its linear approximation.
- Formal definition. $$f$$ is a real-valued function on an open interval in $$\mathbb{R}$$ containing $$a$$. $$f$$ is differentiable at $$a$$ if there exists some number $$m$$ such that

$$f(a + h) = f(a) + mh + E(h), $$\lim_{h \to 0} \frac{E(h)}{h} = 0$$

- We can compute $$m$$ as follows into the standard form:

$$m = \frac{f(a + h) - f(a) - E(h)}{h} = \frac{f(a + h) - f(a)}{h} - \frac{E(h)}{h} \to m = \lim_{h \to 0} \frac{f(a + h) - f(a)}{h}$$

- Differentiability at $$a$$ implies continuity at $$a$$.
- $$E(h)$$ is little-oh of $$h$$, i.e. it is of a smaller order of magnitude than $$h$$.
- $$f(a + h)$$ is the sum of a linear function of $$h$$ and an error term which is $$o(h)$$.
- We can work out standard differentiation rules from this definition.

**The Product Rule.**
Suppose $$f$$ and $$g$$ are differentiable at $$x = a$$.
Then $$f(a + h) = f(a) + f'(a) h + E_1(h)$$ and $$g(a + h) = g(a) + g'(a) h + E_2(h)$$, where $$E_1(h)$$ and $$E_2(h)$$ are both $$o(h)$$.
Then we get

$$f(a + h) g(a + h) = f(a) g(a) + [f'(a) g(a) + f(a) g'(a)]h + E_3(h)$$

Left-hand derivative $$f'_{-}(a)$$ and right-hand derivative $$f'_{+}(a)$$:

$$f'_{\pm}(a) = \lim_{h \to 0^{\pm}} \frac{f(a + h) - f(a)}{h}$$

Mean Value Theorem.
Definition of derivative: passing from local information given by values of $$f(x)$$ for $$x$$ near $$a$$ to the infinitesimal information $$f'(a)$$.
How to go from infinitesimal information to local information? i.e. explain information about $$f$$ given $$f'$$?

**Proposition 2.5.**
Suppose $$f$$ is defined on an open interval $$I$$ and $$a \in I$$.
If $$f$$ has a local maximum or minimum at the point $$a \in I$$ and $$f$$ is differentiable at $$a$$, then $$f'(a) = 0$$.

**Lemma 2.6 -- Rolle's Theorem.**
Suppose $$f$$ is continuous on $$[a, b]$$ and differentiable on $$(a, b)$$.
If $$f(a) = f(b)$$, then there is at least one point $$c \in (a, b)$$ such that $$f'(c) = 0$$.

**Theorem 2.7 -- Mean Value Theorem I.**
Suppose $$f$$ is continuous on $$[a, b]$$ and differentiable on $$(a, b)$$.
There is at least one point $$c \in (a, b)$$ such that
$$f'(c) = \frac{f(b) - f(a)}{b-a}$$

**Theorem 2.8.**
Suppose $$f$$ is differentiable on the open interval $$I$$.
1. If $$\vert f'(x) \vert \le C$$ for all $$x \in I$$, then $$\vert f(b) - f(a) \vert \le C \vert b - a \vert$$ for all $$a, b \in I$$.
2. If $$f'(x) = 0$$ for all $$x \in I$$, then $$f$$ is constant on $$I$$.
3. If $$f'(x) \ge 0$$ for all $$x \in I$$, then $$f$$ is increasing on $$I$$.

**Theorem 2.9 -- Mean Value Theorem II.**
Suppose $$f, g$$ are continuous on $$[a, b]$$ and differentiable on $$(a, b)$$; and $$g'(x) \neq 0$$ for all $$x \in (a, b)$$.
Then there is a point $$c \in (a, b)$$ such that
$$\frac{f'(c)}{g'(c)} = \frac{f(b) - f(a)}{g(b) - g(a)}$$

**Theorem 2.10 -- L'Hopital's Rule I.**
Suppose $$f, g$$ are differentiable functions on $$(a, b)$$ and $$\lim_{x \to a^+} f(x) = \lim_{x \to a^+ g(x) = 0}$$.
If $$g'$$ never vanishes on $$(a, b)$$ and the limit $$\lim_{x \to a^+} \frac{f'(x)}{g'(x)} = L$$ exists, then $$g$$ never vanishes on $$(a, b)$$ and $$\lim_{x \to a^+ \frac{f(x)}{g(x)}} = L$$.
The same result holds for the left-handed limit, the two-sided limit, and limits to infinity or negative infinity.

**Theorem 2.11 -- L'Hopital's Rule II.**
Thoerem 2.10 remains value when the limits of $$f(x)$$ and $$g(x)$$ go to infinity.

**Corollary 2.12 -- Rates of Growth.**
For any $$a > 0$$:

$$\lim_{x \to +\infty} \frac{x^a}{e^x} = \lim_{x \to +\infty} \frac{\log x}{x^a} = \lim_{x \to 0+} \frac{\log x}{x^-a} = 0$$

Vector-valued functions.
- The derivative of $$\mathbf{f} = (f_1, ..., f_n)$$ is

$$\mathbf{f}'(a) = \lim_{h \to 0} \frac{\mathbf{f}(a + h) - \mathbf{f}(a)}{h} = \left( \lim_{h \to 0} \frac{f_1(a + h) - f_1(a)}{h}, ..., \lim_{h \to 0} \frac{f_n(a + h) - f_n(a)}{h} \right)$$

- The mean value theorem is not valid for vector-valued functions.

### 2.2: Differentiability in Several Variables


### 2.7: Taylor's Theorem
- Taylor expansions in their finite form
- Taylor's theorem -- higher-order version of the tangent line approximation.
- A function $$f$$ of class $$C^k$$ on an interval $$I$$ containing the point $$x = a$$ is the sum of a certain polynomial of degree $$k$$ and a remainder term that vanishes more rapidly than $$\vert x - a \vert^k$$ as $$x \to a$$
- The polynomial $$P = P_{a, k}$$ of order $$k$$ such that $$P^{(j)}(0) = f^{(j)} (a)$$ for $$0 \le j \le k$$; the $$k$$th-order Taylor polynomial for $$f$$ based at $$a$$:

$$P_{a, k}(h) = \sum_{j = 0}^k \frac{f^{(j)}(a)}{j!} h^j$$

- The $$k$$-th order taylor remainder is given by

$$R_{a, k}(h) = f(a + h) - P_{a, k}(h) = f(a + h) - \sum_{j = 0}^k \frac{f^{(j)(a)}}{j!} h^j$$

- The Taylor polynomial is a good approximation of $$f$$ near $$a$$.

**Theorem 2.55.** -- Taylor's Theorem with Integral Remainder, I.
Suppose that $$f$$ is of class $$C^{k+1}$$, with $$k \ge 0$$ on an interval $$I \subset \mathbb{R}$$, and $$a \in I$$. Then the remainder $$R_{a, k}$$ defined by 2.53 - 2.54 is given by

$$R_{a, k}(h) = \frac{h^{k+1}}{k!} \int_0^1 (1 -t )^k f^{(k+1)} (a + th) dt$$.

**Theorem 2.58.** -- Taylor's Theorem with Integral Remainder, II.
Suppose that $$f$$ is of class $$C^k$$, $$k \ge 1$$ on an interval $$I \subset \mathbb{R}$$, and $$a \in I$$. Then the remainder $$R_{a, k}$$ is given by

$$R_{a, k}(h) = \frac{h^k}{(k-1)!} \in_0^1 (1 - t)^{k-1} [ f^{(k)}(a + th) - f^{(k)(a)} ] dt$$

**Corollary 2.60.**
If $$f$$ is of class $$C^k$$ on $$I$$, then $$R_{a, k}(h) / h^k \to 0$$ as $$h \to 0$$.

- If $$f$$ is $$C^k$$ near $$x = a$$, we can write $$f(x)$$ as the sum of a $$k$$-th order polynomial

**Corollary 2.61.**
If $$f$$ is of class $$C^{k+1}$$ on $$I$$ and $$\vert f^{(k+1)} (x) \vert \le M$$ for $$x \in I$$, then

$$\vert R_{a, k} (h) \vert \le \frac{M}{(k+1)!} \vert h \vert^{k+1}, a + h \in I$$

**Lemma 2.62.**
suppose $$g$$ is $$k + 1$$ times differentiable on $$[a, b]$$. If $$g(a) = g(b)$$ and $$g^{(j)(a) = 0} for 441 \le j \le k$$, then there is a point $$c \in (a, b)$$ such that $$g^{(k+1)}(c) = 0$$

**Theorem 2.63.** -- Taylor's Theorem with Lagrange's Remainder.
Suppose $$f$$ is $$k + 1$$ times differentiable on an interval $$I \in \mathbb{R}$$, and $$a \in I$$. For each $$h \in \mathbb{R}$$ such that $$a + h \in I$$, there is a point $$c$$ between $$0$$ and $$h$$ such that

$$R_{a, k}(h) = f^{(k + 1)}(a + c) \frac{h^{k+1}}{(k + 1)!}

**Proposition 2.65.**
The Taylor Polynomials of degree $$k$$ about $$a = 0$$ are:

- For $$e^x$$: $$\sum_{0 \le j \le k} \frac{x^j}{j!}$$
- For $$\cos x$$: $$\sum_{0 \le j \le k/2} \frac{(-1)^j x^{2j}}{(2j)!}$$
- For $$\sin x$$: $$\sum_{0 \le j \le (k-1)/2} \frac{(-1)^j x^{2j + 1}}{(2j + 1)!}$$
- For $$(1 - x)^{-1}$$: $$\sum_{0 \le j \le k} x^j$$

- Taylro polynomials can approximate complicated functions with easier computations
- Theoretically, importantly, the behavior of any function near some point is determined by the first nonvanishing term
- Suppsoe $$f : \mathbb{R}^n \to \mathbb{R}$$ is of class $$C^k$$ on a convex open set $$S$$. We can derive a Taylor expansion for $$f(\mathbf{x})$$ about a point $$\mathbf{a} \in S$$ by looking at the restriction of $$f$$ and the line joining $$\mathbf{a}$$ and $$\mathbf{x}$$.
- With $$\mathbf{h} = \mathbf{x} - \mathbf{a}$$ and $$g(t) = f(\mathbf{a} + t(\mathbf{x} _ \mathbf{a})) = f(\mathbf{a} + t \mathbf{h})$$; so $$g'(t) = \mathbf{h} \cdot \nabla f(\mathbf{a} + t \mathbf{h})$$

**Theorem 2.68.** -- Taylor's Theorem in Several Variables.
Suppose $$f : \mathbb{R}^n \to \mathbb{R}$$ is a class $$C^k$$ on an open convex set $$S$$.
If $$\mathbf{a} \in S$$ and $$\mathbf{a} + \mathbf{h} \in S$$. Then

$$f(\mathbf{a} + \mathbf{h}) = \sum_{\vert \alpha \vert \le k} \frac{\partial^\alpha f(\mathbf{a})}{\alpha!} \mathbf{h}^\alpha + R_{\mathbf{a}, k}(\mathbf{h})$$

**Corollary 2.75.**
If $$f$$ is of class $$C^k$$ on $$S$$, then $$R_{\mathbf{a}, k}(\mathbf{h}) / \vert \mathbf{h} \vert^k \to 0$$ as $$\mathbf{h} \to 0$$.

**Lemma 2.76.**
If $$P(\mathbf{h})$$ is a polynomial of degree $$\le k$$ that vanishes to order $$> k$$ as $$\mathbf{h} \to 0$$.

**Theorem 2.77.**
Suppose $$f$$ is of class $$C^{(k)}$$ near $$\mathbf{a}$$.
If $$f(\mathbf{a} + \mathbf{h}) = Q(\mathbf{h}) + E(\mathbf{h})$$ where $$Q$$ is a polynomial of degree $$\le k$$ and $$E(\mathbf{h}) / \vert \mathbf{h} \vert^k \to 0$$ as $$\mathbf{h} \to \mathbf{0}$$, then $$Q$$ is the Taylor polynomial $$P_{\mathbf{a}, k}$$.

### 2.8: Critical Points
- $$\mathbf{a} \in S$$ is a critical point for $$f$$ if $$\nabla f(\mathbf{a}) = \mathbf{0}$$.
- $$f$$ has a local maximum at $$\mathbf{a}$$ if $$f(\mathbf{x}) \le f(\mathbf{a})$$ for all $$\mathbf{x}$$ in some neighborhood of $$\mathbf{a}$$

**Proposition 2.78.**
If $$f$$ has a local max or min at $$\mathbf{a}$$ and $$f$$ is differentiable at $$\mathbf{a}$$, then $$\nabla f(\mathbf{a}) = \mathbf{0}$$.

- How can we tell if a function has a local maximum or minimum?
- If $$f$$ is of class $$C^2$$, then $$f$$ has a local min at $$a$$ if $$f''(a) > 0$$.

**Definition.**
Suppose $$f$$ is a real-valued function of class $$C^2$$ on some open set $$S \subset \mathbb{R}^n$$ and $$f$$ has a critical point at $$\mathbf{a}$$. One needs an $$n \times n$$ matrix $$H$$

$$H = H(\mathbf{a}) = \begin{pmatrix} \partial_1^2 f(\mathbf{a}) & \partial_1 \partial_2 f(\mathbf{a}) & ... & \partial_1 \partial_n f(\mathbf{a}) \\ \partial_2 \partial_1 f(\mathbf{a}) & \partial_2^2 f(\mathbf{a}) & ... & \partial_2 \partial_n f(\mathbf{a}) \\ \vdots & \vdots & \ddots & \vdots \\ \partial_n \partial_1 f(\mathbf{a}) & \partial_n \partial_2 f(\mathbf{a}) & ... & \partial_n^2 f(\mathbf{a}) \end{pmatrix}$$

- The Hessian is always a symmetric matrix
- Spectral theorem: every symmetric matrix has an orthonormal eigenbasis

**Theorem 2.81.**
Suppose $$f$$ is of class $$C^2$$ at $$\mathbf{a}$$ and that $$\nabla f(\mathbf{a}) = 0$$, and let $$H$$ be the Hessian matrix.
For $$f$$ to have a local min at $$\mathbf{a}$$, it is necessary for the eigenvalues of $$H$$ all to be nonnegative and sufficient for them all to be strictly positive.
For $$f$$ to hav ea local max at $$\mathbf{a}$$, it is necessary for the eigenvalues of $$H$$ all to be nonpositive and sufficient for them all to be strictly negative.
- If two eigenvalues have opposite signs, $$f$$ has a saddle point.
- A critical point for which zero is an eigenvalue of the Hessian is degenerate (like Vivek)

**Theorem 2.8.**
Suppose $$f$$ is of class $$C^2$$ on an open set in $$\mathbb{R}^2$$ containing the point $$\mathbf{a}$$, and suppose $$\nabla f(\mathbf{a}) = \mathbf{0}$$.
Let $$\alpha = \partial_1^2 f(\mathbf{a}), \beta = \partial_1 \partial_2 f(\mathbf{a}), \gamma = \partial_2^2 f(\mathbf{a})$$.
1. If $$\alpha \gamma - \beta^2 < 0$$, $$f$$ has a saddle point at $$\mathbf{a}$$.
2. If $$\alpha \gamma - \beta^2 > 0$$ and $$\alpha > 0$$, $$f$$ has a local min at $$\mathbf{a}$$.
3. If $$\alpha \gamma - \beta^2 > 0$$ and $$\alpha < 0$$, $$f$$ has a local max at $$\mathbf{a}$$.
4. If $$\alpha \gamma - \beta^2 = 0$$, the test is inconclusive.


### 2.10: Vector-Valued Functions and Their Derivatives
- It can be useful to consider vector-valued functions -- i.e. mappings from $$\mathbb{R}^n$$ to $$\mathbb{R}^m$$, $$n, m > 0 \in \mathbb{Z}$$.

$$\mathbf{f}(\mathbf{x}) = (f_1(\mathbf{x}), f_2(\mathbf{x}), ..., f_m(\mathbf{x}))$$

- A mapping $$\mathbf{f}$$ from $$S \in \mathbb{R}^n$$ to $$\mathbb{R}^m$$ is differentiable at $$\mathbf{a} \in S$$ if $$\exists$$ an $$m \times n$$ matrix $$L$$ such that

$$\lim_{\mathbf{h} \to \mathbf{0}} \frac{\vert \mathbf{f}(\mathbf{a} + \mathbf{h}) - \mathbf{f}(\mathbf{a}) - L \mathbf{h}}{\vert \mathbf{h} \vert} = 0$$

- There can only be one such derivative, the **Frechet derivative.** -- $$D\mathbf{f}(\mathbf{a})$$.

**Proposition 2.85.**
An $$\mathbb{R}^m$$-valued function $$\mathbf{f}$$ is differentiable at $$\mathbf{a}$$ precisely when each of its components $$f_1, ..., f_m$$ is differentiable at $$\mathbf{a}$$.
$$D\mathbf{f}(\mathbf{a})$$ is a matrix whose $$j$$th row is the row vecvtor $$\nabla f_j(\mathbf{a})$$.

**Theorem 2.86.** -- Chain Rule III.
Suppose $$\mathbf{g} : \mathbb{R}^k \to \mathbb{R}^n$$ is differentiable at $$\mathbf{a} \in \mathbb{R}^k$$ and $$\mathbf{f} : \mathbb{R}^n \to \mathbb{R}^m$$ is differentiable at $$\mathbf{g}(\mathbf{a}) \in \mathbb{R}^n$$.
$$\mathbb{H} = \mathbf{f} \circ \mathbf{g} : \mathbb{R}^k \to \mathbb{R}^m$$ is differentiable at $$\mathbf{a}$$, and

$$D \mathbf{H}(\mathbf{a}) = D\mathbf{f}(\mathbf{g}(\mathbf{a})) D\mathbf{g}(\mathbf{a})$$

where the expression on the right is the product of the matrices $$D \mathbf{f}(\mathbf{g}(\mathbf{a}))$$ and $$D \mathbf{g}(\mathbf{a})$$.

**Definition.**
Norm of a linear mapping is the smallest constant $$C$$ such that $$\vert A\mathbf{x} \vert \le C \vert x \vert4$

**Theorem 2.88.**
Suppose $$\mathbf{f}$$ is a differentiable $$\mathbb{R}^m$$-valued function on an open convex set $$S \subset \mathbb{R}^n$$, and suppose that $$\Vert D\mathbf{f}(\mathbf{x}) \Vert \le M$$ for all $$\mathbb{x} \in S$$. Then

$$\vert \mathbf{f}(\mathbf{b}) - \mathbf{f}(\mathbf{a}) \vert \le M \vert \mathbf{b} - \mthbf{a} \vert , \forall \mathbf{a}, \mathbf{b} \in S$$

**Definition.**
The Jacobian of a mapping $$\mathbf{f}$$ is a scalar-valued function on $$S$$ and is the determinant of $$D\mathbf{f}$$.

---

## Chapter 4: Integral Calculus

### 4.1: Integration on the Line

- You can interpret $$\int_a^b f(x) dx$$ as the area of the region between the graph of $$f$$ and the $$x$$-axis over the interval $$[a, b]$$ -- Riemann sums, etc.
- Partition $$P$$: subdivision of $$[a, b]$$ into non-overlapping subintervals
- $$P'$$ is a refinement of $$P$$ if $$P \subset P'$$
- Let $$f$$ be a bounded real-valued function on $$[a, b]$$. Given a partition $$P = \{ x_0, ..., x_J \}$$ of $$[a, b]$$, with $$1 \le j \le J$$, then we set

$$m_j = \inf \{ f(x) : x_{j - 1} \le x \le x_j \}$$

$$M_j = \sup \{ f(x) : x_{j - 1} \le x \le x_j \}$$

- Lower Riemann sum $$s_P f = \sum_{1}^J m_j (x_j - x_{j - 1})$$
- Upper Riemann sum $$S_P f = \sum_{1}^J M_j (x_j - x_{j - 1})$$

- **Lemma 4.3.** If $$P'$$ is a refinement of $$P$$, then $$s_{P'} f \ge s_P f$$ and $$S_{p'} f \le S_P f$$.
- **Lemma 4.4.** If $$P$$ and $$Q$$ are any partitions of $$[a, b]$$, then $$s_P f \le S_Q f$$

- Lower integral of $$f$$ on $$[a, b]$$: $$L_{a}^b (f) = \sup_P s_P f$$
- Upper integral of $$f$$ on $$[a, b]$$: $$I_a^b(f) = \inf_P S_p f$$
- (Supremum and infimum are taken over all partitions of $$[a, b]$$)
- Riemann vs. Lebesgue integral.
- **Lemma 4.5.** (important!): If $$f$$ is a bounded function on $$[a, b]$$, the following conditions are equivalent:
  - $$f$$ is integrable on $$[a, b]$$
  - For every $$\epsilon > 0$$ there is a partition $$P$$ of $$[a, b]$$ such that $$S_P f - s_P f < \epsilon$$
- For any partition $$P$$, we have

$$s_P f \le \int_a^b f(x) dx \le S_P f$$

- If $$S_P f - s_P f < \epsilon$$, $$S_P f$$ and $$s_P f$$ are both within $$\epsilon$$ of $$\int_a^b f(x) dx$$.
- **Theorem 4.6.**
  - Suppose $$a < b < c$$. If $$f$$ is integrable on $$[a, b]$$ and on $$[b, c]$$, then $$f$$ is integrable on $$[a, c]$$, and $$\int_a^c f(x) dx = \int_a^b f(x) dx + \int_b^c f(x) dx$$
  - If $$f, g$$ are integrable on $$[a, b]$$, then so is $$f + g$$, and $$\int_a^b [f(x) + g(x)] dx = \int_a^b f(x) dx + \int_a^b g(x) dx$$.
- Observe negation and ordering of bounds:

$$\int_b^a f(x) dx = -\int_a^b f(x) dx$$

- **Theorem 4.9.** Properties of functions integrable on $$[a, b]$$
  - If $$c \in \mathbb{R}$$, then $$cf$$ is integrable on $$[a, b]$$, and $$f_a^b c f(x) dx = c \int_a^b f(x) dx$$
  - If $$[c, d] \in [a, b]$$, then $$f$$ is integrable on $$[c, d]$$
  - If $$g$$ is integrable on $$[a, b]$$ and $$f(x) \le g(x)$$ for $$x \in [a, b]$$, then $$f_a^b f(x) dx \le f_a^b g(x) dx$$
- **Theorem 4.10.** If $$f$$ is bounded and monotone on $$[a, b]$$, then $$f$$ is integrable on $$[a, b]$$. Proof sketch:
  1. Suppose $$f$$ is increasing on $$[a, b]$$.
  2. Consider the partition $$P_k$$ of $$[a, b]$$ into $$k$$ equal subintervals
  - The difference between the lower and upper Riemann sums is $$\frac{(b - a) [f(b) - f(a)]}{k}$$
  3. We can make $$k$$ sufficiently large, so $$f$$ is integrable
- **Theorem 4.11.** If $$f$$ is continuous on $$[a, b]$$, then $$f$$ is integrable on $$[a, b]$$.
  - We know that $$f$$ is uniformly continuous on $$[a, b]$$
- **Theorem 4.12.** If $$f$$ is bounded on $$[a, b]$$ and continuous at all except finitely many points in $$[a, b]$$, then $$f$$ is integrable on $$[a, b]$$
- A set $$Z \in \mathbb{R}$$ has **zero content** if for any $$ \epsilon > 0$$, there is a finite collection of intervals $$I_1, ..., I_L$$ such that $$Z \in \bigcup_1^L I_l$$ and the sum of lengths of the $$I_l$$'s is less than $$\epsilon$$.
- **Theorem 4.13.** If $$f$$ is bounded on $$[a, b]$$ and the set of points in $$[a, b]$$ at which $$f$$ is discontinuous has zero content, then $$f$$ is integrable on $$[a, b]$$
- **Proposition 4.14.** Suppose $$f$$ and $$g$$ are integrable on $$[a, b]$$ and $$f(x) = g(x)$$ for all except finitely many points $$x \in [a, b]$$. Then $$f_a^b f(x) dx = f_a^b g(x) dx$$
- **Theorem 4.15.** (The Fundamental Theorem of Calculus)
  1. Let $$f$$ be an integrable function on $$[a, b]$$. For $$x \in [a, b]$$, let $$F(x) = \int_a^x f(t) dt$$. Then $$F$$ is continuous on $$[a, b]$$; moreover, $$F'(x)$$ exists and equals $$f(x)$$ at every $$x$$ at which $$f$$ is continuous.
  2. Let $$F$$ be a continuous function on $$[a, b]$$ that is differentiable except perhaps at finitely many points in $$[a, b]$$, and let $$f$$ be a function on $$[a, b]$$ that agrees with $$F'$$ at all points where the latter is defined. If $$f$$ is integrable on $$[a, b]$$, then $$f_a^b f(t) dt = F(b) - F(a)$$
- Given an integrable function $$f$$ on $$[a, b]$$, for which partitions $$P$$ do the sums $$s_P f$$ and $$S_P f$$ give a good approximation of $$\int_a^b f(x) dx$$?
- **Proposition 4.16.** Suppose $$f$$ is integrable on $$[a, b]$$. Given $$\epsilon > 0$$, there exists $$\delta > 0$$ such that if $$P = \{ x_0, ..., x_J\}$$ is any partition of $$[a, b]$$ satisfying $$\max_{1 \le j \le J} (x_j - x_{j-1}) < \delta$$, the sums $$s_P f$$ and $$S_P f$$ differ from $$\int_a^b f(x) dx$$ by at most $$\epsilon$$.
- The definite integral -- good to understand as a sum of infinitely many infinitesimal terms.


### 4.2: Integration in Higher Dimensions
- Rectangle: a set of the form $$R = [a, b] \times [c, d]$$
- Partition of $$R$$: a subdivision of $$R$$ into rectangles by partitioning both sides of $$R$$
- We define the previous terms as follows:

$$m_{jk} = \inf \{ f(x, y) : (x, y) \in R_{jk}\}$$

$$M_{jk} = \sup \{ f(x, y) : (x, y) \in R_{jk} \}$$

$$\delta A_{jk} = (x_j - x_{j-1}) (y_k - y_{k-1})$$

$$s_P f = \sum_{j = 1}^J \sum_{k=1}^K m_{jk} \delta A_{jk}$$

$$S_P f = \sum_{j=1}^J \sum_{k=1}^K M_{jk} \delta A_{jk}$$

$$_LI_R (f) = \sup_P s_P f$$

$$_RI_R (f) = \inf_P S_P f$$

- $$f$$ is Riemann integrable on $$R$$ if the lower and upper integrals coincide:
$$\int \int_R f dA = \int \int_R f(x, y) dx dy$$

- How can we integrate over regions other than rectangles?
- Draw a large rectangle containing $$S$$, redefine $$f$$ to be zero outside of $$S$$, and integrate over $$R$$.
- Characteristic / indicator function of $$S$$: $$\chi_S(\mathbf{x}) = 1 \text{ if } \mathbf{x} \in S, 0 \text{ otherwise}$$
- $$f$$ is integrable on $$S$$ if $$f_{\chi S}$$ is integrable on $$R$$

$$\int \int_S f dA = \int \int_R f_{\chi S} dA$$

- **Theorem 4.17.**
  - If $$f_1, f_2$$ are integrable on the bounded set $$S$$ and $$c_1, c_2 \in \mathbb{R}$$, then $$c_1 f_1 + c_2 f_2$$ is integrable on $$S$$, and $$\int \int_S [c_1 f_1 + c_2 f_2] dA = c_1 \int \int_S f_1 dA + c_2 \int \int_S f_2 dA$$
  - Let $$S_1, S_2$$ be bounded sets with no points in common, and let $$f$$ be a bounded function. If $$f$$ is integrable on $$S_1$$ and on $$S_2$$, then $$f$$ is integrable on $$S_1 \cup S_2$$, in which case $$\int \int_{S_1 \cup S_2} f dA = \int \int_{S_1} f dA + \int \int_{S_2} f dA$$.
  - If $$f$$ and $$g$$ are integrable on $$S$$ and $$f(\mathbf{x}) \le g(\mathbf{x})$$ for $$\mathbf{x} \in S$$, then $$\int \int S f dA \le \int \int_S g dA$$
  - If $$f$$ is integrable on $$S$$, then so is $$\vert f \vert$$, and $$\vert \int \int_S f dA \vert \le \int \int_S \vert f \vert dA$$
- A set $$Z \subset \mathbb{R}^2$$ has zero content if for any $$\epsilon > 0$$, there is a finite collection of rectangles which cover $$Z$$ and the sum of their areas is less than $$\epsilon
- **Theorem 4.18.** Suppose $$f$$ is a bounded function on the rectangle $$R$$. If the set of points in $$R$$ at which $$f$$ is discontinuous has zero content, then $$f$$ is integrable on $$R$$.
- Smooth curves can in fact have zero content
- **Proposition 4.19.**
  - If $$Z \subset \mathbb{R}^2$$ has zero content and $$U \subset Z$$, then $$U$$ has zero content.
  - If $$Z_1, ..., Z_k$$ have zero content, then so does $$\bigcup_1^k Z_j$$.
  - If $$\mathbf{f} : (a_0, b_0) \to \mathbb{R}^2$$ is of class $$C^1$$, then $$\mathbf{f}([a, b])$$ has zero content whenever $$a_0 < a < b < b_0$$
- **Lemma 4.20.** The function $$\chi_S$$ is discontinuous at $$\mathbf{x}$$ iff $$\mathbf{x}$$ is in the boundary of $$S$$.
- We need the boundary of a set to have zero content. A set $$S \subset \mathbb{R}^2$$ is Jordan measurable if it is boudned and its boundary has zero content.
  - Any bounded set whose boundary is a finite union of pieces of smooth curves is measurable
- **Theorem 4.21.** Let $$s$$ be a measurable subset of $$\mathbb{R}^2$$. Suppose $$f : \mathbb{R}^2 \to \mathbb{R}$$ is bounded adn the set of points in $$S$$ at which $$f$$ is discontinuous has zero content. Then $$f$$ is integrable on $$S$$.
- **Proposition 4.22.** Suppose $$Z \subset \mathbb{R}^2$$ has zero content. If $$f : \mathbb{R}^2 \to \mathbb{R}$$ is boounded, then $$f$$ is integrable on $$Z$$ and $$\int \int_Z f dA = 0$$.
- **Corollary 4.23.**
  - Suppose $$f$$ is integrable on $$S \subset \mathbb{R}^2$$. If $$g$$ is bounded and $$g(\mathbf{x}) = f(\mathbf{x})$$ except for $$\mathbf{x}$$ in a set of zero content, then $$g$$ is integrable on $$S$$ and $$\int \int_S g dA = \int \int_S f dA$$
  - Suppose $$f$$ is integrable on $$S, T$$, and $$S \intersect T$$ has zero content. Then $$f$$ is integrable on $$S \cup T$$. We have $$\int \int_{S \cup T} f dA = \int \int_S f dA + \int \int_T f dA$$
- If $$S$$ is any Jordan measurable set in a plane, its area is the integral over $$SS$$ of the constant function $$f(\mathbf{x}) \equiv 1$$.

$$\text{area}(S) = \int \int_S 1 dA = \int \int \chi_S dA$$

- Theory of $$n$$-dimensional integrals -- need to use $$n$$-dimensional rectangular boxes in $$\mathbb{R}^n$$
- A bounded set $$Z \subset \mathbb{R}^n$$ has zero content iff for any $$\epsilon > 0$$ there are rectangular boxes $$R_1, ..., R_k$$ whose total volume is less than $$\epsilon$$, where the union of $$R_j$$ is a cover for $$Z$$.

- **Theorem 4.24.** (The Mean Value Theorem for Integrals.) Let $$S$$ be a compact, connected, measurable subset of $$\mathbb{R}^n$$, and let $$f, g$$ be continuous functions on $$S$$ with $$g \ge 0$$. Then there is a point $$\mathbf{a} \in S$$ such that $$\int ... \int_S f(\mathbf{x}) g(\mathbf{x}) d^n \mathbf{x} = f(\mathbf{a}) \int ... \int_S g(\mathbf{x}) d^n \mathbf{x}$$.
- **Corollary 4.25.** Let $$S$$ be a compact, connected, measurable subset of $$\mathbb{R}^n$$. Let $$f$$ be a continuous function on $$S$$. Then there is a point $$\mathbf{a} \in S$$ such that $$\int ... \int_S f(\mathbf{x}) d^n \mathbf{x} = f(\mathbf{a}) \vert S \vert $$ -- this is the average of mean value of $$f$$ on $$S$$

### 4.3: Multiple Integrals and Iterated Integrals
- In the case of $$n = 2$$, we should have that

$$\int \int_R f dA = \int_c^d \left[ \int_a^b f(x, y) dx \right] dy$$

- Integrability of $$f$$ on $$R$$ does not need to imply the integrability of $$f(x, y_0)$$ as a function of $$x$$ for fixed $$y_0$$ on $$[a, b]$$
- A line segment is a set of zero content, so in fact it could be discontinuous at every point in it

**Theorem 4.26.**
Let $$R$$ be a rectangle bounded by $$[a, b]$$ in $$x$$ and $$[c, d]$$ in $$y$$.
Let $$f$$ be an integrable function in $$R$$.
Suppose that the "slices" in each dimension are integrable.
Then

$$\int \int_R f dA = \int_c^d \left[ \int_a^b f(x, y) dx \right] dy = \int_a^b \left[ \int_c^d f(x, y) dy \right] dx$$

- Iterated integrals
- An integral over an $$n$$-dimensional rectangular solid can be evaluated as an $$n$$-fold iterated integral
- Under suitable conditions for the integrand $$f$$, the order of integration in an iterated integral can be reversed.

### 4.4: Change of Variables for Multiple Integrals
- If $$g$$ is a one-to-one function of class $$C^1$$ on the interval $$[a, b]$$, then for a continous function $$f$$,

$$\int_a^b f(g(u)) g'(u) du = \int_{g(a)}^{g(b)} f(x) dx$$

- Sometimes have to compensate for the 'right order' of the bounds because $$g$$ might reverse them

$$\int_I f(x) dx = \int_{g^{-1}(I)}
 f(g(u)) \vert g'(u) \vert du $$

 - Suppose $$\mathbf{G}$$ is a one-to-one transformation from a region $$R$$ to another region $$S$$. $$R = \mathbf{G}^{-1}(S)$$
 - Area of any matrix $$\mathbb{A}$$ as a transformation on the unit matrix is the absolute value of the determinant of $$\mathbb{A}$$

$$\int \int_S f(x, y) dx dy = \vert ad - bc \vert \int \int_{G^{-1}(S)} f(au + bv, cu + dv) du dv$$

**Theorem 4.37.**
Let $$A$$ be an invertible $$n \times n$$ matrix, and let $$\mathbf{G}(\mathbf{u}) = A \mathbf{u}$$ be the corresponding linear transformation of $$\mathbb{R}^n$$. Suppose $$S$$ is a measurable region in $$\mathbb{R}^n$$ and $$f$$ is an integrable function on $$S$$.
Then $$\mathbf{G}^{-1}(S) = \{ A^{-1} \mathbf{x} : \mathbf{x} \in S \}$$ is measurable and $$f \circ \mathbf{G}$$ is integrable on $$\mathbf{G}^{-1}(S)$$, and

$$\int ... \int_S f(\mathbf{x}) d^n \mathbf{x} = \vert \det A \vert \int ... \int_{G^{-1}(S)} f(A \mathbf{u}) d^n \mathbf{u}$$

**Theorem 4.41.**
Given open sets $$U, V$$ in $$\mathbb{R}^n$$, let $$\mathbf{G} : U \to V$$ be a one-to-one transformation of class $$C^1$$ whose derivative $$D \mathbf{G}(\mathbf{u})$$ is invertible for all $$\mathbf{u} \in U$$.
Suppose that $$T \subset U$$ and $$S \subset V$$ are measurable sets such that $$\bar{T} \subset U$$ and $$\mathbf{G}(T) = S$$.
If $$f$$ is an integrable function on $$S$$, then $$f \circ \mathbf{G}$$ is integrable on $$T$$, and

$$\int ... \int_S f(\mathbf{x}) d^n \mathbf{x} = \int ... \int_T f(\mathbf{G}(\mathbf{u})) \vert \det D \mathbf{G}(\mathbf{u}) \vert d^n \mathbf{u}$$

### 4.5: Functions defined by integrals
- We can form functions out of integrating variables. How do properties of $$f$$ relate to properties of $$F$$?
- To limits commute across integral operations? In general, the answer is no.

**Theorem 4.46.**
Suppose $$S, T$$ are compact subsets of $$\mathbb{R}^n$$ and $$\mathbb{R}^m$$, respectively, and $$S$$ is measurable.
If $$f(x, y)$ is continuous on the set $$T \times S$$, then the function $$F$$ defined by $$F(x) = \int ... \int_S f(x, y) d^n y$$ is continuous on $$T$$.

**Theorem 4.47.**
Suppose $$S \subset \mathbb{R}^n$$ is compact and measurable, and $$T \subset \mathbb{R}^m$$ is open.
If $$f$$ and $$\nabla_x f$$ are continuous on $$T \times S$$, then the function $$F$$ is of class $$C^1$$ on $$T$$, and 

$$\frac{\partial F}{\partial x_j} (\mathbf{x}) = \int ... \int_S \frac{\partial f}{partial x_j} (\mathbf{x}, y) d^n y$$

**Theorem 4.52.**
(Bounded Convergence Theorem.)
Let $$S$$ be a measurable subset of $$\mathbb{R}^n$$ and $$\{ f_j \}$$ be a sequence of integrable functions on $$S$$.
SUppose $$f_j(y) \to f(y)$$ for each $$y \in S$$, where $$f$$ is an integrable function on $$S$$, and there is a constant $$C$$ such that $$\vert f_j(y) \vert \le C$$ for all $$j$$ and all $$y \in S$$.
Then,

$$\lim_{j \to \infty} \int ... \int_S f_j (y) d^n y = \int ... \int_S f(y) d^n y$$

### 4.6: Improper Integrals
- Type I proper integrals: $$\int_a^\infty f(x) dx$$, $$f$$ integrable over every finite subinterval $$[a, b]$$
- Type II proper integrals: $$\int_a^b f(x) dx$$, $$f$$ integrable over $$[c, b]$$ for every $$c > a$$ but unbounded near $$x = a$4

$$\int_a^\infty f(x) dx = \lim_{b \to \infty} \int_a^b f(x) dx$$

- The integral converges if the RHS limit exists; otherwise, the limit diverges
- Does $$\int_a^\infty f(x) dx$$ converge?

**Lemma 4.54.**
If $$\phi$$ is a bounded increasing function on $$[a, \infty)$$, then $$\lim_{x \to \infty} \phi(x)$$ exists and equals $$\sup \{ \phi(x) : x \ge a \}$$.

- The integral $$\int_a^\infty f(x) dx$$ converges iff $$\int_a^b f(x) dx$$ remains bounded as $$b \to \infty$$

**Theorem 4.55.**
Suppose that $$0 \le f(x) \le g(x)$$ for all sufficiently large $$x$$.
If $$\int_a^\infty g(x) dx$$ converges, so does $$\int_a^\infty f(x) dx$$.
If $$\int_a^\infty f(x) dx$$ diverges, so does $$\int_a^\infty g(x) dx$$.

**Corollary 4.56.**
Suppose $$f > 0$$, $$g > 0$$, $$f(x) / g(x) \to l$$ as $$x \to \infty$$.
If $$0 < l < \infty$$, then $$\int_a^\infty f(x) dx$$ and $$\int_a^\infty g(x) dx$$ are both convergent or both divergent.
If $$l = 0$$, the convergence of $$\int_a^\infty g(x) dx$$ implies the convergence of $$\int_a^\infty f(x) dx$$.
If $$l = \infty$$, the divergence of $$\int_a^\infty g(x) dx$$ implies the divergence of $$\int_a^\infty f(x) dx$$.

$$\int_1^b \frac{dx}{x^p} = \frac{b^{1-p} - 1}{1 - p} \to \begin{cases} \infty & p < 1 \\ (p - 1)^{-1} & p > 1 \end{cases}$$

$$\int_1^b x^{-1} dx = \log b \to \infty$$

- $$\int_1^\infty x^{-p}$$ converges iff $$p > 1$$

**Corollary 4.57.**
If $$0 \le f(x) \le Cx^{-p}$$ for all sufficiently large $$x$$, where $$p > 1$$, then $$\int_a^\infty f(x) dx$$ converges.
If $$f(x) \ge cx^{-1} (c > 0)$$ for all sufficiently large $$x$$, then $$\int_a^\infty f(x) dx$$ diverges.

- There are functions whose rate of decay at infinity is faster than $$x^{-1}$$ but slower than $$x^{-p}$$ for any $$p > 1$$, and their integrals can converge or diverge.

**Theorem 4.58.**
If $$\int_a^\infty \vert f(x) \vert dx$$ converges, then $$\int_a^\infty f(x) dx$$ converges.

- integral is absolutely convergent if the same integral with absolute value of the function converges.
- The integral may converge even if the absolute integral does not converge because of cancellation effects in positive and negative values.

Type II integrals

$$\int_a^b f(x) dx = \lim_{c > a, c \to a} \int_c^b f(x) dx$$

- $$\int_a^b f(x) dx$$ converges if the RHS limit and diverges otherwise

**Theorem 4.59.**
Suppose that $$0 \le f(x) \le g(x)$$ fro all $$x$$ sufficiently close to $$a$$.
If $$\int_a^b g(x) dx$$ converges, so does $$\int_a^b f(x) dx$$. If $$\int_a^b f(x) dx$$ diverges, so does $$\int_a^b g(x) dx$$.

$$\int_c^b (x - a)^{-p} dx = \frac{(x-a)^{1-p}}{1-p} \bigg \vert_c^b \to \begin{cases} (1 - p)^{-1} (b - a)^{1 - p} & p < 1 \\ \infty & p > 1 \end{cases}$$

$$\int_c^b (x - a)^{-1} dx = \log(x - a) \vert_c^b \to \infty$$

**Corollary 4.60.**
If $$0 \le f(x) \le C(x - a)^{-p}$$ for $$x$$ near $$a$$ where $$p < 1$$, then $$\int_a^bf(x) dx$$ converges.
If $$f(x) > c(x - a)^{-1} (c > 0)$$ for $$x$$ near $$a$$, then $$\int_a^b f(x) dx$$ diverges.
























