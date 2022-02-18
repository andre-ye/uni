---
layout: default
title: Lecture Notes
parent: MATH 125
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


## Week 1 Monday - Antiderivatives and Syllabus

### Exams
{: .no_toc }

- Two midterms; not that much time in between midterms.
- Standard calculator and 2-sided cheat sheet is allowed.
 
### Assignments
{: .no_toc }

- Homework is due on Tuesdays at 11:00 PM.
- Quizes are between 9 AM and 11 AM on WebAssign based on the homework. These are 30 minutes. No makeups or quizzes are granted. Relatively short - designed to be completed in 20 to 30 minutes.
  - Material for Quizzes on Tuesday are the same as homework due that Tuesday.
- Worksheets are given during Thursday section with the TA. These are designed to give an opportunity to work on more complex problems. Graded on completion basis.

### Class Administrative
{: .no_toc }

- Lectures will generally be recorded

### 4.9: The Antiderivative
{: .no_toc }

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

e.g. $$\frac{d}{dx} \int_2^{x^2} t^5 dt \frac{d}{dx} g(x^2) = \frac{d}{dx} x^2 \cdot g'(x^2} = 2x \cdot f(x^2) = 2x \cdot (x^2)^5 = 2x$$.

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

$$\int_a^b f(x) dx = \int f(x) dx \large]^b_a$$

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

> Example: Find the volume of a sphere of radius $$r$$. We know that the radius is $$r$$, meaning that the distance between any point on the surface and the center is $$r$$. We have the radius of a cross section at $$x$$ as $$\sqrt{r^2 - x^2}$$. The area is $$A(x) = \pi (r^2 - x^2)$$. To find the volume, we integrate $$\int_{-r}^r \pi(r^2 - x^2) dx = \int_{-r}^r \pi r^2 - \pi x^2 dx = \pi r^2 x - \frac{\pi}{3} x^3 \|_{-r}^r$$.

> Example: Find the volume of a square pyramid whose base is $$L \times L$$ and whose height is $$h$$. The area for a certain height $$h$$ is $$\frac{l}{L} = \frac{z}{h} \to A(z) = \frac{L^2 z^2}{h^2}$$. The volume is thus given by $$\int_0^h \frac{L^2 z^2}{h^2} dz = \frac{L^2}{h^2} \cdot \frac{z^3}{3} \|^h_0 = \frac{1}{3} L^2 h$$.

- A common type of solid is a solid of revolution forme dby rotating a region around an axis.
- Use the 'washer method' to compute the area.

> Example: Find the volume of a solid formed by rotating the region between $$y = x^2$$ and $$y = 4$$ about the $$y$$-axis. The area of a cross-section perpendicular to the $$y$$-axis is given by $$A(y) = \pi y$$. We obtain the volume by finding $$\int_0^4 \pi y dy$$.

---

## Week 4 Monday - Cylindrical Shell Method
- When we have items rotated around an axis, we can find disks perpendicular to the axis and integrate along that axis.

> Example. Let $$R$$ be the region bounded by $$y = 0$$, $$y = x$$, and $$x^2 + y^2 = 9$$. What is the volume of the solid formed by rotating $$R$$ around the $$y$$-axis. We know $$x^2 + y^2 = 9$$, so we have $$x = \sqrt{9 - y^2}$$. We have the area of a disk at $$y$$ as $$\pi \left(9 - y^2 - y^2 \right)$$. Integrate this from $$0$$ to $$\sqrt{\frac{9}{2}}$$ (the intersection between $$x^2 + y^2$$ and $$y = x$$).

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


> If a constant force F is applied to an object over a distance $$d$$, the work performed is $$W = Fd$$. Common units of work are joules ($$1J = 1 N \cdot m$$) or foot-pounds (feet per lb).

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

---

## Week 5 Monday - Work Con't and Average Value of a Function
- Exam grades and answers will be posted tomorrow
- Average - around 70%.

**Work**
- Work is a concept from physics that deals with how energy is transfered from one object to another - a force is applied across a distance. 

$$\text{Work} = \text{Force} \times \text{Distance}$$

- When the force is not constant with respect to distance, we need to involve integration.

> Example: A 20 pound weight is attached to a 100 foot rope. Suppose that the rope weighs 10 pounds. Find the amount of work required to pull both the weight and the rope to the top.

> For the weight, the force required is $$20 \times 100 = 2000$$ foot-pounds. Different parts of the rope, however, have a different distance to travel. Consider a small section of rope of size $$\Delta x$$ a distance of $$x$$ from the top. The section weighs $$\frac{1}{10}\Delta x$$ pounds. Because it needs to be pulled up to the top, the work required is $$x \cdot \frac{1}{10} \Delta x$$ ft-lb. The total work for the whole rope is $$\int_0^100 \frac{1}{10} x dx = 500$$ ft-lb. The total work for the weight and the rope together is 2500 ft-lb.



> Example: A basin shaped like a hemisphere with radius 10 meters is filled to a depth of 6 meters. Find the amount of work needed to pump the water to the top of the basin. The density of water is 1000 kilograms per cubic meter, and assume the acceleration due to gravity is 10 meters per second squared.

> The volume at a depth $$x$$ is $$\pi(100 - x^2) \Delta x$$ and its weight/force is $$10 \cdot 1000 \cdot \pi (100-x^2) \Delta x $$. The work required to pump it out is $$x\cdot 10000\pi (100 - x^2) \Delta x$$ J. We need to integrate this across each of the possible slices, yielding $$17,640,000\pi$$ joules.


**Average Value of a Function**
- If you take the average of several numbers, you add up all $$n$$ numbers and divide by $$n$$.

> The average value of a function $$f$$ on the interval $$[a, b]$$ is $$\frac{1}{b-a} \int_a^b f(x) dx$$.

