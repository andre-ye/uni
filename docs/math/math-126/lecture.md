---
layout: default
title: Lecture Notes
parent: MATH 126
grand_parent: Mathematics
nav_order: 1
---

# Lecture Notes
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

## Week 1 Monday - Syllabus and Course Introduction
- Canvas holds all the information in the course.
- Preferrred way of communicating - Ed
- In-class work counts 3% of the total grades. If you submit 80% of in-class, you will get full credit for that category.
- Quizzes are demonstrations of conceptual understandings with relatively simple questions. Taken during Thursday quiz sections.
  - You must pass every quiz.
  - You can retake quizzes up to 3 times.
- Homework
  - 10% of the homework will be dropped. Indirectly raises the homework grade.
  - You can request extensions with no penalty for every assignment. However, it needs to be done 17 days within the original due date. Two weeks and three days = 17 days to complete the homework.
- Midterms
  - APril 21st, May 19th
  - Need to take both midterms
- Final exam
  - Common final exam - 5:00 to 7:50 PM on Saturday in Guggenheim
- Worksheets - there are no official worksheets in Math 126.
  - There are worksheets available from Dr. Loveless that we will work on during quiz section.
- Grades
  - 2.0: submit all preclass reflections and have an average of at least 70%. You must pass every quiz.
- Median will be set to 2.9. 50% or less will be a 0.


Course Content
- 126 in the beginning is reiminiscent of 124.
- We will expand many of the tools in 126 in three-dimensions.
- Derivatives and integration in higher-dimension functions.
- For two weeks, we will talk about Taylor polynomials and Taylor series.

Coordinate Systems and Vectors
- All axes must be perpendicular. We will determine a $$z$$ axis perpendicular to an $$x$$ and $$y$$.
- By convention, there is no freedom. Right hand rule - start with fingers in the $$x$$ and move towards the $$y$$-axis. The thumb points in the $$z$$ axis.
- The origin is the point at which the three axes intersect.
- You can decide to put to the origin anywhere in the space you please. You make a decision and live with that - all equations are in reference to the origin.
- In three dimensions, we have eight segments/sectors - *octants* (as opposed to quadrants in two dimensions).
- We want to use the coordinate system to describe a variety of geometric entities.
- Points - we can describe any point in the coordinate system using $$(a, b, c)$$. We always write in the $$(x, y, z)$$ order.
- Vector - a quantity with a direction and a magnitude.
  - Often represented as arrows.
  - Vectors with the same direction and magnitude are the same, regardless of their position in space.
  - A vector is only something that is applied.
- To indicate, you can use $$\vec{u}$$ or a bolded $$u$$.
  - $$\vec{u} = \langle 2, 4 \rangle$$

---

## Week 1 Wednesday
- Think about sets as bags upon which to put stuff in.
- Give the form of the elements put in, followed by a vertical line ('such that', 'which hold') and a rule. 
- The dot product is a scalar.
- The dot product and the Pythagorean theorem are both good tests for orthogonality.

---

## Week 1 Friday
- Dot product has a lot of nice features, especially

$$\vec{v} \cdot \vec{w} = \| \vec{v} \| \| \vec{w} \| \cos \theta$$

> $$\theta is the smaller angle between two vectors when their initial points meet.

- Projection. Magnitude/lnegth of the projection is the component. Shadow of a vector onto $$\vec{a}$$.

> *Question.* Consider the triangle with corners at $$A (0, 0, 1)$$, $$B(1, 1, 3)$$, and $$C(-1, 2, 4)$$. To the nearest degree, find the angle at $$A$$ in the triangle $$BAC$$.

> *Approach*. Let us compute $$\vec{AB}$$ and $$\vec{AC}$$. We know that $$\vec{AB} = \langle 1, 1, 2 \rangle$$ and $$\vec{AC} = \langle -1, 2, 3 \rangle$$. Let's use the dot product $$\vec{AB} \cdot \vec{AC} = \| \vec{AB} \| \| \vec{AC} \| \cdot \cos \theta$$. We have $$7 = \sqrt{6 \cdot 14} \cdot \cos \theta \implies \cos \theta = \frac{7}{\sqrt{6 * 14}} \implies \theta \approx 40^\circ$$.

