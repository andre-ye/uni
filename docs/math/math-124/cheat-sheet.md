---
layout: default
title: Cheat Sheet
parent: MATH 124
grand_parent: Mathematics
nav_order: 100
---

# Cheat Sheet

MATH 125
{: .fs-6 .fw-300 }

---

## Navigation
- [Limits](#limits)
  * [Limit Laws](#limit-laws)
  * [Limit Case Dynamics](#limit-case-dynamics)
  * [Methods to Solve Limits](#methods-to-solve-limits)
  * [Asymptotes](#asymptotes)
  * [Limits to Infinity](#limits-to-infinity)
- [Derivatives](#derivatives)
  * [Formal Definition](#formal-definition)
  * [Derivative Patterns](#derivative-patterns)
  * [Fundamental Differentiation Formulas](#fundamental-differentiation-formulas)
  * [Function Specific Differentiation Formulas](#function-specific-differentiation-formulas)
  * [Differentiation Techniques](#differentiation-techniques)



---



## Limits

### Limit Laws

| Law | Equation |
| --- | --- |
| Sum Law | $$\lim_{x\to a} \left[f(x)+g(x)\right] = \lim_{x\to a} f(x) + \lim_{x\to a} g(x)$$ |
| The Difference Law | $$\lim_{x\to a}\left[f(x)-g(x)\right] = \lim_{x\to a}f(x) - \lim_{x\to a}g(x)$$ |
| Constant Multiple Law | $$\lim_{x\to a} \left[ cf(x) \right] = c \lim_{x\to a} f(x)$$ |
| Product Law | $$\lim_{x\to a}\left[f(x) g(x)\right] = \lim_{x\to a}f(x) \cdot \lim_{x\to a}g(x)$$ |
| Quotient Law | $$\lim_{x\to a}\frac{f(x)}{g(x)} = \frac{\lim_{x\to a}f(x)}{\lim_{x\to a}g(x)} \text{ if } \lim_{x\to a}g(x) \neq 0$$ |
| Power Law | $$\lim_{x\to a}\left[f(x)\right]^n = \left[\lim_{x\to a}f(x)\right]^n$$ |
| Constant Law | $$\lim_{x\to a}c = c$$ |
| Linear Law | $$\lim_{x\to a} x = a$$ |
| Exponential Law | $$\lim_{x\to a} x^n = a^n$$ | 
| Specific Root Law | $$\lim_{x\to a} \sqrt[n]{x} = \sqrt[n]{a}$$ |
| General Root Law | $$\lim_{x\to a} \sqrt[n]{f(x)} = \sqrt[n]{\lim_{x\to a} f(x)}$$ |

### Limit Case Dynamics

| Limit Type | Result |
| --- | --- |
| $$c + \infty$$ | $$\infty$$ |
| $$c - \infty$$ | $$-\infty$$ |
| $$\infty + \infty$$ | $$\infty$$ |
| $$-\infty-\infty$$ | $$-\infty$$ |
| $$\infty-\infty$$ | Needs further work |
| $$c\cdot \infty$$, $$c>0$$ | $$\infty$$ |
| $$c\cdot \infty$$, $$c<0$$ | $$-\infty$$ |
| $$0 \cdot \infty$$ | Needs further work |
| $$\infty \cdot \infty$$ | $$\infty$$ |
| $$\infty \cdot -\infty$$ | $$-\infty$$ |
| $$-\infty\cdot-\infty$$ | $$\infty$$ |
| $$\frac{c}{\pm\infty}$$ | $$0$$ |
| $$\frac{\pm\infty}{\pm\infty}$$ | Needs further work |
| $$\frac{0}{0}$$ | Needs further work |
| $$\frac{c}{0}$$ | Needs further work |

### Methods to Solve Limits
- **Distribution Substitution Property**: if $$f(x)$$ is an algebraic function and $$a$$ is in the domain of $$f$$, then $$\lim_{x\to a} f(x) = f(a)$$. Much of solving for limits is changing the expression of a limit such that the DSP can be used.
- If $$\lim_{x\to a}\frac{P(x)}{Q(x)}$$ is a rational function with $$P(a)=Q(a)=0$$, then $$(x-a)$$ must be a factor of $$P(x)$$ and $$Q(x)$$. Factor it out and remove it from the rational function.
- In $$\frac{0}{0}$$ cases, use rationalization. Multiply numerator/denominator with square root terms by the conjugate.

### Asymptotes
To find horizontal asymptotes of $$f(x)$$, compute $$\lim_{x\to\pm\infty} f(x)$$.

Rules for computing $$x\to\pm\infty$$:
- $$\lim_{x\to\infty} \frac{1}{x^r} = 0$$ for $$r>0$$.
- $$\lim_{x\to\infty} a^x = \infty$$ for $$a > 1$$; $$0$$ for $$a < 1$$.
- $$\lim_{x\to-\infty} a^x = 0$$ for $$a > 1$$; $$\infty$$ for $$a < 1$$.
- Polynomials: identify the term with the highest power; only that term plays the important role.

### Limits to Infinity

- In a polynomial, the highest power domnates the long term behavior.
- In rational functions, the highest power dominates.
  - If roots are involved in a rational function, like $$\lim_{x\to -\infty }\frac{\sqrt{x^2+4x}-2x}{x+4}$$, make sure you take into account the negative sign of limits to negative infinity when pulling division by the highest polynomial term into the root.
- $$r^x$$ dominates over every $$x^r$$ (taking into account directionality of the exponential).

*Technique*: When taking a limit towards infinity or negative infinity for functions involving polynomial terms, find a way to divide all terms by the term by the highest polynomial term. For instance, when calculating $$\lim_{x\to \infty }\frac{5x^4+x^3}{4x^4-9x}$$ one would divide the terms in the numerator and the denominator by $$x^4$$: 

$$\lim_{x\to \infty }\frac{\frac{5x^4}{x^4}+\frac{x^3}{x^4}}{\frac{4x^4}{x^4}-\frac{9x}{x^4}}=\li _{x\to \:\infty \:}\frac{5+x^{-1}}{4-9x^{-3}}=\frac{5}{4}$$



---



## Derivatives
### Formal Definition
When $$x\to a$$, the slope of the secant line will approach the slope of the tangent line.

$$f'(x) = \lim_{x\to a}\frac{f(x) - f(a)}{x-a}$$

$$f'(a)$$ is the derivative of $$f$$ at $$x=a$$. The units of the derivative are $$\frac{y \text{ unit}}{x \text{ unit}}$$.

### Derivative Patterns
- When $$f(x)$$ is increasing, $$f'(x)$$ is positive.
- When $$f(x)$$ is decreasing, $$f'(x)$$ is positive.
- When $$f(x)$$ is at a local minima or maxima, $$f'(x) = 0$$.
- When $$f(x)$$ is convex (pointing up, smiling face), $$f'(x)$$ is increasing.
- When $$f(x)$$ is concave (pointing down, frowning face), $$f'(x)$$ is decreasing.

### Fundamental Differentiation Formulas

| Name | Rule |
| --- | --- |
| Constant Function Rule | $$\frac{d}{dx} c = 0$$ |
| Power Rule | $$\frac{d}{dx} x^n = nx^{n-1}$$ |
| Euler Number Rule | $$\frac{d}{dx} e^x = e^x$$ |
| Constant Multiplier Rule | $$(cf)' = cf'$$ |
| Function Sum Rule | $$(f + g)' = f' + g'$$ |
| Function Difference Rule | $$(f-g)' = f' - g'$$ |
| Function Product Rule | $$(fg)' = fg' + gf'$$ |
| Function Quotient Rule | $$\left(\frac{f}{g}\right)' = \frac{gf' - fg'}{g^2}$$ |
| Chain Rule | $$\frac{d}{dx} f(g(x)) = f'(g(x))\cdot g'(x)$$ |

Note that the limit $$\lim_{h\to 0} \frac{\sin(h)}{h} = 1$$.

### Function Specific Differentiation Formulas

| Function | Derivative |
| --- | --- |
| $$\ln x$$ | $$\frac{1}{x}$$ |
| $$a^x$$ | $$a^x \ln(a)$$ |
| $$\log_a (x)$$ | $$\frac{1}{x\ln (a)}$$ |
| $$\sin x$$ | $$\cos x$$ |
| $$\cos x$$ | $$-\sin x$$ |
| $$\tan x$$ | $$\frac{1}{\cos^2 x} = \sec^2 x$$
| $$\csc x$$ | $$-\frac{\cos x}{\sin^2 x} = -\cot x \cdot \csc x$$ |
| $$\sec x$$ | $$\frac{\sin x}{\cos^2 x} = \tan x \cdot\sec x$$ |
| $$\cot x$$ | $$-\frac{1}{\sin^2 x} = -\csc^2 x$$ |
| $$\sin^{-1} x$$ | $$\frac{1}{\sqrt{1-x^2}}$$ |
| $$\cos^{-1} x$$ | $$-\frac{1}{\sqrt{1-x^2}}$$ |
| $$\tan^{-1} x$$ | $$\frac{1}{1+x^2}$$ |

### Differentiation Techniques

- *Implicit differentiation*. If a curve cannot be written explicitly as $$y = ...$$, differentiate both sides of the equation, treat $$y$$ as a function of $$x$$ and thus use chain rule to differentiate, solve for $$y'$$.
- *Parametric differentiation*. If you are given $$x=x(t)$$ and $$y=y(t)$$, solve for $$\frac{\frac{dy}{dt}}{\frac{dx}{dt}}$$.
- *Logarithmic differentiation*. For complex derivatives as well as derivatives of functions in the form $$f(x)^{g(x)$$, use logarithmic differentiation by taking the log of both sides and implicitly differentiating, then solving for $$y'$$.



---



## Derivative Applications

### Real Life Rates
Often, in real-world problems we want to understand the dynamics of related rates - as one quantity changes, another desired quantity correspondingly changes.

1. Use geometric tools to establish a mathematical relationship.
2. Identify known variables and derivatives.
3. Implicitly differentiate the mathematical relationship with respect to time or a different appropriate variable.
4. Plug in knowns and solve for the desired derivative.

### Linearization
We can approximate the value of a function by using the line tangent to a nearby convenient point.

Consider a convenient point $$(c_x, c_y)$$, a desired point $$(d_x, d_y)$$, and a function to be evaluated $$f$$.

$$d_y = f'(d_x - c_x) + c_y$$

### Critical Points
- Critical numbers exist where the derivative is zero or does not exist.
- All extrema are critical numbers, but not all critical numbers are extrema.
- When solving for when the derivative is equal to 0, factor but do not get rid of solutions.
- When solving for absolute extrema within a defined domain $$[a, b]$$, make sure to consider $$x=a$$ and $$x=b$$ as candidates.

### L'Hopital's Rule

$$\lim \frac{f(x)}{g(x)} = \lim \frac{f'(x)}{g'(x)}$$

- Works only for 0/0 or infty/infty.
- When working with roots, it may be easier not to use L'Hopital's rule.
- Indeterminate limit types require more work.
- Rewrite $$fg$$ as $$\frac{f}{\frac{1}{g}}$$ or $$\frac{g}{\frac{1}{f}}$$ to use L'Hopital's.
- For $$[\infty - \infty]$$, factor out like $$f - g = f\left(1 - \frac{g}{f}\right)$$
- For exponential limits, use a logarithmic approach.