- The area under the line $$y = \hat{f(x)}$$ between $$[a, b]$$ is the same as the area under $$y = f(x)$$ from $$a$$ to $$b$$. 
- Mean Value Theorem (special case of the Intermediate Value Theorem) - If $$f$$ is continuous on $$[a, b]$$, then there exists some $$c$$ in the interval such that $$f(c) = \frac{1}{b-a} \int_a^b f(x) dx$$.
- Other applications: suppose you want to know the average speed of the car: compute the distance and divide by the length of the interval.

---

## Week 5 Wednesday - Integration by Parts
- Quiz statistics have been posted on the discussion board
- The exam solutions have been posted on Canvas and grades are available on Gradescope
- Chapter 7 is concerned with techniques of integration.
- Most integrals are hard to do; Chapter 7 allows us to perform more complicated integration procedures.
- Integration by parts is the 'opposite' of the product rule - undoing the product rule
- Similarly with $$u$$-substitution, we need to choose certain expressions. It will take some practice to figure out how to select the correct 'keys'.
- Product rule for differentiation: $$\frac{d}{dx} (f(x) \cdot g(x)) = f(x) \cdot g'(x) + f'(x) \cdot g(x)$$
- If we take the antiderivative of both sides, we get $$f(x) \cdot g(x) = \int g(x) g'(x) dx + \int g(x) f'(x) dx$$.
- Suppose you know how to compute one of the terms; them you can compute the others.
- We will rearrange as such:

$$\int f(x) g'(x) dx = f(x) \cdot g(x)  - \int g(x) f'(x) dx$$

- Sometimes, the LHS integral is difficult, but we can choose $$f(x)$$ and $$g(x)$$ such that the RHS is more convenient.
- Also written as such - $$u = f(x)$$, $$du = f'(x)$$, $$v = g(x)$$, $$dv = g'(x) dx$$, thus:

$$\int u dv = uv - \int v du$$

- We want to compute $$\int u dv$$. Instead of directly computing, we compute $$du$$ (the derivative of $$u$$) and $$dv$$ (the integral of $$v$$) and plug into the RHS of the integration by parts formula.

> Example: Find $$\int x \cos x dx$$.

> We need to choose a $$u$$ and a $$v$$ such that $$uv - \int v du$$ is easier to compute. Let $$u = x$$ and $$v = \cos x$$. We have $$du = dx$$ and $$v = \sin x$$. Plugging into the integration by parts formula yields  $$x\sin x - \int \sin x dx = x\sin x + \cos x + C$$. We can verify the integral by taking the derivative: $$\frac{d}{dx} \left(x \sin x + \cos x\right) = x \cdot \cos x + \sin x - \sin x = x \cos x$$.

- For definite integrals, you need to evaluate $$uv$$ between the two limits $$a$$ and $$b$$ of your integral.

$$\int_a^b u dv = uv \big]_a^b - \int_a^b v du$$

> Example: Find $$\int_e^{e^2} \ln x dx$$.

> Let $$u = \ln x$$ and $$dv = dx$$. $$du = \frac{dx}{x}$$ and $$v = x$$. $$\int_e^{e^2} \ln x dx = x\ln x \big]_e^{e^2} - \int_e^{e^2}  dx =  (e^2\ln e^2 - e \ln e) - x \big]_e^{e^2} = (2e^2 - e) - (e^2 - e) = e^2$$.

- $$du$$ must be simpler than $$u$$, and you actually have to be able to integrate $$dv$$.
- You may need to repeatedly apply integration by parts.

> Example: Find $$\int x^2 e^{3x} dx$$.

> Let $$u = x^2$$ and $$v = e^{3x}$$. We have $$du = 2x dx$$ and $$v = \frac{1}{3} e^{3x}$$. $$\int x^2 e^{3x} dx = \frac{1}{3} x^2 e^{3x} - \frac{2}{3} \int xe^{3x} dx$$. Let us perform integration by parts of $$\frac{2}{3} \int xe^{3x}$$ again. Let $$u = x$$ and $$dv = e^{3x} dx$$. We have $$du = dx$$ and $$v = \frac{1}{3}e^{3x}$$. Using integration by parts, $$\int xe^{3x} dx = \frac{1}{3} x e^{3x} - \int \frac{1}{3} e^{3x} dx = \frac{1}{3} xe^{3x} - \frac{1}{9} e^{3x} + C$$. Returning to the original integration by parts formula, we have $$\int x^2 e^{3x} dx = \frac{1}{3} x^2 e^{3x} - \frac{2}{3} \left(\frac{1}{3}xe^{3x} - \frac{1}{9} e^{3x} \right) + C'$$. ($$C'$$ is sometimes used to denote a modified $$C$$ through iterations of integration.)




> Example: Find $$\int e^x \cos x dx$$.

> Let $$u = e^x$$ and $$dv = \cos x$$. We have $$du = e^x dx$$ and $$v = \sin x$$. We have $$\int e^x \cos x dx = e^x \sin x - \int e^x \sin x dx$$. Let us apply integration by parts upon the term $$\int e^x \sin x dx$$, using a similar substitution scheme with $$u = e^x$$ and $$dv = \sin x$$; this yields $$du = e^x dx$$ and $$v = -\cos x$$. Plugging into the integration by parts formula yields  $$\int e^x \sin x dx = - e^x \cos x + \int e^x \cos x dx$$. We plug this back into the original formula and obtain $$\int e^x \cos x dx = e^x \sin x - (- e^x \cos x + \int e^x \cos x dx) \implies 2 \int e^x \cos x dx = e^x \sin x + e^x \cos x + C \implies \int e^x \cos x dx = \frac{e^x \sin x + e^x \cos x}{2}$$.




> Example: Find $$\int e^{\sqrt{x}} dx$$.

> Let $$y = \sqrt{x}$$; we have $$\int e^{\sqrt{x}} dx = 2 \int e^y \cdot y dy$$. Let $$u = y$$ and $$dv = e^y dy$$; we have $$du = dy$$ and $$v = e^y$$. $$2\int y e^y dy = 2 \left(ye^y - \int e^y dy\right) = 2\left(ye^y - e^y \right) + C$$; substituting back in yields $$2\left(\sqrt{x} e^{\sqrt{x}} - e^{\sqrt{x}}\right) + C$$.