- Projections - the shadow doesn't care about the vector it is being projected on, but rather the direction - that's it. 

---

## Week 2 Monday
- Problem: $$\langle 1, 0, 1 \rangle \times \langle 0, 1, -2 \rangle$$
  - $$\langle 0 - 1, 0 - (-2), 1 - 0 \rangle = \langle -1, 2, 1 \rangle$$
- The cross product reveals a fundamental/deep structure within $$\mathbff{R}^2$$.
  - Related to Lie-algebras.
  - $$(\mathbb{R}^3, \times, +)$$ - an algebra. An axiom list.
  - Abstract algebra
- Interpretation - the output is orthogonal/perpendicular to both vectors. 
- The length of the cross product is the area of a parallelogram formed by the two vectors; dividing by two gives a formula for the area of a triangle.
- Find line equations when two points are given, when one point and a direction is given, and other parallel, orthogonal, etc. features are given.


---

## Week 2 Wednesday
- Quiz tomorrow, in-person.
- Lines will not be relevant on the quiz tomorrow, topic will cover up to projection.
- Line: you need a point (position vector, $$A(1, 1, 2) \to \vec{r}_0 = \langle 1, 1, 2 \rangle$$) and a direction vector.

$$\vec{r} = \vec{r}_0 + t \cdot \vec{v}, t \in \mathbb{R}$$

- You can write out individual parametric equations by reading out the data from the vector equation component-wise.
- By solving for $$t$$ in each of the parametric equations and setting equal to each other, you obtain symmetric form.
- When switching back from symmetric form to parametric form, you need to introduce the $$t$$ yourself.
- Lines, two dimensions - need one equality. Lines, three dimensions - need two equalities.
- Planes are quite different from lines. 
- Given a plane, a normal vector is any vector that sticks out in a perpendicular way.
- A plane can be placed in only one way such that it is normal to a given vector. If a normal vector is given, the plane's "direction" is fixed. If another point is given, then the plane's position is fixed too. A normal vector and one point is all you need to determine a plane.
- Find the normal vector of the plane $$x + 2y - z = 0$$. We get $$\langle 1, 2, -1 \rangle$$ by reading off the coefficient - this is the normal vector of the plane.
  - Plane equation: any triple $$(x, y, z)$$ that satisfies the condition given is on the plane.

> **Problem.** Find an equation of a line that is orthogonal to the plane $$3x - y + 2z = 10$$ and passes through the point $$P(1, 4, -2)$$.

> **Solution.** The point given is $$(1, 4, -2)$$; the position vector is thus $$\vec{r}_0 = \langle 1, 4, -2 \rangle$$. The direction vector is the normal vector of the plane. The normal vector is given from the plane: $$\vec{r} = \langle 3, -1, 2 \rangle$$.

> **Problem.** Find the equation for the line of intersection of the planes $$x + y + z = 4$$ and $$10x + y - z = 6$$.
> **Solution.** We begin by solving for $$z$$ and plugging in: $$10x + y - (4 - y - 5x) = 6 \implies 15x + 2y = 10$$. Now,w e can play the plugging-in game! We can set $$x = 0, y = 5$$. We can find $$z$$ by plugigng back: $$z = -1$$. One point can be found as $$(0, 5, -1)$$.The direction vector lies in both planes/is parallel to both planes. *We want to find the vector that is perpendicular to both normal vectors of the plane.* Let $$v$$ be perpendicular to $$\langle 5, 1, 1 \rangle$$ and $$\langle 10, 1, -1 \rangle$$. We can take the cross product $$\langle 5, 1, 1 \rangle \times \langle 10, 1, -1 \rangle = \langle -1 - 1, 10 + 5, 5 - 10 \rangle = \langle -2, 15, -5 \rangle$$.. We get the line equation:

$$\vec{r} = \langle 0, 5, -1 \rangle + t \langle -2, 15, -5 \rangle$$

- To find the line intersection of two given planes, you need to find a point that lies on the line, then find the vector perpendicular to both nromal vectors of the planes.

---

