---
layout: default
title: Preclass Notes
parent: MATH 126
grand_parent: Mathematics
nav_order: 3
---

# Preclass Notes
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

---

## Week 2 Wednesday (12.5)
- Vector form of a line: $$\vec{r} = \vec{r}_0 + t\vec{v}$$
  - $$\vec{v}$$ is the direction vector
  - $$\vec{r}_0$$ is the position vector.
- Parameter form of a line: $$x = x_0 + ta, y = y_0 + tb, z = z_0 + tc$$
  - You can obtain this simply by multiplying out the parameter form of the line, in which you find each component of the line $$\langle x, y, z\rangle$$.
  - The slopes are the direction vectors, and the $$y$$-intercepts are the position vectors
- Symmetric form of a line if $$a, b, c \neq 0$$:

$$\frac{x - x_a}{a} = \frac{y - y_0}{b} = \frac{z - z_0}{c}$$

  - Obtained by solving each equation for $$t$$. $$t$$ should be the same for points.
- Two lines are parallel if their direction vectors are parallel
- Two vectors intersect if they have a point in common
- Two lines are skew if they are not parallel and do not intersect.
- You can specify a certain $$t$$ range.
- Planes - to find vector equations for all points on a plane.
- Normal vector - any vector that sticks out in a perpendicular function.
- Suppose we are given a normal vector (can be found using the cross product), a point $$R$$, and an unknown point $$P(x, y, z)$$.
  - $$\vec{r} - \vec{r}_0$$ is in the plane.
  - $$\vec{r} - \vec{r}_0$$ is orthogonal to $$\vec{n}$$, the normal vector.
  - Vector form: $$(\vec{r} - \vec{r}_0) \cdot \vec{n} = 0$$.
- If $$\vec{n} = \langle a, b, c \rangle, \vec{r} = \langle x, y, z \rangle, \vec{r}_0 = \langle x_0, y_0, z_0 \rangle$$, then we have

$$a(x - x_0) + b(y - y_0) + c(z - z_0) = 0$$

This is the standard form/scalar equation of the plane.

If two planes are not parallel, they intersect along a line; the acute angle of intersection is the acute angle between their normal vectors.


$$\vec{n}_1 \cdot \vec{n}_2 = \| \vec{n}_1 \| \| \vec{n_2} \| \cos \theta$$

---

## Week 2 Friday (12.6)
- Goal: to become familiarized with 7 three-dimensional shapes and names: cylinders, cones, ellipsoids, paraboloids (2 types), hyperboloids (2 types).
- Two-dimensional shape review
  - Line
  - Parabola: $$ax^2 + by = c$$ or $$ax + by^2 = c$$.
  - Ellipse: $$ax^2 + by^2 = c$$, $$a, b, c > 0$$.
  - Hyperbola: $$ax^2 - by^2 = c$$ or $$-ax^2 + by^2 = c$$.
- Cylinders
  - If one variable is absent, then the graph is a two-dimensional curve extended into the third dimension.
  - Circular cylinder: $$x^2 + y^2 = 1$$
  - Cosine cylinder: $$z = \cos x$$
- Quadratic surfaces
  - Any surface given by an equation involving sum of first and second powers of $$x, y, z$$.
  - $$ax^2 + bx + cy^2 + dy + ez^2 + fz = g$$.
  - To visualize, use traces. Fix one variable at a time and then find the resulting 2D shape. Fix the other two to find the cross-section and find the resulting plane.
- Elliptical/Circular Paraboloid
  - $$\frac{x^2}{a^2} + \frac{y^2}{b^2} = \frac{z}{c}$$
- Hyperbolic Paraboloid
  - $$\frac{x^2}{a^2} - \frac{y^2}{b^2} = \frac{z}{c}$$
  - Traces build together a surface.
- Ellipsoid/Sphere
  - $$\frac{x^2}{a^2} + \frac{y^2}{b^2} + \frac{z^2}{c^2} = 1$$
- Circular/Elliptical Cone
  - $$\frac{x^2}{a^2} + \frac{y^2}{eb2} = \frac{z^2}{c^2}$$
- Hyperboloid of one sheet
  - $$\frac{x^2}{a^2} + \frac{b^2}{e^2} - \frac{z^2}{f^2}= 1$$
- Hyperboloid of two sheets
  - $$\frac{x^2}{a^2} + \frac{b^2}{e^2} - \frac{z^2}{f^2}= 1$$