---

## Week 5 Friday - Trigonometric Integrals
- Integrating functions that are a relationship between trigonometric functions.
- Suppose we wish to evaluate an integral like $$\int \sin^m x \cos^n x dx$$. If $$m$$ or $$n$$ is 1, we can do $$u$$-substitution - but this becomes a difficult problem for larger values of $$m$$ and $$n$$.
- A trick if $$m$$ or $$n$$ is odd: we can turn all but one of the $$\sin$$'s into $$\cos$$'s using the Pythagorean identity $$\sin^2 x = 1 - \cos^2 x$$; then, use u-substitution $$u = \cos x$$.

> Example: Find $$\int \sin^3 x \cos^2 x dx$$.

> Turn all the other $$\sin$$ into $$\cos$$ except for one: this is equal to $$\int \sin x (1 - \cos^2 x) \cos^2 x dx$$. Let $$u = \cos x$$; thus, $$du = -\sin x dx$$. Using u-substitution yields $$- \int (1 - u^2) u^2 du = \int (u^4 - u^2) du = \frac{1}{5} u^5 - \frac{1}{3} u^3 + C = \frac{\cos^5 x}{5} - \frac{\cos^3 x}{3} + C$$.


> Example: Find $$\int \cos^5 x dx$$. 

> We have $$\int \cos x \cdot (1 - \sin^2)^2$$. Let $$u = \sin x$$; $$du = \cos x dx$$. The integral is this $$\int (1 - u^2)^2 du = \int (1 - 2u^2 + u^4) du = u - \frac{2}{3} u^3 + \frac{1}{5} u^5 + C = \sin x - \frac{2}{3} \sin^3 x + \frac{1}{5} \sin^5 x + C$$.

- If $$m$$ and $$n$$ are both even, we will need to use a different identity: $$\sin^2 x = \frac{1}{2} (1 - \cos 2x)$$ and $$\cos^2 x = \frac{1}{2} (1 + \cos 2x)$$.
- The identity $$\sin x \cos x = \frac{1}{2} \sin 2x$$ can also help save some algebra.

> Example: Find $$\int \cos^2 x dx$$.

> We have $$\int (1 + \cos 2x) dx = \frac{1}{2} \int (1 + \cos 2x) dx$$. Using a u-substitution for $$u = 2x$$, we have $$\frac{1}{2} \left(x + \frac{1}{2} \sin 2x + C$$.

> Example: Find $$\int \sin^2 x \cos^2 x dx$$.

> We have $$\int \frac{1}{4} \sin^2 (2x)$$. Plugging in another trigonometric identity, we get $$\int \frac{1}{4} \cdot \frac{1}{2} \left(1 - \cos 4x \right) dx = \frac{1}{8} \left(x - \frac{\sin 4x}{4} \right) + C$$.

- If you have any integral with products of $$\sin$$ and $$\cos$$ powers, you can use these methods to integrate.
- Additional problems: products of secants and tangents.


  
- For integrals of tangents and secants, use a similar strategy using the identity $$\sec^2 x = 1 + \tan^2 x$$.
- To find $$\int \tan^m x \sec^n x dx$$:
 - If $$m$$ is odd: turn all but one of the tangents into secants and let $$u = \sec x$$; thus $$du = \sec x \tan x$$.
 - If $$n$$ is even, turn all but two secants into tangents and let $$u = \tan x$$; thus $$du = \sec^2 x dx$$.

> Example: Find $$\tan^2 x \sec^4 x dx$$.

> Because $$n$$ is even, we turn all but two secants into tangents: $$\int \tan^2 (1 + \tan^2 x) \sec^2 x dx$$. Let $$u = \tan x$$; $$du = \sec^2 x dx \implies \int u^2 (1 + u^2) du \implies \int u^2 + u^4 du \implies \frac{u^3}{3} + \frac{u^5}{5} + C \implies \frac{\tan^3 x}{3} + \frac{\tan^5 x}{5} + C$$. 

- A little bit of a rote exercise - once you know & practice the algorithm, you'll get used to it.

> Example: Find $$\int \tan^5 x \sec^5 x dx$$.

> We have $$m$$ as odd; thus, we turn all but one of the remaining tangents into secants: $$\int (\sec^2 x - 1)^2 \sec^4 x - \sec x \tan x dx. Let $$u = \sec x$$; $$du = \sec x \tan x dx$$. $$\int (u^2 - 1)^2 u^4 du \implies ... \implies \frac{\sec^9 x}{9} - \frac{2 \sec^7 x}{7} + \frac{sec^5 x}{5} + C$$.

- The rules also theoretically apply to negative powers, too.

> Example: Find $$\int \tan x dx$$.

> Use the same rule as before. In this case, $$m$$ is odd. Let $$u = \sec x$$; $$du = \sec x \tan x dx \implies \tan x dx = \frac{du}{\sec x} = \frac{du}{u}$$. This yields $$\int \frac{du}{u} = \ln \|u\| + C = \ln \| \sec x \| + C$$.

> Example: Find $$\int \sec x dx$$.

> Uses a bit of a clever/cheating trick: rewrite as $$\int \sec x \cdot \frac{\sec x + \tan x}{\sec x + \tan x} dx$$; this yields $$\int \frac{\sec^2 x + \sec x \tan x}{\sec x + \tan x} dx$$. If you take the derivative of the bottom, it gives you the numerator. Let $$u = \sec x + \tan x$$; $$du = \sec^2 x + \sec x \tan x$$. The integral becomes $$\int \frac{du}{u} = \ln \|u\| + C = \ln \| \sec x + \tan x} + C$$.

- See textbook for the calculation of $$\int \sec^3 x dx$$.

---

## Week 6 Monday - Trigonometric Substitutions

> Example: Find $$\int \sqrt{4 - x^2} dx$$.

