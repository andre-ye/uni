---
layout: default
title: Textbook Notes
parent: MATH 124
grand_parent: Mathematics
nav_order: 2
---

# Preclass Video & Textbook Notes

MATH 124
{: .fs-6 .fw-300 }

---

## Navigation
* [Chapter 0](#chapter-0)
* [Chapter 2](#chapter-2)
  + [Section 2.1](#section-21)
  + [Section 2.2](#section-22)
  + [Section 2.3](#section-23)
  + [Section 2.5](#section-25)
  + [Section 2.6](#section-26)
  + [Section 2.7](#section-27)
  + [Section 2.8](#section-28)
* [Chapter 3](#chapter-3)
  + [Section 3.1](#section-31)
  + [Section 3.2](#section-32)
  + [Section 3.3](#section-33)
  + [Section 3.4](#section-34)
  + [Section 3.5](#section-35)
  + [Section 3.6](#section-36)
  + [Section 3.9](#section-39)
  + [Section 3.10](#section-310)
* [Chapter 4](#chapter-4)
  + [Section 4.1](#section-41)
  + [Section 4.3](#section-43)
  + [Section 4.4](#section-44)
  + [Section 4.5](#section-45)
  + [Section 4.7](#section-47)
* [Chapter 10](#chapter-10)
  + [Section 10.1](#section-101)
  + [Section 10.2](#section-102)

---

## Chapter 0

*Task*: Find tangent lines.
- Is the point of tangency given?
  - If yes, use the slope of the radial line and the point to find the tangent line.
  - If no, identify unknowns and solve algebraicly using geometric rules.
  
**Example Problem**

*Question*: Find the equation for all lines that are tangent to the unit circle and pass through the point $$P(3,4)$$.

*Solution*:
1. You want to find the points of tangency $$(a,b)$$ and the slopes of the tangent lines $$m_t$$.
2. The radial slope is $$\frac{b}{a}$$; the tangent slope is thus $$m_t=-\frac{a}{b}$$.
3. The tangent slope can also be written as $$m_t=\frac{4-b}{3-a}$$.
4. Use 2 and 3 to create an relationship: $$-\frac{a}{b}=\frac{4-b}{3-a} \rightarrow -a(3-a)=b(4-b) \rightarrow -3a+a^2 = 4b-b^2 \rightarrow -3a+a^2+b^2=4b$$.
5. The equation of the unit circle is $$a^2 + b^2 = 1$$.
6. Use 4 and 5: $$-3a+1=4b \rightarrow b = -\frac{3}{4}a+\frac{1}{4}$$.
7. Plug back into circle equation: $$a^2 + \left(-\frac{3}{4}a+\frac{1}{4}\right)^2 = 1$$.
8. Expand and simplify: $$a^2 + \frac{9}{16}a^2 - \frac{3}{8}a + \frac{1}{16} = 1 \rightarrow \frac{25}{16}a^2 - \frac{3}{8}a - \frac{15}{16} = 0 \rightarrow 25a^2 - 6a - 15=0$$
9. Solve for $$a$$ using the quadratic formula, yielding $$\frac{6\pm\sqrt{1536}}{50} \approx 0.9, -0.66.$$
10. Find $$b$$ from $$-\frac{3}{4}a+\frac{1}{4}=b$$ to yield $$b\approx -0.43, 0.75$$ (respectively).
11. Find $$m_t$$ from $$m_t=\frac{a}{b}\approx 2.1, 0.89$$ (respectively).
12. Put everything together to yield the tangent lines: $$y+0.43=2.1(x-0.9)$$ and $$y-0.75=0.89(x+0.66)$$.

---

## Chapter 2

### Section 2.1

#### Video Notes
- Developing a more specific understanding of what 'touching' means.
- A tangent line is a point on the curve that almost forms a line when 'zoomed in'.
- We are aiming for the true tangent, but we can obtain an imperfect secant line by sampling two points close to one another on the line.
  - Continually move the two points closer and closer together.
- Limit - moving things closer and closer to a certain target point and measuring the corresponding approaching value.
- Application - position over time, concentration over time, etc.; rate representations. Secant line is average rate of change; the interpretation of the tangent line is the *instantaneous rate of change* - this is the 'current speed'.

#### Textbook Notes
*Section 2.1, "The Tangent Problem"*
- *Tangent* - derived from Latin *tangens*, meaning "touching".
- *Secant* - derived from Latin *secans*, meaning "cutting".
- Limits - the convergence of a function with respect to an independent variable's approach towards some value.


*Section 2.1, "The Velocity Problem"*
- The velocity of a car as it travels through city traffic is not constant.
- How can we define instantaneous velocity?
- Say that the velocity function at time $$t$$ is given by $$v(t)$$. The instantaneous velocity can then be obtained by $$\frac{v(t+\Delta) - v(t)}{\Delta}$$.







### Section 2.2

#### Video Notes
Question: What happens to $$f(x)$$ as $$x$$ approaches some value $$a$$? $$\lim_{x\rightarrow a} f(x)$$

**Three methods**:
- Construct a table. This is inexact but it suffices for the time being.
- Algebra (common sense). As $$x \rightarrow 1$$, $$x^2 \rightarrow 1^2 = 1$$, $$x^2 + 1 \rightarrow 1 + 1 = 2$$.
- Graph. Also an inexact method but suffices. Graph the chart and interpolate between values.

*Definition*: The limit of a function $$f(x)$$ as $$x$$ approaches $$a$$ equals $$L$$ if the values of $$f(x)$$ get aribtrarily close to $$L$$ when $$x$$ is sufficiently close to $$a$$.

- **One-sided limits** - $$\lim_{x\rightarrow 1^+} f(x)$$ may not always be equal to $$\lim_{x\rightarrow 1^-} f(x)$$.
- **What makes a limit fail to exist?** If $$\lim_{x\to a^+} f(x) \neq \lim_{x\to a^-} f(x)$$, the limit does not exist (DNE).
- **Using common sense** - what happens to the numerator or denominator as $$x$$ changes? What is the relationship between the growth/decay patterns?
- **Unbounded growth** - $$\lim_{x\to a} f(x) = \infty$$ or $$\lim_{x\to a} f(x) = -\infty$$.







### Section 2.3

#### Textbook Notes
*2.3 - Calculating Limits Using the Limit Laws*

- **The Sum Law**: the limit of a sum is the sum of the limits. $$\lim_{x\to a} \left[f(x)+g(x)\right] = \lim_{x\to a} f(x) + \lim_{x\to a} g(x)$$.
- **The Difference Law**: the limit of a difference is the difference of the limits. $$\lim_{x\to a}\left[f(x)-g(x)\right] = \lim_{x\to a}f(x) - \lim_{x\to a}g(x)$$.
- **Constant Multiple Law**: the limit of a constant times a function is the constant times the limit of the function. $$\lim_{x\to a} \left[ cf(x) \right] = c \lim_{x\to a} f(x)$$.
- **Product Law**: the limit of a product is the product of the limits. $$\lim_{x\to a}\left[f(x) g(x)\right] = \lim_{x\to a}f(x) \cdot \lim_{x\to a}g(x)$$.
- **Quotient Law**: the limit of a quotient is the quotient of the limits. $$\lim_{x\to a}\frac{f(x)}{g(x)} = \frac{\lim_{x\to a}f(x)}{\lim_{x\to a}g(x)} \text{ if } \lim_{x\to a}g(x) \neq 0$$.
- **Power Law**: the limit of an exponentiated term is the exponentiated limit of the base. $$\lim_{x\to a}\left[f(x)\right]^n = \left[\lim_{x\to a}f(x)\right]^n$$, provided $$n$$ is a positive integer. Derived from applying the product law repeatedly.
- **Constant Law**: the limit of a constant function is the constant. $$\lim_{x\to a}c = c$$.
- **Linear Law**: the limit of the function $$y=x$$ is $$a$$. $$\lim_{x\to a} x = a$$.
- **Exponential Law**: the limit of an exponential function $$y=x^n$$ is $$a^n$$. $$\lim_{x\to a} x^n = a^n$$, where $$n$$ is a positive integer. Derived from power law and linear law.
- **Specific Root Law**: the limit of a root function $$\sqrt[n]{x}$$ is $$\sqrt[n]{a}$$. $$\lim_{x\to a} \sqrt[n]{x} = \sqrt[n]{a}$$, where $$n$$ is a positive integer.
- **General Root Law**: the limit of any function that is $$n$$-rooted is the $$n$$th root of the limit of that function. $$\lim_{x\to a} \sqrt[n]{f(x)} = \sqrt[n]{\lim_{x\to a} f(x)}$$, where $$n$$ is a positive integer.

#### Video Notes
- **Distribution Substitution Property**: if $$f(x)$$ is an algebraic function and $$a$$ is in the domain of $$f$$, then $$\lim_{x\to a} f(x) = f(a)$$.
  - Much of solving for limits is changing the expression of a limit such that the DSP can be used.
- If $$\lim_{x\to a}\frac{P(x)}{Q(x)}$$ is a rational function with $$P(a)=Q(a)=0$$, then $$(x-a)$$ must be a factor of $$P(x)$$ and $$Q(x)$$. Factor it out and remove it from the rational function.
- Useful trick: rationalization in $$\frac{0}{0}$$ cases. Multiply numerator/denominator with square root terms by the conjugate.

**Limit Laws Involving $$\infty$$**

| Limit Type | Result |
|  |  |
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







### Section 2.5
#### Video Notes
- A function is continuous at $$x=a$$ if the graph does not break at $$x=a$$.
- More formally, a function $$f(x)$$ is continuous if $$f(a)$$ exists and $$\lim_{x\to a} f(x) = f(a)$$.
- Limit properties applied to continuity:
  - The sum, difference, and product of continous functions is continuous.
  - The quotient of continuous functions is continuous as long as the denominator is not 0.
  - The composition of continuous functions is continuous.







### Section 2.6
#### Video Notes
- Looking at horizontal asymptotes - what happens when $$x\to\infty$$ in $$f(x) = \frac{1}{x}$$, for instance?
- Approach methods:
  - Plug in large values and see what the function approaches.
  - Graphing; analyze where graph ends approach.
- Not all functions have a horizontal asymptote. $$\lim_{x\to\infty} 3x+7 = \infty$$, for instance.
- Horizontal asymptote of $$y = \arctan(x)$$ - $$\lim_{x\to\infty} = \frac{\pi}{2}$$, $$\lim_{x\to-\infty} = -\frac{\pi}{2}$$.
- Rules for computing $$x\to\pm \infty$$:
  - $$\lim_{x\to\infty} \frac{1}{x^r} = 0$$ for $$r>0$$.
  - $$\lim_{x\to\infty} a^x = \infty$$ for $$a > 1$$; $$0$$ for $$a < 1$$.
  - $$\lim_{x\to-\infty} a^x = 0$$ for $$a > 1$$; $$\infty$$ for $$a < 1$$.
  - Polynomials: identify the term with the highest power; only that term plays the important role.

#### Textbook Notes
*Examples 4 and 5 in Section 2.6*

Find the horizontal and vertical asymptotes of the graph of the function $$f(x) = \frac{\sqrt{2x^2+1}}{3x-5}$$.

> Vertical asymptotes can be found when the denominator is equal to 0; $$3x-5=0 \implies x = \frac{5}{3}$$.

> Horizontal asymptotes can be found via $$\lim_{x\to\infty} \frac{\sqrt{2x^2+1}}{3x-5} \implies \lim_{x\to \infty }\frac{\sqrt{\frac{2x^2+1}{x^2}}}{\frac{3x-5}{x}} \implies \lim_{x\to \infty }\frac{\sqrt{2+\frac{1}{x^2}}}{3-\frac{5}{x}} \implies \frac{\lim _{x\to \infty }\left(\sqrt{2+\frac{1}{x^2}}\right)}{\lim _{x\to \:\infty }\left(3-\frac{5}{x}\right)} \implies \frac{\sqrt{2}}{3}$$.

Compute $$\lim_{x\to \inf\left(\sqrt{x^2+1}-x\right)$$.

> Multiply by conjugate radical: $$\lim_{x\to \infty }\frac{\left(\sqrt{x^2+1}-x\right)\cdot \left(\sqrt{x^2+1}+x\right)}{\sqrt{x^2+1}+x} = \lim_{x\to \infty }\frac{1}{\sqrt{x^2+1}+x} = 0$$.








### Section 2.7
#### Video Notes
- When $$x\to a$$, the slope of the secant line will approach the slope of the tangent line.

$$f'(x) = \lim_{x\to a}\frac{f(x) - f(a)}{x-a}$$

- $$f'(a)$$ is the derivative of $$f$$ at $$x=a$$.

#### Textbook Notes
Examples 2, 3, and 4 in Section 2.7.

*Find an equation of the tangent line to the hyperbola $$y = \frac{3}{x}$$ at the point $$(3,1)$$.*

The slope of the tangent line can be found using the formal definition of a derivative.

$$m = \lim_{h\to 0} \frac{f(3+h) - f(3)}{h} = \lim_{h\to 0} \frac{\frac{3}{3+h} - 1}{h} = \lim_{h\to 0} \frac{-h}{h(3+h)$$

$$ = \lim_{h\to 0} -\frac{1}{3+h} = -\frac{1}{3}$$

*Suppose a ball is dropped from the upper observation deck of the CN Tower 450 meters above the ground. What is the velocity fo the ball after 5 seconds?*

We need to use $$f(t) = 4.9t^2$$; we obtain $$f'(x) = \lim_{h\to 0} \frac{4.9\cdot(t+h)^2 - 4.9t^2}{h} = \lim_{h\to 0} 4.9(2t+h) = 9.8t$$. The velocity after 5 seconds is $$f'(5) = 49 m/s$$. 

*Find the derivative of the function $$f(x) = x^2 - 8x + 9$$ at the number $$a$$.

Simplifying $$f'(a) = \lim_{x\to 0} \lim_{h\to 0}\frac{\left[\left(a+h\right)^2-8\left(a+h\right)+9\right]-\left[a^2-8a+9\right]}{h} = \lim_{h\to 0}\frac{2ah+h^2-8h}{h} = \lim _{h\to 0}\left(2a+h-8\right) = 2a-8$$. The derivative of $$f$$ at $$a$$ is the slope of the tangent line. If $$f'(a)$$ exists, we say that $$f$$ is differentiable at $$(a, f(a))$$.







### Section 2.8
#### Video Notes
- $$a$$ is now varying - it is variable, not a point. We can rewrite the definition of a limit as

$$f'(x) = \lim_{h\to 0} \frac{f(x+h) - f(x)}{h}$$

- The derivative of a line is a constant function - its slope.
- When drawing the derivative grpah, look for (local) minima and maxima.
- Engage in analysis of positive and negative derivatives.
- Note when the slope gets smaller and when it gets larger.
- Differentiability: the limit exists for $$f(x)=x^2$$ but not for $$f(x) = |x|$$ at $$x=0$$; thus the absolute value function is not differentiable at that point.
- If $$f$$ is differentiable at $$a$$, then $$f$$ is continuous at $$a$$. If $$f$$ is not continuous at $$a$$, then $$f$$ is not differentiable at $$a$$.


---

## Chapter 3



### Section 3.1
#### Textbook Notes

$$\frac{d}{dx} (c) = 0$$

$$\frac{d}{dx} x^n = nx^{n-1}$$

#### Video Notes
- We will work on formulas in which taking the limit is too tedious and not necessary anymore.
- Important differentiation rules:

$$\frac{d}{dx} x^n = nx^{n-1}$$

$$\frac{d}{dx} e^x = e^x$$

$$\frac{d}{dx} (f(x) + g(x)) = \frac{d}{dx} f(x) + \frac{d}{dx} (x)$$

$$\frac{d}{dx} cf(x) = c \frac{d}{dx} f(x)$$







### Section 3.2
#### Video Notes
- Stick to the rules that have been learned so far.
- Constant rule, power rule, function sum rule.
- Entering areas in which our intuition is wrong.

$$(f\cdot g)' \neq f' \cdot g'$$

- Product and quotient rules.

#### Textbook Notes
Find equations of the tangent line and normal line to the curve $$y=x\sqrt{x}$$ at the point $$(1,1)$$.

By the power rule, we have that $$f'(x) = \frac{3}{2}x^{\frac{1}{2}} = \frac{3}{2}\sqrt{x}$$. The slope of the tangent line at $$(1,1)$$ is thus $$f'(1) = \frac{3}{2}$$, yielding the equation $$y = \frac{3}{2}x - \frac{1}{2}$$. The equation of the normal line uses the negative reciprocal slope: $$y = -\frac{2}{3}x + \frac{5}{3}$$.

Product Rule: $$\left(f(x)g(x)\right)'; h'(x) = f(x)g'(x) + f'(x)g(x)$$

Quotient Rule: $$\left(\frac{f(x)}{g(x)}\right) = \frac{g(x)f'(x) - f(x)g'(x)}{g(x)^2}$$







### Section 3.3
#### Video Notes
- Derivative of trigonometric functions - $$\sin x$$ and $$\cos x$$.
- $$\lim_{h\to 0} \frac{\sin(h)}{h} = 1$$; $$\lim_{h\to 0}{\sin(\text{BLAH!})}{\text{BLAH!}} = 1$$.
- $$\frac{d}{dx} \sin(x) = \cos(x)$$
- $$\frac{d}{dx} \cos(x) = -\sin(x)$$







### Section 3.4

- So far we know about a few derivatives. We can perform basic operations with these functions. 
- We always use 'pure $$x$$' - for instance, we can find $$2\cos(x)$$ but not $$\cos(2x)$$.
- We can use the chain rule to understand the derivative of $$f(g(x))$$.

| Version | Rule |
|  |  |
| Physics | $$y = f(g(x))$$, $$g(x) = u$$, then $$\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx}$$ |
| Algebra | $$\frac{d}{dx} f(g(x)) = f'(g(x))\cdot g'(x)$$ |

- Put a 'blind eye' on the inputs of the outer function, the "outer derivative".
- We can generalize this: $$\frac{d}{dx} f(g(h(x))) = f'(g(h(x))) \cdot g'(h(x)) \cdot h'(x)$$.
- We can indicate higher-order derivatives as such: the $$n$$th derivative is $$f^{(n)} x$$. 

| $$f$$ | $$f'$$ | $$f''$$ |
|  |  |  |
| increases | $$>0$$ | - |
| decreases | $$<0$$ | - |
| concave up | $$f'$$ increases | $$>0$$ |
| concave down | $$f'$$ decreases | $$<0$$ |









### Section 3.5
#### Logarithmic and Exponential Derivatives

What is $$\frac{d}{dx} a^x$$ and $$\lim_{h\to 0}\frac{a^h - 1}{h}$$?

$$\frac{d}{dx} a^x = \frac{d}{dx} e^{x\ln(a)} = e^{x\ln(a)} \cdot \ln(a) = e^{\ln(a^x)} \cdot \ln(a) = a^x \cdot \ln(a)$$

$$\implies \frac{d}{dx} a^x = a^x \cdot \ln(a)$$

$$\lim_{h\to 0}\frac{a^h - 1}{h} = \ln(a)$$

#### Implicit Differentiation
Given a curve in the $$xy$$-coordinate system in which each $$x$$ gives rise to a $$y$$, but cannot be expressed as an explicit function $$y=...$$.

Example: find $$y'$$ in $$x^3 + xy + y^3 = 1$$.

> Even if we don't have an explicit formula, we treat each $$y$$ as a function of $$x$$: $$x^3 + xy(x) + y(x)^3 = 1$$. Take the derivative: $$3x^2 + (1\cdot y(x)) + x\cdot y'(x)) + 3y(x)^2\cdot y'(x) = 0$$. Solve for $$y'(x)$$ by simplifying, factoring out $$y'(x)$$, and re-arranging.

Steps for implicit differentiation:
1. Differentiate
2. Plug in points, if possible/given.

#### Inverse Trigonometric Functions
Goal - derive $$\frac{d}{dx} \arcsin x = ?, \frac{d}{dx} \arccos x = ?, \frac{d}{dx} \arctan x = ?$$.

Find $$y'$$ if $$y = \arcsin(x)$$. Apply $$\sin$$ to both sides: $$\sin y = \sin(\arccos x) \implies \sin y = x \implies \cos(y) \cdot y' = 1 \implies y' = \frac{1}{\cos y} = \frac{1}{\cos(\arcsin(x))}$$. This result can be simplified as $$y' = \frac{1}{\sqrt{1 - x^2}$$.

The remaining derivatives can be derived:

$$\frac{d}{dx} \arccos x = -\frac{1}{\sqrt{1-x^2}}; \frac{d}{dx} \arctan x = \frac{1}{1+x^2}$$








### Section 3.6
What is the derivative of $$y = \ln x$$? $$e^y = e^{\ln x} \implies e^y = x$$; take the implicit derivative, we obtain $$e^y \cdot y' = 1 \implies y' = \frac{1}{e^y} \implies y' = \frac{1}{x}$$.

$$(\log_a x)' = \frac{1}{x\cdot \ln a}$$

Logarithmic differentiation: sometimes, it is worth thinking about a new way to differentiate. Call the function $$y$$; take the natural log of both sides, differentiate both. Use log rules to simplify complex problems (quotients, products, etc.).

When $$x$$ is in the base, use power rule. When $$x$$ is in the exponent, rewrite using natural logarithm nd $$e$$ method. What is $$x$$ is both in the base *and* in the exponent? Use logarithmic differentiation.







### Section 3.9

- Often, one quantity is related to another.
- We are given that one change results in the change of another variable.

Scheme
1. Make a sketch
2. Identify rate of changes you know, and the desired rate of change in terms of derivatives
3. Find functions to relate the quantities
4. Implicitly differentiate w.r.t. $$t$$
5. Solve for the derivative you need
6. Plug in all known values







### Section 3.10
- Linearization/linear approximation.
- Say you have a very complex function you want to evaluate. Find the line tangent to a convenient value.
- When we are very close to a tangent point, we can approximate the functional value by going on the tangent value rather than the original value.
- Given a function $$f$$, is there an easy way to find a functional value $$f(a)$$?
  - *Easy* - using arithmetic operations.
  - *Hard* - ln, sin, cos, tan, square roots, exponentials.

> Given $$f$$ and the tangent line $$L(x)$$ to the curve at $$a$$, if $$x \approx a$$ then $$f(x) \approx L(x)$$. The tangent line is a linear approximation, linearization, or tangent line approximation.

- Is an estimate an overestimate or an underestimate? Look at the concavity of the curve by taking the second derivative. If the curve is concave down, it is an overestimate; if the curve is concave up, it is an underestimate.


---

## Chapter 4

### Section 4.1
- We can analyze a function that allows us to sketch a pretty accurate graph using derivatives.
- Local extrema: a point that is higher or lower than the points around it. The derivative is zero or does not exist.

Fermat's Theorem: If $$f$$ has a local maximum or a local minimum at $$c$$ and $$f'(c)$$ exists, then $$f'(c)=0$$.

- Candidates for local extrema are at places where $$f'=0$$ or $$f'=DNE$$. Thes are critical numbers.
- Not all critical numbers are local extrema. For instance, $$x^3$$.
- To find critical numbers, factor negative powers, denominators, and common factors. Then, clean up.
- Absolute max/min value - highest/lowest value a function takes on.
- In a limited bound problem, always compare the zero-derivative solutions to the ends.








### Section 4.3
- If $$a$$ is in the domain of $$f$$ and $$f'(a) = 0$$ or $$f'$$ is not defined at $$a$$, then $$a$$ is a critical number and a candidate for local minima or extrema.
- Change in sign of the derivative indicates local extrema if $$f$$ is continuous at the critical number.
- The second derivative tells us about the shape of the curve.
- $$f''(a) < 0$$: concave down, $$f''(a) > 0$$: concave up. $$a$$ is a critical number candidate.
- If the second derivative is $$f''(a) = 0$$, the critical point is not a local extrema.
- Note:
  - Only valid if the first and second derivatives exist.
  - Requires quite a bit of computation.







### Section 4.4
- Recall limits: if we have a zero-over-zero type, we factor/use other algebraic tools and simplify, then use direct substitution property. 
- For limits to infinity, divide by highest power and utilize simplification of terms to zero.
- $$\lim_{x\to 0} \frac{\sin x}{x} = 1$$; geometric argument, sandwich theorem.

**L'Hopital's rule takes care of all these situations:** $$\frac{0}{0} and \frac{\pm\infty}{\pm\infty}$$. Does not take care of $$[\infty - \infty]$$, etc. cases.

Suppose $$f$$ and $$g$$ are differentiable and that $$g'(x) \neq 0 $$ near $$a$$, except possibly at $$a$$:

$$\lim_{x\to a} \frac{f(x)}{g(x) = \lim_{x\to a} \frac{f'(x)}{g'(x)}$$

The type often changes when taking the derivative. Also works with limits $$x\to a$$.

$$f(x)$$ and $$g(x)$$ look very similar to their linearization when zoomed in to the scale of the limit. The approximation becomes exact. 

Tricks to transform: purposefully create a fraction by dividing by a reciprocal to use L'Hopital. Bring powers down by taking the logarithm and later adjust by raising the answer to a power.








### Section 4.5
With curve function, determine the following:
- Domain of $$f$$
- Compute $$y$$ and $$x$$ intercept
- Horizontal asymptotes (limits $$x$$ to $$\pm\infty$$)
- Find $$f'$$ and critical numbers, where $$f$$ is increasing/decreasing, and local maxima/minima
  - Critical numbers must be in the domain of the function.
- Find $$f''$$ and where $$f''(x) = 0$$, concavity, inflection points.
- Symmetry - $$f(-x) = f(x)$$, $$f(-x) = -f(x)$$








### Section 4.7
- Optimization - something is being maximized or minimized.
- We need to come up with formulas and solve in a targeted method.
- Sketch the situation and perform a close reading.
- Find the variable that must be maximized or minimized, and find the formula for it.
- What is the constraint? (a given/set constant). Find an equation and use it such that there is only one variable left in the original function.
- Find critical numbers of the function.
- Compare end points and critical numbers.

---

## Chapter 10

### Section 10.1
$$t$$ -t time. $$x,y$$ - position. New interpretations can be developed later.

- *Uniform linear motion* - constant speed and on a straight line. $$x=at+b, y=ct+d$$; $$a, b, c, d$$ are constants.
  - To find the path in the $$xy$$ coordinate system, cancel out the parameter $$t$$.
  - In uniform linear motion, the speed is $$\sqrt{a^2 + c^2}$$.
- *Uniform circular motion* - modeled as $$x = x_c + r\cos(\theta_0 + \omega t)$$, $$y = y_c + r\sin(\theta_0 + \omega t)$$; where $$(x_c, y_c)$$ is the circle center, $$r$$ is the circle radius, $$\nu = \frac{\Delta \text{distance}}{\Delta \text{time}}$$, $$\omega = \frac{\Delta \theta}{\Delta t}$$ (radians/time); $$\theta_0$$ is initial angle at $$t=0$$.
  - Important fact: $$\nu = \omega r$$, $$\cos^2(a) + \sin^2(a) = 1$$
  - Solve for $$\cos(blah)$$ and $$\sin(blah)$$ to utilize Pythagorean identity.


### Section 10.2
For **Uniform Linear Motion**
We have $$x=at+b, y=ct+d$$.

Horizontal velocity is given by $$x'$$, vertical velocity is given by $$y'$$. The speed is $$\sqrt{x'^2 + y'^2}$$.

Tangent lines to a parametric curve - asking in the $$xy$$ system, the $$t$$ parameter is eliminated.

Use **Chain Rule** - $$\frac{dy}{dx} = \frac{\frac{dy}{dt}}{\frac{dx}{dt}}$$.

*Second derivative* for parametric equations: $$\frac{d}{dx}\left(\frac{dy}{dx}\right) = \frac{d^2 y}{(dx)^2}$$. Consider $$\frac{dy}{dx}$$ to be your new $$y$$; $$\tilde{y}$$ - you thus need to find $$\frac{d\tilde{y}}{dx}$$.

---



