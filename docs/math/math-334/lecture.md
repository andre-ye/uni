---
layout: default
title: Lecture Notes
parent: MATH 334
grand_parent: Mathematics
nav_order: 2
---

# Lecture Notes
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

## Lecture 1: Background and Notation

- Plan for fall -- chapters 1 to 4 of the Folland textbook
- Pre-midterm I: chapter 1
- Pre-midterm 2: chapters 2 and 3
- Grade breakdown:
  - Reading responses, free points, 5%
  - HW, posted weekly, assigned on Wednesday and due the following Wednesday at 11:59, 25%
  - Midterms: 20%
  - Final: 30%
  - All exams are inclass.

Historical Background
- Fourier and the crisis of the 19th century
- Fourier's ideas animate the course
- 1795: joined Napolean's expedition to Cairo
- Mathematics and imperialism
- Becomes very interested in heat
- How does heat diffuse across an object?
- The total heat distribution should solve $$\frac{\partial^2 u}{\partial x^2} = \partial w^u$$ and $$u(0, x) = f(x)$$
- Fourier found a general method for solving this -- partial differential equations
- His method requires assuming a special form: you can write your initial function as a sum of cosines. Then the distribution $$u$$ can be found easily.
- However this assumes that $$f(x) = 0; x = \pm 1$$, and that the function is continuous
- You can't solve $$f(x) = 1$$, for instance: you can't solve for heat when the temperature applied to a bar is constant.
- What's the solution? Bold idea: larger sums of cosines can predictably better approximate functions which cannot themselves be written as a finite sum.
  - For instance: write $$1 = \frac{4}{\pi} \left[ \cos \left( \frac{\pi x}{2} \right) - \frac{1}{3} \cos \left( \frac{3\pi x}{2} \right) + \frac{1}{5} \cos \left( \frac{5 \pi x}{2} \right) + ... \right]$$, for $$x \in (-1, 1)$$
  - You cannot do this with a Taylor epansion, you can't write constant functions in terms of nonconstant functions.
  - You immediately begin to run into all sorts of funny paradoxes
  - Notice that $$\cos \left( \frac{(2n-1) \pi (x+2)}{2} \right) = \cos \left( \frac{(2n-1) \pi x}{2} + (2n-1) \pi \right)$$: this amounts to a phase shift of $$\pi$$ in each instance
  - Therefore you could write $$-1$$ simply by shifting, so the formula is the same but the interval is now $$(1, 3)$$
  - All you did was add continuous things, but you got something totally noncontinuous...
- Response to Fourier: this is not a function. If you could call that a function and consider it a representation of such a familiar function, maybe Weierstrauss was onto something when he claimed $$W(x) = \cos(\pi x) + \frac{1}{2} \cos (13 \pi x) + \frac{1}{4} \cos (169 \pi x) + ... = \sum_{j=0}^\infty \frac{\cos(13^j \pi x)}{2^j}$$. 
  - This series converges and is a function
  - It is continuous in $$x$$
  - It is differentiable nowhere -- why can't I just take the derivatives of each term? -- you can't
  - "A monstrosity"
  - What does this do to our conception of continuity?
- Several questions follow:
  - What is a function in the first place?
  - When can a function be represented as a Fourier series, ideally one that converges?
  - When can a series be differentiated or integrated, term-by-term?
  - What is differentiation? What is integration?
  - What is continuity? WHat is convergence?
- This class will be occupied by these questions

Notation
- Basic
  - $$\forall$$, for all
  - $$\exists$$, there exists
  - Summation: $$\sum_{n=1}^k a_n = a_1 + a_2 + ... + a_k$$
  - $$\mathbb{N}$$, the naturals / whole numbers. $$\mathbb{N} = \{1, 2, 3, ...\}$$
  - $$\mathbb{Z}$$, the integers. $$\mathbb{Z} = \{..., -2, -1, 0, 1, 2, ...\}$$
  - $$\mathbb{Q}$$, the rationals. $$\mathbb{Q} = \left\{ \frac{p}{q} \mid p, q \in \mathbb{Z}, q \neq 0 \right\}$$
  - $$\mathbb{R}$$, the reals.
- Set theory
  - $$\Omega$$, the universal set
  - Union: $$A \cup B = \{x \in \Omega \vert x \mid x \in A \vee x \in B\}$$
  - Intersection: $$A \cap B = \{x \in \Omega \vert x \mid x \in A \wedge x \in B\}$$
  - Complement: $$A^C = \{x \in \Omega \vert x \mid x \notin A\}$$
  - Set difference: $$A \setminus B = \{x \in \Omega \vert x \mid x \in A \wedge x \notin B\}$$
    - Can also be written as $$A \setminus B = A \cap B^C$$
  - Big-Union: $$\bigcup_{j=1}^k A_j = A_1 \cup A_2 \cup ... \cup A_k = \{ x \| \exists j, x \in A_j \}$$
  - Big-Intersection: $$\bigcap_{j=1}^k A_j = A_1 \cap A_2 \cap ... \cap A_k = \{ x \| \forall j, x \in A_j \}$$
- Mappings and functions
  - *Function* from a set $$A$$ to a set $$B$$ is an assignment of every element in $$A$$ to exactly one element in $$B$$, denoted by $$f: A \to B$$
  - $$A$$: domain of $$f$$
  - $$B$$: codomain of $$f$$
  - $$f(A) = \{ y \in B \vert \exists x \in A, f(x) = y \} \subset B$$, the image/range of $$f$$
  - $$f$$ is injective / 1-to-1 if $$a_1 \neq a_2 \to f(a_1) \neq f(a_2)$$
  - $$f$$ is surjective / onto if $$\forall b \in B, \exists A \in A : f(A) = b$$
  - $$f$$ is bijective if both injective and surjective. Bijectivity gives you one-on-one pairing. Bijection is pairing but also works for infinite sets.
  - If $$f: A \to B$$ and $$g : B \to C$$, we can write their composition as $$g \circ f : A \to C$$, where $$(g \circ f)(x) = g(f(x))$$. Requirement: the codomain of $$f$$ must be a subset of the domain of $$g$$.
  - If $$f : A \to B$$ and $$g : B \to A$$, $$f$$ is invertible if $$\exists g: B \to A : g \circ f$$ s.t. $$A \to A$$ satisfies $$\forall x \in A, g \circ f(x) = x$$ an $$f \circ g: B \to B$$ satisfies $$\forall y \in B, f \circ g(y) = y$$. Basically: it sends every element back to itself.
    - Bijectivity implies invertability. 
    - Definition: $$g = f^{-1}$$
- Euclidean spaces and vectors
  - The reals $$\mathbb{R}$$
  - We can also consider tuples of reals: $$\mathbb{R}^n$$ for $$n \in \mathbb{N}$$, the set of ordered tuples of reals. $$\mathbb{R}^n = \{(x_1, x_2, ..., x_n) \vert \forall j, x_j \in \mathbb{R}\}$$
  - Vectors also used to describe $$n$$-tuples
  - Vector arrows are menat to capture that an $$n$$-tuple can also describe a direction and magnitude
  - The magnitude / norm of a vector / $$n$$-tuple is $$\Vert \vec{x} \Vert = \sqrt{x_1^2 + x_2^2 + ... + x_n^2}$$
  - Vector addition: $$\vec{x} + \vec{y} = (x_1 + y_1, x_2 + y_2, ..., x_n + y_n)$$
  - Scalar multiplication: $$\lambda \vec{x} = (\lambda x_1, \lambda x_2, ..., \lambda x_n)$$
  - Dot product / inner product: $$\vec{x} \cdot \vec{y} = x_1 y_1 + x_2 y_2 + ... + x_n y_n$$
    - Note that the norm is defined in terms of a dot product: $$\Vert \vec{x} \Vert = \sqrt{\vec{x} \cdot \vec{x}}$$

The Cauchy-Schwarz Inequality
- If $$\vec{a}, \vec{b} \in \mathbb{R}^n$$, $$\vert \vec{a} \cdot \vec{b} \vert \leq \Vert \vec{a} \Vert \Vert \vec{b} \Vert$$
- Going to be your best friend in this class
- This proof, which seems to work only in Euclidean space, is very much broadly applicable.
- Proof:
  1. If $$\vec{b} = \vec{0}$$, then both sides are zero. The inequality holds.
  2. Now, assume $$\vec{b} \neq \vec{0}$$. Consider the function $$f : \mathbb{R} \to \mathbb{R}_{\ge 0}$$ where $$f(t) = \vert \vert \vec{a} - t \vec{b} \vert \vert^2 = (\vert{a} \cdot t \vert{b}) \cdot (\vec{a} - t\vec{b}) = \vert \vert \vec{a} \vert \vert^2 - 2t (\vec{a} \cdot \vec{b}) + t^2 \vert \vert \vec{b} \vert \vert^2$$
  3. This quadratic function has a minimum at $$t = \frac{\vec{a} \cdot \vec{b}}{\vert \vert b \vert \vert ^2}$$
  4. Plugging this into $$f$$ gives you $$\vert \vert \vec{a} \vert \vert^2 - \frac{(\vec{a} \cdot \vec{b})^2}{\vert \vert \vec{b} \vert \vert^2}$$
  5. Since $$f(t) \ge 0$$, $$\vert \vert \vec{a} \vert \vert^2 - \frac{(\vec{a} \cdot \vec{b})^2}{\vert \vert \vec{b} \vert \vert^2} \ge 0$$, so $$\vert \vert \vec{a} \vert \vert^2 \vert \vert \vec{b} \vert \vert^2 \ge (\vec{a} \cdot \vec{b})^2$$
  6. Take square roots to get our inequality.