> This is the area under a semi-circle; we are going to get a $$pi$$ somehow. Let $$x$$ be something such that this square root will simplify: $$x = 2\sin \theta$$; $$\dx = 2\cos\theta d\theta$$. If we now compute the integral, we get $$\int \sqrt{4 - 4\sin^2 \theta} = 2 \sqrt{1 - \sin^2 \theta} = 2\cos \theta$$. When we take the square root, we need to make sure $$\cos theta > 0$$; we can impose a limit $$-\frac{\pi}{2} \le \theta \le \frac{\pi}{2}$$. Taking the integral, we obtain $$\int 2 \cos \theta \cdot 2\cos \theta d\theta = \int 4 \cos^2 \theta d\theta = \int 4\left(\frac{1 + \cos 2\theta}{2}\right) d\theta = \int 2(1 + \cos 2\theta) d\theta = 2(\theta + \frac{1}{2} \sin 2\theta) + C$$. We need this in terms of $$x$$: we have that $$x = 2\sin \theta \implies $$. Firstly, we can use the double angle formula: $$2 \theta + 2 \sin \theta \cos \theta + C$$. We have $$2 \sin^{-1} \frac{x}{2} + x\sqrt{4 - x^2} + C$$.

- To navigate tricky trigonometric relationships, you can draw a right triangle, interpolate its values interpretatively, and extrapolate relationships.
- Steps:
  1. Choose a substitution
  2. Plug the substitution in
  3. Evaluate the substitution
  4. Replace the trigonometric $$\theta$$ substitution with the original variable
- When should you use trigonometric substitutions? Some heuristics:

| Integrand contains... | Try substitution... | So you can... |
| --- | --- | --- |
| $$\sqrt{a^2 - x^2}$$ | $$x = a\sin \theta$$ | Use the identity $$1 - \sin^2\theta = \cos^2\theta$$. |
| $$\sqrt{a^2 + x^2}$$ | $$x = a\tan \theta$$ | Use the identity $$1 + \tan^2 \theta = \sec^2 \theta$$. |
| $$\sqrt{x^2 - a^2}$$ | $$x = a\sec \theta$$ | Use the identity $$\sec^2 \theta - 1 = \tan^2 \theta$$. |

- Make sure to change the limits of integration if you evaluate w.r.t. $$\theta$$.

> Example: Find $$\int_3^6 \frac{\sqrt{x^2 - 9}}{x} dx$$.

> Let $$x = 3 \sec \theta$$; $$dx = 3 \sec \theta \tan \theta d\theta$$. We can rewrite the numerator as $$3 \tan \theta$$. The original integral can be rewritten as $$\int_0^{\frac{\pi}{3}} \frac{3\tan \theta}{3 \sec \theta} \cdot 3 \sec \theta \tan \theta d \theta$$ (notice the bound recalculation). This can be simplified as $$\int_0^{\frac{\pi}{3}} 3 \tan^2 \theta d\theta$$. We can rewrite $$\tan^2$$ in terms of $$\sec^2$$: 

$$3 \int_0^{\frac{\pi}{3}} \left(\sec^2 \theta - 1\right) d\theta$$

$$\implies 3 \left(\tan \theta - \theta) \big]_0^{\frac{\pi}{3}}$$

$$\implies 3 \left( \tan \frac{\pi}{3} - \frac{pi}{3}\right) = 3 \sqrt{3} - \pi$$



> Example: Find $$\int \frac{\dx}{\sqrt{4 + 9x^2}}$$.

> Note that $$\sqrt{4 + 9x^2} = 3 \sqrt{ \frac{4}{9} + x^2 }$$. Let $$x = \frac{2}{3} \tan \theta$$; $$dx = \frac{2}{3} \sec^2 \theta d\theta$$. Plugging things in yields

$$\int \frac{\frac{2}{3} \sec^2 \theta d\theta}{\sqrt{4 + 4 \tan^2 \theta}}$$

$$\implies \int \frac{\frac{2}{3} \sec^2 \theta d\theta}}{2 \sec \theta}$$

$$\implies\frac{1}{3} \int \sec \theta d\theta$$

$$\implies \frac{1}{3} \ln \left \| \sec\theta + \tan \theta \| + C$$

$$\implies \frac{1}{3} \ln \left\| \frac{\sqrt{4 + 9x^2}}{2} + \frac{3x}{2} \right\|$$


- Sometimes, you will have multiple terms involved. You may need to complete the square first to realize one of the trigonometric substitution precondition forms.

> Example: Find $$\int \frac{x}{1 + 4x - x^2}{dx}$$.

> We can complete the square by rewriting $$1 + 4x - x^2 = -(x^2 - 4x - 1) = -(x^2 - 4x + 4 - 5) = -((x-2)^2 - 5) = 5 - (x-2)^2$$. The integral is thus

$$\int \frac{x}{\sqrt{5 - (x-2)^2}} dx$$

> We can perform a $$u$$-substitutiton; let $$u = x-2 \implies du = dx$$.

$$\int \frac{u + 2}{\sqrt{5 - u^2}} du$$

> Let us perform another substitution: let $$u = \sqrt{5} \sin \theta \implies du = \sqrt{5} \cos \theta d \theta$$.

$$\int \frac{ \sqrt{5} \sin \theta + 2}{\sqrt{5} \cos \theta} \sqrt{5} \cos \theta d \theta \implies \int (\sqrt{5} \sin \theta + 2) d\theta$$

> Integrating yields $$- \sqrt{5} \cos \theta + 2 \theta + C$$. We now need to rewrite it in terms of $$u$$:

$$- \sqrt{5 - u^2} + 2 \sin^{-1} \frac{u}{\sqrt{5}} + C$$

> We need to substitute back in for $$x$$:

$$- \sqrt{5 - (x-2)^2} + 2 \sin^{-1} \frac{x - 2}{\sqrt{5}} + C$$

---


## Week 6 Wednesday - Partial Fractions
- Last Quiz: average of 9.0, median 10.
- Partial fractions can be used to integrate any rational function - a polynomial divided by another polynomial.

$$f(x) = \frac{P(x)}{Q(x)}$$

- A polynomial is a sum of integer, nonnegative powers of an independent variable $$x$$.

