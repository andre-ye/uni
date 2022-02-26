---
layout: default
title: Textbook Notes
parent: MATH 125
grand_parent: Mathematics
nav_order: 2
---

# Textbook Notes
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

## 5.1: Areas and Distances
- When we find the area under a curve or the distance traveled over time, we end up with a special type of limit.
- Measure by using areas, Riemann sums.

$$\lim_{n\to\infty} \sum^n_{i = 1} f(x_i^*} \Delta x = \lim_{n\to\infty} \left[f(x_1^*) \Delta x + f(x_2^*) \Delta x + ... + f(x_n^*) \Delta x \right]$$

---

## 5.2: The Definite Integral

- The definite integral of $$f$$ from $$a$$ to $$b$$ is

$$\int_a^b f(x) dx = \lim_{n\to\infty} \sum^n_{i = 1} f(x_i} \Delta x$$

**Precise meaning of a limit that defines the integral.**

> For every number $$\epsilon > 0$$, there is an integer $$N$$ such that for every integer $$n > N$$ and for every choice of $$x_i^*$$ in $$\left[x_{i-1}, x_i\right]$$, the following is true: $$\| \int_a^b f(x) dx - \int^n_{i=1} f(x_i^*) \Delta x \| < \epsilon$$.

**Theorem 3.**

> If $$f$$ is continuous on $$[a, b]$$, or if $$f$$ has only a finite number of jump discontinuities, then $$f$$ is integrable on $$[a, b]$$; that is, the definite integral $$\int_a^b f(x) dx$$ exists.

**Integral Properties**

| Integral Property |
| --- |
| $$\int_a^b c dx = c(b-a)$$ |
| $$\int_a^b [f(x) + g(x)] dx = \int_a^b f(x) dx + \int_a^b g(x) dx$$ |
| $$\int_a^b cf(x) dx = c\int_a^b f(x) dx$$ |
| $$\int_a^b [f(x) - g(x)]dx = \int_a^b f(x) dx - \int_a^b f(x) dx$$ |
| If $$f(x) \ge 0$$ for $$a \le x \le b$$, then $$\int_a^b f(x) dx \ge 0$$ |
| If $$f(x) \ge g(x)$$ for $$a\le x\le b$$, then $$\int_a^b f(x) dx \ge \int_a^b g(x) dx$$ |
| If $$m \le f(X) \le M$$ for $$a \le x \le b$$, then $$m(b-a) \le \int_a^b f(x) dx \le M(b-a)$$ |

---

## 5.3: The Fundamental Theorem of Calculus
- Establishes a connection between differential and integral calculus. 

**Part 1**

> If $$f$$ is continuous on $$[a, b]$$, then the function $$g$$ defined by $$g(x) = \int_a^x f(t) dt$$ with $$a \le x \le b$$ is continuous on $$[a, b]$$, and differentiable on $$(a, b)$$, then $$g'(x) = f(x)$$.

> In other words, the derivative of a definite integral with respect to its upper limit is the integrand evaluated at the upper limit.

> Alternatively, $$\frac{d}{dx} \int_a^x f(t) dt = f(x)$$.

*Proving Part 1:*

If $$x$$ and $$x+h$$ are in the range $$(a, b)$$, then we have

$$g(x + h) - g(x) = \int_a^{x+h} f(t) dt - \int_a^x f(t) dt = \int_x^{x+h} f(t) dt$$

For $$h\neq$$ 0, we have

$$\frac{g(x+h) - g(x)}{h} = \frac{1}{h} \int_x^{x+h} f(t) dt$$

Assume $$h > 0$$. Let $$m$$ and $$M$$ be the absolute minimum and maximum values of $$f$$ on $$[x, x+h]$$. We have

$$mh \le \int_x^{x+h} f(t) dt \le Mh$$

Consider two numbers $$u$$ and $$v$$ such that $$f(u) = m$$ and $$f(v) = M$$. The inequality can be rewritten as

$$f(u) h \le \int_x^{x+h} f(t) dt) \le f(v) h$$

Dividing by $$h$$ yields

$$f(u) \le \frac{1}{h} \int_x^{x+h} f(t) dt \le f(v)$$