---

## Lecture 2: Euclidean Spaces, Open Sets, Limits and Continuity, Sequences

- Triangle inequality: $$\forall \vec{a}, \vec{b} \in \mathbb{R}^n$$, $$\| \vec{a} + \vec{b} \| \le \| \vec{a} \| + \| \vec{b} \|$$
  - Norm of sum is less than or equal to the sum of the norms
  - Proof
    1. Since $$(\| \vec{a} + \vec{b} \|)^2 = (\vec{a} + \vec{b}) \cdot (\vec{a} + \vec{b}) = \|a\|^2 + 2\vec{a}\vec{b} + \|b\|^2$$
    2. Appplying CS to the middle term: $$ \le \| \vec{a} \|^2 + 2 \| \vec{a} \| \| \vec{b} \| + \| \vec{b} \|^2$$
    3. Simplify: $$( \| \vec{a} \| + \| \vec{b} \|)^2$$
  - Why is it called the triangle inequality?
    - Define distance between two vectors using a norm: it's faster to go along the direct line ('hypotenuse') than the legs of the triangle
    - Formally: $$d(\vec{a}, \vec{b}) = \| \vec{a} - \vec{b} \| = \sqrt{(a_1 - y_1)^2 + (x_2 - y_2)^2 + ... } $$
- We use $$\vec{x} \cdot \vec{y}$$ or $$\langle \vec{x}, \vec{y} \rangle$$ to denote the dot product
- The angle between vectors describes some plane. By the Cauchy-Schwartz theorem, $$\frac{\vec{ x} \cdot \vec{y}}{\| \vec{x} \| \|\vec{y} \|}$$ is between $$-1$$ and $$1$$, so it is a cosine. Therefore, $$\cos \theta_{\vec{x}, \vec{y}} = \frac{\vec{x} \cdot \vec{y}}{\| \vec{x} \| \| \vec{y} \|}$$
  - $$\vec{x}, \vec{y}$$ are perpendicular iff $$\vec{x} \cdot \vec{y} = 0$$, in which case they are orthogonal.
  - As soon as you have a notion of inner product, you can define the angle between vectors.
- Useful inequality: if you have a vector $$\vec{x} \in \mathbb{R}^n$$, $$\vec{x} = (x_1, ..., x_n)$$, then its maximum of the absolute value of the vector is less than the norm of $$\vec{x}$$, and itself less than $$\sqrt{n} max \{ \vert x_1 \vert, ..., \vert x_n \vert \}$$.
  - $$\| \vec{x} \|_{\infty} = max \{ \vert x_1 \vert, ..., \vert x_n \vert \}$$, called the $$L^\infty$$ norm.
  - This is to be contrasted with the usual L-2 norm, $$ \Vert \vec{x} \Vert_2$$, which is the square root of the sum of the squares of the components.
  - Norms are generalizable across vector spaces.

Subsets of $$\mathbb{R}^n$$ - introduction to topology
- Topology tries to abstract the notion of "nearness" or "closeness" in a space, without specific notions of angle, length, etc.
- What do you need to describe a space? You need to say when points are near, and you don't need to do so quantiatively. 
- Definition: Let $$\vec{y}$$ be a point in $$\mathbb{R}^n$$ and $$r > 0$$. Define an open ball $$B_r(\vec{y})$$ to be the collection of all points in $$\mathbb{R}^n$$ such that the distance from every point to the center is less than $$r$$.
  - Formally: $$B_r(\vec{y}) = \{ \vec{x} \in \mathbb{R}^n \vert \| \vec{x} - \vec{y} \| < r \}$$
- A set $$S \subset \mathbb{R}^n$$ is bounded if it is contained in some ball centered at the origin $$\vec{0}$$. There exists a sufficiently large radius for an enclosing ball.
- Definition: a point $$\vec{x} \in \mathbb{R}^n$$ is an interior point of $$S$$ if there exists a ball centered at some point which is strictly contained in that set, where $$\vec{x}$$ is contained in that ball.
- Definition: the set of points in $$S$$ which are interior points of $$S$$ is called the interior of $$S$$, denoted $$S^\text{int}$$.

$$S^\text{int} = \{ \vec{x} \in S \vert \exists r > 0, B_r(\vec{x}) \subset S \}$$

- Examples of interiors:
  - If $$S = Br(\vec{y})$$, then $$S^\text{int} = S$$
  - If $$S = \{ \frac{1}{n} \in \mathbb{R} \vec n \in \mathbb{N} \}$$ (subset of a line), then $$S^\text{int} = \emptyset$$, since there is no ball around any point which is contained in $$S$$. Also note that $$0 \notin S$$.
- Definition: a point $$\vec{x} \in \mathbb{R}^n$$ is a boundary point of $$S$$ if every ball centered at $$\vec{x}$$ contains a point in $$S$$ and a point not in $$S$$.
- Definition: the set of boundary points of $$S$$ is called the boundary of $$S$$, denoted $$\partial S$$.
  - Example 1: if $$S = Br(\vec{y})$$, $$\partial S = \{ \vec{x} \in \mathbb{R}^n \vert \| \vec{x} - \vec{y} \| = r \}$$, the sphere of radius $$r$$ centered at $$\vec{y}$$.
  - Example 2: if $$S = \{ \frac{1}{n} \in \mathbb{R} \vert n \in \mathbb{N} \}$$, the boundary is $$\{ 0 \}$$. This is because every ball around $$0$$ contains points in $$S$$ and points not in $$S$$. **Or maybe not... depends on if you need to look at the center or not.** Otherwise the definition is kind of empty... need to clarify.
- Definition: the closure of a set $$\bar{S} = S \cup \partial S$$. The closure is the set of all points in $$S$$ and all boundary points of $$S$$.
  - Example 1: if $$S = Br(\vec{y})$$, then $$\bar{S} = \{ \vec{x} \in \mathbb{R}^n \vert \| \vec{x} - \vec{y} \| \le r \}$$, the closed ball of radius $$r$$ centered at $$\vec{y}$$.
  - Example 2: if $$S = \{ \frac{1}{n} \in \mathbb{R} \vert n \in \mathbb{N} \}$$, then $$\bar{S} = S \cup \{ 0 \}$$.
- Definition: $$S$$ is open if it contains no boundary points. $$S$$ is closed if it contains all of its boundary points.
  - Example 1: $$Br(\vec{y})$$ is open
  - Example 2: $$\{ \frac{1}{n} \in \mathbb{R} \vert n \in \mathbb{N} \}$$ is closed
  - Example 3: $$\{ \frac{1}{n} \in \mathbb{R} \vert n \in \mathbb{N} \} \cup \{ 0 \}$$ is neither open nor closed
- Proposition: If $$S \subset \mathbb{R}^n$$,
  - $$S$$ is open iff it is equal to its interior
  - $$S$$ is closed iff its complement is open
  - Proof:
    1. An element of $$S$$ is iether an interior point or a boundary point.
    2. $$S$$ is open iff every point is interior.
    3. $$S = \bar{S} = S \cup \partial S \iff \partial S \subset S \implies \partial(S^C) \subset S$$ (boundaries are shared between a set and its complement) $$\iff S^C$$ contains no boundary points
  - Example:
    - If $$S = \emptyset$$, this is a set which is both open and closed.
    - If $$S = \mathbb{Q}$$, the set of fractions, this set is neither open nor closed. The interior is empty, $$S^{\text{int}} = \emptyset$$; yet the closure of $$S$$ is $$\mathbb{R}$$, so $$S$$ is not closed.
  
Limits
- "You can't lift your pencil"
- Definition: let $$f: \mathbb{R}^n \to \mathbb{R}$$ be a real-valued function.

$$\lim_{\vec{x} \to \vec{a}} = L \text{ if } \forall \epsilon_{> 0}, \exists \delta_{> 0} : \vert f(\vec{x}) - L \vert < \epsilon \text{ whenever } \Vert \vec{x} - \vec{a} \Vert < \delta$$

- $$a$$ whenever $$b$$: $$b \to a$$
- We can replace $$\Vert \vec{x} - \vec{a} \Vert < \delta$$ with the $$L^\infty$$ norm:

$$\Vert \vec{x} - \vec{a} \Vert_{\infty} = \max \{ \vert x_1 - a_1 \vert, ..., \vert x_n - a_n \vert \} < \frac{\delta}{\sqrt{n}}$$

- You can also consider a limit on a subset, $$f : S \sub \mathbb{R}^n \to \mathbb{R}$$.

$$\lim_{\vec{x} \to \vec{a}, \vec{x} \in S} f(\vec{x}) = L \text{ if } \forall \epsilon_{> 0}, \exists \delta_{> 0} : \vert f(\vec{x}) - L \vert < \epsilon \text{ whenever } \Vert \vec{x} - \vec{a} \Vert < \delta \text{ and } \vec{x} \in S$$

