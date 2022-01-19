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











