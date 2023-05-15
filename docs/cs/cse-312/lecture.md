---
layout: default
title: Lecture Notes
parent: CSE 312
grand_parent: Computer Science
nav_order: 1
---

# Lecture Notes
{: .no_toc }

CSE 312
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

## Week 1 Monday -- Introduction and Counting
- May 3rd evening exam
- 312 is intro to statistics and probability theory
- Useful and interesting branch of mathematics
- Probability as frequency: $$X / (X + \neg X)$$.
- Set -- unordered list of elements ignoring repeats.
- Sum rule -- cardinality of union of two non intersecting sets is the sum of the cardinalities of each set
- A nontemporal definition of combinatorics via product of elements?
- Product rule: if you have a sequential process in which step $$k$$ has $$n_k$$ options, the total number of possibilities is $$n_1 \cdot n_2 \cdot ... \cdot n_k$$
  - This is taking the Cartesian product of the relevant sets.
- Cardinality of a powerset is two to the cardinality of the original set
  - How to generate this?
  - For every element of the original set we can either include it or not include it -- this gives us the formula
- Complementary counting

---

## Week 1 Wednesday -- Counting
- In a sequence, order matters. 
- The number of ways to permute $$n$$ elements is $$n!$$.
- $$k$$-permutation: the number of $$k$$-element sequences of distinct symbols from a universe of $$n$$ symbols is $$n!/(n-k)!$$. Also denoted $$_nP_k$$. $$_nP_n = n!$$ and $$_nP_0 = 1$$
- Derivation of choose formula
  - How many size $$k$$ subsets in a size $$n$$ univeral set?
  - How many ways can we get an ordered list? Choose a subset and put it in order, $$k!$$ ways to do so
  - But also we have $$k$$-permutation formula: $$_nP_k = ? \cdot k!$$. We can find ? by dividing both sides by $$k!$$.
- $$k$$-combination: the number of $$k$$-element subsets from a set of $$n$$ symbols is $$n! / (k!(n - k)!)$$

$$C(n, 0) = 1$$, $$C(n, n) = 1$$

- This trick of 'what happens if order does matter?' will be useful later on
- Path counting on a $$a \times b$$ Cartesian lattice: $$_nC_k$$ unique paths from bottom left to top right corner only moving up and right
- Anagrams of "seattle", not $$7!$$ but $$7! / 4$$
- Is there an interpretation of this as a choosing problem?

---

## Week 1 Friday -- More Counting
- Multinomial coefficient: in general, $$\binom{k}{a, b, ..., z} = \frac{k!}{a!b!...z!}$$.
- Symmetry of combinations: $$\binom{n}{k} = \binom{n}{n-k}$$
- Pascal's rule: $$\binom{n}{k} = \binom{n-1}{k-1} + \binom{n-1}{k}$$
  - You can $$n - 1$$ people are trying out for a $$k$$ person time
  - Can calculate as n choose k
  - Can also say: number of teams without me plus number of teams with me
- Binomial theorem: $$(x + y)^n = \sum_{i=0}^n \binom{n}{i} x^i y^{n-i}$$

$$2^n = \sum_{i=0}^n \binom{n}{i}$$

- Inclusion-exclusion principle

$$\vert A \cup B\vert  = \vert A\vert  + \vert B\vert  - \vert A \cap B \vert $$

$$\vert A \cup B \cup C\vert  = \vert A\vert  + \vert B\vert  + \vert C\vert  - \vert A \cap B\vert  - \vert B \cap C\vert  - \vert A \cap C\vert  + \vert A \cap B \cap C\vert $$

---

## Week 2 Monday -- More More Counting
- Pigeonhole principle
  - With 5 pigeons placed in 4 holes, at least one hole has two pigeons
  - If you have $$n$$ pigeons and $$k$$ pigeonholes, then there is at least one pigeonhole which has at least $$\lceil \frac{n}{k} \rceil$$
