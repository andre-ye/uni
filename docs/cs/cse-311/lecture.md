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

## Week 1 Friday -- Propositional Logic
- Implication: $$p \to q$$
- Order of operations: parentheses, negation, and, or, implication, biconditional
- $$p \Leftrightarrow q$$: biconditional -- $$p$$ if and only if $$q$$, $$p$$ iff $$q$$, $$p$$ is equivalent to $$q$$, $$p$$ is necessary and sufficient for $$q$$
- Exclusive or: $$(p \vee q) \wedge (p \wedge q)$$
- Two propositions are equal iff they are character-for-character identical: $$(p \wedge q) \neq (q \wedge p)$$.
- Two propositions are equivalent iff they have the same truth table: $$p \wedge q \equiv q \wedge p$$
- $$a \Leftrightarrow b$$ is a statement across two propositions with variable variable values; $$a \]equiv b$$ is a statement across all possible truth values
- DeMorgan's laws: $$\neg(p \vee q) \equiv \neg p \wedge \neg Q$$, $$\neg(p \wedge q) \equiv \neg p \vee \neg Q$$.
- 

---

## Week 2 Monday -- Contrapositive Proof
- We can express implication as $$p \to q \equiv \neg (p \wedge \neg q) \equiv \neg p \vee q$$
- Logical connective properties
  - Associative across conjunction and disjunction
  - Distributive
  - Absorption
  - etc.
- Proof-writing: make sure you know what you are trying to show.

---

## Week 2 Wednesday -- Normal Forms and Predicates
- We do proofs not just to prove things but also to know why they are true. 
- Modifying implications:
  - Implication: $$p \to q$$
  - Converse: $$q \to p$$
  - Contrapositive: $$\neg q \to \neg p$$
  - Inverse: $$\neg p \to \neg q$$
- Proving implication and contrapositive are equivalent:

$$p \to q \\ \equiv \neg p \vee q \\ \equiv \neg \neg \neg p \vee \neg \neg q \\ \equiv \neg \neg q \vee \neg \neg \neg p \\ \equiv \neg \neg \neg q \to \neg \neg \neg p \\ \equiv \neg q \to \neg p$$

- Work from both ends, but make sure it makes sense from top to bottom.
- Digital logic:
  - Digital circuits, computing with logic
  - Gates correspond to propositional connectives.
- More vocabulary
  - Tautology -- always true
  - Contradiction -- always false
  - Contingency -- can be both true and false
- Boolean algebra
  - $$+$$ for disjunction
  - $$\cdot$$ for conjunction
  - `'` for negation
  - Boolean semiring
- Canonical forms for a truth table: have a standard way of going from a truth table to an expression.
  - Disjunctive normal form (DNF): conjoin all the conditions for truthhood and disjunct against them
  - Conjunctive normal form (CNF): disjoin the negations of all the conditions for falsehood and conjoin against them
  - Don't simplify canonical forms

---

## Week 4 Monday -- Quantifier Proofs, English proofs
- Direct proof rule -- assume and get result to show an implication
- Arbitrary: just another variable doesn't depend on variables
- Fresh: new symbol, hasn't been used before
- You need to eliminate all dependencies when you eliminate a universal.
- Symbolic proofs -- preparation for writing proofs in English

---

## Week 4 Wednesday -- English Proofs and Sets
- Definitions are inherently iff statements.
- Sets are an unordered group of distinct elements.

$$A \subset B \equiv \forall x (x \in A \to x \in B)$$

$$A = B \equiv A \subset B \wedge B \subset A$$

---

## Week 4 Friday -- Sets and Number Theory
- The intersection of the complement of $$A$$ and the complement of $$B$$ is the complement of the union of $$A$$ and $$B$$
- Analogs of DeMorgan's laws













