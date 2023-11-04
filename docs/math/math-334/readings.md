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

$$R_{a, k}(h) = f(a + h) - P_{a, k}(h) = f(a + h) - \sum_{j = 0}^k \frac{f^{(j)}(a)}{j!} h^j$$

- The Taylor polynomial is a godo approximation of $$f$$ near $$a$$.

**Theorem 2.55.** -- Taylor's Theorem with Integral Remainder, I.
Suppose that $$f$$ is of class $$C^{k+1}$$, with $$k \ge 0$$ on an interval $$I \subset \mathbb{R}$$, and $$a \in I$$. Then the remainder $$R_{a, k}$$ defined by 2.53 - 2.54 is given by

$$R_{a, k}(h) = \frac{h^{k+1}}{k!} \int_0^1 (1 -t )^k f^{(k+1)} (a + th) dt$$.

**Theorem 2.58.** -- Taylor's Theorem with Integral Remainder, II.
Suppose that $$f$$ is of class $$C^k$$, $$k \ge 1$$ on an interval $$I \subset \mathbb{R}$$, and $$a \in I$$. Then the remainder $$R_{a, k}$$ is given by

$$R_{a, k}(h) = \frac{h^k}{(k-1)!} \in_0^1 (1 - t)^{k-1} \[ f^{(k)}(a + th) - f^{(k)(a)} \] dt$$

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
- For $$\cos x$$: $$\sum_{0 \le j \le k/2} \frac{(-1)^j x^{2j}}{(2j)!}
- For $$\sin x$$: $$\sum_{0 \le j \le (k-1)/2} \frac{(-1)^j x^{2j + 1}}{(2j + 1)!}$$
- For $$(1 - x)^{-1}$$: $$\sum_{0 \le j \le k} x^j$$

- Taylro polynomials can approximate complicated functions with easier computations
- Theoretically, importantly, the behavior of any function near some point is determined by the first nonvanishing term
- Suppsoe $$f : \mathbb{R}^n \to \mathbb{R}$$ is of class $$C^k$$ on a convex open set $$S$$. We can derive a Taylor expansion for $$f(\mathbf{x})$$ about a point $$\mathbf{a} \in S$$ by looking at the restriction of $$f$$ and the line joining $$\mathbf{a}$$ and $$\mathbf{x}$$.
- With $$\mathbf{h} = \mathbf{x} - \mathbf{a}$$
