- When applying the principle, think: what are the pigeons? What are the pigeonholes? HOw do you map pigeons to pigeonholes?
- Stars and bars: try to assign objects into different groups, count how many ways to place dividers. 
  - There are $$\binom{n + k - 1}{k - 1}$$ ways to arrange $$n$$ things into $$k$$ groups where order of groups doesn't matter and every element of each group is indistinguishable
  - Like building $$n + k - 1$$ character string but the $k - 1$$ dividers are indistinguishable
- It's hard to count sets where one of the conditions is 'at least X' -- often you need to break these conditions into disjoint sets and use a summing rule
- Choose 8 pieces of fruit (apples, oranges, bananas): pick at most 2 apples and at least 1 banana. Pick your one banana and toss it in your box. You now need 7 fruits, of which at least 0 is a banana. This is just a stars and bars problem. Now do complementary counting and find the number of combinations where we need at least 3 apples. Now toss them into the basket. Now we need 4 pieces of fruit: choose apples, oranges, bananas. Then subtract. $$\binom{9}{2} - \binom{6}2 = 36 - 15 = 21$$.
  - 'Throw the banana in' is a good generalizable set

---

## Week 2 Wednesday -- Probability
- Probability is a method of quantifying our uncertainty. 
- Sample space $$\Omega$$ -- set of all possible outcomes of an experiment
- Event: $$E \subset \Omega$$; subset of possible outcomes
- Probability: a number between 0 and 1 describing how likely a particular outcome is. $$\mathbb{P}: \Omega \to [0, 1]$$. Also: $$Pr[\omega], P(\omega)$$
- A didscrete probability space is a pair $$(\Omega, P)$$ where

$$\forall x ; \mathbb{P}(x) \ge 0$$
$$\sum_{x \in \Omega} \mathbb{P}(x) = 1$$
$$(E \subset \Omega \wedge F \subset \Omega \wedge E \cap F = \emptyset ) \to (\mathbb{P}(E \cup F) = \mathbb{P}(E) + \mathbb{P}(F))$$

- Uniform probability measure: $$\mathbb{E} = \frac{\vert E\vert }{\vert\Omega\vert }$$
- Two events $$E, F$$ are mutually exclusive if they cannot happen simultaneously: $$E \cap F = \emptyset$$ (disjoint subsets of the sample space)
- Axioms for probability measures:
  - Non-negative
  - Sum to one across sample space
  - If two events are mutually exclusive, the probability of their union is the sum of their independent probabilities
- Three corollaries
  - Complementation: $$P(\bar{E}) = 1 - P(E)$$
  - Monotonicity: $$E \subset F \to P(E) \le P(F)$$
  - Inclusion-exclusion: $$P(E \cup F) = P(E) + P(F) - P(E \cap F)$$

---

## Week 2 Friday -- Conditional Probability
- Uniform measure helps to simplify calculations -- solve two counting problems and divide
- If you have a different measure, then it's a more difficult counting process
- There might be information you don't need in your sample space
- Conditioning: partial information which provides an impetus to update your porbabilities

$$P(A\vert B) = \frac{P(A\cap B)}{P(B)}$$

- If $$P(B) = 0$$, the conditional probability is not defined.
- $$P(A\vert B)$$ and $$P(B\vert A)$$ are different quantities
- Independence: conditioning does not affect probabilities
- Bayes' Rule: $$P(A\vert B) = P(B\vert A)P(A)/P(B)$$
- Law of total probability: $$P(S) = P(S\vert G) \cdot P(G) + P(S \vert  \bar{G}) \cdot P(\bar{G})$$

---

## Week 3 Monday -- Bayes' Rule

$$P(A \vert  B) = P(A \cap B) / P(B)$$
- A way to reverse the conditioning

$$P(A \vert  B) = P(B\vert A) P(A) / P(B)$$
$$P(A) = P(B) P(A\vert B) + P(\bar{B}) P(A\vert \bar{B})$$

- Law of total probability
  - Consider a partition of a set which is mutually exclusive but wholly covering
  - In general, $$P(E) = \sum_{\forall i} P(E \vert  A_i) P(A_i)$$

