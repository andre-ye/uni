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
  - $$P(E) = \sum_{\forall i} P(E \cap A_i)$$
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
  