Steps:
- Make sure the rational function is in proper form - the degree of the numerator must be smaller than the degree of the denominator using long division.

> Consider $$\frac{x^3 + 1}{x^2 - 3x + 2}$$. It can be reduced as $$x + 3 + \frac{7x - 5}{x^2 - 3x + 2}$$ through polynomial division.

- Factor the denominator. You can always factor a quadratic into linear $$$ax+b$$ or quadratic factors $$ax^2 + bx + c$$ with no real roots.

> Consider $$x^2 - 3x + 2$$; this can be factored as $$(x-1)(x-2)$$.

- If the result consists of all distinct linear factors, rewrite the rational function as a sum of terms $$\frac{A}{ax+b}$$ and integrate.

> Consider $$\frac{7x - 5}{(x-1)(x-2)}$$. We can always rewrite this as $$\frac{A}{x-1} + \frac{B}{x-2}$$. Multiplying both sides fot eh LHS denominator, we have $$7x-5 = A(x-2) + B(x-1)$$. Now, we plug in values of $$x$$ and get an output. By plugging in $$x = 1$$, we get $$2 = -A + 0 \implies A = -2$$. If $$x = 2$$, we get $$9 = 0 + B \implies B = 9$$. It follows that $$\frac{7x-5}{(x-1)(x-2)} = \frac{-2}{x-1} + \frac{9}{x-2}$$.

> An alternative method: take $$7x - 5 = A(x-2) + B(x-1)$$ and expand as $$7x - 5 = (A+B)x - 2A - B$$. We know that $$A+B = 7$$ and $$-2A-B = -5$$. Solve the linear system.

> We can now integrate the result: we rewrote $$\int \frac{x^3 + 1}{x^2 - 3x + 2} dx = \int \left(x + 3 + \frac{-2}{x-1} + \frac{9}{x-2} \right) dx = \frac{x^2}{2} + 3x - 2\ln \|x-1\| + 9 \ln \|x-2\| + C$$.

- If the result contains a repeated linear factor $$(ax + b)^k$$, write as a sum of terms $$\frac{A}{ax + b} + \frac{B}{(ax+b)^2} + \frac{C}{(ax+b)^3} + ... + \frac{Q}{(ax+b)^k}$$.

> Consider $$\int \frac{2x + 3}{x^3 - 2x^2 + x} dx$$. We need to factor the denominator: $$x^3 - 2x^2 + x = x (x-1)^2$$. We want to write $$\frac{2x+3}{x(x-1)^2} = \frac{A}{x} + \frac{B}{x-1} + \frac{C}{(x-1)^2}$$. Multiplying by the LHS denominator yields

$$2x+3 = A(x-1)^2 + Bx(x-1) + Cx$$

> We can plug in $$x = 0$$ and $$x = 1$$; if $$x = 0$$, we get $$3 =  A$$. If $$x = 1$$, we get $$5 = C$$. If $$x = 2$$, we get $$7 = A + 2B + 2C \implies 3 + 2B + 10 \implies B = -3$$. The original function is thus rewritten as

$$ \frac{3}{x} - \frac{3}{x-1} + \frac{5}{(x-1)^2}$$

$$\int \frac{2x + 3}{x^3 - 2x^2 + x} dx = \int\left( \frac{3}{x} - \frac{3}{x-1} + \frac{5}{(x-1)^2} \right) dx = 3 \ln \|x\| - 3 \ln \|x-1\| - \frac{5}{x-1} + C$$.

- If the result contains distinct quadratic factors $$ax^2 + bx + c$$, write as a sum of terms $$\frac{Ax+B}{ax^2 + bx + c}$$.

> Find $$\int \frac{x^2 - 1}{x^3 + 2x^2 + 5x}$$. We can factor this as $$x^3 + 2x^2 + 5x = x(x^2 + 2x + 5)$$. We write this as $$\frac{x^2 - 1}{x(x^2 + 2x + 5)} = \frac{A}{x} + \frac{Bx + C}{x^2 + 2x + 5}$$. We can clear the denominator: $$x^2 - 1 = A(x^2 + 2x = 5) + (Bx + C)x$$. We get $$A = -\frac{1}{5}, B = \frac{6}{5}, C = \frac{2}{5}$$.

> The integral is thus rewritten as follows:

$$\int \frac{x^2 - 1}{x^3 + 2x^2 + 5x} dx = \frac{1}{5} \int \left( -\frac{1}{x} + \frac{6x+2}{x^2 + 2x + 5} \right) dx$$

> The second term in the integrand requires some work. We can remember the following identity: 

$$\int \frac{dx}{x^2 + a^2} = \frac{1}{a} \arctan \left( \frac{x}{a} \right) + C$$

> We can evaluate as follows:

$$\int \frac{6x + 2}{x^2 + 2x + 5} dx = \int \frac{6x+2}{(x+1)^2+4} dx$$

> Let $$u = x+1$$; $$du = dx$$:

$$ \implies \int \frac{6u - 4}{u^2 + 4} du = \int \frac{6u}{u^2 + 4} du - \int \frac{4}{u^2 + 4} du$$

> Let $$v = u^2 + 4$$; $$dv = 2udu$$.

$$ \implies \int \frac{6u}{u^2 + 4} du = \int \frac{3}{v} dv$$

> We can use the other formula to evaluate the second term:

$$ \implies 3 \ln (u^2 + 4) - 2 \arctan \left( \frac{u}{2} \right) + C$$

- Then, substitute back the remaining variables.


---

## Week 6 Friday - Strategy for Integration
Last time - partial fractions
1. Use long division to make the numerator hav ea smaller degree than the denominator (i.e. proper form)
2. Factor the denominator into lienar factors or quadratic factors.
3. Write as a sum of fractions in partial fraction form.
4. Obtain equations for $$A, B, C, ...$$ and solve by plugging in values of $$x$$ or expanding and equating coefficients.
5. Integrate each term using previous techniques ($$u$$-substitution for linear factors, completing the square/trig substitution $$\int \frac{dx}{x^2 + a^2} = \frac{1}{a} \tan^{-1} \frac{x}{a} + C$$ for quadratic factors).