$$P(E) = \sum_{\forall i} P(E \cap A_i)$$

- View tests as updating your beliefs, not as revealing the truth

---

## Week 3 Wednesday -- Independence
- Two events $$A, B$$ are independent if $$P(A \cap B) = P(A) \cdot P(B)$$
- Statistical indepednence: we're talking about probabilities, not physical interactions
- If $$A, B$$ both have nonzero probability, then $$P(A\vert B) = P(A)$$ and $$P(B\vert A) = P(B)$$ -- if the two are independent
- Two zero-probability events are always independent
- If either of your events has zero probability, it's going to be independent. 
- Chain rule: $$P(A_1 \cap A_2 \cap  ...  \cap A_n) = P(A_n \vert  A_1 \cap  ...  A_{n-1}) \cdot P(A_{n-1} \vert  A_1 \cap  ...  \cap A_{n-2})  ...  P(A_2 \vert  A_1) \cdot P(A_1)$$
  - Starts from $$P(A \cap B) = P(A \vert  B) P(B)$$
  - The probability of an intersection of events -- start from $$P(A_1)$$, then $$P(A_2 \vert  A_1)$$, then $$P(A_3 \vert  A_1 \cap A_2)$$
- Conditional independence: $$A$$ and $$B$$ are conditionally independent on $$C$$ if $$P(A \cap B\vert C) = P(A \vert  C) \cdot P(B \vert  C)
  - Condition everything on C
  - If we condition on $$C$$, these events become independent
  
---

## Week 3 Friday -- Applications of Bayes Rule
- Prevalence -- probability of disease
- Sensitivity -- probability of test given disease -- pick up on disease when it's there -- of the positive tests, there is a high disease (few false negatives)
  - 1 - false negative rate
- Specificity -- probability of not test given not disease -- of the positive disease, there is a positive test (few false positives)
  - 1 - false positive rate
- Intuition trick: 
  - Think about the broader population of people who also don't have the disease
  - Multiply the prior (the prevalence of the disease before tests) by the Bayes Factor: sensitivity / false positive rate, or (1 - FNR) / (FPR)
  - For negative texts, FNR / specificity
- Trouble brewing when you have very different population sizes -- becuase it's a small population, even small effects become significnat

---

## Week 4 Monday -- Random Variables
- Infinite processes  -- a sequential process can be infinite
- We can still calculate probabilities because the tree is self-similar: I know what each step looks like
- Infinite sums: we have a common ratio 
- A sum of infinite geometric series: closed form of first term divided by 1 - ratio (only works if common ratio is between -1 and 1).
- Can also calculate the complement, which is finite
- Random variable: Any function $$X: \omega \to \mathbb{R}$$; $$X(\omega)$$ is the summary of the outcome $$\omega$$ -- it summarizes some sort of numerical information about your experiment. Don't think about what specifically happens, but in fact we get $$X(\omega)$$ -- the random variable of that outcome, which will be some real number
- Random variables let us do things more conveniently: you can define many random variables for any one sample space
- Formally speaking, random variables are functions
- Support: the range of values that $$X$$ can actually take -- this is the image in 311.
  - "$$S$$ is supported on ..."
- Two ways to represent a random variable
  - Probability mass function (PMF)
    - Often we're interested in $$\{\omega : X(\omega) == x\}$$ -- the event that the random variable takes on that value, or $$\mathbb{P}(X = x)$$
    - $$p_x(x)$$ or $$f_X(x)$$: pmf
  - Patition
    - A random variable partitions $$\Omega$$: a way of splitting up the outcome space
- Make sure to be specific about the pmf, including handling different cases: the pmf has to give you an answer regardless of if the input to the pmf is in the support or not
- Good check: sum of $$p_x(x) \forall x \in \Omega$$ you should get 1.
- CDF: gives you the probability that $$X \le x$$. $$F_X(x) = \mathbb{P}(X \le x)$$
  - You can sum up the PDF to get the CDF
  - CDF should handle decimal values
- Good check: $$F_x(\infty) = 1$$

---

