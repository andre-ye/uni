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




























