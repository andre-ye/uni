---
layout: default
title: Textbook Notes
parent: MATH 126
grand_parent: Mathematics
nav_order: 1
---

# Textbook Notes
{: .no_toc }

MATH 126
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

## Chapter 12: Vectors and the Geometry of Space

### 12.1: Three-Dimensional Coordinate Systems
- Three axes form a three-dimensional space.
- The three-dimensional space is divided into octants.
- If we drop from $$P$$ to some plane, it is the projection of $$P$$ onto the $$xy$$-plane.
- The Cartesian product $$\mathbb{R} \times \mathbb{R} \times \mathbb{R} = {(x, y, z) \| x, y, z \in \mathbb{R}}$$ is the set of all ordered triples of real numbers; denoted $$\mathbb{R}^3$$.

#### Surfaces
{: .no_toc }

- If $$k$$ is constant, then:
  - $$x = k$$ represents a plane parallel to the $$yz$$-plane
  - $$y = k$$ represents a plane parallel to the $$xz$$-plane
  - $$z = k$$ represents a plane parallel to the $$xy$$-plane
- Circles and cylinders, free restirction over axes

#### Distance and Spheres
{: .no_toc }

The distance formula $$\|P_1P_2\|$$ between two points $$P_1 (x_1, y_1, z_1)$$ and $$P_2 (x_2, y_2, z_2)$$ is

$$\|P_1P_2\| = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2 + (z_2 - z_1)^2}$$

- This formula is a natural extension of the Pythagorean theorem in two dimensions.
- The equation of a sphere with center $$C$ (h, k, l)$$ and radius $$r$$ is

$$(x - h)^2 + (y - k)^2 + (z - l)^2 = r^2$$

### 12.2: Vectors
- Vector: used to indicate a quantity that has both magnitude and direction. Often represented by an arrow or directed line segment. Vectors are denoted as $$\vec{v}$$.
- A displacement vector $$v$$ has initial point $$A$$ and terminal point $$B$$, which can be notated as $$\mathbf{v} = \vec{AB}$$.
- To combine vectors, simply add the changes.
- You can multiply a vector by a scalar $$c$$.

**Components**
- If we place the initial point of a vector $$a$$ at the origin of a rectangular coordinate system, the terminal point of $$a$$ has a coordinate of the form $$(a_1, a_2)$$ or $$(a_1, a_2, a_3)$$.
- Coordinates are the components of $$\mathbf{a}$$. We can write these as

$$\mathbf{a} = \langle a_1, a_2 \rangle$$

$$\mathbf{a} = \langle a_1, a_2, a_3 \rangle$$

- This represents a vector rather than a point.
- Different representations of a vector have the same direction and magnitude but may be in different positions. The position with the beginning point at the origin is the posiiton vector of a point.
- The magnitude or length of a vector is the length of any of its representations, and is denoted as $$\| \vec{v} \|$$.
- An $$n$$ dimensional vector is an ordered $$n$$-tuple.
- Basis vectors: 
  - $$\vec{i} = \langle 1, 0, 0, \rangle$$
  - $$\vec{i} = \langle 0, 1, 0, \rangle$$
  - $$\vec{i} = \langle 0, 0, 1, \rangle$$
- Any vector can be expressed as a linear sum of basis vectors.
- Unit vector: a vector whose length is 1. In general if $$\vec{a} \neq 0$$, then the unit vector that has the same direction as $$\vec{a}$$ is $$\vec{u} = \frac{\vec{a}}{\|\vec{a}\|}$$. 

**Applications**
- Vectors are useful in many aspects of physics and engineering.
- Force is represented by vector because it obht has magnitude and direction.

### 12.3: The Dot Product
- Can we multiply two vectors such that the product is a useful quantity?

> If $$\vec{a} = \langle a_1, a_2, a_3 \rangle$$ and $$\vec{b} = \langle b_1, b_2, b_3 \rangle$$, then the dot product $$\vec{a} \cdot \vec{b}$$ is

$$\vec{a} \cdot \vec{b} =  a_1 b_1 + a_2 b_2 + a_3 b_3$$

- The result of a dot product is not a vector, but a scalar. The dot produce is sometimes called the scalar product or inner product.

- Properties of the dot product:
  1. $$\vec{a} \cdot \vec{a} = \|\vec{a}\|^2
  2. $$\vec{a} \cdot \vec{b} = \vec{b} \cdot \vec{a}$$
  3. $$0 \cdot \vec{a} = 0$$
  4. $$\vec{a} \cdot (\vec{b} + \vec{c}) = \vec{a} \cdot \vec{b} + \vec{a} \cdot \vec{c}$$
  5. $$(c\vec{a}) \cdot \vec{b} = c(\vec{a} \cdot \vec{b}) = \vec{a} \cdot (c\vec{b})$$
- The dot product can be interpreted in terms of the angle between $$\vec{a}$$ and $$\vec{b}$$:

> If $$\theta$$ is the angle between the vectors $$\vec{a}$$ and $$\vec{b}$$, then

$$\vec{a} \cdot \vec{b} = \|\vec{a} \| \| \vec{b} \| \cos \theta$$

> If $$\theta$$ is the angle between the nonzero vectors $$\vec{a}$$ and $$\vec{b}$$, then

$$\cos \theta = \frac{\vec{a} \cdot \vec{b}}{\| \vec{a} \| \| \vec{b} \|}$$

- Two nonzero vectors are perpendicular/orthogonal if the angle between them is $$\theta = \frac{\pi}{2}$$. Two nonzero vectors ar eorthogonal if and only if their dot product is 0.


**Direction Angles and Direction Cosines**