## Week 4 Wednesday -- Expectation
- The expectation of a random variable $X$ is $\mathbb{E}[X] = \sum_k k \cdot \mathbb{P}(X = k)$
- $$\mathbb{E}(X)$$ is not the most likely outcome necessarily, but the average -- what is going to happen
- The expectation does not need to be an actual possible outcome; it is just the average value you would expect
- $$X$$ is random, but $$\mathbb{E}[X]$$ is not -- it's a deterministic number
- Two events are independent if $$P(A \cap B) = P(A) \cdot P(B)$$. We would have defined it as $$P(A \vert  B) = P(A)$$ but $$P(A\vert B)$$ is not defined for zero $$B$$.
- What about independence for 3 or more events? We need two kinds of independence. There are different levels at which the events can be independent of each other.
  - Pairwise Independence: every pair of events is independent of each other: $$\forall i \forall j P(A_i \cap A_j) = P(A_i) \cdot P(A_j)$$
  - Mutual Independence: $$P(A_{i_1} \cap A_{i_2} \cap ... \cap A_{i_k}) = P(A_{i_1} \cdot P(A_{i_2}) \cdot ... \cdot P(A_{i_k}))$$ for all subsets $$i_1, i_2, ..., i_k$$ of $${1, 2, ..., n}$$ -- all subsets must be independent
- Even though two events might be independent, the intersection of three events might interact in some unique way. 
- Not pairwise independent implies not mutually independent
- Independence of random variables: $$X$$ and $$Y$$ are independent if $$\forall k, l P(X = k, Y = l) = P(X = k) P(Y = l)$$
  - Commas in lieu of $$\cap$$

---

## Week 4 Friday -- Linear Expectation
- Random variables are mutually independent iff $$\forall x_1, x_2,  ... , x_n$$ $$P(X_1 = x_1, X_2 = x_2,  ...  X_n = x_n) = P(X_1 = x_1) P(X_2 = x_2)  ...  P(X_n = x_n)$$
- You don't need to check all subsets for random variables, but you still need to check all possible values for $$x_1$$
- Expectation of a random variable: weighted average of values $$X$$ can take on
- Linearity of expectation: for any two random variables $$X$$ and $$Y$$, $$\mathbb{E} [X + Y] = \mathbb{E}[X] + \mathbb{E}[Y]$$
  - Holds for every random variable $$X$$ and $$Y$$
  - Also holds for multiple variables
  - Works even if two variables are dependent on each other
  
$$E[X + Y] = \sum_\omega P(\omega) (X (\omega) + Y(\omega)) = E[X] + E[Y]$$

  - Constants are also fine: $$E[aX + bY] = aE[X] + bE[Y]$$
- Probability of flipping a heads is $$p$$, we want to find the total number of heads flipped when we flip the coin $$n$$ times
  - Looks like the binomial theorem uwu: $$k \binom{n}{k} = n \binom{n-1}{k-1}$$
  - We can conclude: $$\mathbb{E}[Y] = np$$
- Indicator random variable
  - For an event $$A$$, the indicator random variable $$\mathbf{1}[A]$$ is 1 if $$A$$ occurs and 0 if otherwise. It takes an event and casts it to an integer.

$$\mathbb{E}[\mathbb{1}[A]] = 0 (1 - P(A)) + 1 P(A) = P(A)$$

- Three steps to solve complicated expectations 
  1. Decompose: find the right way to decompose random variables into a sum of simple random variables
  2. Apply linearity of expectations
  3. Conquer: compute expectation of each random variable, easier usually with indicator variables
  
---

## Week 5 Monday -- Variance
- Variance is average square deviation
- The variance of a random variable $$X$$ is

$$Var(X) = \sum_\omega P(\omega) * (X(\omega) - E[X])^2 = E[(X-E[X])^2] = E[X^2] - E[X]^2$$

- If $$X$$ and $$Y$$ are independent, then $$Var(X+Y) = Var(X) + Var(Y)$$
- Squaring an indicator random variable doesn't actually do anything to it, useful for calculating variances
- Expectation and variance aren't everything -- you can have different random variables with the same expectation and variance; you need the PMF or CDF to fully describe a random variable