## Week 2 Friday
- Whenever you set up a plane, you always need a point/position vector and a normal vector.
- Planes - $$\langle x, y, z \rangle \cdot$$ normal vector $$ = $$ position vector $$\cdot $$ normal vector.
- Algebraically understanding the perspectives of the shape by taking traces/cross-sections - set a variable to some $$k$$ and simplify. 

---

## Week 3 Monday
- Getting a picture of a space curve.
- Find the path of a space curve that is independent of any time $$t$$, like the symmetric form of a line.
- We lose the information w.r.t. time, but we see the path as a whole.
- Surface of motion - get rid of $$t$$ by substituting with the goal of having one equation in $$x, y, z$$.
- A surface of motion needs only two variables at minimum from $${x, y, z}$$.
- Intersecting objects - we want to come up with a curve. We might have two 3d objects: if you intersect those, you get a curve.
- When we intersect two curves, you need to introduce a different name for the other parameter. Otherwise, you are looking for a collision rather than for an intersection. Set expressions for time in relation to each axis and set equal, then solve for the system of equations.
- Intersecting two surfaces - how can we come up with a curve equation?
  - If there are circles involved ($$a^2 + b^2$$), you can try a trigonometric parametrization ($$x = \cos t$$, $$y = \sin t$$, etc.)
  - Alternatively, try setting $$x=t, y=t, \| z=t$$


> **Problem.** Find the parametric equations that represent the curve of intersection between the surfaces $$x^2 + y^2 = 4$$ and $$z = xy$$.

> **Solution.** $$x = 2 \cos t$$, $$y = 2 \sin t$$, $$z = 4 \cos t \sin t$$.


---

## Week 3 Wednesday - Vector Derivatives and Integrals
- Today - perform calculus with these curves; we can derive and integrate the function.
- Everything goes component-wise; we just take the derivatives and integrals component-wise. In this sense, there is nothing new.
- We need to give a notation to the component-wise derivative. 
- Norm the vector - scale by the length/magnitude of the vector such that it has a magnitude of 1.
- $$T(t) = \frac{r'(t)}{\| r'(t) \| }$$, unit tangent vector (assuming the tangent vector is not a zero vector).
- Three different multiplications - dot product, cross product, scalar product. Each can be a vector in $$t$$.
- Derivative - what rules apply? The product rule works with every product - $$(fg)' = f'g + fg'$$ for any of the defined vector multiplications.
- Distance travelled - measure the length of the curve assuming the curve is traversed only once.

