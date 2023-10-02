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
  2. Now, assume $$\vec{b} \neq \vec{0}$$. Consider the function $$f : \mathbb{R} \to \mathbb{R}_{\ge 0}$$ where $$f(t) = \vert \vert \vec{a} - t \vec{b} \vert \vert^2 = (\vert{a} \cdot t \vert{b}) \cdot (\vet{a} - t\vert{b}) = \vert \vert \vec{a} \vert \vert^2 - 2t (\vec{a} \cdot \vec{b}) + t^2 \vert \vert \vec{b} \vert \vert^2$$
  3. This quadratic function has a minimum at $$t = \frac{\vec{a} \cdot \vec{b}}{\vert \vert b \vert \vert ^2}$$
  4. Plugging this into $$f$$ gives you $$\vert \vert \vec{a} \vert \vert^2 - \frac{(\vc{a} \cdot \vec{b})^2}{\vert \vert \vec{b} \vert \vert^2}$$
  5. Since $$f(t) \ge 0$$, $$\vert \vert \vec{a} \vert \vert^2 - \frac{(\vec{a} \cdot \vec{b})^2}{\vert \vert \vec{b} \vert \vert^2} \ge 0$$, so $$\vert \vert \vec{a} \vert \vert^2 \vert \vert \vec{b} \vert \vert^2 \ge (\vc{a} \cdot \vec{b})^2$$
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
- We use $$\vec{x} \cdot \vec{y}$$ or $$\langle \vec{x}, \vec{y} \rangle$ to denote the dot product
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
    - If $$S = \nullset$$, this is a set which is both open and closed.