Partial fraction form:

- $$\frac{A}{ax+b}, \frac{B}{(ax+b)^2}, ...$$ if $$(ax+b)^k$$ appears
- $$\frac{Ax+B}{ax^2 + bx + c}, \frac{Cx+D}{(ax^2+bx+c)^2}, ...$$ if $$(ax^2+bx+c)^k$$ appears
- Quadratic factors must have no real roots (i.e. $$0 > b^2 - 4ac \implies b^2 < 4ac$$).

*Strategy for integration* (mysterious!)

- A difference between knowing a technique and knowing how to integrate an arbitrary integral.
- The best way to get better at integrals is to do a lot of them

Tips
- Recognize integrals of common expressions/standard integrals or a simple $$u$$-substitution from a common expression/standard integrals. See table in section 7.5.
- Try performing algebraic manipulations.
- Look for good $$u$$-substitutions. Many integrals require you to make a clever substitution that can be integrated more easily.
  - If your integrand contains a very complicated subexpression in a denominator, radicals, power, etc. - try substituting for the subexpression.
    - Rationalizing substitution: $$u = \sqrt{g(x)}$$
  - Try to recognize potential derivatives and substitute for the antiderivative such that $$du$$ cancels out the derivative. 
- If the integrand is a product of two components, try integration by parts. One of the things has to be easy to integrate, and the other needs to be easy to differentiate. 

Remember that we have various specialized techniques for certain types of integrals: product of trig functions, trig substitutions, rational functions, etc.

**Examples**

> Consider the function $$\int (x + \sin x)^2 dx$$. Possible ideas:
- Let $$u = x + \sin x$$ substitution? However, $$du = (1 + \cos x) dx$$ - this does not simplify our situation.
- Use integration by parts with $$u = x + \sin x$$ and $$dv = (x + \sin x)dx$$, yielding $$du = 1 + \cos x$$ and $$v = \frac{x^2}{2} - \cos x$$. The $$v du$$ term is quite complicated to integrate, so it will not really work.
- Expand the integral: $$(x + \sin x)^2 = x^2 + 2x\sin x + \sin^2 x$$. We can integrate each of the terms.
  - The first term is trivial: $$ \frac{1}{3} x^3$$
  - The second term can be integrated with integration by parts: let $$u = x$$ and $$dv = \sin x dx$$; $$du = dx$$ and $$v = -\cos x$$; the integral is $$-x\cos x + \int \cos x dx = 2(-x \cos x + \sin x)$$
  - The third term can be integrated by rewriting using the double angle identity $$\int \sin^2 x dx = \int \frac{1 - \cos 2x}{2} dx$$, which can be integrated.'
> The answer is $$\frac{x^3}{3} - 2x \cos x + 2\sin x + \frac{x}{2} - \frac{\sin 2x}{4} + C$$


> Consider the function $$\int \frac{1}{x + \sqrt{x + 2}} dx$$. Possible ideas:
- Rationalize the denominator using the conjugate of the denominator. $$\frac{1}{x + \sqrt{x+2}} \cdot \frac{x - \sqrt{x+2}}{x - \sqrt{x + 2}} = \frac{x - \sqrt{x+2}}{x^2 - x - 2}$$. Integrating this expression is very difficult.
- Let $$u = x+2$$ with $$u$$-substitution. Our interval becomes $$\int \frac{1}{u - 2 + \sqrt{u}}$$. This is also very difficult to integrate.
- Let $$u = \sqrt{x + 2}$$ with $$u$$-substitution. $$du = \frac{1}{2\sqrt{x+2}}dx \implies 2x = 2udu$$. $$\int \frac{1}{x + \sqrt{x + 2}} dx = \int \frac{1}{u^2 - 2 + u} \cdot 2udu$$. This is a rationalizing substitution - we took something that wasn't a rational function and turned it into a rational function. You can now use partial fractions.
> The result is $$\frac{4}{3} \ln \| \sqrt{x+2} + 2 \| + \frac{2}{3} \ln \| \sqrt{x+2} - 1 \| + C$$.

> Consider the function $$\int \frac{\tan^{-1} x}{x^2} dx$$.
- Integration by parts: let $$u = \frac{1}{x^2}$$ and $$dv = \tan^{-1} x dx$$. $$u = \tan^{-1} x$$, $$dv = \frac{1}{x}^2 dx$$, $$du = \frac{1}{1+x^2} dx$$, $$v = -\frac{1}{x}$$. The result is $$-\frac{\tan^{-1}x}{x} + \int \frac{1}{x(1+x^2)} dx$$. We can then apply partial fractions: $$ \frac{A}{x} + \frac{Bx+C}{1+x^2} = \frac{1}{x(1+x^2)}$$. After solving, we get $$A = 1, B = -1, C = 0 \implies \frac{1}{x} - \frac{x}{1+x^2}$$. Use a $$u$$-substitution on thes econd term. The final integral is $$-\frac{\tan^{-1} x}{x} + \ln\|x\| - \frac{1}{2} \ln \| 1 + x^2 \| + C$$.


---

## Week 7 Monday - Approximate Integration
Midterm Exam next Thursday: up to section 7.8, and includes everything before the exam - cumulative. 
- Applications of integration - work, cylindrical shells, techniques of integration in Chapter 7, through improper integrals & approximating integrals
- Format will be similar to that of the first exam - 4 to 5 problems. Roughly of the same length and relative difficulty. Generally material between the first and second exams is inherently more difficult.
- Go to your section - you will start doing exam practice questions. 

Last time: talked about strategies for integration.
- Recommend looking at the corresponding section of the textbook, section 7.5. Has an outline for how to attack an integral which you may not be able to figure out immediately, with several associated steps.

Suppose you have an integral and you want to approximate it. Why would you only want to find an approximate?
- Sometimes, antiderivatives are really complicated and it's not worth figuring out what the antiderivative is.
- Many innocuous-looking integrals do not have integrals expressable via elementary functions.
- It may be faster in some domains to approximate the ingral rather than to express it symbolically.
- Functions may not be given as a formula, but rather as (for instance) experimental data.
- Maybe you have a guage measuring the flow of watrer into a tank over time - it's not really a continuous function.

