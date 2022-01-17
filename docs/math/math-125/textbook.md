---
layout: default
title: Textbook Notes
parent: MATH 125
grand_parent: Mathematics
nav_order: 2
---

# Textbook Notes

MATH 125
{: .fs-6 .fw-300 }

---

## Navigation

---

## 5.1: Areas and Distances
- When we find the area under a curve or the distance traveled over time, we end up with a special type of limit.
- Measure by using areas, Riemann sums.

$$\lim_{n\to\infty} \sum^n_{i = 1} f(x_i^*} \Delta x = \lim_{n\to\infty} \left[f(x_1^*) \Delta x + f(x_2^*) \Delta x + ... + f(x_n^*) \Delta x \right]$$

---

## 5.2: The Definite Integral

- The definite integral of $$f$$ from $$a$$ to $$b$$ is

$$\int_a^b f(x) dx = \lim_{n\to\infty} \sum^n_{i = 1} f(x_i^*} \Delta x$$

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

$$\frac{g(x+h) - g(x)}{h} = \frac{1}{h} \int_x^{x+h} f(t) dt$$.

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

$$\int \csc ^2x\:dx=-\cot x+C$$

$$\int \csc x\cot x\:dx=-\csc x+C$$

$$\int \frac{1}{\sqrt{1-x^2}}\:dx=\sin ^{-1}x+C$$

$$\int \cosh x\:dx=\sinh x+C$$

---

## 5.5: The Substitution Rule
- Let $$u$$ be some quantity; we integrate with respect to $$du$$ instead of $$dx$$.
- If $$u = f(x)$$, then $$du = f'(x) dx$$.
- The substitution method works whenever we have an integral in the form $$f(g(x)) g'(x) dx$$.

**Substitution Rule**
> If $$u = g(x)$$ is a differentiable function whose range is an interval $$I$$ and $$f$$ is continuous $$I$$, then $$\int f(g(x)) g'(x) dx = \int f(u) du$$.
