---
layout: default
title: Cheat Sheet
parent: MATH 125
grand_parent: Mathematics
nav_order: 100
---

# Cheat Sheet
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

## Antiderivatives


| $$\int b^xdx=\frac{b^x}{\ln b}+C$$ | $$\int \left[f\left(x\right)+g\left(x\right)\right]\:dx=\int f\left(x\right)dx+\int g\left(x\right)dx$$ | |
| $$\int 0 \: dx = C$$ | $$\int cf\left(x\right)\: dx=c\int f\left(x\right)dx$$ | $$\int x^n\: dx=\frac{x^{n+1}}{n+1}+C\left(n\ne -1\right)$$ |
| $$\int e^x\: dx=e^x+C$$ | $$\int \sin x\:dx=-\cos x+C$$ | $$\int \sec^2x\:dx=\tan x+C$$ |
| $$\int \sec x\:\tan x\:dx=\sec x+C$$ | $$\int \frac{1}{x^2+1}\:dx=\tan ^{-1}x+C$$ | $$\int \sinh x\:dx=\cosh x+C$$ |
| $$\int \frac{1}{x}\:dx=\ln \left|x\right|+C$$ | $$\int \cos x\:dx=\sin x+C$$ | $$\int \tan x\: dx = \ln \| \cos x \| + C$$ |
| $$\int \csc ^2x\:dx=-\cot x+C$$ | $$\int \csc x\cot x\:dx=-\csc x+C$$ | $$\int \frac{1}{\sqrt{1-x^2}}\:dx=\sin ^{-1}x+C$$ |
| $$\int \cosh x\:dx=\sinh x+C$$ | $$\int \tan x \:dx = -\ln | \cos(x) | + C$$ | $$\int \sec x \:dx = \ln | \tan(x) + \sec(x) | + C$$ |
| $$\int \csc x \:dx = \ln | \tan\left(\frac{x}{2}\right)| + C$$ | $$\int \sin^2 x\:dx = \frac{1}{2} \left(x - \frac{1}{2} \sin(2x)\right) + C$$ | $$\int \cos^2 x\:dx = \frac{1}{2} \left(x + \frac{1}{2} \sin (2x) \right) + C$$ |
| $$\int \sin^2(x)\cos^2(x)\:dx = \frac{1}{8} \left(x - \frac{1}{4} \sin(4x) \right) + C$$ | | |

--

## Techniques

| Technique | Description |
| --- | --- |
| $$u$$-Substitution | Given $$\int f(x) dx$$, write $$u = g(x) \implies du = g'(x) dx$$. We can rewrite the original integral as $$\int \frac{f(x)}{g'(x)} du \implies \int h(u) du$$. The choice of $$u$$ must allow for a more convenient rewriting such that $$h(u)$$ can be easily integrated; after integration, plus in $$u$$ for $$g(x)$$. |
| Integration by Parts | We have that $$\frac{d}{dx} \left(f(x) \cdot g(x) \right) = f(x) \cdot g'(x) + f'(x) + g(x)$$. This can be rewritten as $$\int f(x) g'(x) dx = f(x) \cdot g(x) - \int g(x) f'(x) dx$$. When you are given an integral $$\int a(x) b(x) dx$$, choose some $$u = a(x)$$ and $$dv = b(x) dx$$; this leads to $$du = a'(x) dx$$ and $$v = \int b(x)$$. We have that $$\int u dv = uv - \int v du$$. |
| Trigonometric Identities | Use trigonometric identities to rewrite an integral into a more convenient form.  See the below section on trigonometric identities. |

---

## Trigonometric Identities

$$\sin^2 x + \cos^2 x = 1$$

$$\sin^2 x = \frac{1}{2} \left(1 - \cos 2x\right)$$

$$\cos^2 x = \frac{1}{2} \left(1 + \cos 2x\right)$$

$$\sin x \cos x = \frac{1}{2} \sin 2x$$

$$\sec^2 x = 1 + \tan^2 x$$

---




