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

**Theorem 1.13.** Suppose $$\mathbf{f} : \mathbb{R}^n \to \mathbf{R}^k$$ is continuous and $$u$$ \subset \mathbb{R}^k$$. Let $$S = \{ \mathbf{x} \in \mathbb{R}^n : \mathbf{f}(\mathbf{x}) \in U\}$$. Then $$S$$ is open if $$U$$ is open and $$S$$ is closed if $$U$$ is closed.




