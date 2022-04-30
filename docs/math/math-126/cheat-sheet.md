---
layout: default
title: Cheat Sheet
parent: MATH 126
grand_parent: Mathematics
nav_order: 100
---

# Cheat Sheet
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

## Linear Algebra

### Fundamentals, Operations, Products

The dot product is defined as follows.

$$\langle a_1, a_2, ..., a_n \rangle \cdot \langle b_1, b_2, ..., b_n \rangle = a_1 b_1 + a_2 b_2 + ... + a_n b_n$$

If the dot product between two vectors $$\vec{a}$$ and $$\vec{b}$$ is 0, then the two vectors are orthogonal to each other.

$$\vec{a} \cdot \vec{b} = \| \vec{a} \| \| \vec{b} \| \cos \theta \implies \cos \theta = \frac{\vec{a} \cdot \vec{b}}{\| \vec{a} \| \| \vec{b} \|}$$

A vector is defined $$\vec{a} = \langle a_1, a_2, a_3 \rangle$$. $$\alpha, \beta, \gamma$$ are the angles $$\vec{a}$$ makes with the $$x, y, z$$ axes. The following are true:

$$\cos \alpha = \frac{a_1}{\| \vec{a} \|}$$

$$\cos \beta = \frac{a_2}{\| \vec{a} \|}$$

$$\cos \gamma = \frac{a_3}{\| \vec{a} \|}$$

The projection of a vector $$\vec{a}$$ onto $$\vec{b}$$ is $$\text{proj}_{\vec{b}} \vec{a}$$, defined as follows.

$$\text{proj}_{\vec{b}} \vec{a} = \text{comp}_{\vec{b}} \vec{a} \left( \frac{\vec{b}}{\| \vec{b} \| } \right)$$

$$\text{comp}_{\vec{b}} \vec{a} = \frac{\vec{a} \cdot \vec{b}}{\| \vec{b} \|}$$

The cross product between two three-dimensional vectors is defined as follows.

$$\langle a_1, a_2, a_3 \rangle \times \langle b_1, b_2, b_3 \rangle = \langle a_2 b_3 - a_3 b_2, a_3b_1 - a_1 b_3, a_1b_2 - a_2b_1 \rangle$$

The cross product of two vectors $$\vec{a}$$ and $$\vec{b}$$ is orthogonal to both $$\vec{a}$$ and $$\vec{b}$$.

The magnitude of the cross product is the area of a parallelogram formed by the two vectors $$\vec{a}$$ and $$\vec{b}$$.

If the cross product of two vectors is zero, they are parallel.

### Geometric Entities
A line can be defined using a vector equation: $$\vec{r} = \vec{r}_0 + t \vec{v}$$. It can be rewritten in parametric equations and symmetric equations.

A plane is defined by $$a(x - x_0) + b(y - y_0) + c(z - z_0)$$ for some point $$(x_0, y_0, z_0)$$ and a normal vector $$\langle a, b, c \rangle$$.

Clinders are formed by two-dimensional cross-sections extended across a free variable.

Quadric surfaces are formed by second-degree equations across three variables. To identify a quadric surface, take traces in each dimension.

## Vector Calculus

To take the derivative of a vector, simply take the element-wise derivative. All differentiation rules for single-variable differentiation apply.

Arc length is given by $$L = \int_a^b \| r'(t) \| dt$$, where $$r(t)$$ is the position vector, $$r'(t)$$ is the velocity vector, and $$\| r'(t) \|$$ is the speed. That is, distance can be computed as the integral of speed.

You can parametrize a curve with respect to arc length. Derive an equation for arc length $$s$$ equal to some function of $$t$$, then solve for $$t$$ in terms of $$s$$ and substitute in the original position vector equation.

Curvature is defined by $$\kappa = \frac{\| \vec{r}'(t) \times \vec{r}''(t) \| }{\| r'(t) \|^3}$$.

Tangent, Normal, and Binormal vectors:

$$\vec{T}(t) = \frac{\vec{r}'(t)}{\| \vec{r}'(t) \|}$$

$$\vec{N}(t) = \frac{\vec{T}'(t)}{\|\vec{T}'(t)\|}$$

$$\vec{B}(t) = \vec{T}(t) \times \vec{N}(t)$$

- The normal plane is spanned by the normal and binormal vectors. The normal vector of the normal plane is the unit tangent vector $$\vec{T}$$.
- The osculating plane is spanned by the unit tangent vector and the normal vectors. The normal vector of the osculating plane is the binormal vector.

Motion in Space

$$\vec{v}(t) = \vec{v}(t_0) + \int_{t_0}^t \vec{a}(u) du$$

$$\vec{r}(t) = \vec{r}(t_0) + \int_{t_0}^t \vec{v}(u) du$$

$$\vec{F}(t) = m \vec{a}(t)$$

$$\vec{a} = a_T \vec{T} + a_n \vec{N}$$

$$\vec{a_T} = \nu' = \frac{\vec{r}'(t) \cdot \vec{r}''(t)}{\| \vec{r}'(t) \| }$$

$$\vec{a_N} = \kappa \nu^2 = \frac{\| \vec{r}'(t) \times \vec{r}''(t)\|}{\| \vec{r}'(t) \|}$$

## Partial Derivatives
To take the partial derivative of a function with respect to some variable $$k$$, treat all other variables as constants and differentiate w.r.t. $$k$$.

Clairaut's Theorem. $$f_{xy} (a, b) = f_{yx}(a, b)$$ for two continuous functions $$f_{xy}$$ and $$f_{yz}$$.

Laplace's equation: $$\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} = 0$$. SOlutions to Laplace's equation are harmonic functions.

The tangent plane to the surface $$S$$ at a point $$P$$ is the plane containing both tangent lines.

$$z - z_0 = f_x(x_0, y_0) (x - x_0) + f_y(x_0, y_0) (y - y_0)$$

To find critical values, find points at which all partial derivatives are 0 or one partial derivative does not exist. To determine the nature of the critical value, find $$D$$ as defined below and follow the algorithm.

$$D(a, b) = f_{xx}(a, b) f_{yy}(a, b) - \[f_{xy} (a, b)\]^2$$

1. If $$D > 0$$, then $$f(a, b)$$ is a local minimum or maximum.
  1. If $$f_{xx}(a, b) > 0$$, then local minimum.
  2. If $$f_{xx}(a, b) < 0$$, then local maximum.
2. If $$D < 0$$, then not a local maximum or minimum (saddle point).
3. If $$D = 0$$, then inconclusive.