- In all of the above, replace $$\text{var}$$ with $$(\text{var} - r$$ to shift the future. 

---

## Week 3 Monday (13.1)
- Goals:
  1. Given curve equations, describe what the curve looks like
  2. Given surfaces, find curve equations for the intersections
- We allow for vector components to be expressions of an independent variable $$t$$. You can read out the parametric equations component-wise.
- Space curve. A line is indeed a space curve with a specific term in which the $$t$$ can be factored out.
- How does the space curve look like in the $$x, y, z$$ coordinate systems? There is no $$t$$ in the coordinate system - $$t$$ is just a parameter, a time.
- Eliminate $$t$$ from the equation and find the curve in the $$x, y, z$$ coordinate system.
- Surface of motion - the surface upon which the particle moves. We must have one equation.
- When trigonometry is involved, invoke the Pythagorean theorem. In general algebra, try to use substitution to obtain only one equation involving $$x$$ and/or $$y$$ and/or $$z$$.
- Intersection between a curve and a surface: plug in and solve for times, then plug back into the curve or the surface to obtain points.
- Intersection between two curves: do they intersect? Do they collide?
- Intersecting two surfaces. Begin by finding a parametrization for two surfaces. 
  - Let one of $$x, y, z$$ be equal to $$t$$ and solve the others in terms of $$t$$.
    - Set the most complicated independent variable to $$t$$.
  - For circles/ellipses, try $$x = a\cos t$$ and $$y = b\sin t$$.

---

## Week 3 Wednesday (13.2)
- Derivatives and integrals of vector functions.
- $$t$$ can be interpreted as a time.
- Limit of a vector: take the limits of the individual components of a vector function.
- Derivative of the vector: take component-wise derivative.
- Continuous vector functions
- The unit tangent vector $$\vec{T}(t) = \frac{\vec{r}'t}{\| \vec{r}'(t) \|}$$.
- The tangent vector cannot be a zero-vector.
- The tangent line is parallel to $$\vec{r}'(t)$$ and passes through the point $$\vec{r}(t)$$.
- The integral of a vector is done component-wise.
- The distance traveled on a curve from time $$a$$ to $$b$$ is:

$$\int_a^b \| \vec{r}'(t) \| dt = \int_a^b \sqrt{x'(t)^2 + y'(t)^2 + z'(t)^2} dt$$

- This is arc length if the arc is not traversed multiple times.

---

## Week 3 Friday (13.3a)
- Given a curve, we will assume that its derivative is always continuous.
- Continuity is considered component-wise.
- We can compute the distance along a curve by integrating the magnitude of the derivative.
- Arclength function: feed arc-length with a variable and make the arc length dependent on a variable - the endpoint $$t$$.

$$s(t) = \int_a^b \| \vec{r}'(u) \| du$$

- Fundamental theorem of analysis: $$f(x) = \frac{d}{dx} \int_a^x f(u) du$$.
- $$\frac{s(t)}{dt}$$ is the speed function - distance over time.
- Re-parametrization: describe the same curve with different equations.
- Parametrization in terms of $$s$$: where is the vector location after it has traveled $$s$$ units along the curve?
- $$\vec{T}'$$ measures change in the direction of the curve, represented via $$\vec{T}$$>
- Curvature $$K$$ or $$\kappa$$ - measure of how quickly a curve changes direction at some point.

$$\kappa = \| \frac{d\vec{T}}{ds} \| \approx \| \frac{\text{change in direction}}{\text{change in distance}} \| $$

$$K(t) = \frac{\| \vec{r}'(t) \times \vec{r}''(t) \|}{ \| \vec{r}'(t) \|^3} = \frac{\| \vec{T}'(t)}{\| \vec{r}'(t) \|}$$

- For two dimensional vectors, expand dimensions to the third dimension and simplify.

- $$\frac{1}{\kappa(t)}44 is the radius of the curvature: it is the radius of the circle that best matches the curve, dependent on $$t$$.


---

## Week 4 Monday (13.3b)
- Unit tangent vector for a smooth curve - $$\vec{T}(t)$$.
- Principal unit normal vector/normal vector - $$\vec{N}(t)$$.

$$\vec{N}(t) = \frac{\vec{T}'(t)}{\| \vec{T} '(t) \| }$$

- $$\vec{T}(t)$$ and $$\vec{T}'(t)$$ are orthogonal.
- Binormal vector - $$\vec{B}(t)$$$

$$\vec{B}(t) = \vec{T}(t) \times \vec{N}(t)$$

- We can create a time-dependent coordinate system with three orthogonal axes using these vectors. This is a TNB frame.

$$\| \vec{B}(t) \| = \| \vec{T}(t) \| \cdot \| \vec{N} (t) \| \cdot \sin \theta \implies 1 = 1 \cdot 1 \cdot 1$$

- $$\vec{B}(t)$$ is a unit vector.
- Normal plane - plane spanned by $$\vec{N}(t)$$ and $$\vec{B}(t)$$.
- The normal plane is orthogonal to the unit tangent vector; thus, some point on a curve $$P$$ and the derivative of the curve at $$P$$ can be plugged into the plane equation to define the normal plane.

























