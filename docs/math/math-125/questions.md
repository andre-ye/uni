---
layout: default
title: Questions & Answers
parent: MATH 125
grand_parent: Mathematics
nav_order: 1000
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

Across the course, I had a lot of questions about generalizations and expansions to course content. The professor, Ricky Liu, took up the time to write awesome and super interesting answers to each. They are republished here.

---

**Q**: Is there such a thing as an infinitely discontinuous function? When I search for it, I see results for infinite discontinuities but not functions that are discontinuous in the sense that $$\lim_{h\to 0} f(x+h) - f(x) \neq 0$$ for all $$x$$ in the real domain. I'm curious if the uncountably infinite nature of the reals makes this sort of function impossible. If that is so, then is it possible considering only a function defined for the 'rational domain'?

**A**: Yes, a function can be "nowhere continuous" (or "everywhere discontinuous"). The standard example is the function $$f(x)$$ such that $$f(x)=1$$ if $$x$$ is rational and $$f(x)=0$$ if $$x$$ is irrational. Since every real number has both rational and irrational numbers arbitrarily close to it, $$f(x)$$ is not continuous anywhere. Of course, such pathological functions usually don't arise naturally except in real analysis courses.

---

**Q**: I was just wondering out of curiosity if there was such a thing as a 'noninteger' derivative, like a '1.5 derivative' or a 'pi derivative' (beyond the integer first derivative, second derivative, etc.). I don't know how to conceptualize it but I get the feeling mathematicians like to generalize/interpolate and that someone has come up with a definition/formalization for noninteger derivatives.

**A**: This is a concept that has been studied by mathematicians under the name "fractional derivatives," though it would likely only be taught in a graduate-level analysis course. For polynomials, you can define fractional derivatives in terms of the gamma function, which is a continuous version of the factorial function defined in terms of a convergent improper integral. For other functions, there may not be a single good way to define fractional derivatives, so different definitions are used that have different properties. For more information, see the Wikipedia page for fractional calculus.

---

**Q**: The integral of a function $$f(x) = x^a$$ is $$\frac{x^{a+1}}{a+1} (+C)$$, were $$a \neq -1$$. When $$a = -1$$, the integral is $$\ln(x)$$. However, when one plots out the graph of $$\frac{x^{a+1}}{a+1}$$ as $$a44 gets very close to $$-1$$, the shape of the graph doesn't 'approach' or look anything like $$\ln(x)$$ as $$a \to -1$$ even though at $$a = -1$$ the integral is $$\ln (x)$$. It's like there is this continuous function morphing for all values of $$a$$, except at this point $$x = -1$$ it is $$\ln x$$. This discontinuity is a bit jarring for me. I understand from a technical perspective that $$\frac{d}{dx} \ln x = \frac{1}{x}$$ and so $$\int \frac{1}{x} = \ln \vert x\vert  + C$$, but in the scope of generalizing to the $$x^n$4 family it seems a bit out of place. Is there an intuitive explanation or solace that can be provided here?

**A**: You have chosen your antiderivative of $$x^n$$ to be $$\frac{x^{a+1}}{a+1}$$ since it passes through the origin for $$a >=1$$, but actually this is not a very natural choice for $$a < -1$$ since there is a discontinuity at $$x = 0$$. Instead, you should take the antiderivative that passes through the point $$(0, 1)$$ where there are no continuity isseus for any $$a$$. This gives

$$\frac{x^{a+1} - 1}{a+1}$$

which satisfies

$$\lim_{a\to -1} \frac{x^{a+1} -1}}{a+1} = \ln x .$$

---

**Q**: I was intrigued by the arc length lecture and was requesting Wolfram Alpha to compute some interesting arc lengths. Particularly, I am interested in the function $$y = \sin (\frac{1}{x})$$, which has an infinitely oscillating pattern as $$x\to 0$$. There is expectedly no finite arclength of the function across $$[-1, 1]$$. I tried the modified function $$y = x \sin (\frac{1}{x})$$, with hopes that for $$\vert x\vert  < 1$$ there would be a diminishing effect. However, the result still does not converge. I tried $$y = x^2 \sin (\frac{1}{x})$$, which yields no solution - but $$y = x^3 \sin (\frac{1}{x})$$ does yield a solution, about 2.848673. I assume that there is some value $$a$4 in $$y = x^a \sin (\frac{1}{x})$$ where there is some discrete jump between being computable and not being computable. I am wondering - firstly, is the significance here between computability and uncomputability mainly determined by Wolfram Alpha and not 'pure math' (maybe something to do with precision/computer representation)? Secondly, I am wondering how to understand and think about these discrete jumps (if they exist) in a world that I am so familiar to thinking of as continuous.

**A**: This is a limitation of WolframAlpha: the curve $$f(x) = x^a \sin (\frac{1}{x})$$ from $$[0, 1]$$ has finite arc length for $$a > 1$$. (I will restrict to positive xx just to avoid any issues with taking fractional powers of negative numbers, which usually requires complex numbers.) To see this, we compute its derivative as

$$f'(x) = ax^{a-1} \sin (\frac{1}{x}) - x^{a - 2} \cos (\frac{1}{x}$$

This has absolute value at most

$$\vert ax^{a-1}\vert  + \vert x^{a-2}\vert  = (ax + 1) \cdot x^{a-2} \le Cx^{a-2}$$

(where $$C = a+1$$.) IN particular, we can then bound the arc length by

$$\int_0^1 \sqrt{1 + f'(x)^2} dx < C' \int_0^1 \vert f'(x)\vert  dx < C^n \int_0^1 x^{n-2} dx$$

for some constants $$C'$$ and $$C''$$. One can then show by direct computation that this integral converges whenever $$a - 2 > -1$$, which holds for $$a > 1$$. A similar argument shows that the arc length is infinite for $$a \le 1$$. Likely the reason WolframAlpha has trouble computing these arc lengths in cases when they are finite is that it is using an approximation method whose speed of convergence is dependent on how "wiggly" the function being integrated is. For small $$a>1$$, its approximation method probably does not converge fast enough to give a satisfactory answer in the time allotted for the computation. In general, issues of convergence and divergence can be very subtle. We will not touch upon it much in this course, but Math 126 does cover some of these issues in the form of sequences and series.

---

**Q**: What is wrong with the following argument?

![](https://andre-ye.github.io/uni/assets/images/argument.png)

**A**: This is a great question! Technically, the reason this argumen tis not valid is because you are not allowed to write

$$\int_0^\infty f(x) dx + \int_0^\infty f(-x) dx = \int_0^\infty (f(x) + f(-x)) dx$$

if the integrals on the left do not converge. (If the frist one goes to $$\infty$$ while the second goes to $$-\infty$$, you can't cancel those out but get something indeterminate.)

Philosophically, the reason the argument doesn't work is because you are trying to compute the infinite integral as 

$$\lim_{t\to\infty} \int_{-t}^t f(x) dx,$$

but you should actually be thinking of it as 

$$\lim_{s\to -\infty}_{t\to\infty} \int_s^t f(x) dx$$

That is, the two end points should be allowed to go to $$\pm \infty$$ independently. It is done this way because we want $$\int_{-\infty}^\infty f(x) dx$$ to be a good approximation for $$\int_a^b f(x) dx$$ for any sufficienlty large interval $$[a, b]$$, not just the ones of the form $$[-b, b]$$ that happen to be symmetric about 0.














