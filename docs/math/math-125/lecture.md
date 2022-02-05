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

> Use the same rule as before. In this case, $$m$$ is odd. Let $$u = \sec x$$; $$du = \sec x \tan x dx \implies \tan x dx = \frac{du}{\sec x} = \frac{du}{u}$$. This yields $$\int \frac{du}{u} = \ln |u| + C = \ln | \sec x | + C$$.

> Example: Find $$\int \sec x dx$$.

> Uses a bit of a clever/cheating trick: rewrite as $$\int \sec x \cdot \frac{\sec x + \tan x}{\sec x + \tan x} dx$$; this yields $$\int \frac{\sec^2 x + \sec x \tan x}{\sec x + \tan x} dx$$. If you take the derivative of the bottom, it gives you the numerator. Let $$u = \sec x + \tan x$$; $$du = \sec^2 x + \sec x \tan x$$. The integral becomes $$\int \frac{du}{u} = \ln |u| + C = \ln | \sec x + \tan x} + C$$.

- See textbook for the calculation of $$\int \sec^3 x dx$$.













