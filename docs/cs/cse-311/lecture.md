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
- Forall proofs: reason about properties and show arbitrary point results
- Existential proofs (disprove forall proofs)
  - Give an example
  - Proof by cases. 
- $$x$$ divides $$y$$ means that $$x$$ is a factor of $$y$$. $$x \mid y$$.

---

## Week 5 Monday -- Number Theory
- Division theorem
- mod -- refers to a set of rules, modular arithmetic -- arithmetic mod $$k$$.
- $$13 \equiv 1 (\text{mod } 12)$$. Or $$13 \equiv_{12} 1$$.
- Formal definition: Let $$a, b, n \in \mathbb{Z}$$ and $$n > 0$$. $$a \equiv_n b$$ iff $$n | (b - a)$$.
- $$a \equiv_n b \to a + c \equiv_n b + c$$
- Proof by contrapositive: instead of showing $$p \to q$$, show $$\neg q \to \neg p$$. Use if there are a lot of nots involved.

---

## Week 5 Wednesday -- Number Theory and Induction
- Each step has to follow only from what is before it. Do not begin from a false statement.
- We must derive from known truths.
- How do we know that recursion works?
- Two cases we need: base and recursive
- How to prove this: define a truth function $$P$$. We need to show that $$\forall k [P(k) \to P(k+1)]$$
- Steps for induction:
  1. Define $$P(n)$$ and state proof by induction on $$n$$
  2. Show the base case
  3. Suppose $$P(k)$$ for an arbitrary $$k$$
  4. Show $$P(k+1)$$
  5. Suggest that $$P(n)$$ is true for all $$n$$ by induction.

---

## Week 5 Friday -- Strong Induction
- Take-home midterm
- 2 hours to submit solutions for the midterm
- Induction proofs can work on all recursive-type problems
- $$P(n)$$ must be true or false.
- When making arithmetic proofs, move from LHS to RHS to avoid backwards proofs.
- Inductive hypothesis: $$P(k)$$ holds
- Fundamental theorem of arithmetic: every positive integer greater than 1 has a unique prime factorization.
- Induction on primes: use inductive step in cases (prime and composite)
- Strong induction: we assume $$P(\text{base case})$$ through $$P(k)$$ -- same fundamental idea as weak induction.

---

## Week 6 Monday -- Proof by Contradiction
- Proof by contrapositives
- Prove that $$\neg P \to F$$, so $$\neg P$$ is false, so $$\claim \equiv T$$.
- Proof by contradiction will be a messy process of exploring the world -- you will write down things which may or may not be useful.
- Proofs in class: there are infinitely many primes, $$\sqrt{2}$$ is irrational

---

## Week 6 Wednesday -- Wrap-Up for Number Theory
- Greatest common advisor and least common multiple
- $$gcd(a, b) = gcd(b, a % b)$$
- Euclidean algorithm: $$7x \equiv_n 1$$
- Division is not defined for modular arithmetic
- Bezout's theorem: if $$a$$ and $$b$$ are positive integers, then there exist two integers $$s$$ and $$t$$ such that $$gcd(a, b) = sa + tb$$.
- Given two numbers, we can find the GCD quickly. 
- RSA encryption
  - $$n = pq$$; send you $$n$$ and $$e$$.
  - Send unmber $$a$$. Compute $$C = a^e % n$$ and send Amazon $$c$$.
  - Amazon computes the multiplicative inverse of $$e$$ in mod $$[p-1][q-1]$$
  - Amazon finds $$C^d % n$$, which is $$a$$.
- How to raise large numbers to exponents mod $$n$$?

---

## Week 6 Friday -- Even More Induction
- Induction across cases
- Forcing expressions to appear
- Watch out for hideen assumptions in your induction step.

---

## Week 7 Monday -- Structural Induction
- Recursive definitions of sets
  - Basic step: certain elements which are in the element
  - Recursive step: if some element is in the set, then this other element is in the set
  - Exclusion rule: every element in the set is from the basis step or a finite number of the recursive step.
- Structural induction: prove $$P(s)$$ for all $$s \in S$$: the inductive step is to prove $$P$$ for a new element in the set.
- Weak induction is a special case of structural induction.
- Recursion on strings
  - $$\Sigma$$ -- the alphabet
  - $$\sum^*$$ -- the set of all strings you can build off the letters
  - $$\epsilon$$ -- the empty string
  
---

## Week 7 Wednesday -- Regular Expressions and Structural Induction
- Recursive definition of string
- Binary trees are a source of structural induction
- Basis: a single node
- We can define the size and height of a tree recursively
- Size: size of left and right nodes plus one
- Height: maximum of height of left tree and height of right tree plus one
- Regular expressions -- find a certain format of string. 
- A set of strings is a language.
- $$(0 \cup 1)*$$ -- the set of all binary strings

---

## Week 7 Friday -- More Regular Expressions, Context Free Grammars
- A language is a set of strings
- Regular expressions are recursively defined. 
  - Recursive steps: or, concatenate, star operator