$$Var(X+c) = Var(X)$$

$$Var(ax) = a^2 Var(x)$$

---

## Week 5 Wednesday -- Discrete RV Zoo
- $$Var(X + Y) + Var(X) + Var(Y)$$ for independent random variables
- $$E[X\cdot Y] = E[X] \cdot E[Y]$$ for independent random variables
- There are some common patterns for experiments
- Bernoulli
  - Flip a biased coin once and record whether it is heads or not. 
  - Distribution which defines a variable -- following a Bernoulli distribution, $$X ~ \text{Ber}(p)$$
  - $$X$$ follows a Bernoulli distribution with parameter $$p$$
- Binomial
  - Flipping repeatedly $$n$$ times and coming up with a probability $$p$$
  - $$n$$ repeated Bernoulli experiment
  - Binomial distribution: $$p_X (k) = \binom{n}{k} p^k(1 - p)^{n-k} \text{ for } $$k \in [0, n]$$
  - Expected value: $$\mathbb{E}[X] = np$$
  - Variance: $$Var(X) = np(1 - p)$$
- Geometric
  - You flip a coin which comes up heads with probability $$p$$ until you get heads. how many flips needed? OR: How many independent triasl needed until the first success?
  - $$p$$, probability of success; $$X$$, number of trials needed to see the first Success.
  - PMF: $$p_X(k) = (1 - k)^{k-1}p$$ for $$k \in [1, \infty)$$
  - CDF: $$1 - (1 - p)^k$$ for $$k \in \mathbb{N}$$
  - Expectation: $$\mathbb{E}[X] = \frac{1}{p}$$
  - Variance: $$\frac{1-p}{p^2}$$
  - Geometric random variables are 'memoryless' -- self-similar problem at different timesteps
- Uniform
  - Roll a fair die or draw a random integer form $$[1, n]$$
  - Equally likely range  
  - PMF: $$p_X(k) = \frac{1}{b-a+1}$$
  - CDF: $$F_X(k) = \frac{k - a + 1}{b - a + 1}$  
- Negative binomial
  - Generalization up to $$r$$ successes
  - What is the PMF, expectation and variance?
  - PMF: $$p_X(k) = \binom{k-1}{r-1}(1 - p)^{k-r}p^r$$
  - Variance: $$r \cdot \frac{1-p}{p^2}$$
- No need to rederive the PDF, can simply cite the distributions and take advantage of the PDFs, CDFs, etc.

---

## Week 5 Friday: Continuous Probability
- Poisson -- trying to count the number of times something happens over an interval of time, given that we know the expectation of the random variable. We also assume each occurrence is independent of the others. 
  - Useful there is a large number of potential sources
  - The poisson distribution is a modeling choice -- we're choosing math which we believe describes something in the real world well
  - Let $$\lambda$$ be the average number of incidents in a time interval
  - $$X$$ is the total number of incidents seen in a particular interval
  - Support for a Poisson is all natural numbers -- 0, 1, 2, etc.

$$p_X(k) = \frac{\lambda^k e^{-\lambda}}{k!}$$
$$F_x(k) = e^{-\lambda} \sum_{i=0}^k \frac{\lambda^i}{i!}$$
$$\mathbb{E}[X] = \lambda$$
$$Var(X) = \lambda$$

- Poisson distribution comes from taking the binomial to the infinite limit
- Second part of the course -- dealing with probability across uncountable sets

$$\int_{-\infty}^\infty f_X(k) dk = 1$$

- Probability density function, $$f_X(k)$$
- Probability density function works only for events, since single outcomes don't make sense
- Uniform PDF between 0 and 1:

$$f_X(k) = 0 \text{ if } k < 0 \vee k > 1; 1 \text{ else}$$

- PDF != PMF
- For continuous probability spaces, impossible events have probability 0 but some probability 0 events might be possible
- PDF is a way to compare relative chances of being near a particular value

---

