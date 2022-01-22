---
layout: default
title: Lecture Notes
parent: MATH 124
grand_parent: Mathematics
nav_order: 1
---

# Lecture Notes

MATH 124
{: .fs-6 .fw-300 }

---

## Navigation
- [Week 1 Friday](#week-1-friday)
- [Week 2 Monday](#week-2-monday)
- [Week 2 Wednesday](#week-2-wednesday)
- [Week 2 Friday](#week-2-friday)
- [Week 3 Monday](#week-3-monday)
- [Week 3 Wednesday](#week-3-wednesday)
- [Week 3 Friday](#week-3-friday)
- [Week 4 Monday](#week-4-monday)
- [Week 4 Wednesday](#week-4-wednesday)
- [Week 4 Friday](#week-4-friday)
- [Week 5 Monday](#week-5-monday)
- [Week 5 Wednesday](#week-5-wednesday)
- [Week 6 Monday](#week-6-monday)
- [Week 6 Wednesday](#week-6-wednesday)
- [Week 6 Friday](#week-6-friday)
- [Week 7 Monday](#week-7-monday)
- [Week 7 Wednesday](#week-7-wednesday)
- [Week 8 Wednesday](#week-8-wednesday)
- [Week 8 Friday](#week-8-friday)
- [Week 9 Monday](#week-9-monday)
- [Week 9 Wednesday](#week-9-wednesday)
- [Week 10 Monday](#week-10-monday)
- [Week 10 Wednesday](#week-10-wednesday)

---

## Week 1 Friday

Questions to Collect:
- What is it?
- How to compute it?
- Applications?
- Special cases?
- Properties

Tangent Lines to Circles
- Tangent Line intesects with circle exactly one time.
- Tool - make use of the fact that radial line through point of tangency and tangent line are perpendicular ($$m_t = -\frac{1}{m_r}$$).
- One problem in which point of tangency is given, another type in which the point of tangency is not given.
  - When the point of tangency is given, we need to obtain three equations to solve for the three variables ($$(a,b)$$ - point of tangency and $$m_t$$ - tangent line slope).
    - Circle equation - $$a^2 + b^2 = r^2$$
    - Slope of the tangent line - $$m_t = -\frac{a}{b}$$
    - Slope of the tangent line with intersecting point $$(h_x, h_y)$$ - $$m_t = \frac{b-h_y}{a-h_x}$$m

Tangent Lines to Graphs of Functions
- Zoom in until graph does not show a curve.
- Instantaneous rate of change.
- Algebraically, begin with a secant line; note the slope; move the other point closer until you obtain a closer estimate.
- Take secant slope - $$\lim_{x\rightarrow}\frac{f(x) - f(a)}{x-a}$$.

Do in-class problems for practice on quiz.



---



## Week 2 Monday
- Rise over run - $$\lim_{a \to 0} \frac{f(x) - f(a)}{x-a}$$; the limit of the difference quotient.
  - $$x$$ is the point $$a$$ gets closer too.
- On the Thursday quiz, you must be able to describe the secant line approach.
- Secant line - average rate of changes. Tangent line - instantaneous rate of change.
- Currently, our tools do not allow us to evaluate limits nicely.
- Today's section: take away difference quotience and discuss limits in full generality.
- Limit of a function - look closer and closer to a certain point.
- Never look at the point itself.
- One-sided limits: $$\lim_{x\to a^+}$$ vs $$]lim_{x \to a^-}$$
- Methods: tables, ommon sense, graphing.
- WHen does a limit not exist? When the positive and negative values are not equal, or when the limit is infinite. Consider $$\lim_{x\to a} \sin\left(\frac{1}{x}\right)$$; gets 'infinitely squished' near $$x=0$$ and we cannot discern any direction at all.
- $$x=a$$ is the vertical asymptote in cases of infinite limits.



---



## Week 2 Wednesday
- The tangent line slope can only be found if we know how to calculate limits.
- First, identify the limit type and observe the simplified outcome - this is $$\frac{0}{0}$$ type, this is $$c$$ type, etc.
- If plugging in is defined, use the limit laws to solve; a large limit problem can be split into smaller chunks as long as everything is defined.
  - *Direct Substitution Property*: if $$f$$ is an algebraic function and $$a$$ is in the domain, then $$\lim_{x\to a} f(x) = f(a)$$.
- If plugging in obtains something weird - infinity, dividing by zero, etc.
  - If $$\frac{c}{0}$$ case, check vertical asymptotes.
  - If is $$0\times\infty$$, $$\infty-\infty$$, $$\frac{\pm\infty}{\pm\infty}$$, or $$\frac{0}{0}$$ type, use algebra to transofrm the limit into a different type.
- Algebraic tools: factorization, rationalization, simplification, common denominator, squeeze theorem.
- Sandwich/Squeeze Theorem: if two squeezing functions have the same limit at some point, the squeezed function must also have the same limit at that point.



---



## Week 2 Friday
- Continuity of functions at a place $$x=a$$.
  - $$f$$ is continuous at $$a$$ if the graph does not break at $$a$$.
  - $$f$$ is continuous at $$a$$ if $$\lim_{x\to a} f(x) = f(a)$$.
  - $$f$$ is continuous if it is continuous at all places onthe domain.
- New interpretation of DSP: algebraic functions are continuous on their domain. 
- Example: $$\frac{|x+3|}{x+3}$$ is continuous for all $$x\neq -3$$ because it is a well-defined combination of well defined continuous functions.



---



## Week 3 Monday
- *Asymptotos* - never falling together.
- We already have vertical asymptotes in our toolbox; we can similar discuss horizontal asymptotes.
- The only space for the graph to get closer and closer but never touch is to $$-\infty$$ and $$\infty$$.
- Horizontal asymptotes must come with $$x\to\pm\infty$$.
- Understand the behavior of a function far to the right and far to the left; a function can have at most two horizontal asymptotes.
- If $$f(x)$$ becomes constant to one side, the outcome of the one-sided limits to infinity are the respective horizontal asymptotes of the function $$f(x)$$.
- You can have an asymptote on one side and none on the other.
- Algebraic tools to find limits to infinity:
    - In a polynomial, the highest power dominates the long term behavior.
    - Rational functions - the highest power dominates.
    - $$e^x$$ dominaates over every $$x^r$$.
    - Limit types $$[\infty - \infty]$$ and $$\left[\pm\frac{\infty}{\infty}\right]$$ need more algebra toget a different type.
- Special limits to know:
  - $$\frac{1}{x^r}$$ - horizontal and vertical asymptote at $$y=0$$ and $$x=0$$ for $$r>0$$.
  - $$\lim_{x\to\infty} x^r = \infty$$, $$\lim_{x\to-\infty} x^r = -\infty$$ for odd $$r$$.
  - $$\lim_{x\to\infty} x^r = \lim_{x\to-\infty} x^r = \infty$$ for even $$r$$.
  
  ---
  
  
  ## Week 3 Wednesday
- Quiz grades are out; mistakes may have been made by graders.
- Limits you cannot solve yet - when there is something like $$\lim_{x\to 0} \frac{\sin(x)}{x}$$ or $$\lim_{x\to 0} \frac{x}{\sin(x)}$$.
- Begin sharing solutions on Ed.
- Originally, we were interested in finding the tangent line to a graph.


> The tangent line to a curve $$y = f(x)$$ at the point $$P(a, f(a))$$ is the line through $$P$$ with slope $$f'(a) = \lim_{x\to a} \frac{f(x) - f(a)}{x-a} = \lim_{h\to 0} \frac{f(a+h) - f(a)}{h}$$. $$f'(a)$$ is the *derivative* of $$f$$ at $$a$$.

- Rephrasing of original slope definition using $$\lim_{h\to 0}$$.
- Will always be a $$\left[\frac{0}{0}\right]$$ type; transform it into a different type of canceling the $$h$$. *It is easier to cancel out $$h$$ than $$x-a$$.*
- Tangent line equation of $$f$$ at $$(a, f(a))$$: $$y - f(a) = f'(a)(x-a)$$.
- Average rate of change - secant. Instantaneous rate of change - derivative.
- Units of a derivative are $$\frac{y \text{ unit}}{x \text{ unit}}$$.
- The "tangent" line to a line is equal to itself.



---



## Week 3 Friday
- We are interested in the instantaneous rate of change. 
- We can find tangent line slopes if the function allows it so far.
- The derivative is the slope of the tangent line at that point.
- Reminder: $$f'(a) = \lim_{h\to 0} \frac{f(a+h) - f(a)}{h}$$.

$$f'(x) = \frac{d}{dx} f(x) = \frac{df}{dx}$$

- Repeat process with $$f'(x)$$ and get the second derivative $$f''(x)$$, etc. - higher order derivatives.
- You will stil look to pull out an $$h$$ somewhere when finding the derivative using the limit definition.
- $$f'(x)$$ is now a function.
- Generalizaiton: find the limit once and use it to find the slope of a tangent line at any point.
- *Differentiability* - $$f$$ is differentiable at $$a$$ if $$f'(a)$$ exists.
- $$f$$ is differentiable on the interval $$(a,b)$$ if it is differentiable at every position in $$(a,b)$$.
- How can a function fail to be differentiable? If it is not continuous, if there is a corner, vertical tangent line. vertical tangents like in $$\sqrt{x}$$ and $$x^\frac{1}{3}$$. 
- Asymptotic or break discontinuities. 
- Identifying the derivative for graphs:
  - Top of mountain/bottom of valley: $$f'(x) = 0$$
  - $$f$$ increasing: $$f'(x) > 0$$
  - $$f$$ decreasing: $$f'(x) < 0$$



---



## Week 4 Monday
- Midterm will cover everything including Section 3.4 (not including chain rule).
- Sum of two functions - $$(f(x) \pm g(x))' = f'(x) \pm g'(x)$$.
- $$(cf(x)' = cf'(x)$$
- $$(x^n)' = nx^{n-1}$$
- Product Rule and Quotient Rule
- $$c' = 0$$
- Finding $$e$$: $$\lim_{h\to 0}\frac{a^{x+h} - a^x}{h} = \lim_{h\to 0}\frac{a^x(a^h - 1)}{h} = a^x \lim_{h\to 0} \frac{a^h - 1}{h} \implies \lim_{h\to 0} \frac{a^h - 1}{h}$$. We can observe that between $$a=2$$ and $$a=3$$, there is a number $$e$$ such that $$\lim_{h\to 0} \frac{e^h - 1}{h} = 1$$.  Thus, $$\frac{d}{dx} e^x = e^x \cdot \lim_{h\to 0} \frac{e^h - 1}{h} = e^x \cdot 1 = e^x$$.



---



## Week 4 Wednesday
### Administrative
- Midterm will include all content until 3.2.
- 80 minutes long
- 8 problems
- There will be a large range of problems, easy and difficult.
- Only get stuck on a problem for a few minutes; don't spend too much time on just one problem. Be smart about your time.

### Notes
- Product rule and quotient rule.
- We can understand $$\left(\frac{f}{g}\right)' = \left(f \cdot \frac{1}{g}\right)'$$.
- You don't need to simplify it if the problem asks only for the derivative; if you need to use the derivative it is probably wise to further simplify it.



---



## Week 4 Friday
- Look at Midterm 1 revieew
- Whenever a 'co-' is involved (cotangent, cosine, cosecant), the derivative has a negative sign. Otherwise, there is no negative sign (tangent, sine).
- $$\lim_{h\to 0} \frac{\sin h}{h} = 1; \lim_{h\to 0} \frac{\cos h}{h} = 1$$
- e.g.: $$\lim_{x\to 0}{\frac{\sin(7x)}{11x}$$ - multiply numerator and denominator by $$\frac{7}{11}$$ and apply above limit rule.



---



## Week 5 Monday
$$\lim_{x\to 2} \frac{(x-2)(x+1)}{x^2 - 4} = \frac{3}{4}$$

$$\lim_{x\to 2} \frac{(x-2)(x+1)}{x^2 - 4x + 4} = \lim_{x\to 2} \frac{x+1}{x-2}$$ - we know a $$\left[\frac{c}{0}\right]$$ results in $$\infty$$, $$-\infty$$, or $$DNE$$. In this case, one-sided limit analysis concludes that $$\lim_{x\to2^+} \to \infty$$ and $$\lim_{x\to2^- \to -\infty$$, yielding $$DNE$$.

*Be careful when pulling terms into an even root, which does not preserve input sign.*

When you have a $$\frac{c}{x^n}$$ situation, rewrite as $$cx^{-n}$$ and use power rule to find derivative.



---



## Week 5 Wednesday
$$f$$ concave up $$\implies$$ $$f'(x)$$ increasing $$\implies$$ $$f''(x) > 0$$

Chain rule: $$f(g(x))' = f'(g(x)) g'(x)$$, or $$\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx}, f(u) = f(g(x))$$.



---



## Week 6 Monday
- Quiz on Thursday - mainly about derivatives.

Parametric equations: see the parameter $$t$$ as time and $$x$$ and $$y$$ as positions.
- $$x$$ and $$y$$ are presented in terms of $$t$$; they represent the position in the coordinate system.
- To obtain a curve for the path in the $$xy$$ coordinate system, eliminate $$t$$.
- You can use $$\sin^2 t + \cos^2 t = 1$$ trigonometric identity to eliminate $$t$$.
- If the time is restricted $$a\le t\le b4$$, $$(x(a), y(a))$$ is the initial point; $$(x(b), y(b))$$ is the terminal point.
- You need to memorize the generic form of uniform linear motion - pair of equations. Task is typically to determine $$a, b, c, d$$.
- Uniform circular motion - much hated.
  - $$\omega = \frac{\Delta \theta}{\Delta t}$$ - angular speed.
- Use Pythagorean theorem to find distance; use Pythagorean theorem on horizontal and vertical instantaneous velocities to calculate speed at a point.



---



## Week 6 Wednesday
- Parametric equation - $$x$$ and $$y$$ are separate equations, written as a function of a third variable $$t$$. Together, $$x$$ and $$y$$ represent a point in the coordinate system.
- We can find te derivative $$\frac{dy}{dx}$$ aas $$\frac{\frac{dy}{dt}}{\frac{dx}{dt}}$$. 
- The tangent line equation is $$y = \frac{dy}{dx} (x - x_1) + y_1$$.
- Horizontal tangent line - when $$\frac{dy}{dt} = 0$$. Vertical tangent line - when $$\frac{dx}{dt} = 0$$.



---



## Week 6 Friday
- Logarithmic differentiation: useful when many factors/quotients and ane xponent are involved.
- If you have an expression with an $$x$$ in the base and in the exponent.
- $$\ln(x^b) = b\ln(x)$$ - useful property of logarithms.
- In other cases, it is convenient rather than required to use logarithmic differentiation by using properties like $$\ln(xy) = \ln(x) + \ln(y)$$.



---



## Week 7 Monday
- Relating desired quantities to one another.
- Use geometric tools to establish the mathematical relationship - areas, volume, surface of common solid, Pythagorean Theorem, similar triangles, trigonometric laws, uniform linear and circular motions, etc.
- In midterms, you will have to make a sketch and properly label it.
- When implicitly differentiating, we are chasing $$t$$; everything else is a function of $$t$$.



---



## Week 7 Wednesday
- Linear approximation, linearization.
- We can approximate a value by walking on a tangent line rather than one the function itself.

---

## Week 8 Wednesday
Collect information about
- horizontal asymptotes
- critical numbers
- $$f''(x) = 0$$ or DNE
- sign of $$f'(x)$$ (monotonicity4$ and $$f''(x)$$ (concavity) in between critical numbers and $$f''(x) = 0$$ or DNE



---



## Week 8 Friday
- Works only for 0/0 or infty/infty cases. However, not save-the-world universal approach.
- When working with roots, can be difficult to make simpler with L'Hopital.
- Indeterminate limit types: $$0 \cdot \pm \onifty, \infty - \infty, 1^\infty, 0^0, \infty^0$$. Require more work, "forbidden types".
- $$[0\cdot \pm\infty] \cdot fg = \frac{f}{1/g}$$ or $$fg \cdot \frac{g}{1/f}$$
- $$[\infty - \infty]$$: common denominator or factorization. $$f - g = f(1 - \frac{g}{f}) = g(\frac{f}{g} - 1)$$.
- Exponentials involving $$1, 0, \infty$$: use logarithmic approach.



---



## Week 9 Monday
- Symmetry is helpful. However, remember that most functions are not symmetric. Evaluate symmetry with respect to origin, too.
- If you don't get too many points - mainly concavity and an asymptote, etc.; feel free to compute more points and add them to the coordinate system.



---



## Week 9 Wednesday
Preparing for final exam:
- Go to the test archive and begin doing all the finals. Our final will be very similar.
- Related rates and optimization problems can vary quite a bit. Other questions are quite predictable for the majority of the problems.
- For the first practice midterm exam, consider it to be a review. Go back to respective chapters and read.
- Derivative problems should be done in ~ 10 minutes, very quickly.

Tips:
- Don't worry about simplifying your derivative. If you simplify and make a mistake, points will be deducted. Find the derivative and you're good.



---



## Week 10 Monday
- Quiz on Thursday will be about graphing.
- There will be a quiz next Tuesday - cover broad problems.
- Goal of finding derivative using definition of a derivative - cancel out an $$h$$.
- Asymptotic behavior, evening out.
- Monotonicity and increasing/decreasing attributes.
- Verical asymptotes - denominator zero, log argument is 0.
- **Critical numbers must be in the domain of the function.**



---



## Week 10 Wednesday
- Optimization problems - application of derivative skills. Find minimm or maximum of a function (e.g. cost, surface area, distance).
- Reading task - identify the quantity we need to minimize or maximize.
- Find a formula for what we wnat ot minimize or maximize.
- Solve the formula for one of the variables and plug into the optimized function by taking the derivative and setting to zero.