- or with empty string to make a character optional
- Constructing regular expressions by adding up
- Check empty and low-character strings
- 'not' is hard but you can negate at a low level
- To say at least one copy, use  `aa*`.
- Context Free Grammar: a way of defining a set of strings.
- CFG: finite set of production rules over:
  - Terminal symbols, $$\sum$$
  - Nonterminal symbols, $$V$$
  - Start symbol, $$S$$ 
- A production rule for a nonterminal: $$A \to w_1 \vert w_2 \vert ... \vert v_k$$

---

## Week 8 Wednesday -- Context Free Grammars
- Alphabet of terminal symbols, final set of terminal symbols, and a start symbol.  
- Poorly defined CFGs allow mutliple ways to construct a string in which the construction should evaluate to different things. Ambiguous
- Parse tree can be generated from CFG. Preserves identical strings but with different structures.
- A binary relation from A to B is a subset of $$A \times B$$
- A binary relation on A is a subset of $$A \times A$$
- Relations have common properties.

---

## Week 8 Friday -- Relations
- A relation is a subset of $$A \times B$$. 
- Properties of relations for relations $$R$$ on sets $$S$$
  - Symmetry: $$\forall a, b \in S, [(a, b) \in R \to (b, a) \in R]$$
  - Transitivity: $$\forall a, b, c \in S, [(a, b) \in R \wedge (b, c) \in R) \to (a, c) \in R]$$
  - Antisymmetric: $$\forall a, b \in S, [(a, b) \in R \wedge a \neq b \to (b, a) \notin R]$$
  - Reflexivity: $$\forall a \in S, [(a, a) \in R]$$
- Some relationships are neither symmetric or antisymmetric. You can only be both if the implication is vacuous.
- Equivalence realtion: reflexive, symmetric, and transitive
- Partial order Relation: reflexive, antisymmetric, transitive. Can partially put things into order.
- Directed graphs: $$G = (V, E)$$.
  - $$V$$ is a set of vertices -- set of elements
  - $$E$$ is a set of edges (ordered pairs of vertices)
- Graphs can represent relations
- Simple path: distinct vertices
- Cycle: end is same vertex as beginning
- Simple cycle: simple path plus edge $$(v_k, v_0)$$ for $$k > 0$$
- Combining relations
- Relations can be represented using graphs.
- Reflexive-transitive closure of $$R$$. Show a relation which is: minimum number of edges needed to add to $$R$$ to make it reflexive and transitive

---

## Week 9 Monday -- Finite State Machines
- Deterministic finite automaton -- every action is determined, based on the input. 
- Get a string as input. Read one character at a time and update its state. The machine is a finite state of vertices.
- Each state which is not the start will either be accept or reject.
- DFAs cannot count arbitrarily high because it rquires an infinite number of states.
- Cross product construction -- Cartesian product of states, helps us do and configurations

---

## Week 9 Wednesday -- Nondeterministic Finite Automata
- Bit shift register -- remembers previous states
- WHat is the smallest possible DFA for a problem?
- There is a unique minimum DFA for every language
- How can we make our DFAs more powerful?
- Deterministic: your next step is determined, there is one option you can go
- Non-deterministic: you have a 'choice' of where you can go. A given state can have any number of outbound ideas.
- If there is one set of choices which leads us to an accepting state, we accept.
- You have to finish in an accepting state; rejected if it fails in an accepting state
- How to think about NFAs: outside observer, perfect guesser, parallel exploration
- Nondeterminism lets us give simple descriptions of complex objects

---

## Week 9 Friday -- Regular Languages
- NFA
- or statements between DFAs can be represented neatly with NFAs
- Cross product construction for and
- Negation on NFAs is not so easy
- Parallel exploration view of NFAs
- DFAs are a proper subset of NFAs vs DFAs = NFAs?
- Kleene's theorem: for every language $$L$$
  - $$L$$ is the language of a regular rexpression iff
  - $$L$$ is the language of a DFA iff
  - $$L$$ is a language of an NFA
- If a language can be represented as an NFA, DFA, or regular expression, it is a regular language.
- Constructive proofs
- There are languages which are not regular but CFGs. CFGs are more powerful than regular languages.

---

## Week 10 Monday -- Regularity
- Parallel exploration view allows us to convert NFAs to DFAs
- We can build a DFA from an NFA by using states as elements from the powerset of NFA states and linking epsilon transitions
- Nondeterminism isn't magic, but really efficiency 
- Don't say in order to do X, machine must do Y. Impossible to rigoorusly justify.
- Make claims about irregularity via proof by contradiction. 
- A DFA is deterministic and finite.
- How to force the mistake? 
- $$S$$ is an infinite set of strings. There are two different strings $$x, y$$ such that $$x$$ and $$y$$ go to the same state. Consider the string $$z$$. $$xz$$ and $$yz$$, one of them is in the language and the other one is not in the language. But they should be in the same string.

---

## Week 10 Wednesday -- (Un)Countability
- Domain, codomain, bijection, surjection, injection
- Injection: each input goes to one output
- Surjection: each output has one input
- Bijection: both injection and surjection
- There exists a bijection iff both sets are the same size
- Countable: there is an injection from $$A$$ to the natural numbers. 






