## Week 6 Monday: More Contiunous variables
- Integrating the PDF from negative infinity to positive infinity should yield 1
- Evaluating the PDF at a particular point does not give you a particular probability; rather you need to evaluate a density over a range
- integration of PDF is analogous to summing over the PMF
- PDF for uniform real number: $$f_X(k) = 0 : k < 0 \vee k > 1; 1 : 0 \le k \le 1$$
- The PDF is not giving you anything absolute (only PMFs can do that) -- it is giving you how likely a particular variable is to occur relative to other ones -- give you the relative ratio of being near values scaled such that integrating over the whole PDF gives you 1
- The CDF is the integral of the PDF; the PDF is the derivative of the CMF

$$F_X(k) = \mathbb{P}(X \le k) = \int_{-\infty}^k f_X(z) dz$$

$$\frac{d}{dk} F_X(k) = \frac{d}{dk} (\int_{-\infty}^k f_X(z) dz) = f_X(k)$$

$$\mathbb{E}[X] = \int_{-\infty}^\infty X(z) \cdot f_X(z) dz$$

$$\mathbb{E}[g(X)] = \int_{-\infty}^\infty g(X(z)) \cdot f_X(z) dz$$

$$\mathbb{E}[aX + bY + c] = a\mathbb{E}[X] + b \mathbb{E}[Y] + c$$

$$Var(X) = \kmathbb{E}[X^2] - (\mathbb{E}[X])^2 = \int_{-\infty}^\infty f_X(k)(X(k) - \mathbb{E}[X])^2 dk$$

$$\text{Uniform}(a, b) := f_X(k) = \frac{1}{b - a} \text{ if } k \in [a, b] \text{ else } 0$$

$$\text{Uniform}(a, b) := Var(X) = \frac{(b-a)^2}{12}$$

- Exponential random variable: like a geometric random variable, but use continuous time. How many flips until see heads? But rather looking at continuous time. When waiting doesn't make the event happen any sooner. Geometric is memoryless. $$P(X \ge k + 1 \vert X \ge 1) = P(Y \ge k)$$

$$X \sim Exp(\lambda): F_Y(t) = P(Y \le t) = 1 - e^{-\lambda t}$$

$$X \sim Exp(\lambda): f_Y(t) = \lambda e^{-\lambda t} : k \ge 0$$

---

## Week 6 Friday: Continuous RV Zoo
- Exponential vs poisson distributtion
- Take a Poisson ranodm variable and ask, what's the time until the next event? You get an exponential distribution.
  - Let $$Y \sim \text{Exp}(\lambda)$$ be the time until the first event when we see an average of $$\lambda$$ events per time unit
  - What is $$P(Y > t)$$? 
  - Let $$X \sim \text{Poi}(\lambda t)$$.
  - We know that $$P(Y > t) = P(X = 0)$$
  - We know that $$P(X = 0) = e^{-\lambda t}$$
  - CDF for exponential is $$F_Y(t) = P(Y \le t) = 1 -e ^{-\lambda t}$$
  - $$X$$: how many events happened?
  - $$Y$$: how long did I wait for the first event

$$f_Y(t) = \frac{d}{dt} (1 - e^{-\lambda t}) = \lambda e^{-\lambda t}$$

- Memorylessness: $$P(X \ge s + t \vert X \ge s) = P(X \ge t)$$
- In continuous RVs, we can switch out $$\le$$ and <
- Expectation of an exponential random variable is $$\frac{1}{\lambda}$$
- Variance is $$\frac{1}{\lambda^2}$$ otherwise
- Normal or Gaussian random variable
- Central Limit THeorem -- many real-world processes are well-approximated by a normal random variable
- $$X$$ is a normal random variable with mean $$\mU$$ and variance $$\sigma^2$$ or $$X \sim (N \mu, \sigma^2)$$ if it has the density
  - $$f_X(x) = \frac{1}{\sigma \sqrt{2\pi}}$$ is a normalization constant


$$f_X(x) = \frac{1}{\sigma \sqrt{2\pi}}e^{-\frac{(x - \mu)^2}{2\sigma^2}}$$

