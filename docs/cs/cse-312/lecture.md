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
- Product rule: if you have a sequential process in which step $$k$$ has $$n_k$$ options, the totla number of possibilities is $$n_1 \cdot n_2 \cdot \hdots \cdot n_k$$
  - This is taking the Cartesian product of the relevant sets.
- Cardinality of a powerset is two to the cardinality of the original set
  - How to generate this?
  - For every element of the original set we can either include it or not include it -- this gives us the formula
- Complementary counting

---

## Week 1 Wednesday -- Counting
- In a sequence, order matters. 
- The number of ways to permute $$n$$ elements is $$n!$$.
- $$k$$-permutation: the number of $$k$$-element sequences of distinct symbols from a universe of $$n$$ symbols is $$n!/(n-k)!$$. Also denoted $$_nP_k$$. 
  - $$_nP_n = n!$$
  - $$_nP_0 = 1$$
- Derivation of choose formula
  - How many size $$k$$ subsets in a size $$n$$ univeral set?
  - How many ways can we get an ordered list? Choose a subset and put it in order, $$k!$$ ways to do so
  - But also we have $$k$$-permutation formula: $$_nP_k = ? \cdot k!$$. We can find ? by dividing both sides by $$k!$$.
- $$k$$-combination: the number of $$k$$-element subsets from a set of $$n$$ symbols is $$n! / (k!(n - k)!)$$
  - $$C(n, 0) = 1$$, $$C(n, n) = 1$$
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
  - $$2^n = \sum_{i=0}^n \binom{n}{i}$$
- Inclusion-exclusion principle
  - $$|A \cup B| = |A| + |B| - |A \cap B |$$
  - $$|A \cup B \cup C| = |A| + |B| + |C| - |A \cap B| - |B \cap C| - |A \cap C| + |A \cap B \cap C|$$

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






