From statement 2, we can replace the middle expression in the inequality: 

$$f(u) \le \frac{g(x+h) - g(x)}{h} \le f(v)$$

Let us take the limit as $$h \to 0$$. Since $$u$$ and $$v$$ lie between $$x$$ and $$x+h$$, $$u\to x$$ and $$v\to x$$.

$$\lim_{h\to 0} f(u) = \lim_{u\to x} f(u) = f(x) \text{ and } \lim_{h\to 0} f(v) = \lim_{v\to x} f(u) = f(x)$$

From the squeeze theorem, we can conclude that

$$g'(x) = \lim_{h\to 0} \frac{g(x+h) - g(x)}{h} = f(x)$$

**Part 2**

> If $$f$$ is continuous on $$[a, b]$$, then $$\int_a^b f(x) dx = F(b) - F(a)$$ where $$F$$ is any antiderivative of $$f$$ (i.e. a function such that $$F' = f$$).

---

## 5.4: Indefinite Integrals and the Net Change Theorem

$$\int 0 \: dx = C$$

$$\int cf\left(x\right)\: dx=c\int f\left(x\right)dx$$

$$\int x^n\: dx=\frac{x^{n+1}}{n+1}+C\left(n\ne -1\right)$$

$$\int e^x\: dx=e^x+C$$

$$\int \sin x\:dx=-\cos x+C$$

$$\int \sec ^2x\:dx=\tan x+C$$

$$\int \sec x\:\tan x\:dx=\sec x+C$$

$$\int \frac{1}{x^2+1}\:dx=\tan ^{-1}x+C$$

$$\int \sinh x\:dx=\cosh x+C$$

$$\int \left[f\left(x\right)+g\left(x\right)\right]\:dx=\int f\left(x\right)dx+\int g\left(x\right)dx$$

$$\int \frac{1}{x}\:dx=\ln \left|x\right|+C$$

$$\int b^xdx=\frac{b^x}{\ln b}+C$$

$$\int \cos x\:dx=\sin x+C$$

$$\int \tan x\: dx = \ln \| \cos x \| + C$$

$$\int \csc ^2x\:dx=-\cot x+C$$

$$\int \csc x\cot x\:dx=-\csc x+C$$

$$\int \frac{1}{\sqrt{1-x^2}}\:dx=\sin ^{-1}x+C$$

$$\int \cosh x\:dx=\sinh x+C$$

---

## 5.5: The Substitution Rule
- Let $$u$$ be some quantity; we integrate with respect to $$du$$ instead of $$dx$$.
- If $$u = f(x)$$, then $$du = f'(x) dx$$.
- The substitution method works whenever we have an integral in the form $$f(g(x)) g'(x) dx$$.
- Make sure to plug in $$x$$ instead of $$u$$ when evaluating definite integrals

**Substitution Rule**
> If $$u = g(x)$$ is a differentiable function whose range is an interval $$I$$ and $$f$$ is continuous $$I$$, then $$\int f(g(x)) g'(x) dx = \int f(u) du$$.

---

## 6.1: Area Between Curves
- We use the Riemann sum logic and express the area in between curves as their vertical difference, i.e. the height of rectangles.

> The area $$A$$ of the region bounded by the curves $$y = f(x)$$, $$y = g(x)$$, and the lines $$x = a$$, $$x=b$$, where $$f$$ and $$g$$ are continuous and $$f(x) \ge g(x)$$ for all $$x$$ in $$[a, b]$$ is $$A = \int_a^b [f(x) - g(x)] dx$$.

- For some cases, you will need to separate the area into several components - when two curves intersect.
- Sometimes, it is more convenient to integrate with respect to $$y$$.

---

## 6.2: Volumes
- We can obtain a cross-section and sum the area of the cross-section across the length of the shape.

> Let $$S$$ be a solid that lies between $$x=a$$ and $$x=b$$. If the cross-sectional area of $$S$$ in the plane $$p_x$$ (through $$x$$ and perpendicular to the $$x$$-axis$$) is $$A(x)$$, where $$A$$ is a continuous function, then the volume of $$S$$ is $$V = \lim_{n \to\infty} \sum^n_{i=1} A(x_i^\*) \Delta x = \int_a^b A(x) dx$$.

- Solids of revolution are obtained by revolving a region about a line. You can calculate the cross-section either in the form of a disk $$A = \pi(\text{radius})^2$$ or as a washer $$A = \pi\left(\text{outer radius}^2 - \text{inner radius}^2\right)$$.
- In some cases you need to use geometric relationships like similar triangles to obtain the cross-sectional area at $$x$$.

---

## 6.3: Volumes by Cylindrical Shells
- Some volume problems are hard to handle using the washer problem.
- We consider the 'shell' of a cylinder summed up across the radius of the revolved solid:

$$V = [\text{circumference}] [\text{height}] [\text{thickness}]$$

> The volume of a solid obtained by rotating about the $$y$$-axis the region under the curve $$y = f(x)$$ from $$a$$ to $$b$$ is $$V = \int_a^b 2\pi xf(x) dx$$, where $$0 \le a < b$$.

- When deciding which method to use when computing the volume of a solid of revolution, consider if the region is better described by the top and bottom boundary curves $$y = f(x)$$ or by left and right boundaries $$x = g(y)$$.

---

## 6.4: Work
- If an object moves along a straight line with position $$s(t)$$, then the force $$F$$ on the object given its mass $$m$$ and acceleration $$a$$ is:

$$F = ma = m \frac{d^2 s}{dt^2}$$

- Mass is measured in kilograms, displacement in meters, time in seconds, and force in newtons ($$N = \text{kg} \cdot \text{m}/\text{s}^2$$.
- Given constant acceleration, the force $$F$$ is constant and the work done is given by

$$W = Fd (\text{work} = \text{force } \times \text{ distance})$$

- When the force is variable, we approximate total work across a force function $$f$$ and selected Riemann points $$x_i^{\*}$$ as $$W \approx \sum^n_{i=1} f(x_i^{\*}) \Delta x$$. We take $$\lim_{n\to\infty}$$ of the sum and obtain $$\int_a^b f(x) dx$$.

- Hooke's Law: the force required to maintain a spring stretched $$x$$ units beyond its natural length is proportional to $$x$$: $$f(x) = kx$$. $$k$$ is a positive constant called the spring constant. 

---

## 6.5: Average Value of a Function
- It is trivial to calculate the aerage value of finitely many numbers.
- To compute the average value for which there are an infinite number of possible values, we find the average value of a function.

$$\hat{f} = \frac{f(x_1) + ... + f(x_n)}{n] = \frac{f(x_1) + ... + f(x_n)}{\frac{b-a}{\Delta x}} = \frac{1}{b-a} \sum_{i=1}^n f(x_i) \Delta x$$

$$\lim_{n\to\infty} \frac{1}{b-a} \sum^n_{i = 1} f(x_i) \Delta x = \frac{b-a} \int_a^b f(x) dx$$

- Thus, the varage value of $$f$$ on the interval $$[a, b]$$ is

$$\hat{f} = \frac{1}{b-a} \int_a^b f(x) dx$$

- Alternatively, this can be thought of as

$$\frac{\text{area}}{\text{width}} = \text{average height}$$

---

## 7.1: Integration by Parts
The product rule states that if $$f$$ and $$g$$ are differentiable, then

$$\frac{d}{dx} f(x) g(x) = f(x) g'(x) + g(x) f'(x)$$

We can express this in terms of indefinite integrals:

$$\int [f(x) g'(x) + g(x) f'(x)] dx = f(x) g(x)$$

This can be rearranged as

$$\int f(x) g'(x) dx = f(x) g(x) - \int g(x) f'(x) dx$$

Let $$u = f(x)$$ and $$v = g(x)$$. The integration by parts formula is thus

$$\int u dv = uv - \int v du$$

---

## 7.2: Trigonometric Integrals
- Write an integrand involving powers of sine and coisne in a form where we only have one sine factor and the rest of the expression in terms of cosine, or one cosine factor and the rest of the expression in terms of sine.
  - We can use $$\sin^2 x + \cos^2 x = 1$$.
- We can also use the half-angle identities to address integrand products of $$\sin$$ and $$\cos$$:

$$\sin^2 x = \frac{1}{2} \left(1 - \cos 2x \right)$$

$$\cos^2 x = \frac{1}{2} \left(1 + \cos 2x \right)$$

- For products involving powers of $$\tan x$$ and $$\sec x$$, use $$\tan^2 x = \sec^2 x - 1$$.

---

## 7.3: Trigonometric Substitution
- In finding the area of a circle or ellipse, we encounter an integral of form $$\int \sqrt{a^2 - x^2} dx$$ where $$a > 0$$.
- If we let $$x = a \sin \theta$$, then the identity $$1 - \sin^2 \theta = \cos^2 \theta$$ allows us to get rid of the root sign.

$$\sqrt{a^2 - x^2} = \sqrt{a^2 - a^2 \sin^2 \theta} = a | \cos \theta |$$

- In general, we can make a substitution $$x = g(t)$$ using the substitution rule in reverse.

$$\int f(x) dx = \int f(g(t)) g'(t) dt$$

| Expression | Substitution | Identity |
| --- | --- | --- |
| $$\sqrt{a^2 - x^2}$$ | $$x = a \sin \theta$$, $$-\frac{\pi}{2} \le \theta \le \frac{\pi}{2}$$ | $$1 - \sin^2 \theta = \cos^2 \theta$$ |
| $$\sqrt{a^2 + x^2}$$ | $$x = a \tan \theta$$, $$-\frac{\pi}{2} < \theta < \frac{\pi}{2}$$ | $$1 + \tan^2 \theta = \sec^2 \theta$$ |
| $$\sqrt{x^2 - a^2}$$ | $$x = a\sec \theta$$, $$0\le \frac{\pi}{2}$$ or $$\pi \le \theta < \frac{3\pi}{2}$$ | $$\sec^2 \theta - 1 = \tan^2 \theta$$ |

---

## 7.4: Integration of Rational Functions by Partial Fractions
- We can integrate any rational functions by expressing it as a sum of simple fractions using the partial fraction method.
- Consider the rational function $$f(x) = \frac{P(x)}{Q(x)}$$ - we can express $$f$$ as a sum of two simpler fractions if $$\deg{P} < \deg{Q}$$. Use long division to convert into proper form.
- Express the proper rational function as a sum of partial fractions of the forms

$$\frac{A}{(ax+b)^i} \text{ or } \frac{Ax+B}{(ax^2+bx+c)^j}$$

- Rationalizing substitutions: some nonrational functions can be changed into rational functions by substituting effectively. If the integrand contains $$\sqrt[n]{g(x)}$$, the substitution $$u = \sqrt[n]{g(x)}$$ may be effective.

---

## 7.5: Strategy for Integration
- Integration is more challenging than differentation.
- Simplify the integrand if possible
- Look for an obvious substitution
- Classify the integrand according to its form
  - Trigonometric functions: use trig substitutions
  - Rational functions: use partial fractions
  - Product of functions: use integration by parts
  - Radicals: use a rationalizing substituion or a trigonometric substitution
- Try again

### Can we integrate all continuous functions?
{: .no_toc}

No, not in terms of functions we are familiar with.

- Elementary functions: polynomials, rational functions, power functions, exponential functions, logarithmic functions, trig and inverse trig functions, hyperbolic and inverse hyperbolic functions, functions that can be obtained from these by the five operations of addition, subtraction, multiplication, and composition.
- If $$f$$ is an elementary function, then $$f'$$ is an elementary function, but $$\int f(x) dx$$ is not necessarily an elementary function.
- The majority of elementary functions do not have elementary antiderivatives.

---

## 7.7: Approximate Integration
- There are two situations in which it is impossible to find the exact value of a definite integral.
  - In order to evaluate $$\int_a^b f(x) dx$$, we need to know an antiderivative of $$f$$; finding the antiderivative is impossible or difficult.
  - The function is determined from a scientific experiment trhough instrument readings or collected data - there is no formula for the function.
- A definite integral is a limit of Riemann sums. A Riemann sum is an approximation of the integral.

$$\int_a^b f(x) dx \approx \sum_{i=1}^n f(x_i) \Delta x$$

- We can choose $$x_i$$ as the left, right, or middle endpoint.
- The Trapezoidal rule results from averaging the left and right approximations.
- Approximation technique error analysis:
  - The signs of the left and right error endpoints or opposite.
  - When we double the size of $$n$$, the left and right errors decrease by about a factor of 2.
  - The Trapezoid and Midpoint rles are more accurate than the endpoint approximations.
  - The errors in the Trapezoid and Midpoint Rules are opposite in sign.
  - When we double the size of $$n$$, the trapezoid and midpoint rule errors decrease by about a factor of 4.
  - The size of the error in the midpoint rule is about half the size of the erorr in the trapezoidal rule.
- Simpson's rule - we can use parabolas instead of straight line segments to approximate a curve. With simplifications, we can obtain the approximation

$$\int_a^b f(x) dx \approx \frac{h}{3} (y_0 + 4y_1 + 2y_2 + 4y_3 + ... + 2y_{n-2} + 4y{n-1} + y_n)$$

---

## 7.8 Improper Integrals
- *Improper integral*: there is an infinite discontinuity in $$[a, b]$$ or the integral is taken on an infinite interval.

### Type 1 Integrals - Infinite Intervals
{: .no_toc }
If $$\int_a^t f(X) dx$$ exists for every number $$t \ge a$$, then

$$\int_a^\infty f(x) dx = \lim_{t\to\infty} \int_a^t f(x) dx$$

If $$\int_t^b f(x) dx$$ exists for every number $$t \le b$$, then

$$\int_{-\infty}^b f(x) dx = \lim_{t\to\infty} \int_t^b f(x) dx$$

- Improper integrals are called convergent if the corresponding limit exists, and divergent if it does not.

### Type 2 Integrals - Discontinuous Integrands
{: .no_toc }

If $$f$$ is continuous on $$[a, b)$$ and is discontinuous at $$b$$, then

$$\int_a^b f(x) dx = \lim_{t\to b^-} \int_a^t f(x) dx$$

If $$f$$ is continuous on $$[a, b)$$ and is discontinuous at $$a$$, then

$$\int_a^b f(x) dx = \lim_{t\to a^+} \int_t^b f(x) dx$$

### The Comparison Test
{: .no_toc }

Suppose that $$f$$ and $$g$$ are continuous functions with $$f(x) \ge g(x) \ge 0$$ for $$x \ge a$$.

1. If $$\int_a^\infty f(x) dx$$ is convergent, then $$\int_a^\infty g(x) dx$$ is convergent.
2. If $$\int_a^\infty g(x) dx$$ is divergent, then $$\int_a^\infty f(x) dx$$ is divergent.

---

## 8.1: Arc Length
- What do we mean by the length of a curve?
- If a curve is a polygon, we can easily find its length by adding together the individual line segments.

The length $$L$$ of a curve $$C$$ with equation $$y = f(x), a\le x\le b$$, is

$$L = \lim_{n\to\infty} \sum_{i=1}^n |P_{i-1} P_i|$$

If we let $$\Delta y_i = y_i - y_{i-1}$$, then

$$\|P_{i-1}P_i\| = \sqrt{(\Delta x_i)^2 + (\Delta y_i)^2}$$

**Arc Length Formula.** If $$f'$$ is continuous on $$[a, b]$$, then the arc length of the curve $$y = f(x)$$, $$a\le a\le b$$, is

$$L = \int_a^b \sqrt{1 + f'(x)^2} dx$$

---

## 8.3: Moments and Centers of Mass
- Objective: find a point $$P$$ upon which a thin plate of any given shape balances horizontally. This is the center of mass (or center of gravity) of the plate.
- Consider a rod with negligible mass balanced on a fulcrum with two masses $$m_1$$ and $$m_2$$ and distances from the fulcrum $$d_1$$ and $$d_2$$. In order to balance, the following must be true:

$$m_1 d_1 = m_2 d_2$$

- Law of the Lever - discovered by Archimedes.
- In a system with $$n$$ particles with masses $$m_1, m_2, ..., m_n$$ located at points $$x_1, x_2, ..., x_n$$ on the $$x$$-axis, it can be shown that the center of mass is at

$$\bar{x} = \frac{\sum m_i x_i}{\sum m_i} = \frac{\sum m_i x_i}{m}$$

- The sum of the individual moments is the *moment of the system about the origin*:

$$M = \sum m_i x_i$$

$$m \bar{x} = M$$

- Moment: if the total mass were considered as being concentrated at the center of mass $$\bar{x}$$, then its moment would be the same as the moment of the system.
- Consider a system of $$n$$ particles with masses $$m_1, m_2, ..., m_n$$ located at points $$(x_1, y_1), (x_2, y_2), ..., (x_n, y_n)$$ in the $$xy$$-plane. We have $$M_y$$ (moment of the system about the $$y$$-axis) and $$M_x$$ (moment of the system abuot the $$x$$ axis) as such:

$$M_y = \sum m_i x_i$$

$$M_x = \sum m_i y_i$$

- The coordinates of the center of mass are as such, where $$m = \sum m_i = \text{total mass}$$:

$$\bar{x} = \frac{M_y}{m}$$

$$\bar{y} = \frac{M_x}{m}$$

- Suppose a region $$R$$ lies between two lines $$x = a$$ and $$x = b$$ above the $$x$$-axis and beneath the graph of $$f$$, where $$f$$ is a continuous function.
- We can divide the interval $$[a, b]$$ into $$n$$ subintervals in Riemann-sum-style approximation.
- The centroid of the $$i$$th approximating rectagle is $$C_i \left(\bar{x}_i, \frac{1}{2} f(\bar{x}_i)\right)$$. The area is $$f(\bar{x}_i) \Delta x$$; the mass is

$$\rho f(\bar{x}_i} \Delta x$$

- The moment of $$R_i$$ about the $$y$$-axis is the product of its mass and the distance from $$C_i$$ to the $$y$$-axis, which is $$\bar{x}_i$$; therefore, the following is true:

$$M_y (R_i) = \left[\rho f(\bar{x}_i) \Delta x\right]\bar{x}_i = \rho \bar{x} i) \Delta x$$

- We can take the limit as $$n\to\infty$$ to sum the moments:

$$M_y = \lim_{n\to\infty} \sum_{i=1}^n \rho \bar{x}_i f(\bar{x}_i) \Delta x = \rho \int_a^b xf(x) dx$$

- We can compute the moment of $$R_i$$ about the $$x$$-axis:

$$M_x (R_i) = \left[\rho f(\bar{x}_i \Delta x\right] \frac{1}{2} f(\bar{x}_i) = \rho \cdot \frac{1}{2} [f(\bar{x}_i)]^2 \Delta x$$

$$M_x = \lim_{n\to\infty} \sum_{i=1}^n \rho \cdot \frac{1}{2} [f(\bar{x})]^2 \Delta x = \rho \int_a^b \frac{1}{2} f(x)^2 dx$$

- Finally, we obtain the following formulas for $$\bar{x}$$ and $$\bar{y}$$.

$$\bar{x} = \frac{M_y}{m} = \frac{\int_a^b x f(x) dx}{\int_a^b f(x) dx}$$

$$\bar{y} = \frac{M_x}{m} = \frac{\int_a^b \frac{1}{2} f(x)^2 dx}{\int_a^b f(x) dx}$$

- If a region lies between two curves $$y = f(x)$$ and $$y = g(x)$$, where $$f(x) \ge g(x)$$. The centroid can be found as such:

$$\bar{x} = \frac{1}{A} \int_a^b x[f(x) - g(x)] dx$$

$$\bar{y} = \frac{1}{A} \int_a^b \frac{1}{2} \left\{ f(x)^2 - g(x)^2 \right\}$$

> **Theorem of Pappus.** Let $$R$$ be a plane region that lies entirely on one side of the line $$l$$ in the plane. If $$R$$ is rotated about $$l$$, then the volume of the resulting solid is the product of the area $$A$$ of $$R$$ and the distance $$d$$ traveled byt eh centroid of $$R$$.
> 