- Density is symmetric around $$\mu$$
- Never goes to zero; will be nonzero for any finite $$x$$
- Scaling normals -- we get a normal random variable back. If $$X \in N(\mu, \sigma^2)$$:

$$Y = aX + b \implies Y \in N(a \mu + b, a^2 \sigma^2)$$

- We will need to standardize Gaussian random variables -- if I have a RV with mean $$\mu$$ and variance $$\sigma^2$$ and instead I want to get $$Y \in N(0, 1)$$, just set $$Y = \frac{X - \mu}{\mu}$$
- We want to use the CDF of a normal but it is really fucking ugly for the normal distribution

---

## Week 7 Monday: Central Limit Theorem

Let $$X_1, X_2, ..., X_n$$ be i.i.d random variables with mean $$\mu$$ and variable $$\sigma^2$$. Let

$$Y_n = \frac{\sum X_i - n \mu}{\sigma \sqrt{n}}$$

Summing together the random variables and then standardizing them. The expectation of $$\mathbb{Y_n}$$ is 0 and the variance is 1. Then, as $$n \to \infty$$, the CDF of $$Y_n$$ converges to the CDF of $$N(0, 1)$$.

- iid: independent and identically distributed, e.g. all bernoulli distributions
- Moment of a distribution: think about raising a random variable to some integer power and take the expectation of this
- Even if it looks fairly strange, we converge to a normal distribution
- A lot of real-world bell curves can be explained as: a random variable comes from a combination of independent factors; CLT says that the distribution will become like a bell curve. 
- Using CLT -- find $$Y_n$$ and pretend that the desired condition operations on the domain of the normal via $$X$$
- Computational trick: $$\Phi(-a) = 1 - \Phi(a)$$ due to the symmetricness of the normal distribution
- When using CLT to find the probability that $$X = 950$$ -- CLT is continuous but $$X$$ is discrete. How to make sense of this? What should we do?
- Continuity correction: the binomial distribution is discrete but the normal is continuous. Before we switch from binomial to normal, we see what values of a continuous random variable round to a particular event.

---

## Week 7 Wednesday: Joint Distributions
- How to deal with non-independent random variables
- What to do when your random variables depend on each other?
- Joint PMF:

$$p_{X, Y} = \mathbb{P}(X = x \cap Y = y)$$

- If $$X, Y$$ are independent then

$$P_{X, Y}(x, y) = p_X(x) p_Y(y)$$

$$P(X = k) = \sum_{\text{partition} \{ E_i \}} \mathbb{P}(X = k \vert E_i) \mathbb{P}(E_i)$$

- $$p_X(k)$$ from a joint distribution: called a marginal distribution because we have marginalized other variables, emphasizes this dimension. 
- Expected value of joint function

$$\mathbb{E}[g(X, Y)] = \sum_{x \in \Omega_X} \sum_{y \in \Omega_Y} g(x, y) \cdot p_{XY}(x, y)$$

- Conditioning creates a new probability space with all laws holding

$$\mathbb{E}[X \vert E] = \sum_{x \in \Omega} x \cdot \mathbb{P}(X = x \vert E)$$
$$\mathbb{E}[X \vert Y = y] = \sum_{x \in \Omega} x \cdot \mathbb{P}(X = x \vert Y=y)$$

- Linearity fo expectation holds in conditional expectations

$$\mathbb{E}[(aX + bY + c) \vert E] = a \]mathbb{E}[X \vert E] + b \mathbb{E}[Y \vert E] + c$$

- Law of total expectation; for partitions $$A_i$$:

$$\mathbb{E}[X] = \sum_{i = 1}^n \mathbb{E}[X \vert A_i] \mathbb{P}(A_i)$$
$$\mathbb{E}[X] = \sum_{y \in \Omega_y} \mathbb{E}[X \vert Y = y] \mathbb{P}(Y = y)$$