**Question:** HOw do we approximate $$\int_a^b f(x) dx$$?
- We used Riemann sums to initially approximate the size of the integral by using sums of rectangles.
- Divide $$[a, b]$$ into $$n$$ pieces; $$\Delta x = \frac{b-a}{n}$$, $$x_0 = a, x_1 = a + \Delta x, x_{n-1} = a + (i) \Delta x, x_n = b$$.
- Right vs left vs middle Riemann sums
- We may hope that the middle Riemann sum performs the best.
- Another approximation is simply to take the average of the left and right Riemann sums: *the trapezoid rule*.
  - $$f(x_0) + 2(f(x_1) + 2f(x_2) + ... + 2 (f_{x-1}) + f(x_n))$$
  - Called the trapezoid rule because it's looking at a given interval and approximating the region with a trapezoid instead of a rectagle. 
- Usually the midpoint rule has typically half the error of the trapezoid rule.
- 2:1 ratio has to deal with the area of a parabola vs the area of a triangle, etc.
- We can get a better estimate by modeling the parabolas. The idea is - take the values at each point and try to fit a parabola that passes through any three consecutive sampled points. Then, take the area under this parabola. This gives Simpson's rule: 

> For an even $$n$$, Simpson's rule gives the estimate:

$$\frac{\Deta x}{3} \left(f(x_0 + 4f(x_1) + 2f(x_2) + 4f(x_3) + ... + 2f(x_{n-2}) + 4f(x_{n-1}) + f(x_n)\right)$$

> Note: the coefficients $$1, 4, 2, 4, 2, ..., 4, 1$$ and $$\frac{\Delta x}{3}$$. Usually, a parabola will fit a triangle better than a straight line.


- Relationship between three rules: midpoint, trapezoid, and Simpson's rules: $$S_{2n} = \frac{1}{3} T_n + \frac{2}{3} M_n$$ ($$S_{n}$$ = Simpson's rule, $$\frac{1}{3}T_n$$ = Trapezoid rule, $$\frac{2}{3} M_n$$ = midpoint rule).
- The book pays a lot of attention to error bounds - this has to do with the second or fourth derivatives of functions. 

---

## Week 7 Wednesday - Improper Integrals
- Quiz 6: 7.94 average, 8.24 median
- Exam next Thursday:
  - You must justify any integrals not listed in the table in section 7.5.
  - You must simplify any inverse trig functions inside trig functions.
- Usually, the area under a curve has always been a finite amount.
- Sometimes, we can compute areas under curves that extend infinitely in some direction, either vertically or horizontally. 
- Improper integrals allow us to determine if an infinitely extending region is finite or infinite in area.
- Approximate the integral using a finite region and take the limit as the size of the finite region grows. '
- Type I improper integral: the interval upon which we are integrating is infinite.

> Example: $$y = \frac{1}{x^2}$$. We want to find the area under the curve in the domain $$[1, \infty)$$: $$\int_1^\infty \frac{1}{x^2} dx$$. We can ask what happens as the upper right bound $$t$$ tends towards $$\infty$$. Imagine we have an arbitrary upper boudn $$t$$. The area between $$x = 1$$ and $$x = t$$ is $$\int_1^t \frac{1}{x^2} dx = -\frac{1}{x} \big]_1^t = -\frac{1}{t} + 1$$. As we take the  limit of this expression with $$t \to \infty$$, $$-\frac{1}{t} + 1 \to 1$$. The integral is thus $$\int_1^\infty \frac{1}{x^2} dx = \lim_{t\to\infty} \int_1^t \frac{1}{x^2} dx = 1$$. This integral **converges** - the limit is a finite value.

> Example: $$y = \frac{1}{x}$$. We want to find the area under the curve in the domain $$[1, \infty)$$. We compute the limit: $$\int_1^\infty \frac{1}{x} dx = \lim_{t\to\infty} \int_1^t \frac{1}{x} dx = \lim_{t\to\infty} \ln(x) \big]^t_1 = \lim_{t\to\infty} \ln t$$. As $$t$$ goes to infinity, the natural log also goes to infinity; we say that the integral **diverges**; it does not approach some finite value.

- We define $$\int_a^\infty f(x) dx = \lim_{t\to\infty} \int_a^t f(x) dx$$. If the limits exists and is finite, we say the integral converges; otherwise, it diverges.
- We define $$\int_{-\infty}^\infty f(x) dx = \int_{-\infty}^a f(x) dx + \int_a^\infty f(x) dx$$. 
- Sometimes you need to use L'Hopital's rule to help evaluate difficult derivatives.

- Type II integral: instead of the infinite region extending horizontally, we may have a function with a vertical asymptote.

$$\int_a^b f(x) dx = \lim_{t\to b^-} \int_a^t f(x) dx$$

- If $$f$$ is continuous on $$(a, b]$$ with a vertical asymptote at $$a$$, then take the integral form the right.
- If an asymptote exists within a range, split into two separate components and evaluate. Both integrals must converge; if either integral diverges, then so does the integral across the entire range.

> Example: Find $$\int_0^1 \frac{dx}{\sqrt{1-x}}$$. This has a vertical asymptote at $$x = 1$$. To compute this, we will take the limit $$\lim_{t\to 1^-} \int_0^t \frac{dx}{\sqrt{1-x}}$$. By using a $$u$$-substitution, we get  $$\lim_{t\to 1^-} -2\sqrt{1-x} \big]_0^t = \lim_{t\to 1^-} (2 - 2\sqrt{1-t}) = 2$$. The integral converges to a finite number $$2$$.

- It is important to identify improper integrals.

> Example: Find $$\int_{-1}^1 \frac{x^2}$$. If you didn't notice this was improper, you may just try to integrate and subtract. We should instead write it as $$\int_{-1}^0 \frac{dx}{x^2} + \int_0^1 \frac{dx}{x^2}$$ due to the vertical asymptote at $$x = 0$$. It turns out that the result diverges.


