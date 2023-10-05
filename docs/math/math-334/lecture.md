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
- e.g. the sequence 1, 4, 9, 16, ... can be written as $\{ n^2 \}_{n=1}^\infty$$
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
- Proof that 2 implies 1 (prove the logicallay equivalent contrapositive statement):"not 1 implies not 2$$. If  $$\exists \vec{x}_0 \in \mathbb{R}^n$$ such that $$f(\vec{x})$$ is not continuous at $$\vec{x}_0$$, we'll prove $$\exists \vec{x}_n \to \vec{x}_0$$ and $$f(\vec{x}_n) $$ does not converge to $$f(\vec{x}_0)$$.
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