Continuity
- Definition: $$f(\vec{x})$$ is continuous at $$\vec{a}$$ if the limit as $$\vec{x}$$ approaches $$\vec{a}$$ of $$f(\vec{x})$$, and $$f(\vec{a})$$, both exist and are equal.
- Definitions also make sense for vector-valued functions: you can go from $$\mathbb{R}^n$$ to $$\mathbb{R}^m$$. All you need is a corresponding notion of norm, which you do in any Euclidean space / dimension. The only thing that changes is to replace $$\Vert f(\vec{x}) - \vec{L} \Vert_n < \epsilon$$, where $$n$$ is the dimension of the value space.
  - Alternatively, you can find the limit of each indvididual component, considering the sub-function $$f_{j}: \mathbb{R}^m \to \mathbb{R} \sub \mathbb{R}^n$$.
- The notion of "getting close" is very subtle in high dimensions -- it's harder than just taking left and right limits.
  - Example 1: $$f : \mathbb{R}^2 \to \mathbb{R}, f(x, y) = \frac{xy}{x^2 + y^2}$$. This function is everywhere bounded. $$\vec f(x, y) \vec \le 2$$. A consequence of Cauchy-Schwartz. But the function fails to be continuous at the origin. The limit as $$\vec{x} \to \vec{0}$$ does not exist. By taking linear lines of approach, the line is constant, but the line in particular changes this constant value
- Theorem. Let $$f_1(x, y) = x+ y$$, $$f_2(x, y) = xy$$, $$g(x) = \frac{1}{x}$$. $$f_1, f_2 : \mathbb{R}^2 \to \mathbb{R}$$; $$g: \mathbb{R} \setminus \{0\} \to \mathbb{R}$$. Proof:
  1. Let $$(a, b) \in \mathbb{R}^2$$
  2. Given $$\epsilon > 0$$, we must show that there exists some $$\delta$$ such that if $$\vert x - a \vert < \delta$$ and $$\vert y - b \vert < \delta$$, then $$ \vert (x + y) - (a + b) \vert < \epsilon$$. 
  3. Let us choose $$\delta = \frac{1}{2} \epsilon$$.
  4. $$\vert (x + y) - (a + b) \vert = \vert (x - a) + (y - b) \vert \le \vert (x -a ) \vert + \vert (y - b) \vert$$. Via triangle inequality
  5. We have that $$\delta + \delta = \frac{\epsilon}{2} + \frac{\epsilon}{2} = \epsilon$$.
  6. **Revisit proof!**
- *Theorem. Say $$f : \mathbb{R}^n \to \mathbb{R}^m$$ and $$g = \mathbb{R}^m \to \mathbb{R}^k$$. If $$f$$ and $$g$$ are continuous at $$\vec{a}$$, then $$g \circ f$$ is continuous at $$\vec{a}$$. Proof:*
  1. Let $$\epsilon > 0$$.
  2. Since $$g$$ is continuous at $$f(\vec{a})$$, there exists $$\delta_1 > 0$$ such that $$\Vert g(\vec{y}) - g(f(\vec{a})) \Vert < \epsilon$$ whenever $$\Vert \vec{y} - f(\vec{a}) \Vert < \delta_1$$.
  3. Since $$f$$ is continuous at $$\vec{a}$$, there exists $$\delta_2 > 0$$ such that $$\Vert f(\vec{x}) - f(\vec{a}) \Vert < \delta_1$$ whenever $$\Vert \vec{x} - \vec{a} \Vert < \delta_2$$.
  4. Let $$\delta = \delta_2$$.
  5. Then $$\Vert g(f(\vec{x})) - g(f(\vec{a})) \Vert < \epsilon$$ whenever $$\Vert \vec{x} - \vec{a} \Vert < \delta$$.
- Later, with sequences: $$a_n = 2a_{n-1} - a_n-2 + 2$$. Claim: $$a_n = n^2$$. You can prove this with induction.

---

## Lecture 3: Sequences, Induction, the Completeness Axiom

Sequences
- A sequence is a collection of mathematical objects which are indexed by the natural numbers
- We denote a sequence by $$\{x_k \}^\infty_{k=1}$$
- A set has no notion of order, whereas a sequence does have order
- e.g. the sequence 1, 4, 9, 16, ... can be written as $$\{ n^2 \}_{n=1}^\infty$$
- e.g. a sequence of intervals $$(-1, 1), (-1/2, 1/2), (-1/3, 1/3), ...$$ can be written as $$\{ (-1/n, 1/n) \}_{n=1}^\infty$$
- You can also define sequences inductively: $$F_1 = 1, F_2 = 1, F_n = F_{n+2} = F_{n+1} + F_n$$
- A nice proof technique: an inductive proof. Useful for proving statements of the form $$\forall n \in \mathbb{N}, P(n)$$ is true. First, show $$P(1)$$. Then, show $$P(n) \implies P(n+1)$$ (inductive step)
- Example: consider $$a_1 = 1, a_2 = 4, a_n = 2a_{n-1} - a_{n-2} + 2$$ for $$n \ge 3$$. Claim: $$a_n = n^2$$.
- Sequences of real numbers / vectors, $$\{ x_n \}_{n=1}^\infty \subseteq \mathbb{R}^2$$ converge to $$\vec{a} \in \mathbb{R}^n$$ if $$\forall \epsilon > 0, \exists N > 0$$ such that $$\Vert \vec{x}_n - \vec{a} \vert < \epsilon, \forall n > N$$. If this is so, then $$\vec{x}_n \to \vec{a}$$. if $$\{ \vec{x}_{n=1}^\infty \}$$ does not converge to any vector, the sequence diverges. 
- We can describe limits / continuity in the form of sequences
- e.g. the sequence $$\{ 1/k \}_{k=1}^\infty$$ converges to 0.
- e.g. the sequence $$\{ (-1)^k \}_{k=1}^\infty$$ is divergent.
- The following are equivalent.
  1. $$f : \mathbb{R}^n \to \mathbb{R}^n$$ is continuous.
  2. $$\forall \vec{x}_0 \in \mathbb{R}^n, \forall \{ \vec{x}_n \}_{n=1}^\infty$$ converging to $$\vec{x}_0$$, $$\{ f(\vec{x}_n ) \}_{n=1}^\infty$$ converges to $$f(\vec{x}_0)$$.
  3. $$\forall U \subseteq \mathbb{R}^k$$ an open set, the preimage $$f^{-1}(U) = \{ \vec{x} \in \mathbb{R}^n \vert f(\vec{x}) \in U \} \subseteq \mathbb{R}^n$$ is also open.
- Proof that 1 implies 2: 
  1. Let $$\vec{x}_0 \in \mathbb{R}^n$$ be arbitrary, and assume $$f$$ is continuous at $$\vec{x}_0$$. 
  2. Let $$\{ \vec{x}_n \}_{n=1}^\infty$$ be a sequence converging to $$\vec{x}_0$$.
  3. By continuity, $$\forall \epsilon > 0$$, $$\exists \delta > 0$$ such that $$ \Vert f(\vec{x}) - f(\vec{x}_0) \Vert > \epsilon$$ whenever $$\Vert \vec{x} - \vec{x}_0 \Vert < \delta$$.
  4. Since $$\vec{x}_n \to \vec{x}_0$$, $$\exists N > 0$$ such that $$\Vert \vec{x}_n - \vec{x}_0 \Vert < \delta, \forall n > N$$.
- Proof that 2 implies 1 (prove the logicallay equivalent contrapositive statement):"not 1 implies not 2". If  $$\exists \vec{x}_0 \in \mathbb{R}^n$$ such that $$f(\vec{x})$$ is not continuous at $$\vec{x}_0$$, we'll prove $$\exists \vec{x}_n \to \vec{x}_0$$ and $$f(\vec{x}_n) $$ does not converge to $$f(\vec{x}_0)$$.
  1. Since $$f$$ is not continuous at $$\vec{x}_0$$, $$\exists \epsilon_0 > 0, \forall \delta > 0, \exists \vec{x}_{\delta} \in \mathbb{R}^n$$ where $$\Vert \vec{x}_\delta - \vec{x}_0 \Vert < \delta$$ and $$\Vert f(\vec{x}_\delta) - f(\vec{x}_0) \Vert > \epsilon_0$$
  2. For each of $$\delta = 1, 1/2, 1/3, ..., 1/k, ...$$ choose such a vector $$\vec{x}_k$$ as above. 
  3. Although the sequence $$\vec{x}_k \to \vec{x}_0$$, $$f(\vec{x}_k)$$ does not converge to $$f(\vec{x}_0)$$.
- Proof that 1 implies 3:
  1. Say $$U \subseteq \mathbb{R}^l$$ is open. We will show that every point in $$f^{-1}(U)$$ is contained in a ball, contained in the preimage.
  2. If $$\vec{a} \in f^{-1}(u)$$, then $$f(\vec{a}) \in U$$, since $$U$$ is open, $$\exists r > 0$$ such that $$B_r(f(\vec{a})) \subseteq U$$; i.e., $$\forall \vec{y} \in \mathbb{R}^k$$, $$\Vert \vec{y} - f(\vert{a}) \Vert < r, \vec{y} \in U$$.
  3. By continuity of $$f$$, for $$r > 0$$, $$\exists \delta > 0$$ such that $$\Vert f(\vec{x}) - f(\vec{a}) \Vert < r$$ whenever $$\Vert \vec{x} - \vec{a} \Vert < \delta$$; i.e., $$B_\delta(\vec{a}) \subseteq f^{-1}(U)$$, so $$f^{-1}(U)$$ is open. 
