---
layout: default
title: Lecture Notes
parent: CSE 311
grand_parent: Computer Science
nav_order: 1
---

# Lecture Notes
{: .no_toc }

CSE 311
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

## Week 1 Wednesday -- Introduction to Propositional Logic
- Syntax - words and rules for combinations of words
- Proposition - a statement that has a truth value and is well-formed.
- Can propositions have a truth value if they exceed the limits of human knowledge? Prof says yes, but maybe not...
- We want to talk about arbitrary ideas, so we use propositional variables. Lower-case letters, starting from $$p$$ for proposition.
- Logical connectives: $$\wedge$$ (and), $$\vee$$ (or), $$\neg$$ (not)
- Implications: $$p \to q$$. $$\neg(p \wedge \neg q)$$.
- Implication as a promise: can you demonstrate that I am lying / not holding the promise?
- $$p\to q$$ is not equivalent to $$q \to p$$: $$\to$$ is not a commutative operator.

---

## Week 1 Friday -- Logic
- Implication: $$p \to q$$
- Order of operations: parentheses, negation, and, or, implication, biconditional
- $$p \Leftrightarrow q$$: biconditional -- $$p$$ if and only if $$q$$, $$p$$ iff $$q$$, $$p$$ is equivalent to $$q$$, $$p$$ is necessary and sufficient for $$q$$
- Exclusive or: $$(p \vee q) \wedge (p \wedge q)$$
- Two propositions are equal iff they are character-for-character identical: $$(p \wedge q) \neq (q \wedge p)$$.
- Two propositions are equivalent iff they have the same truth table: $$p \wedge q \equiv q \wedge p$$
- $$a \Leftrightarrow b$$ is a statement across two propositions with variable variable values; $$a \]equiv b$$ is a statement across all possible truth values
- DeMorgan's laws: $$\neg(p \vee q) \equiv \neg p \wedge \neg Q$$, $$\neg(p \wedge q) \equiv \neg p \vee \neg Q$$.

























