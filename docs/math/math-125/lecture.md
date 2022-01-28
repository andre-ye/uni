---
layout: default
title: Lecture Notes
parent: MATH 125
grand_parent: Mathematics
nav_order: 1
---

# Lecture Notes

MATH 125
{: .fs-6 .fw-300 }

---

## Navigation
Week 1
- [Monday - Antiderivatives and Syllabus](#week-1-monday---antiderivatives-and-syllabus)
- [Wednesday - Area and Riemann Sums](#week-1-wednesday---area-and-riemann-sums)
- [Friday - Introduction to Integrals](#week-1-friday---introduction-to-integrals)

Week 2


---


## Week 1 Monday - Antiderivatives and Syllabus

### Exams
- Two midterms; not that much time in between midterms.
- Standard calculator and 2-sided cheat sheet is allowed.
 
### Assignments
- Homework is due on Tuesdays at 11:00 PM.
- Quizes are between 9 AM and 11 AM on WebAssign based on the homework. These are 30 minutes. No makeups or quizzes are granted. Relatively short - designed to be completed in 20 to 30 minutes.
  - Material for Quizzes on Tuesday are the same as homework due that Tuesday.
- Worksheets are given during Thursday section with the TA. These are designed to give an opportunity to work on more complex problems. Graded on completion basis.

### Class Administrative
- Lectures will generally be recorded

### 4.9: The Antiderivative
- You are familiar with a derivative; the antiderivative is the 'opposite'

> **Definition**: A function $$F(x)$$ is an *antiderivative* of a function $$f(x)$$ is $$F'(x) = f(x)$$ for al $$x$$.

- Computing the antiderivative is much more difficult than taking the derivative
- Suppose $$f(x) = x^2$$. We have $$F(x) = \frac{x^3}{3}$$ as the antiderivative, since $$F'(x) = \frac{3x^2}{3} = x^2$$.
- Antiderivatives are not unique. We can always add a constant to $$F(x)$$ and it will still be a valid antiderivative. For this reason when finding antiderivatives we always use $$+C$$.
- See Table 2 in Section 4.9 for common antiderivatives. These come from the usual differentiation rules.
- Finding the antiderivative by inspection will only work in a minoirty of cases.
- If we have information about the antiderivative, like the value for an input, we can find the exact antiderivative instead of using a general rule.

---

## Week 1 Wednesday - Area and Riemann Sums
Last time, we found antiderivatives by inspection.

> **Example.** *A particle moves along a line such that its velocity at time $$t$$ is given by $$v(t) = 2\sin t + \frac{1}{1+t^2}$$. Find its position $$s(t)$$ at time $$t$$ if $$s(0)=5$$*. We know that $$s'(t) = v(t)$$; we need to compute the antiderivative of $$v(t)$$: $$s(t) = -2\cos t + \tan^{-1} t + C$$. We have that $$s(0)$$ with $$C=0$$ is $$-2$$. For $$s(0)=5$$, $$C=7$$.

How do we find the area of a region with curved sides? We will approximate it with rectangles. To improve the approximation, we make the rectangle smaller; as we take the limit of the rectangle side length towards zero, we obtain the true area.

> **Example.** Find the area $$A$$ of the region below the parabola $$y=x^2$$ between $$x=0$$ and $$x=1$$. Divide into rectangles and calculate by right point: $$R_5 = \frac{1}{5}\left(\frac{1}{5}\right)^{2}+\frac{1}{5}\left(\frac{2}{5}\right)^{2}+\frac{1}{5}\left(\frac{3}{5}\right)^{2}+...$$. Since $$x^2$$ is increasing, $$A < R_5$$. 

We can also obtain an underestimate by calculating rectangles by the left point: $$L_5 = \frac{1}{5}\left(\frac{0}{5}\right)^{2}+\frac{1}{5}\left(\frac{1}{5}\right)^{2}+\frac{1}{5}\left(\frac{2}{5}\right)^{2}+...$$. We can obtain a good estimate with $$\frac{L_5 + R_5}{2}$$.

We can divide the function into $$n$$ rectangles:

$$R_n = \sum_{i = 1}^n \frac{1}{n} \cdot \left(\frac{i}{n}\right)^2$$

To find the exact area, we need to let the number of rectangles go to infinity:

$$\lim_{n\to\infty} \sum_{i = 1}^n \frac{1}{n} \cdot \left(\frac{i}{n}\right)^2$$

When taking the limit, we have $$A = \frac{1}{3} = \lim_{x\to\infty} R_n = \lim_{n\to\infty} L_n$$.

**Generalizing Riemann Sums**: given a function $$f(x)$$, the area under the curve from interval $$[a, b]$$ is...

$$R_n = \lim_{n\to \infty} \sum_{i = 1}^n f(x_i) \cdot \Delta x$$

...calculated using subintervals of $$\Delta x = \frac{b-a}{n}$$ and $$x_i = a + i \cdot \Delta x$$ for $$0 \le i \le n$$ ($$x_0 = a$$, $$x_n = b$$).

Alternatively, we can use $$x_i^*$$ to indicate any sampling method, like taking the middle, left, or right height. Regardless of the method utilized, as $$n\to\infty$$ all sampling methods converge to the same true area $$A$$.

$$A = \lim_{n\to \infty} \sum_{i = 1}^n f(x_i^*) \cdot \Delta x$$

---

## Week 1 Friday - Introduction to Integrals
- Current plan is to have in classes next week (1/10).
- Lectures and notes will be published.
- Sections should be in-person but may be online.
- Last time: we had a curve $$y=f(x)$$ and approximated area under the curve.
- Subdivided interval from $$a$$ to $$b$$ into several smaller intervals, parametrized by $$n$$. The length is thus $$\Delta x = \frac{b-a}{n}$$. 
- Choose a sample point $$x_i^*$$ from the $$i^{\text{th}}$$ subinterval. Evaluate $$f(x_i^*)$$; this is the rectangle height.

$$\sum_{i = 1}^n f(x_i^*) \Delta x$$

- If you know your speed is constant, you multiply velocity by time to obtain distance.

**Definite integral of $$f(x)$$ from $$a$$ to $$b$$ is the limiting value of the Riemann sums.**

$$\int_a^b f(x) dx = \lim_{n\to\infty} \sum^n_{i=1} f(x_i^*) \Delta x$$

> "the integral of $$f(x) dx$$ from $$a$$ to $$b$$"

Components:
- $$f(x)$$ is the integrand
- $$dx$$ is a very small area (the $$\Delta x$$)

**The integral is a number** (not a function).

The units of an integral is given by

$$(\text{units of }f(x)) \cdot (\text{units of } x)$$

If the bounding function $$f(x)$$ goes below the $$x$$-axis in $$[a, b]$$, negative area will be considered; thus the integral evaluates **signed/net** area.

Next week - will discuss relationship between antiderivative and bounding function; Fundamental Theorem of Calculus.

---

## Week 2 Monday - Integral Properties and Fundamental Theorem of Calculus
- Definite integrals

$$\int_a^b f(x) dx = \text{signed/net area bounded by } y = f(x) \text{ and the } x\text{-axis}$$

- The definite integral is a number with units, given by the units of $$x$$ multiplifed byt eh units of $$f(x)$$
- The area of the rectangle is approximately equal to $$f(x) \cdot \Delta x$$.
- You can also write the smaller number on top and the larger number on bottom; if we switch the limits of integration, we measure 'backwards' and this introduces a negative sign.

$$\int_b^a f(x) dx = -\int_a^b f(x) dx$$

$$\int_a^a f(x) dx = 0$$

$$\int_a^b f(x) dx + \int_b^c f(x) dx = \int_a^c f(x) dx$$

$$\int_a^b (f(x) + g(x)) dx = \int_a^b f(x) dx + \int_a^b g(x) dx$$

$$\int_a^b c f(x) dx = c \int_a^b f(x) dx$$

$$f(x) \ge g(x); \int_a^b f(x) dx \ge \int_a^b g(x) dx$$

$$m \le f(x) \le M \text{ for all } a \le x \le b; m(b-a) \le \int_a^b f(x) dx \le M(b-a)$$

- You cannot separate products or quotients of integrals naively.

**Fundamental Theorem of Calculus**
*How are derivatives and integrals related?* They are inverses of one another. Taking the derivative of the integral of a function should yield the original function.

We want to integrate a function and be able to get another function out. 

For a function $$f(x)$$, let $$g(x) = \int_a^x f(t) dt$$. $$x$$ is the upper limit.

> Important: do not use the same variable in the integrand as in the limits.

$$g'(x) = f(x)$$

**Theorem - Fundamental Theorem of Calculus, Part I.**

> Let $$f$$ be a continuous function on $$[a, b]$$ and let $$g(x) = \int_a^x f(t) d(t)$$ for  $$a \le x \le b$$. Then $$g(x)$$ is continuous and differentiable on $$[a, b]$$ with $$g'(x) = f(x)$$. $$g(x)$$ is an *antiderivative* of $$f(x)$$. 


> Suppose $$g'(x) = c$$. This means that increasing $$x$$ by a small value $$h$$ increases $$g(x)$$ by about $$ch$$.


> When we add part to the function $$f(x)$$'s area, we have a new sliver $$g(x + h) - g(x) \approx h f(x)$$. We have $$g'(x) \approx \frac{g(x+h) - g(x)}{h} \approx f(x)$$.

e.g. $$\frac{d}{dx} \int_2^x t^5 dt = x^5$$

e.g. $$\frac{d}{dx} \int_2^{x^2} t^5 dt \frac{d}{dx} g(x^2) = \frac{d}{dx} x^2 \cdot g'(x^2} = 2x \cdot f(x^2) = 2x \cdot (x^2)^5 = 2x''.

---

## Week 2 Wednesday - Evaluating Definite and Indefinite Integrals
- When you add a very small rectangle, the increase in area is approximately the derivative at that point.

**Theorem - Fundamental Theorem of Calculus, Part II.**
> Let $$f$$ be a continuous function on $$[a, b]$$, and let $$F$$ be an antiderivative of $$f$$. Then $$\int_a^b f(x) dx = F(b) - F(a)$$.

Example:

$$\int_0^\pi \sin x dx = -\cos x |^\pi_0 = (-\cos \pi) - (-\cos 0) = 1 + 1 = 2$$

Indefinite Integrals
- A general antiderivative of a function.
- We use the indefinite integral notation for general antiderivatives.

$$\int f(x) dx = F(x)$$

Example:

$$\int (x^3 + \sin x) dx = \frac{x^4}{4} - \cos x + C$$

A definite integral is a number, whereas an indefinite integral is a family of functions.

The definite and indefinite integral are related by

$$\int_a^b f(x) dx = \int f(x) dx \BIG]^b_a$$

> "Integrating a rate of change gives the net change."

---

## Week 2 Friday - Substitutions
- Classes will remain online for some more weeks.
- Homework and quiz on Tuesday.
- Indefinite integrals - another name for the general antiderivative. 
- For taking the antiderivatives, there are very simple functions with no simple antiderivative.
- The techniques for computing antiderivatives are much more involved and difficult to apply.
- Analogue of the chain rule for integrals: substitutes.

Take $$\frac{d}{dx} \sin \left(x^2 \right) = \cos (x^2) \cdot \frac{d}{dx} x^2 = \cos (x^2) \cdot 2x$$. Suppose you are asked to compute $$\int 2x \cos(x^2) dx = \int \cos(x^2) \cdot 2x 2x dx$$. We make the substitution $$u = x^2$$. $$du = \frac{du}{dx} \cdot dx = 2x dx$$. We can simply substitute: we have $$\int \cos(u) \cdot du = \sin(u) + C = \sin(x^2) + C$$.

- When using substitutions with definite integrals, redefine the limits of integration to the values of $$u$$ for direct substitution. You need only to calculate the values of $$u$$, instead of working through $$x$$ calculations.
- Choosing the best value of $$u$$ is a bit of an art.


---

## Week 3 Wednesday - Area Between Curves
The first midterm will be in person on Thursday, January 27th. It will cover content through section 6.2.

You may choose not to take the exam and replace your midterm 1 grade with the average of your Midterm 2 and Final.

- Any problem that requires splitting into several small pieces and adding them up can be likely solved with integrals.
- Consider an area that lies between two curves $$f(x)$$ and $$g(x)$$ in the interval $$[a, b]$$. The area of the region is $$\int_a^b f(x) - g(x) dx$$. (Relatively straightforward but only for straight-sided.)
- Given a question like *find the area bounded between the parabola $$y = x^2$$ and the line $$y = x+2$$*, you need to find the intersections yourself (i.e. by finding the solutions to $$x^2 = x+2$$).
- Sometimes, you need to separate the area into several pieces. e.g. *Find the total area between $$y = x^3 - x$$ and $$y = x$$.* Find the points of intersection, but you cannot simply integrate over the entire range. Which function tops and which function bottoms switches throughout the interval (i.e. you have vers functions). Separate into intervals where one function consistently tops the other and add ares.
- Total area generally means absolute value.
- Sometimes, it is easier to measure *horizontal strips*; we integrate over $$y$$.
 - e.g. Find the area between $$x = y^2 - 1$$ and $$x = -2y^2 + 2$$.

---

## Week 3 Friday - Volume
- Use integration to compute volumes.
- To compute area, we find the volume of each slice. To compute volume, we cut into cross-sections and sum each up.
- Compute the area of each slice and add the areas together.

$$\text{Volume of a slice at } x \approx A(x) \cdot \Delta x$$

- Express as a limit of a Riemann sum.
- Volume is $$\int_a^b A(x) dx$$, where $$A$$ is the area of a cross-section at $$x$$.

> Example: Find the volume of a sphere of radius $$r$$. We know that the radius is $$r$$, meaning that the distance between any point on the surface and the center is $$r$$. We have the radius of a cross section at $$x$$ as $$\sqrt{r^2 - x^2}$$. The area is $$A(x) = \pi (r^2 - x^2)$$. To find the volume, we integrate $$\int_{-r}^r \pi(r^2 - x^2) dx = \int_{-r}^r \pi r^2 - \pi x^2 dx = \pi r^2 x - \frac{pi}{3} x^3 \|_{-r}^r$$.

> Example: Find the volume of a square pyramid whose base is $$L \times L$$ and whose height is $$h$$. The area for a certain height $$h$$ is $$\frac{l}{L} = \frac{z}{h} \to A(z) = \frac{L^2 z^2}{h^2}$$. The volume is thus given by $$\int_0^h \frac{L^2 z^2}{h^2} dz = \frac{L^2}{h^2} \cdot \frac{z^3}{3} \|^h_0 = \frac{1}{3} L^2 h$$.

- A common type of solid is a solid of revolution forme dby rotating a region around an axis.
- Use the 'washer method' to compute the area.

> Example: Find the volume of a solid formed by rotating the region between $$y = x^2$$ and $$y = 4$$ about the $$y$$-axis. The area of a cross-section perpendicular to the $$y$$-axis is given by $$A(y) = \pi y$$. We obtain the volume by finding $$\int_0^4 \pi y dy$$.

---

## Week 4 Monday - Cylindrical Shell Method
- When we have items rotated around an axis, we can find disks perpendicular to the axis and integrate along that axis.

> Example. Let $$R$$ be the region boudned by $$y = 0$$, $$y = x$$, and $$x^2 + y^2 = 9$$. What is the volume of the solid formed by rotating $$R$$ around the $$y$$-axis. We know $$x^2 + y^2 = 9$$, so we have $$x = \sqrt{9 - y^2}$$. We have the area of a disk at $$y$$ as $$\pi \left(9 - y^2 - y^2 \right)$$. Integrate this from $$0$$ to $$\sqrt{\frac{9}{2}}$$ (the intersection between $$x^2 + y^2$$ and $$y = x$$).

- To find volumes using the disk or washer method, you need to find the limits of integration and ideally integrate slices perpendicular to the axis of revolution.
- The cylindrical shells method allows us to compute volumes along the axis perpendicular to the axis of revolution.
- We take cylindrical shells/tubes and 'unroll' each to yield a sheet with area $$2\pi r\cdot h \cdot \Delta r$$. The volume of the shell is approximately $$2\pi r \cdot h$$ given that $$\Delta r$$ is negligible.
- One of the methods is sometimes easier to compute than the other.

---

## Week 4 Wednesday - Midterm Review
- What to know:
 - Computing definite/indefinite integrals, including $$u$$-substitutions
 - Interpretations of integrals as area or net/total change
 - Approximating integrals with Riemann sums
 - The Fundamental Theorem of Calculus, parts 1 and 2
 - Finding areas using integration
 - Finding volumes using the disk/washer method
- Four questions
- Out of 50 points

---

## Week 4 Friday - Work
- Work is a concept from physics - roughly, "the amount of effort you need to put in to accomplish something"
- Technical term: the energy transferred to an object by applying a force over a distance.
- Defined in terms of a force and a distance.
- By Newton's Second Law, force states that to cause a mass $$m$$ to accelerate by $$a$$, one has to apply a force $$F=ma$$.

> Accelerating a 1 kg mass by 1 meter per second squared takes a force of 1 kg per meters squared, or 1 Newton. Common units of force: Newtons, or pounds.


> If a constant force F is applied to an object over a distance $$d$$, the work performed is $$W = Fd$$. Common units of work are joules ($$1J = 1 N \cdot m) or foot-pounds (feet per lb).

> Lifting a 10 pound weight by 5 feet requires doing 50 foot-pounds of work. Lifting a 2 kg mass of Earth (acceleration due to gravity is g = 9.8 metes per second squared) by 3 meters takes $$(2 kg \cdot 9.8 m/s^2) \cdot 3m = 58.8 N\cdot m$$.

- If you are moving an object, the force exerted on the object may change.
- The more you compress a spring, for instance, the greater the force required.
- To find the total work function, we need to integrate across a changing force.
- If the force is not constant, imagine cutting the total distance into small pieces of length, $$\Delta x$$.
 - For each piece, we compute how much work is done.

- Hooke's Law: the amount of force needed to stretch or compress a spring a distance $$x$$ past its natural length si proportional to $$x$$. $$F(x) = kx$$.

> Example: Suppose a spring with 8 pounds of force applied to it stretches by half a foot. How much work is done if we stretch it by an additional foot?

> First, we need to solve for $$k$$. $$8 = k \cdot 0.5 \implies k = 16$$. If the spring is stretched by $$x$$, then to stretch it by $$\Delta x$$ more requires $$16x \times \Delta x$$. The total work is $$\int_\frac{1}{2}^\frac{3}{2} 16x dx = 16 \text{ft-lb}$$.

- If your object is spread out (not just a mass at a single point) like a rope, we can also imagine cutting the rope into individual pieces that is moved an approximate certain distance.