- Preimage definition: $$f^{-1}(U) = \{ \vec{x} \in \mathbb{R}^n \vert f(\vec{x}) \in U \}$$
- Proof that 3 implies 1.
  1. Let $$\vec{a} \in \mathbb{R}^n$$ be arbitrary. $$\forall \epsilon > 0, B_\epsilon ( f(\vec{a})) \subseteq \mathbb{R}^k$$ is open.
  2. By 3, $$f^{-1}(B_\epsilon (f(\vec{a})))$$ is open. By openness, $$\exists \delta > 0$$ such that $$B_\delta(\vec{a}) \subseteq f^{-1} (B_\epsilon (f(\vec{a})))$$.
  3. So, if $$\Vert \vec{x} - \vec{x} \Vert < \delta$$, then $$\Vert f(\vec{x}) - f(\vert{a}) \Vert < \epsilon$$, so $$f$$ is continuous at $$\vec{a}$$.
- Corollary: If $$f : \mathbb{R}^n \to \mathbb{R}^k$$ is continuous and $$V \subset \mathbb{R}^k$$, then $$f^{-1}(V)$$ (the preimage) is also closed.
- Example: if $$C > 0$$, the sequence $$\{ C^n / n! \}_{n=1}^\infty$$ converges to 0.
  1. Choose $$N > 2C$$, then $$\forall n > N$$ we have $$0 < C^n / n! = C^N / N! \cdot C / (N+1) \cdot C / (N+2) \cdot ... \cdot C / n$$
  2. We can upper-bound the rest of these $$C^n / N! \cdot \frac{1}{2} \cdot \frac{1}{2} \cdot ... \cdot \frac{1}{2}$$
  3. These factors are $$n - N$$ in number, and going to zero as $$n \to \infty$$. Therefore the sequence converges to zero.
- **Theorem.** $$A \subseteq \mathbb{R}^n$$ is a subset. Then $$\vec{x} \in \bar{A} \iff A \text{ intersects every neighborhood of } \vec{x}$$. (A point is in the closure of a set if the set intersects every neighborhood of the point.) Recall that $$\vec{x}$$ has a neighborhood $$U$$ if $$\vec{x}$$ is interior to $$U$$. We will prove the contrapositive: a point is not in the closure of a set iff the point has a neighborhood not intersecting $$A$$.
  1. Say $$ \vec{x} \notin \bar{A}$$, then $$\mathbb{R}^n \setminus \bar{A} = U$$ is a neighborhood which does not intersect $$A$$.
  2. Say $$\exists U$$, a neighborhood of $$\vec{x}$$ not meeting $$A$$. Then $$\mathbb{R}^n \setminus U$$ is a closed set containing $$A$$, implying that the closure of $$A$$ is a subset of $$\mathbb{R}^n \setminus U$$. Since $$\vec{x} \notin \mathbb{R}^n \setminus U, \vec{x} \notin A$$.
- **Theorem.** If $$S \subseteq \mathbb{R}^n$$, and $$\vec{x}_0 \in \mathbb{R}^n$$, $$\vec{x}_0 \in \bar{S} \iff \exists \{ \vec{x}_n \}_{n=1}^\infty \subseteq S \text{ where } \vec{x}_n \to \vec{x}_0$$.
  - "It's not possible to take a sequence of points and escape a closed ball"
  1. **Leftwards proof.** If $$\vec{x}_n \to \vec{x}_0$$ and $$\forall n, \vec{x}_n \in S$$, then every neighborhood of $$\vec{x}_0$$ contains an element of $$S$$, namely $$\vec{x}_n$$ for $$n$$ sufficiently large.
  2. Since $$\vec{x}_n \to \vec{x}_0$$, $$\forall \epsilon > 0$$, $$\exists N > 0$$ such that $$\Vert \vec{x}_n - \vec{x}_0 \Vert < \epsilon$$, $$\forall n > N$$; any neighborhood of $$\vec{x}_0$$ contains such a ball and $$\vec{x}_n \in B_\epsilon ( \vec{x}_0 ) \subseteq U$$, a neighborhood of $$\vec{x}_0$$. 
  3. So $$\vec{x}_n \in S \cap U$$ for every neighborhood $$U$$, and thus $$\vec{x}_0 \in S$$.
  4. **Rightwards proof.** Say we have a point which is in the closure $$\vec{x}_0 \in \bar{S}$$. If $$\vec{x}_0 \in S$$, then in fact we can take a constant sequence $$\exists \{ \vec{x}_0 \}_{n=1}^\infty$$ which converges to $$\vec{x}_0$$.
  5. If $$\vec{x}_0 \in \bar{S}$$ but $$\vec{x}_0 \notin S$$, then $$B_{1/k} (\vec{x}_0)$$ is a neighborhood of $$\vec{x}_0$$, $$\forall k \in \mathbb{N}$$. 
  6. By theorem, $$\forall k, \exists \vec{x}_k \in B_{1/k}(\vec{x}_0) \cap S$$. Choosing one for each ball produces a sequence. This sequence clearly converges to $$\vec{x}_0$$. 
- The rightward implication: you can construct something just outside your set, to the closure, but no further.
- **Important property of the reals.** Completeness in the reals: every sequence of real numbers which gets close to itself converges to a real number. When we talk about a limit existing, we point towards an existing limit. But even if we don't know about the limit, the numbers get closer and closer to each other.