## Week 7 Friday - The Comparison Test and Arc length
- Last time, we talked about improper integrals - we are trying to find the integral of an integral that stretches off to infinity in some direction.
- Either the limit of the integral approaches some finite value or it shoots off to infinity
- Comparison Theorem - gives us a way to determine if an integral converges or diverges without actually computing it.
  - Can be useful in cases where we don't actually know the antiderivative or it is difficult to find.
- Suppose you have two functions, and you know that the integral of one converges; if the second is smaller than the first, then the second also converges.

> Let $$f$$ and $$g$$ be continuous functions that satisfy the inequality $$0 \le g(x) \le f(x)$$ for all $$x \ge a$$. If $$\int_a^\infty f(x) dx$$ converges, then so does the integral $$\int_a^\infty g(x) dx$$. If $$\int_a^\infty g(x) dx$$ diverges, then so does $$\int_a^\infty f(x) dx$$.'

- Good functions (which converge under the given conditions) to use for comparison:

$$\int_1^\infty \frac{1}{x^p} dx, p > 1$$

$$\int_a\infty e^{-x} dx$$

> Example: does $$\int_0^\infty e^{-x^2} dx$$ converge or diverge? This has no elementary antiderivative. This gets smaller faster than $$\int_a^\infty e^{-x} dx$$, so it converges. $$\int_0^\infty e^{-x^2} dx = \int_0^1 e^{-x^2} dx + \int_1^\infty e^{-x^2} dx$$. Note that $$x^2 \ge x$$ for $$x \ge 1$$, so $$e^{-x^2} \le e^{-x}$$ for $$x \ge 1$$.  We have that $$\int_1^\infty e^{-x^2} dx \le \int_1^\infty e^{-x} dx$$, which converges. So, $$\int_1^\infty e^{-x^2} dx$$ converges, as does $$\int_0^\infty e^{-x^2} dx$$.

> Example: does $$\int_0^\infty \frac{1}{1+\sqrt{x}} dx$$ converge or diverge? For $$x \ge 1$$, $$\sqrt{x} \ge 1$$. This implies that $$1 + \sqrt{x} \le 2 \sqrt{x} \implies \frac{1}{1+\sqrt{x}} \ge \frac{1}{2\sqrt{x}}$$. $$\int_0^\infty \frac{1}{1+\sqrt{x}} dx = \int_0^1 \frac{1}{1+\sqrt{x}} dx + \int_1^\infty \frac{1}{1+\sqrt{x}} dx$$. $$\int_1^\infty \frac{1}{1+\sqrt{x} dx \ge  \int_1^\infty \frac{1}{2\sqrt{x}} dx = \frac{1}{2} \int_1^\infty \frac{1}{\sqrt{x}} dx$$ diverges. Therefore, $$\int_0^\infty \frac{1}{1+\sqrt{x}} dx $$ diverges.

- If you want to show something converges, it must be smaller than something that converges; if you want to show that something diverges, it must be larger than something that diverges.

**Section 8.1 - Arclength**
- We will cut the curve into a bunch of pieces, approximate the length of the piece using a straight line, add all together, and take the limit as the pieces get smaller.
- We consider many small right triangle hypoteni with base length $$\Delta x$$ and height $$\approx f'(x) \cdot \Delta x$$. The arclength is $$\sqrt{\Delta x^2 + f'(x)^2 \Delta x^2} = \Delta x \sqrt{1 + f'(x)^2}$$.
- We can find the arc length by replacing $$\Delta x$$ with $$dx$$ and integrating. 

> To find the arclength of $$f(x)$$ between $$x = a44 and 44y = b4$, we add up these segments of length $$\Delta x \sqrt{1 + f'(x)^2}$$ and take the limit of $$\Delta x \to 0$$ to get

$$L = \int_a^b \sqrt{1 + f'(x)^2} dx$$

> Example: find the lnegth of a semicircle $$y = \sqrt{1 - x^2}$$. The derivative is $$ - \frac{x}{\sqrt{1-x^2}}$$. We want to integrate $$\sqrt{1 + \frac{x^2}{1-x^2}} = \frac{1}{\sqrt{1-x^2}}$$. THe arclength is $$\int_{-1}^1 \frac{1}{\sqrt{1-x^2}} dx = \sin^{-1} x \big]_{-1}^1 = \frac{pi}{2} - (-\frac{\pi}{2}) = \pi$$.

- One way to remember the arc length formula is to define an arc length function $$s$$ which measures arc length starting at some initial point on the curve. What's the derivative of $$s$$? We have that $$ds^2 = dx^2 + dy ^2 \implies ds = \sqrt{dx^2 + dy^2}$$ (a bit hand-wavey notation). Imagine manipulating differentials like variables: you can factor out a $$dx^2$$ and get $$dx \sqrt{1 + \left(\frac{dy}{dx}\right)^2}$$. Integrate the differential to find $$s$$: $$s(t) = \int ds = \int_a^t \sqrt{1 + \left(\frac{dy}{dx}\right)^2} dx$$.
- If the curve is given as $$x = g(y)$$, $$ds = \sqrt{dx^2 + dy^2}$$ but we could factor out $$dy$$, yielding $$dy\sqrt{1 + \left(\frac{dx}{dy}\right)^2} = dy\sqrt{1 + g'(y)}$$. We have that $$s = \int \sqrt{1 + g'(y)} dy$$.

> Example: Find the length of the curve $$x = y^{\frac{3}{2}}$$ between $$y = 0$$ and $$y = 1$$. We need to find $$\int_0^1 \sqrt{1 + \frac{9}{4}y} dy$$. Let $$u = 1 + \frac{9}{4} y$$; $$du = \frac{9}{4} dy$$. $$\frac{4}{9} \int_1^{\frac{13}{4}} \sqrt{u} du = \frac{8}{27} \left(\frac{13}{4}^{\frac{3}{2}} - 1\right) = \frac{13\sqrt{13} - 8}{27}$$.




