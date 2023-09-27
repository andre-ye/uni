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

## Lecture 1:
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
- Response to Fourier: this is not a functio. If you could call that a function and consider it a representation of such a familiar function, maybe Weierstrauss was onto something when he claimed $$W(x) = \cos(\pi x) + \frac{1}{2} \cos (13 \pi x) + \frac{1}{4} \cos (169 \pi x) + ... = \sum_{j=0}^\infty \frac{\cos(13^j \pi x)}{2^j}$$. 
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
  - $$\sum_{n=1}^k a_n = a_1 + a_2 + ... + a_k$$
  - $$\mathbb{N}$$, the naturals / whole numbers. $$\mathbb{N} = \{1, 2, 3, ...\}$$
  - $$\mathbb{Z}$$, the integers. $$\mathbb{Z} = \{..., -2, -1, 0, 1, 2, ...\}$$
  - $$\mathbb{Q}$$, the rationals. $$\mathbb{Q} = \left\{ \frac{p}{q} \mid p, q \in \mathbb{Z}, q \neq 0 \right\}$$
  - $$\mathbb{R}$$, the reals.
- Set theory
  - $$\Omega$$, the universal set
  - $$A \cup B = \{x \in \Omega \vert x \mid x \in A \vee x \in B\}$$
  - $$A \cap B = \{x \in \Omega \vert x \mid x \in A \wedge x \in B\}$$
  - $$A^C = \{x \in \Omega \vert x \mid x \notin A\}$$
  - $$A \setminus B = \{x \in \Omega \vert x \mid x \in A \wedge x \notin B\}$$
    - Can also be written as $$A \setminus B = A \cap B^C$$
  - $$\bigcup_{j=1}^k A_j = A_1 \cup A_2 \cup ... \cup A_k = \{ x | \exists j, x \in A_j \}$$
  - $$\bigcap_{j=1}^k A_j = A_1 \cap A_2 \cap ... \cap A_k = \{ x | \forall j, x \in A_j \}$$
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
    - $$g = f^{-1}$$

Euclidean spaces and vectors