If $$S \subseteq \mathbb{R}$$ is a subset, an upper bound $$b$$ for $$S$$ is a real number $$b \in \mathbb{R}$$ such that$$\forall x \in S, x \le b$$.
Similarly, a lower bound is a $$y \in \mathbb{R}$$ such that $$\forall x \in S$$, $$y \le x$$. Bounds for a set are not unique.
**The Completeness Axiom.** -- one of the defining properties of the reals (proven in Kemp's notes, theorem 4.13). 
If $$S \susbsetequals \mathbb{R}$$ and non-empty,
1. If $$S$$ has an upper bound, it has a least upper bound
2. If $$S$$ has a lower boud, it has a greatest lower bound
Although this is true for the reals, it is false for the rationals.
For example, $$S = \{ x \in \mathbb{R} \vert x \in \mathbb{Q} \text{ and } x^2 < 2 \}$$. There is no least upper bound in the rationals (it is in the reals).

---

## Lecture 4: Sequences, Extrema

- Monotone Sequence Theorem: every bounded monotone sequence is convergent. 
- Since $$l$$ is a least upper bound, $$\forall \epsilon > 0, \exists N > 0$$ s.t. $$l - \epsilon < x_n, \forall n > N$$, as otherwise $$l - \epsilon$$ would be a smaller upper bound than $$l$$. Thus $$\forall \epsilon > 0, \exists N > 0, l - \epsilon \le x_n < l, \forall n > N$$. Therefore, $$x_n \to l$$. 
- Nested Interval Theorem: consider a sequence of intervals $\{I_k\}_{k=1}^\infty$$, where $$I_k = [a_k, b_k]$$ such that $$I_1 \supset I_2 \supset I_3 \supset ... \supset I_k \supset ...$$. $$b_k - a_k \to 0$$ as $$k \to \infty$$. Then $$\exists$$ a unique $$x_0$$ in every $$I_n$$. Proof:
  1. Since $$I_1 \supset I_2 \supset I_3 \supset ...$$, then $$a_1 \le a_2 \le a_3 \le ...$$, and $$b_1 \ge b_2 \ge b_3 \ge ...$$. These are monotone sequences.
  2. These are bounded sequences since $$a_1 \le a_k \le b_k \le b_1$$, $$\forall k$$.
  3. We can apply the monotone sequence theorem to show that both sequences are convergent.
  4. Moreover, since $$b_k - a_k \to 0$$, then the converge to the same element. Call this element $$x_0$$. Since $$a_k \le x_o \le b_k$$, $$\forall k$$, so $$x_0 \in [a_k, b_k] \implies x_0 \in \cap_{k=1}^\infty I_k$$.
  5. We have to show moreover that this point is unique. Assume that there are two unique elements which are both in the intersection of all intervals. Then there is some nonzero distance between them. But since $$b_k - a_k \to 0$$, $$\exists N$$ s.t. $$\vert b_N - a_N \vert < \epsilon$$. Since $$x_0, x' \in [a_N, b_N]$$. This is a contradiction because $$\vert x_0 - x' \vert > \epsilon$$.
- $$\{x_n\} = \{(-1)^n \}$$ is bounded but not monotone.
- If $$\{x_k\}_{k=1}^\infty$$ is a sequence, a subsequence $$\{ x_{k_j} \}_{j=1}^\infty$$ and is defined by an injective increasing function from $$j \to k_j$$.
  - That the injection is increasing means that the ordering is preserved.
  - Example: if $$k_j = 2j$$, $$\{ (-1)^k \}_{k=1}^\infty$$ has a subsequence $$\{ (-1)^{2j} \}_{j=1}^\infty = \{ 1, 1, 1, ... \}$$.

**Theorem (Bolzano-Weierstrass).** Every bounded sequence in $$\mathbb{R}$$ has a convergent subsequence. (It doesn't need to be monotone.) Proof by divide and conquer. Have something like an inductive argument, and then we are forced into one of two choices. 
1. Let $$\{x_k\}_{k=1}^\infty$$ be bounded, say $$x_k \in [a, b], \forall k \in \mathbb{N}$$.
2. First, bisect the interval $$[a, b]$$ into $$[a, (a+b)/2]$$ and $$[(a+b)/2, b]$$.
3. Let $$I_1$$ be the biggest interval. One of these subintervals must contain infinitely many terms in the sequence.
4. If both do, just choose the left one. Call this interval $$I_2$$.
5. Bisect $$I_2$$ into $$[a_2, (a_2 + b_2)/2]$$ and $$[(a_2 + b_2)/2, b_2]$$. Choose a subinterval as above, call it $$I_3$$.
6. We continue to narrow in one whichever interval still has an infinite number of terms in the sequence.
7. Proceeding in this way, we produce a sequence of nested intervals $$I_1 \supset I_2 \supset I_3 \supset ...$$.
8. We know, moreover, that their lengths are decreasing to zero. $$\vert I_k \vert = \frac{b - a}{2^{k-1}}$$.
9. To construct our subset, $$k_1 \in \mathbb{N}$$ s.t. $$x_{k_1} \in I_1$$, $$k_2 > \mathbb{N} : k_2 > k_1$$ s.t. $$x_{k_2} \in I_2$$, and so on. This guarantees that the subsequence is contained in the intersection of all the intervals *and* the order is preserved.
10. By the Nested Interval Theorem, there is some $$x_0 \in \cap_{k=1}^\infty I_k$$. $$\{ x_{k_j} \}_{j=1}^\infty$$ converges to $$x_0$$.

**Corollary.**
Every bounded sequence in $$\mathbb{R}^n$$ has a convergent subsequence.
If you look at a sequence of vectors, they all converge component-wise. But you couldn't say that the sequenece converges to a single vector.
$$\forall j = 1, ..., n, \exists a$$ convergent subsequence for $$\{ x_k^{(j)}\}$$ by BW. We proceed inductively.
1. Choose a subsequence of vectors, say $$\{ \vec{x}_{k_l} \}_{l=1}^\infty$$, where the first component converges.
2. Choose a subsubsequence which makes the second components converge. This will preserve the property that the first component converges, too.
3. As long as $$n$$ is finite, you can keep on taking subs `;)`

**Definition.**
A sequence is Cauchy if $$\forall \epsilon > 0, \exists N > 0$$ s.t. $$\Vert \vec{x}_n - \vec{x}_m \Vert < \epsilon$$ whenever $$n, m > N$$.
You can talk about a seuqnece being Cauchy without knowing what it converges to.
Its components pile up, they end up being very close to each other, there is an index such that all the terms after that index are very close to each other.
This is tronger even than saying that consecutive terms go to zzero. It also says that the terms *in general* after a certain point are very close to each other.

- Todd Kemp: the real numbers are equivalence classes of Cauchy sequences which are rational.

**Theorem.** A sequence in $$\mathbb{R}^n$$ is a convergent sequence iff it is Cauchy. You don't need to know the limit to know that the sequence is Cauchy. So often it is easier to show that a sequence of things is Cauchy rather than finding the convergent value. Proof:
1. If $$\{\vec{x}_n\}_{n=1}^\infty$$ is converging to $$\vec{x}_0 \in \mathbb{R}^n$$, the sequence is cauchy. Since $$\vec{x}_j - \vec{x}_k = (\vec{x}_j - \vec{x}_0) + (\vec{x}_0 - \vec{x}_k)$$. Then, appeal to the triangle inequality: $$\Vert \vec{x}_k - \vec{x}_j \Vert \le \Vert \vec{x}_j - \vec{x}_0 \Vert + \Vert \vec{x}_0 - \vec{x}_k \Vert$$ as $$k, j \to \infty$$. (For every $$\epsilon$$, choose the $$N$$ such that the convergence exists such that $$j, k$$ the minimum of the two is greater than $$N$$.) Then $$\Vert \vec{x}_k - \vec{x}_j \Vert < \epsilon$$.
2. Suppose $$\{ \vec{x}_k \}_{k=1}^\infty$$ is Cauchy. Choosing $$\epsilon = 1$$ in the definition of Cauchy, there exists some $$N$$ such that $$\vert \vec{x}_k - \vec{x}_k \Vert < 1$$ for all $$j, k > N$$. Our sequence, then, is bounded. Iin particular, $$\Vert \vec{x}_k \Vert < \Vert \vec{x}_{k+1} \Vert + 1$$, $$\forall k > N$$. Thus the sequence is bounded and thuse has a convergent subsequence. But the Cauchy property shows us that the limit of the subsequence is the same as the limit of the original sequence. 
  - Claim: the sequence converges to $$\vec{x}_0$$, not just the subsequence. 
  - Given $$\epsilon > 0, \exists J > 0$$ s.t. $$\Vert \vec{x}_{k_j} - \vec{x}_0 \Vert < \epsilon / 2$$ if $$j > J$$ (by convergence), further $$\exists N > 0$$ s.t. $$\Vert \vec{x}_k - \vec{x}_m \Vert < \epsilon / 2$$ if $$k, m > N$$ (Cauchy).
  - Thus $$\Vert \vec{x}_k - \vec{x}_0 \Vert \le \Vert \vec{x}_k - \vec{x}_{k_j} \Vert + \Vert \vec{x}_{k_j} - \vec{x}_0 \Vert < \epsilon / 2 + \epsilon / 2 = \epsilon$$ if $$k > N$$ and $$j > J$$.

Compactness
- **Definition.** A set $$S \subseteq \mathbb{R}^n$$ is compact if it is closed and bounded / every sequence in $$S$$ has a convergent subsequence whose limit is in $$S$$.
- Remark: finite sets are compact. Compact sets can be infinite, but behave like finite sets.
- **Theorem** (Extreme Value Theorem). If $$f: [a, b] \to \mathbb{R}$$ is continuous, it achieves its max and min.


Notes
- Midterm 1 is going to cover chapter 1 of the book. 

---


## Lecture 5: Compactness and Connectedness

**COMPACTNESS**

**Definition.**
$$S \subseteq \mathbb{R}^n$$ is compact if it is closed and bounded.

**Theorem.**
The following are equivalent:
1. $$S \subseteq \mathbb{R}^n$$ is compact
2. Every sequence of points in $$S$$ has a convergent subsequence whose limit is also in $$S$$

Proof:
1. If $$S$$ is closed and bounded, then Bolzano-Weierstrass guarantees that you have a convergent subsequence. Closedness implies the limit lies in $$S$$. 
2. Suppose $$S$$ is not compact. If $$S$$ is not bounded, then there exists a sequence in $$S$$ such that the norm of the vector goes to infinity, in which case there is no convergent subsequence. If $$S$$ is not closed, then there exists an element in the closure of the set but not in the set itself, but because this is an element of the closure, there exists a subsequence converging to $$\vec{x}_0$$, since $$\vec{x}_k \in B_{1/k} (\vec{x}_0)$$, $$\forall k \in \mathbb{N}$$.

**Remark.** Every finite set is compact.
- Compactness is an expansion of useful properties of finite sets to infinite sets. 

**Theorem.**
Continuous functions map compact sets to compact sets.
If $$f: S \to \mathbb{R}^m$$ is continuous and $$S$$ is compact, then the image of $$S$$ under $$f$$ is compact.

Proof:
1. Suppose there is a set of points in the image $$\{\vec{y}_k\} \subseteq f(S)$$, then $$\forall k \in \mathbb{N}, \exists \{ vec{x}_k \} \subseteq S : f(\vec{x}_k) = \vec{y}_k$$.
2. Since $$S$$ is compact, there exists a subsequence $$\vec{x}_{k_j}$$ which is converging in $$S$$: $$\vec{x}_{k_j} \to \vec{x}_0 \in S$$.
3. Since $$f$$ is continuous at $$\vec{x}_0$$, $$f(\vec{x}_k) \to f(\vec{x}_0)$$
4. So $$\{\vec{y}_{k_j}\} = \{f(\vec{x}_{k_j})\} \to f(\vec{x}_0) \in f(S)$$.

**Extreme Value Theorem.**
If $$f : S \subseteq \mathbb{R}^n \to \mathbb{R}$$ is continuous, $$S$$ is compact. 
Then $$f$$ has a max and min value which is attained in $$S$$, i.e. $$\exists \vec{a}, \vec{b} \in S$$ s.t. $$f(\vec{a}) \le f(\vec{x}) \le f(\vec{b})$$, $$\forall \vec{x} \in S$$. These values are attained in the set.
We know we have supremums and infimums in the reals. But we don't know that we have max and min values. This theorem says that we do have max and min values if we are in a compact set.

**Definition.**
Maybe the most general notion of compactness.
Let $$S \subseteq \mathbb{R}^n$$. Let $$\{ \mathcal{U}_\alpha \}_{\alpha \in A} \subseteq \mathbb{R}^n$$ be a cover of $$S$$ if $$S \subseteq U_{\alpha \in A} \mathcal{U}_\alpha$$.

**Heine-Borel Theorem.**
If we have a subset of $$\mathbb{R}^n$$ $$S$$, $$S$$ is compact iff every open cover of $$S$$ has a finite subcover.

Example.
Let $$S = [0, 1]$$ are compact.
Then the collection $$\{B_\epsilon(x)\}_{x \in [0, 1]}, \epsilon > 0$$

**Definition.** (Metric Spaces.)
A metric space is a set $$X$$ with a function $$d : X \times X \to \mathbb{R}$$ satisfying the following properties for every pair of points:
1. Symmetry: $$d(x, y) = d(y, x)$$
2. Positivity: $$d(x, y) \ge 0$$
3. Definiteness: $$d(x, y) = 0 \iff x = y$$
4. Triangle Inequality: $$d(x, z) \le d(x, y) + d(y, z)$$

Examples of metric spaces.
- Real space with Euclidean distance: $$\mathbb{R}^n$$ with $$d(\vec{x}, \vec{y}) = \Vert \vec{x} - \vec{y} \Vert_2$$
- Real space with $$L$$-infinity distance: $$\mathbb{R}^n$$ with $$d(\vec{x}, \vec{y}) = \Vert \vec{x} - \vec{y} \Vert_\infty$$
- Function space with sup-norm: $$C^0 ([0, 1]) = \{ f: [0, 1] \to \mathbb{R} \vert f \text{ is continuous.}\}$$ with $$d(f, g) = \Vert f - g \Vert_\infty := \sup_{x \in [0, 1]} \vert f(x) - g(x) \vert$$

**Definition.**
If $$(x, d)$$ is a metric space, an $$\epsilon$$-ball is $$B_\epsilon (x) = \{ y \in X \vert d(x, y) < \epsilon \}$$.

**Definition.**
A set $$S \subseteq (X, d)$$ is open if $$\forall x \in S, \exists \epsilon > 0$$ s.t. $$B_\epsilon (x) \subseteq S$$.
Closed sets are complements of an open set.

*What is compactness now?*
A sequential definition of compactness: every sequence has a convergent subsequence whose limit is in $$S$$.
Consider the sequence $$\{ f_n (x) \}_{n=1}^\infty$$ in $$C^0([0, 1])$$, $$f_n(x) = x^n$$
The sequence is bounded. The sup-norm is bounded by 2, but their ``limit'' seems to be discontinuous, where it is $$y = 0$$ for $$[0, 1)$$ and $$1$$ at $$1$$.
Clearly this sequence does not have a convergent subsequence, because they converge to something outside of our space.
So compactness needs to be more complex when thinking about spaces that are infinite-dimensional.


**CONNECTEDNESS**

**Definition.**
A separation of a set $$S \subseteq \mathbb{R}^n$$ is a pair of disjoint nonempty sets $$A, B \subseteq \mathbb{R}^n$$ such that $$S = A \cup B$$ and $$\bar{A} \cap B = A \cap \bar{B} = \emptyset$$.
A set is connected if no separation exists.

Example:
- The set $$S = \{ (x, y) \vert (x - 1)^2 + y^2 < 1\} \cup \{(x, y) \vert (x + 1)^2 + y^2 < 1 \}$$
- The origin does not belong to either set

**Theorem.**
The connected subsets of $$\mathbb{R}$$ are the intervals [open, closed, half-open, unbounded].

Proof:
- If $$S$$ is not an interval, it is disconnected. This means that there exist $$a, b$$ in $$S$$ and $$c \in \mathbb{R}$$ s.t. $$a < c < b$$, but $$c \notin S$$. Set $$A = S \cap (-\infty, c), B = S \cap(c, \infty)$$. There is only one point in common across the intersection $$\bar{A} \cup \bar{B}$$, which is $$c$$. But $$c \notin S$$.
- If $$S = [a, b]$$, say $$S$$ has some separation $$A \cup B = S$$. WLOG, we can assume $$a \in A, b \in B$$. Let's set $$c = \sup A$$, $$c \in \bar{A}$$. Because this is a separation, then $$c \notin B$$ by the definition of separation. Therefore $$c \in A$$. Because $$c \in A, \notin B$$, in particular, $$c \neq b$$. But then $$(c, b] \subseteq B$$, so $$c \in \bar{B}$$ and thus cannot be in $$A$$. This is a contradiction. So, $$[a, b]$$ must be connected. Say $$S$$ is an unboudned interval and has a separation $$A \cup B = S$$.

**Intermediate Value Theorem.**
The continuous image of a connected set is connected.
If $$f$$ is a map from $$S \cap \mathbb{R}^n \to \mathbb{R}^m$$ is continuous and $$S$$ is connected, then $$f(S)$$ is connected. 

Proof by contrapositive: if the image is disconnected, then the original set is disconnected.
1. If $$A \cup B = f(S)$$ is a separation of the image, then $$f^{-1}(A) \cup f^{-1}(B) = S$$ is a separation of the original set.
2. Both of these sets are nonempty because their union was the image.
3. Take $$\vec{x}_0 \in f^{-1}(A)$$ and say $$\vec{x}_0 \in \bar{f^{-1}(B)}$$.
4. Use the sequential definition of belonging to the closure; there exists a sequence of points $$\vec{x}_k$$ which are in the preimage of $$B$$ which converge $$\vec{x}_k \to \vec{x}_0 \in f^{-1}(B)$$.
5. Since $$f$$ is continuous, $$f(\vec{x}_k) \to f(\vec{x}_0) \in B$$.
6. But $$f(\vec{x}_0) \in A \cap \bar{B}$$, contradicting that $$A \cap B = f(S)$$ is a separation.

Corollary:
If $$f : S \supseteq \mathbb{R}^n \to \mathbb{R}$$ and $$S$$ is connected, then $$f(S)$$ is an interval.
Thus $$\forall \vec{a}, \vec{b} \in S$$, where $$f(\vec{a}) < t < f(\vec{b})$$, there must exist a third element of the set such that $$f(\vec{c}) = t$$

Example:
The function $$f(x) = x^{367} + \frac{57}{3}x^{250} + \frac{e^{\pi^2}}{42} x^{83} + x^2 + 17$$ has a solution in $$\mathbb{R}$$.
How do we know it exists?
Because of the intermediate value theorem. At some point it is positive, and at some point it is negative, which means that at some point it is zero.

**Definition.**
A set is path-connected if $$\forall \vec{x}, \vec{y} \in S : \exists g : [0, 1] \to S : g(0) = \vec{x}, g(1) = \vec{y}$$, noting $$g$$ is continuous.
This function defines a path in the set $$S$$.

**Theorem.**
If $$S$$ is path-connected, then $$S$$ is connected. 
To prove, show the contrapositive and proof by contradiction as needed.

**Topologist's Sine Curve.** It's possible to be connected but not path connected.
Let $$S = \{ (0, y) \vert y \in [-1, 1] \} \cup \{ (x, \sin(\pi / x)) \vert 0 < x < 2 \} $$.
This is not a separation because if you look at the closure of either of these two sets, they meet the other.
But if you look at any point on the vertical line, there is no continuous path in the set which goes from a point in one set to the other, because it would need to pass through the crazy part of the curve. 



Notes
- Every function is surjective onto its own preimage


---

## Lecture 6: Uniform Continuity 

- When we define $$f : S \subset \mathbb{R}^n \to \mathbb{R}^m$$ continuous on $$S$$, this means that for all points in $$S$$, $$f$$ is continuous at that point (epsilon-delta) definition.
- However, note that the delta we choose is dependent on $$\vec{x}$$ (i.e. we need to adapt the delta based on the given conditions, i.e. shape of $$f$$ around $$x$$ and tightness of $$\epsilon$$)

**Uniform continuity.**
A function $$f : S \subseteq \mathbb{R}^n \to \mathbb{R}^m$$ is uniformly continuous on $$S$$ if the following definition is satisfied.

$$\forall \epsilon > 0, \exists \delta > 0 : \forall \vec{x}, \vec{y} \in S, \Vert \vec{x} - \vec{y} \Vert < \delta \implies \Vert f(\vec{x}) - f(\vec{y}) \Vert < \epsilon$$

- Example: $$f(x) = \sin(x)$$ is uniformly continuous on $$\mathbb{R}$$. 

Geenerally speaking, if $$f$$ satisfies
$$\forall \vec{x}, \vec{y} \in S, \exists M > 0 : \Vert f(\vec{x}) - f(\vec{y}) \Vert \le M \Vert \vec{x} - \vec{y} \Vert$$,
then $$f$$ is uniform continuous on $$S$$, with $$\epsilon = \delta / M$$.

Lipschitz inequality with Lipschitz constant $$M$$.
We say $$f$$ is $$M$$-Lipschitz on $$S$$.

Consider $$f(x) = e^x : \mathbb{R} \to \mathbb{R}$$ is not uniformly continuous on $$\mathbb{R}$$.
This is **not uniformly continuous.**
Assume that it is uniformly continuous on $$\mathbb{R}$$.
Let $$\epsilon = 1$$. Then there exists some positive $$\delta$$ such that $$\forall x, y \in \mathbb{R}$$, $$\vert x - y \vert < \delta \implies \vert e^x - e^y \vert < 1$$.
Notice that $$\vert e^{\delta / 2} - 1 \vert > 0$$ and $$\lim_{x \to \infty} e^x = \infty$$, thus $$\exists x_0 \in \mathbb{R}$$ s.t. then $$\vert e^{x_0} (e^{\delta / 2} - 1) \vert > 1$$. But then, $$\vert e^{x_0 + \delta / 2} - e^{x_0} \vert > 1$$, which is a contradiction.

**But, who gives a fuck about uniform continuity?**

- Suppose $$f : S \subset \mathbb{R}^n \to \mathbb{R}^m$$ is continuous, and $$\{ \vec{x}_n \}_{n=1}^\infty \subseteq S$$ is Cauchy. Is $$\{f(\vec{x}_n)\}_{n=1}^\infty$$ Cauchy?
- Consider $$S = (0, 1)$$, $$f(x) = 1/x : (0, 1) \to \mathbb{R}$$. The sequence converges outside of its set. $$\{ x_n \}_{n=1}^\infty = \{ 1/n \}_{n=1}^\infty \subseteq S$$, $$x_n \to 0$$, $$\{ f(x_n) \}_{n=1}^\infty = \{ n \}_{n=1}^\infty$$

**Theorem.**
If $$f : S \subseteq \mathbb{R}^n \to \mathbb{R}^m$$ is uniform continuous on $$S$$, then $$f$$ sends Cauchy sequences to Cauchy sequences.

**Theorem.** (Heine, 1870).
Suppose $$S \subseteq \mathbb{R}^n$$ is compact.
Then if $$f : S \subseteq \mathbb{R}^n \to \mathbb{R}^m$$ is continuous, it is uniformly continuous. 

(Proof.)
1. Assume for the sake of contradiciton that $$f$$ is not unfiromly continuous.
2. This means that there exists an $$\epsilon$$ such that for every $$\delta$$, there exists $$\vec{x}, \vec{y} \in S$$ such that $$\Vert \vec{x} - \vec{y} \Vert < \delta$$ and $$\Vert f(\vec{x}) - f(\vec{y}) \Vert > \epsilon$$.
3. Suppose we have the sequence $$\delta = 1, 1/2, 1/3, ..., 1/n, ...$$.
4. For each element in this sequence, $$\exists \vec{x}, \vec{y} s.t. \Vert \vec{x}_n - \vec{y}_n \Vert < 1/n$$ and $$\Vert f(\vec{x}_n) - f(\vec{y}_n) \Vert > \epsilon$$.
5. By BW Theorem, there exists a subsequence $$\vec{x}_{n_j} \to \vec{a} \in S$$, and also that $$\Vert \vec{x}_{n_j} - \vec{y}_{n_j} \Vert \to 0$$, so $$\vec{y}_{n_j} \to \vec{a}$$.
6. Therefore, $$f(\vec{x}_{n_j} - f(\vec{y}_{n_j}) \to 0)$$.
7. This contradicts $$\Vert f(x_{n_j}) - f(y_{n_j}) \Vert > \epsilon$$.

---

## Lecture 7: Differential Calculus
Some history
- Many real analysis cours eare taught "backwards"
- Sharaf al-Din al-Tusi, 12th century Iranian mathematician, derivative of cubic equation
- Bhaskara II, 12th century Indian mathematician, derivative of sine function, Taylor approximations
- Merton School, 14th century, mean value theorem, etc.
- An explosion of interest in calculus and derivatives in the 17th century, growing out of practical questions, trying to solve this type of question: You have a curve which is the graph of a function. You want to find the tangent line to that point.
- Applications:
  - Angles of intersecting curves (Decartes)
  - Building telescopes and clocks (Galilei, Huygens)
  - Finding maxes and mins of functions (Newton, Fermat)
  - Astronomy (Kepler, Newton)

Derivatives
- Leibniz's proof: If $$x$$ changes by $$\delta x$$, then $$y = x^2$$ should change by $$y + \delta y = (x + \delta x)^2 = x^2 + 2x\delta x + (\delta x)^2$$. Relabel $$\delta x, \delta y$$ as $$dx, dy$$ and as they become 'infinitely small', then $$(\delta x)^2$$ gets infinitely smaller. Also subtract $$y = x^2$$. So we get $$dy = 2x dx$$, or $$dy/dx = 2x$$.
- But what does "infinitely small" mean? When can we just drop $$(\delta x)^2$$?
- Leibniz is considering some kind of limiting argument. 
- Consider this as a sort of linear approximation.
- Idea: given $$f : \mathbb{R} \to \mathbb{R}$$. Find a linear function $$l(x) = mx + b; m, b \in \mathbb{R}$$ approximating $$f(x)$$ at $$x = a$$.
  1. Basic criteria: $$f(a) = l(a)$$; i.e. $$f(a) = ma + b$$; $$l(x) = m(x - a) + f(a)$$
  2. The difference $$f(x) - l(x)$$ goes to zero faster than $$x - a$$ as $$x \to a$$. In other words, $$\frac{f(x) - l(x)}{x - a} \to 0$$ as $$x \to a$$.
- We can rewrite the error of the linear approximation. Let $$h = x - a$$. Then $$f(x) - l(x) = f(a + h) - f(a) - mh =: E(h)$$ ''error''. '

**Definition.**
Let $$f : I \subseteq \mathbb{R} \to \mathbb{R}$$ where $$a \in I$$. We say $$f$$ is differentiable at $$a$$ if there exists $$m \in \mathbb{R}$$ s.t.
$$f(a + h) = f(a) + mh + E(h)$$ where $$\lim_{h \to 0} E(h) / h = 0$$, where $$h = x - a$$.
We call $$m$$ the derivative of $$f$$ at $$a$$.
(Note that this is a first-order Taylor approximation.)

But we can rearrange: $$m = \frac{f(a + h) - f(a) - E(h)}{h} = \frac{f(a + h) - f(a)}{h}$$. (Error goes to zero.)
But if you think of it in the first way, you're thinking that it can be easured as a linear approximation plus an error.

The condition $$\lim_{h \to 0} \frac{E(h)}{h} = 0$$ is often denoted $$E(h)$$ is $$\mathcal{O}(h)$$, ''little-oh''. Thus differentiability is described as ``$$f(a + h)$$ is linear $$ + \mathcal{O}(h)$$''.

Note that if $$\lim_{h \to 0} \frac{E(h)}{h} = 0$$, then $$\lim_{h \to 0} E(h) = 0$$.
Then $$\lim_{h \to 0} f(a + h) - f(a) - mh = \lim_{h \to 0} E(h) = 0$$.
But this implies that $$f$$ is continuous.
Differentiability at a point implies continuity at a point.

We will write the value of $$m$$ as $$f'(a)$$, the derivative of $$f$$ at $$a$$.
There may not be a function $$f'(x)$$ such that $$m = f'(x) \vert_{x = a}$$.

**Example.**
Proof of the product rule.
If $$f, g$$ are differentiable at $$a$$, the derivative of $$f(x)g(x)$$ at $$a$$ is $$f'(a) g(a) + f(a) \cdot g'(a)$$.
Since $$f, g$$ are differentiable, we can write out their linear approximations. $$f(a + h) = f(a) + f'(a) h + E_1(h)$$, $$g(a + h) = g(a) + g'(a)h + E_2(h)$$.
Therefore, $$f(a + h) g(a + h) = f(a) g(a) + \left[ f'(a) g(a) + f(a) g'(a) \right]h + E_3(h)$$.
We have a really ugly term $$E_3 = \left( f(a) + f'(a) h + E_1(h)\right) E_2(h) +  \left( g(a) + g'(a) h + E_2(h) \right) E_1(h) + f'(a) g'(a) h^2$$.
This is all little-oh, they all have limits which, if you divide by zero, still go to zero as you go to zero.

---

## Lecture 8: Derivatives in 1 Variable, Several Variables, the Mean Value Theorem
- Bigger than 45: A; between 37 and 44: B; between 30 and 36: C; less than 29; D
- Average: 38, 81%
- Median: 40, 84%

**Definition.**
Let $$f : I \subseteq \mathbb{R} \to \mathbb{R}$$, and $$a \in I$$ be an open interval. $$f$$ is differentiable at $$a$$ if there exists $$m \in \mathbb{R}$$ s.t. $$f(a + h) = f(a) + mh + E(h)$$, such that $$\lim_{h \to 0} \frac{E(h)}{h} = 0$$.

Note that, in the limit as $$h \to 0$$, this limit equals $$m$$. 

**Lemma.**
Say we have $$f : I \subset \mathbb{R} \to \mathbb{R}$$ and $$a \in I$$ is open, and $$a$$ is a local maximum or minimum of the function.
If $$f$$ is differentiable at $$a$$, then $$f'(a) = 0$$.

Proof.
1. Since $$a$$ is the local min, $$f(a + h) \ge f(a)$$ for all $$h$$ sufficiently small.
2. Then $$(f(a + h) - f(a)) / h$$ has the same sign as $$h$$..
3. Look at the left and right limits as $$h \to 0^\pm$$ 
4. Since $$f$$ is differentiable, the limits must agree, so $$f'(a) = 0$$.

**Rolle's Theorem.** 
One of the earliest ideas about calculus.
If $$f$$ is continuous on a closed interval $$[a, b]$$ and $$f$$ is differentiable on $$(a, b)$$ and if $$f(a) = f(b)$$, then there exists $$c \in (a, b)$$ s.t. $$f'(c) = 0$$.
"What comes up must come down."

Proof.
1. From the extreme value theorem, because the closed interval is compact, any continuous function on it has a max and a min.
2. If one of each is at the endpoints, since $$max = f(a) = f(b) = min$$, then $$f$$ is cnonstant. Then the derivative of the function is 0.
3. Otherwise, a min or max occurs in the interval, and the mean occurs there.

Non-constructive proof: doesn't tell you where the min or max is.
You can guarantee your tangent slope will vanish somewhere in the interval.

**One-variable mean value theorem.**
Important consequence of Rolle's theorem.
Say $$f$$ is continuous on $$[a, b]$$ and differentiable on $$(a, b)$$.
Then $$\exists c \in (a, b)$$ s.t. $$f'(c) = \frac{f(b) - f(a)}{b - a}$$.
This line is the secant line connecting the two points. The slope of the tangent line is the same as the slope of the secant line.

Proof
1. $$(a, f(a))$$ and $$(b, f(b))$$ are connected by the line $$l(x) = f(a) + \frac{f(b) - f(a)}{b - a} (x - a)$$.
2. Exists $$c \in (a, b)$$ where $$f'(c)$$ is the slope of the line.
3. We claim $$\exists c \in (a, b)$$ where $$f'(c)$$ equals the slope of the secant line.
4. We can write down a new function which is just a difference of the other two: $$g(x) = f(x) - l(x)$$. $$g'(c) = 0$$ means that $$f'(c) = l'(c)$$.
5. Since $$g(a) = g(b) = 0$$, we can apply Rolle's theorem to $$g$$, which means that $$g'(c) = 0$$ for some $$c \in (a, b)$$.

**Definition.**
We say that $$f$$ is either increasing or decreasing if $$\forall a < b$$, $$f(a) \le f(b)$$ or $$f(a) \ge f(b)$$, respectively.
Strictly increasing if $$f(a) < f(b)$$ or $$f(a) > f(b)$$, respectively.

**Theorem.**
Say $$f$$ is differentiable on $$I$$, an open interval.
1. If $$\vert f'(x) \vert \le C$$, $$\forall x \in I$$, then $$f$$ is Lipschitz with constant $$C$$. That is, $$\vert f(x) - f(y) \vert \le C \vert x - y \vert$$.
2. If $$f'(x) = 0$$, $$\forall x \in I$$, then $$f$$ is constant.
3. If $$f'(x) \ge 0$$, $$\forall x \in I$$, then $$f$$ is increasing.

Proof.
1. For $$a, b \in I$$, by the MVT, we have $$c \in (a, b)$$ s.t. $$f'(c) (b - a) = f(b) - f(a)$$.
2. Then 1 implies $$\vert f'(c) \le C$$ and 2 implies $$f(b) = f(a)$$.
3. The constant in the Lipshitz inequality is the absolute value of the derivative, so $$\vert f(b) - f(a) \vert \le C \vert b - a \vert$$.
4. If $$f'(c) \ge 0$$, then $$f(b) - f(a) \ge 0$$. SO $$f(a) \le f(b)$$.

**Corollary.**
For any $$a > 0$$, we have

$$\lim_{x \to +\infty} \frac{x^a}{e^x} = \lim_{x \to +\infty} \frac{\log x}{x^a} = \lim_{x \to 0^+} \frac{\log x}{x^{-a}} = 0$$

At infinity, exponentials grow larger than any power of $$x$$; any power of $$x$$ grows larger than $$\log$$; any $$\log$$ grows larger than any negative power of $$x$$.

**L'Hopital's rule** -- need to be continuous and differentiable in the neighborhood.

**1-variable, vector-valued functions**
Suppose you have a function $$f : \mathbb{R} \to \mathbb{R}^n$$, then $$f(x)$$ is a scalar quantity, but the output is a vector.
For each $$j$$, you can write the derivative at $$a$$ as $$f'(a) = \lim_{h \to 0} \frac{f(a + h) - f(a)}{h} = (f_1'(a), f'_2(a), ..., f'_h(a))$$.
$$f$$ is differentiable at $$a$$, or $$f_j$$ is differentiable at $$a$$ for all $$j = 1, ..., n$$.
If $$\phi : \mathbb{R} \to \mathbb{R}$$ and $$g : \mathbb{R} \to \mathbb{R}^n$$.
Then it satisfies $$(\phi f)' = \phi' f + \phi f'$$.
Moreover, $$(\langle f, g \rangle)' = \langle f', g \rangle + \langle f, g' \rangle$$.
It follwos that $$(\Vert f \Vert^2)' = 2 \Vert f \Vert$$

Think about these functions as parametrized curves in $$\mathbb{R}^n$$: $$t \to f(t)$$, e.g. the path of a particle, in which case $$t \to f'(t)$$ is the path of velocity vectors of the particle.

The tangent line too $$f(t)$$ is $$l(t) = f(t_0) + t f'(t_0)$$.

**Scalar-valued, multi-variable differentiability**. $$f : D \subseteq \mathbb{R}^n \to \mathbb{R}$$.
Start with a partial derivative.
The derivative of a function w.r.t. 1 variable while fixing the others  as constant.
Suppose $$f(\vec{x}) = f(x_1, ..., x_n)$$. Then $$\frac{\del f}{\del x_j} (\vec{x}) = \lim_{h \to 0} \frac{f(x_1, ..., x_{j+h}, ..., x_n) - f(x_1, ..., x_j, ..., x_n)}{h}$$
Just changing a single component of the input.

Partial derivatives don't tell you the whole story about a function's local behavior.

**Definition.**
A function $$f: D \subseteq \mathbb{R}^n \to \mathbb{R}$$ is differentiable at $$\vec{a} \in D$$ if there exists $$\vec{c} \in \mathbb{R}^n$$ s.t. $$f(\vec{a} + \vec{h}) = f(\vec{a}) + \langle \vec{c}, \vec{h} \rangle + E(\vec{h})$$ s.t. $$\lim_{\vec{h} \to \vec{0}} \frac{E(\vec{h})}{\Vert h \Vert} = 0$$.
Equivlaently, $$\lim_{\vec{h} \to 0} \frac{f(\vec{a} + \vec{h}) - f(\vec{a}) - \langle \vec{c}, \vec{h} \rangle}{\Vert \vec{h} \Vert} = 0$$.
If this limit exists, we write $$\vec{c} = \nabla f(\vec{a})$$, the gradient of $$f$$ at $$\vec{a}$$.

For example, $$z = f(\vec{x})$$ is a surface. $$z = f(\vec{a}) + \langle \nabla f(\vec{a}), \vec{x} - \vec{a} \rangle$$ is a plane.
$$f$$ is differentiable at $$\vec{a}$$ if $$Z_{\text{surface}} - Z_{\text{plane}} = f(\vec{x}) - f(\vec{x} - \vec{a}) - \langle \nabla f(\vec{a}), \vec{a} - \vec{a} \rangle = E(\vec{x} - \vec{a}) \to_{\text{ faster than } \Vert \vec{x} - \vec{a} \Vert \to 0} 0$$.
At any point, the tangent plane is a good approximation for points near the point on the surface.

**Theorem.**
If $$f$$ is differentiable at $$\vec{a}$$, then all $$\del_j f(\vec{a})$$ exist, and $$\nabla f(\vec{a}) = (\del_1 f(\vec{a}), ..., \del_n f(\vec{a}))$$.

if there exists $$m \in \mathbb{R}$$ s.t. $$f(\vec{a} + \vec{h}) = f(\vec{a}) + m \cdot \vec{h} + E(\vec{h})$$, where $$\lim_{\vec{h} \to 0} \frac{E(\vec{h})}{\Vert \vec{h} \Vert} = 0$$.

Partials are all components of the derivative. If we know something about all of the partials, we can conclude something about the derivative at a point.

**Theorem.**
If $$f$$ is differentiable at $$\vec{a}$$, then $$f$$ is continuous at $$\vec{a}$$.

**Theorem.**
If $$f : D \subseteq \mathbb{R}^n \to \mathbb{R}$$ and for $$\vec{a} \in D$$, if all $$\del_j f$$ exist in a neighborhood of $$\vec{a}$$ and are continuous at $$\vec{a}$$, then $$f$$ is differentiable at $$\vec{a}$$.

Proof in 2D for simplicity.
1. We want to show that $$\frac{f(\vec{a} + \vec{h}) - f(\vec{a}) - \langle \vec{c}, \vec{h} \rangle}{\Vert \vec{h} \Vert} \to 0$$ as $$\vec{h} \to 0$$.
2. Let $$\vec{c} = (\del_1 f(\vec{a}), \del_2 f(\vec{a}))$$.
3. Then, for $$\vec{h} = (h_1, h_2)$$.
4. Since $$f(\vec{a} + \vec{h}) - f(\vec{a}) = [f(a_1 + h_1, a_2 + h_2) - f(a_1, a_2 + h_2)] + [f(a_1, a_2 + h_2) - f(a_1, a_2)]$$
5. Use the one-variable mean value theorem to bound each of these components.
6. For $$\Vert \vec{x} - \vec{a} \Vert \le \Vert \vec{h} \Vert < \delta$$ sufficiently small, we have that the first term is less than $$\del_1 f(a_1 + c_1, a_2 + h_2) h_1$$, $$\del_2 f(a_1, a_2 + c_2) h_2$$.
7. Therefore, $$\frac{f(\vec{a} + \vec{h}) - f(\vec{a}) - \langle \vec{c}, \vec{h} \rangle}{\Vert \vec{h} \Vert} \le [\del_1 f(a_1 + c_1, a_2 + h_2) - \del_1 f(a_1, a_2)] \frac{h_1}{\Vert \vec{h} \Vert} + [\del_1 f(a_1, a_2 + c_2) - \del_2 f(a_1, a_2)] \frac{h_2}{\Vert \vec{h} \Vert} \le \epsilon/2 + \epsilon /2 < \epsilon$$.
8. This applies WLOG, apply mean value in every coordinate.




