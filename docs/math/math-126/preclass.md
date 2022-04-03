---
layout: default
title: Preclass Notes
parent: MATH 126
grand_parent: Mathematics
nav_order: 3
---

# Preclass Notes
{: .no_toc }

MATH 125
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

## Week 1 Monday (12.1)
- Three-dimensional spaces
- We need an origin - a reference point. Begin with two axes that are perpendicular. The third axis must extend perpendicular to both of the existing axes.
- Right hand rule: helps you determine in which direction a third axis points.
- We can describe every point space with some set of coordinates $$(a, b, c)$$/$$(x, y, z)$$.

- $$\mathbb{R} = (-\infty, \infty)$$ - the set of real unmbers.
- Set notation. All points in 3D form:

$$\mathbb{R} \times \mathbb{R} \times \mathbb{R} = \mathbb{R}^3$$

$$ = {(x, y, z) | x, y, z \in \mathbb{R}$$

- Set theory: {\text{bag of possibilities} | \text{ rule(s)}}$$
- Surfaces: $${(x, y, z) | x, y, z \in \mathbb{R}, z = 3}$$ gives you the $$x-y$$ plane hovering at level $$z = 3$$.
- Three important planes: at $$x = 0, y = 0, z = 0$$.
- Just stating the rule $$z = 3$$ (the equations) is also acceptable.

---

## Week 1 Wednesday (12.2)
- Vector: depicted as an arrow, with a length as its magnitude, an initial point, and a terminal point
- Adding two vectors. The sum of two vectors is the vector from the initial point of one vector to the terminal point of the other vector.
- Scalar multiplication. Scalar - a real number. Preserves parallel properties.
- A position vector is a vector extending from the origin to a specific point.
- Components - number of dimensions of a vector.
- Length/magnitude of a vector can be calculated using Pythagorean theorem
- Standard basis vectors - unit vectors along the dimensions.
  - You can decompose any vector into a linear sum of the standard basis vectors.

---

## Week 1 Friday (12.3)
- Dot product/scalar product/inner product: element-wise weighted sum. For a vector $$\vec{a} = \langle a_1, a_2, ..., a_n \rangle$$ and $$\vec{b} = \langle b_1, b_2, ..., b_n \rangle$$, the dot product is $$\vec{a} \cdot \vec{b} = a_1 b_1 + a_2 b_2 + ... + a_n b_n$$.
- The input is a set of vectors, but the output is a scalar. The dot product produces a different mathematical structure.
- $$\vec{v} \cdot \vec{v} = \| \vec{v} \|^2$$

- Theorem: if the angle between two vectors $$\vec{a}$$ and $$\vec{b}$$ is $$\theta$$, then $$ \vec{a} \cdot \vec{b} = \| \vec{a} \| \| \vec{b} \| \cos \theta $$.
  - Alternatively, $$\cos \theta = \frac{\vec{a} \cdot \vec{b}}{\| \vec{a} \| \| \vec{b} \| }$$
- Two vectors are orthogonal if and only if $$\vec{v} \cdot \vec{w} = 0$$.
  - A zero-vector is orthogonal to every other vector.
- Projection - what does some $$\vec{b}$$ do to $$\vec{a}$$?
  - Scalar projection of $$\vec{b}$$ onto $$\vec{a}$$: $$\text{comp}_{\vec{a}} \vec{b} = \frac{ \vec{a} \cdot \vec{b}}{\| \vec{a} \|}$$. This *component* is a real number. Exploits a trigonometric relationship.
  - To obtain the vector projection, scale the vector to a unit vector and multiply by the scalar projection.

---

## Week 2 Monday (12.4, 12.5)
Section 12.4
- The cross-product holds only for three-dimensional vectors.
- Determinant method.
- The resulting vector $$\vec{v} = \vec{a} \times \vec{b}$$ is orthogonal to both $$\vec{a}$$ and $$\vec{b}$$.
- If you swap the order, you will get the negative product.
- $$\| \vec{a} \times \vec{b} \| = \| \vec{a} \| \| \vec{b} \| \sin \theta$$, where $$\theta$$ is the smallest angle between $$\vec{a}$$ and $$\vec{b}$$. This is a good test for parallelity (equals 0).
- Area of parallelogram: $$\| \vec{a} \times \vec{b} \|$$

Section 12.5 Part I
- Vector equations: equations in which we want to equate a vector on the LHS to a vector on the RHS.
- Map a vector to a point
- You can multiply a vector by a scalar and it will remain on the same parallel line.
- Multiply the direction vector - make it shorter, longer, switch the direction, etc.
- If $$t \in \mathbb{R}$$, we get all points on that line.
- $$\vec{r} = \vec{r_0} + t\vec{v}$$
  - $$\vec{r_0}$$ - position vector
  - $$t \in \mathbb{R}$$ - parameter
  - $$\vec{v}$$ - direction vector
- Sometimes, we write vectors vertically instead of horizontally.
- Properties:
  - Two lines are parallel if their direction vectors are parallel
  - Two lines intersect if they have a point $$(x, y, z)$$ in common
  - Two lines are skew if they are not parallel and do not intersect.