$$\int_a^b \int{(x'(t)^2 + y'(t)^2 + z'(t)^2}$$

- Fact about planes: an arbitrary point $$P \langle x, y, z \rangle \cdot n = \langle \text{point} \rangle \cdot n$$. Originates from $$(\langle x, y, z \rangle - \langle \text{point} \rangle ) \cdot n = 0$$; the difference vector is always orthogonal to the normal vector, thus the dot product is 0.


---

## Week 3 Friday
- Curvature - measure of change in direction over change in distance traveled.
- Arclength $$s(t) = \int_0^t \| r'(t) \|$$
- Reparametrization is too complicated. We can use a different method to compute the curvature.
- $$\frac{1}{\kappa}$$ is the radius of the circle that best fits into the curve at that point.

> **Problem.** Find the curvature of $$\langle t, t^2, t^3 \rangle$$ at $$(1, 1, 1)$$.

$$r'(t) = \langle 1, 2t, 3t^2 \rangle$$

$$r''(t) = \langle 0, 2, 6t \rangle$$

$$r'(t) \times r''(t) = \langle 12t^2 - 6t^2, 0 - 6t, 2 \rangle = \langle 6t^2, -6t, 2 \rangle \rangle$$

$$\| r' \times r'' \| = \sqrt{36t^4 + 36t^2 + 4}$$

Plugging in $$t = 1$$ yields $$14^3$$.

> **Problem.** Find the curvature of $$y = x^4$$.

$$y' = 4x^3$$

$$y'' = 12x^2$$

$$ \kappa = \frac{\| f''(x) \|}{\sqrt{1 + f'(x)^2}^3} = ...$$ 

Use the correct formula!

- Finding minima/maxima without derivatives - analyze relationships between maximization and minimization for relatively simple relationships.

---

## Week 4 Monday
- 5 problems for 50 minutes. It is standard - it will be similar to past midterms.
- Given $$\vec{r}(t)$$, we have the principal unit normal $$\vec{N}(t) = \frac{\vec{r}'(t)}{\| \vec{T}'(t) \|}$$ and the binormal vector $$\vec{B} = \vec{T}(t) \times \vec{N}(t)$$.
- Normal plane - spanned by $$\vec{B}$$ and $$\vec{N}$$; the tangent vector is normal to this plane.

> **Problem.** Find the equation of the normal plane of the curve of intersection of the parabolic cylinders $$x = y^2$$ and $$z = x^2$$ at the point $$(1, 1, 1)$$.

> **Solution.** Let's begin by finding the curve. Let $$y = t$$. $$x = t^2$$; $$z = x^2 = t^4$$. Thus, the intersection is given by the curve $$\vec{r}(t) = \langle t^2, t, t^4 \rangle$$. The desired point of intersection occurs at $$t = 1 \implies (1, 1, 1)$$. The derivative of the curve is $$\vec{r}'(t) = \langle 2t, 1, 4t^3 \rangle$$. The tangent vector is $$\langle 2, 1, 4 \rangle$$. This is normal to the normal plane. Thus, the plane equation is $$2(x - 1) + (y - 1) + 4(z - 1) = 0$$.

- The normal vector points in the direction of the circle 'fitted' inside the curve.

---

## Week 4 Wednesday
- Midterm - tomorrow during quiz section, 50 minutes, 5 problems, covering 12.1 to 13.2. Credit will only be given if work is shown.
- There will be no vector calculus.


> **Problem.** Consider the plane $$P$$ that contains the point $$(1, -1, 2)$$ and is orthogonal to the line $$L: {x = -3t, y = 2+7t, z=5-t}$$.

> **Solution.** The normal vector to the plane is $$\langle -3, 7, -1 \rangle$$. The plane equation is thus $$-3(x-1) + 7(y + 1) - (z - 2) = 0$$.

> **Problem.** Find two different surfaces of motion for $$\vec{r} = \langle 5 \cos t, -3, 5 \sin t$$.

> **Solution.** $$x^2 + z^2 = 25$$ and $$y = -3$$.

---

## Week 4 Friday
- Acceleration decomposition: how much does acceleration change the direction with which I am currently moving (i.e. the tangent vector) and the orthogonal normal vector? An intuitive method of decomposition.
- $$\vec{a} \cdot \vec{T} = \vec{a}_\vec{T} = \nu'$$ - derivative of the speed
- $$\vec{a} \cdot \vec{N} = \vec{a}_\vec{N} = \kappa \nu^2$$

> **Problem.** Compute the tangential and normal components of acceleration of a particle traveling by the position function $$\vec{r} = \langle t^2, t^2, t^3 \rangle$$.

> **Solution.** We have that $$\vec{r}'(t) = \langle 2t, 2t, 3t^2 \rangle$$ and $$\vec{r}''(t) = \langle 2, 2, 6t \rangle$$. We can then calculate the components.

$$\vec{a}_\vec{T} = \frac{\vec{r} \cdot vec{r}''}{\| vec{r}' \|} = \frac{8t + 18t^2}{\sqrt{8t^2 + 9t^4}}$$

$$\vec{a}_\vec{N} = \frac{\| vec{r}' \times vec{r}''}{\| vec{r}' \|} = \frac{6t\sqrt{2}}{\sqrt{6 + 9t^2}}$$

---

## Week 5 Monday
- Functions in two variables - input $$(x, y) \to z$$, $$z \in \mathbb{R}$$.
- Graph of $$f(x, y) \to z$$ is a surface.
- Contour maps

---

## Week 5 Wednesday
- We are interested in a measure of change for each dimension.
- If you are interested in the derivative, simply take the derivative while treating the other dimension as a constant.
- Higher order derivatives - measure concavity by taking the partial derivative of the same dimension twice.
- Clairaut's throerem - it does not matter in which order you take the partial derivatives. It has commutativity.
- Given a surface, if you zoom in to a point $$(x_0, y_0, z_0)$$, the surface will seem flat like a plane; this is the tangent plane.

$$z - z_0 = f_x (x_0, y_0) (x - x_0) + f_y (x_0, y_0) (y - y_0)$$

- Implicit partial differentiation: the $$z$$ is entangled with $$x$$ and $$y$$. We cannot extract it as $$z = ...$$. Treat $$z$$ as a function of whatever independent variable.
- Linear approximation from a tangent value.


---

## Week 5 Friday
- The tangent plane contains all of the tangent lines. You can obtain the tangent plane equation just from two tangent vectors. The two direction vectors in each plane can help us understand the tangent plane.
- We can therefore check extrema just using $$f_x = 0$$ and $$f_y = 0$$.
- Second derivative test - $$D = f_{xx} (a, b) f_yy(a, b) - f{xy}^2(a, b)$$.

> Find the extrema of $$f(x, y) = 4 + x^3 + y^3 - 3xy$$.

> **Solution.** $$f_x = 3x^2 - 3y$$, $$f_y = 3y^2 - 3x$$. From $$f_x = 0$$, we know that $$y = x^2$$. Plugging this in into $$f_y = 0$$, we know that $$3x^4 - 3x = 0 \iff x \in {0, 1}$$. The two critical numbers are $$x = 0$$ and $$x = 1$$. The two critical points are $$(0, 0)$$ and $$(1, 1)$$.

---

## Week 6 Monday
- If you want to find the absolute minimum and maximum, evaluate all local minima and maxima, as well as boundary points. 

> Consider the function $$x^2 y^2 + x^4$$. Find the absolute minimum and maximum in the fourth quadrant of a circle with radius 4.

> We begin by finding partial derivatives. $$f_x = 2xy^2 + 4x^3 = 0; f_y = 2x^2y = 0$$. $$x = 0$$ or $$y = 0$$. If $$x = 0$$, then for all $$y$$ we have $$f_x = 0$$ and $$f_y = 0$$. $$(0, y)$$ are $$\infty$$ many critical points. We can also use $$y = 0 \to x = 0$$. The minimum value is $$f(0, y) = 0$$. Now we can work with the boundaries. The region is enclosed by $$x = 0, y = 0, x^2 + y^2 = 16 {x>0, y<0}$$. Rewrite the equation for the boundary, plug in, and solve. 

---

## Week 6 Wednesday
- Optimization problems: eliminate one variable for three-variable optimization problems and solve as a function of two variables. Use absolute maxima/minimum rules from there.
- Double integrands - integrate finer and finer, make base areas of the rectangles smaller and smaller. Smooth out the eventual surface via approximation.

---

## Week 6 Friday
- Solve planes for $$z$$ and integrate the difference between them.

---

## Week 7 Monday
- Polar coordinates operate on the same plane, we have the same two axes - just a different description for the very same points.
- When you have a polar curve, try to graph out the relationship between $$r$$ and $$\theta$$.

---

## Week 7 Wednesday
- Integrate over polar coordinates by substituting $$dx dy$$ with $$r dr d\theta$$.
- You can find the area by integrating over $$z = 1$$ with the relevant bounds.
- Sometimes, you have to break up the region into several angle regions to preserve local relationships.

---

## Week 7 Friday
- Break region into rows and columns; find the center of mass of each rectangle; estimate the mass of each rectangle; use the formula for $$n$$ points with limit $$n \to \infty$$.
- Proportionality - desntiy proportional to...

| the y axis | $$\rho(x, y) = kx$$ |
| the x axis | $$\rho(x, y) = ky$$ |
| the origin | $$\rho(x, y) = k \sqrt{x^2 + y^2}$$ |
| the square of the distance to the origin | $$\rho(x, y) = k(x^2 + y^2)$$ |
| inversely proportional to the distance from the origin | $$\rho(x, y) = \frac{k}{\sqrt{x^2 + y^2}}$$ |

- Sometimes, it is more convenient to rewrite the integral in polar coordinates

---

## Week 8 Monday
To review for midterm:
- Curves, curvature, speed/velocity/acceleration
- Binormal and normal vectors will not be assessed
- Critical point identification and classification
- Tangent planes

---

## Week 8 Wednesday
- Bounds - noy necessarily about best bounds, but any bound. 
- Work with worst-case scenarios. Work term-wise.
- 