- Covariance: we wnat to  measure how intertwined $$X$$ and $$Y$$ are. Covariance is a very common way to see how things work out. Covariance tries to see: If $$X$$ is bigger than its expectation, what happens to $$Y$$? Do you expect it to be bigger or less than its expectation? Do they varry together or opposite?

$$\text{Cov}(X, Y) = \mathbb{E}[(X - \mathbb{E}[X])(Y - \mathbb{E}[Y])] = \mathbb{E}[XY] - \mathbb{E}[X] \mathbb{E}[Y]$$

$$\text{Cov}(X, X) = \mathbb{E}[X^2] - \mathbb{E}[X]^2 = \text{Var}(X)$$

$$\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y) + 2 \cdot \text{Cov}(X,  Y)$$

- If $$X$$ and $$Y$$ are independence, then their covariance must be zero, such that $$\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y)$$
- When covariance is positive, $$X$$ being more than its expectation means $$Y$$ is also more than its expectation. When covariance is negative, $$X$$ being big should make $$Y$$ be small.
- Covariance is symmetrically permutable about its arguments

---

## Week 7 Friday -- Polling
- We can approximate some discrete phenomena as a continuous distribution
- CLT steps
  1. Write event interested in as a sum of random variables
  2. Apply continuity correction if RVs are discrete
  3. Normalize RV with 0 mean and 1 std
  4. Replace RV with a unit normal distribution
  5. Write event in terms of $$\phi$$
  6. Look up CDF result in table
- How many people needed to poll to determine accurately how people will vote
- How to sample? Random sampling vs sample without replacement
- Accuracy of a poll is dependent on the number of people you choose, not the size of the population -- given polling idealization of with replacement
- Margin of error -- if you do many polls, 95% of the time, the value ou get will between the true value minus and plus the margin of error

---

## Week 8 Monday -- Tail Bounds
- Make clear that the substitution recommended by CLT, it is an approximation, need to do approx equal. 
- Handle similar scenarios in ways which give us airtight guarantees
- Tail bound -- most of the probability is near the center -- the probability concentrates near its expectation
- We don't wnat to do an exact computation but we are going to have an inequality -- probability is at least some value and at most some value
- Markov's inequality: Let $$X$$ be a random variable supported only on non-negative numbers. For any $$t > 0$$, or for any $$k > 0$$,

$$\mathbb{P}(X \ge t) \le \frac{\mathbb{E}[X]}{t}$$

$$\mathbb{P}(X \ge k \mathbb{E}[X]) \le \frac{1}{k}$$

- Markov's inequality is not often a tight bound, but it's one that we can find pretty easily. 
- Sometimes Markov's inequality gives you useless results, that is if your bound is less than the expectation
- Markov's inequality -- you can't be hugely more than your expectation. If you're inside your expectation, then so be it, it doesn't really matter or help that much
- We are trying to bound the tails of the distribution; the variance tells you about the tails. 
- Chebyshev's inequality: Let $$X$$ be a random variable. For any $$t > 0$$ or $$k > 0$$,

$$ \mathbb{P}(\vert X - \mathbb{E}[X] \vert \ge t) \le \frac{\text{Var}(X)}{t^2}$$
$$ \mathbb{P}\left( \vert X - \mathbb{E}[X] \vert \ge k \sqrt{\text{Var}(X)} \right) \le \frac{1}{k^2}$$

- Cute proof of Chebyshev, with $$Z = X - \mathbb{E}[X]$$. Uses Markov's inequality

$$\mathbb{P}(\vert Z \vert \ge t) = \mathbb{P}(Z^2 \ge t^2) \le \frac{\mathbb{E}[Z^2]}{t^2} = \frac{\mathbb{E}[Z^2] - \mathbb{E}[Z]^2}{t^2} = \frac{\text{Var}(Z)}{t^2} = \frac{\text{Var}(X)}{x^2}$$

- Chebyshev doesn't assume non-negative values. Chebyshev -- considring boht right and left tails, sometimes yo uhave a factor 2x number because you are accounting for both t ails.
- Markov tends to be used for one-tail bounds even though Chebyshev has access to the variance








