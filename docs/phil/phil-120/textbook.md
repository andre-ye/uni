---
layout: default
title: Lecture Notes
parent: PHIL 120
grand_parent: Philosophy
nav_order: 2
---

# Textbook Notes
{: .no_toc }

PHIL 120
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

## Chapter 1: Let the Adventure Begin

### 1.1: Welcome to the Newsroom
- Logic is the rules and principles of reasoning we use every day.
- Logic can also mean the study of our reasoning.
- Formal logical systems/logical systems: a model we create to study our reasoning.

### 1.2: Active Learning 
- Humans learn best by doing.
- *Tabula rasa* vs constructivism
- *Constructivism*: Students must actively build their understanding of the material..

### 1.3: Logic and Form
- We study the form/structure of reasoning an dinferences.
- Structure is a repeatable pattern.
- Replacing words with symbols allows us to reveal forms. 
- Reasoning depends on form.

### 1.4: Entailment = Validity
- In logic, we want to know when some logic guarantees something is true. 
- Deductive logical entailment/entailment.
- A set of premises entails a conclusion if whenever the premises are true, the conclusion is also true.
- A valid argument: the premises entail the conclusion.

### 1.5: Deductive vs Inductive Logic
- Inductive logic: probability and likelihood.
- Deductive logic: guarantee and certainty.
- Principle of Charity: give people the benefit of the doubt and interpret their arguments in a reasonable way, if possible.

---

## Chapter 2: Weird Cases of Validity

### 2.1: First Weird Case of Validity
- Circular reasoning: the prmeise and conclusion are the same.
- All circular reasoning is valid: if the premise is true, so is the conclusion.
- Circular reasoning is any case of assuming what you are trying to prove.
- Fallacy: a tempting but flawed form of reasoning. 
- Whether circular reasoning is good or bad depends on the circumstances one is in.

### 2.2: Second Weird Case of Validity
- Reasoning from a contradiction is valid.
- Contradiction - occurs when two sentneces say the opposite of each other. 
- Contradiction - a logical falsehood, a sentence that is necessarily false.
- Contradictory set - a group of sentences that can't be true at once.
- Any argument with contradictory premises is valid.
- Validity says that whenever all premises are true, the conclusion must be true. Contradictory premises satisfy this definition trivially because the premises can never be true.
- The only way to show that an argument is invalid is to find a way to make the premises true but the conclusion false.

### 2.3: Third Weird Case of Validity
- A set of premises can be empty. We can still use the definition of validity to assess the argument.
- If there are no premises, the conclusion must always be true.
- We can cehck the validity of an argument with an empty set of premises by checking if the conclusion is necessarily true.
- Logical turth -a sentence that is necessarily true because of the laws of logic.
- An argument with a logically true conclusion is always valid.


### 2.4: Necessary vs. Contingent
- Some statements are neither necessarily true or necessarily false.
- The opposite of necessary is contingent - something that may or may not be true.
- Necessary truths may manifest in a wide variety of laws and backgrounds.

### 2.5: Augmentation
- Augmentation: to add one or more premises to make an argument a new argument.
- When we augment a valid argument, the new premise may add relevant or irrelevant information. It may also contradict existing premises - but the argument will always remain valid.
- Induction - a set of premises may support or confirm a conclusion.
- Validity is a tipping point. once information guarantees the conclusion is true, you cannot destroy validity by adding information - only by taking the information away.

---

## Chapter 3: Argument Herooics

### 3.1: Identifying Arguments
- Identifying arguments can be surprisingly difficult.
- Argument: premises and conclusion.
- Premise signals: words that indicate a premise. "Because", "since", "for", "given".
- Conclusion signals: words that indicate a conclusion. "Thus", "so", "hence", "therefore".

### 3.2: Sentences
- Anything that can carry information can be studied with logic.
- Sentences can be short in pithy; some ask questions; some make comma ds.
- We care interested in assertions or statements: sentences that make cleaims.
- Sentences int he context of logic have truth values.

### 3.3: Soundness and Premise Truth
- Validity doesn't care about actual truth values; it is a hypothetical/conditional property.
- Truth concerns the relationship between premises and the world.

### 3.4: Bivalence
- Truth and falsity: truth values.
- In logical systems studied in this course, there are only two possible truth values (True and False).
  - These are bivalent logics.

---

## Chapter 4: Meet the Boolean Connectives

### 4.1: And here is the conjunction &
- BOOL: a logical system, short for Boolean logic.
- & is only allowed to connect two entences together; we technically shouldn't say P&Q&R but we can infer an order of operations.
- If English groups sentences clearly, we need to also group them in bool.
- & - conjunction, ampersand, and
- Sentences are atomic sentences/atoms - they are the building blocks of BOOL.
- Complex sentences are combinations of atomic sentneces.

### 4.2: Or Is it Disjunction v
- Disjunction, wedge, or: v.
- Disjunction is connective; we can use long strings of disjunctions.
- Conjuncts and disjuncts

### 4.3: Not to Neglect Negation ~
- The third connective is ~: negation, tilde, not.
- These three connectives are the Boolean connectives.
- Preserve as much structure whne translating into BOOL as possible.
- Negation always applies to the smallest possible scope of sentence.
- Scope - how much of a sentence a connective governs.
- Default: negation has a narrow scope.

### 4.4: Lost in Translation
- Some bits are lost in translation.
- BOOl helps us study how we reason.
- When we translate a complex sentence into BOOL, we need to capture logical commitmnets.

---

## Chapter 5: Features of Connectives

### 5.1: Scope
- Scope is the extent of a connective - how much of a sentence it governs.
- Each occurrence of a connective has its own scope.
- Main connective - the connective with wide scope, governs the whole sentence

### 5.2: Arity
- Arity: the number of inputs a connective takes.
- If a connective takes only one input, it is unary. If it takes two inputs, it is binary.

### 5.3: Advanced Boolean Translations
- 'Neither Pia nor Quinn is guilty'. `~P&~Q` or `~(PvQ)`
- You can translate neither/not in two ways.
- When connectives are the same time, we can allow chaining because any way of grouping yields the same result. `(P&Q)&R = P&(Q&R)`.
  - This property does not hold for mixed connectives.
- When you have mixed binary connectives and English doesn't group them, you must give both translations until you know which is correct.
- Ambiguity - when a word or sentence has two different but possible meanings.

---

## Chapter 6: Semantics for BOOL - Truth Tables
- Truth tables: charts showing every possible way a sentence could be true or false.
- Truth table for an atomic sentence $$P$$:

| P |
| --- | 
| T |
| F |

- Truth functionality: the truth value of any complex sentence is dependent on the truth values of the atomic sentences it is comprised of.

| P | ~P |
| --- | --- |
| T | F |
| F | T |

- Canonical form: reference columns are alphabetical; the patterns of Ts and Fs are awlays the same.

| P | Q | P&Q |
| --- | --- | --- |
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | F |

| P | Q | PvQ |
| --- | --- | --- |
| T | T | T |
| T | F | T |
| F | T | T |
| F | F | F |

### 6.2: Computing Truth Functions
- BOOL has only three connectives; all are truth functional.

| P | Q | ~Pv(Q&P) |
| --- | --- | --- |
| T | T | ? |
| T | F | ? |
| F | T | ? |
| F | F | ? |

- We begin by computing the inputs to the disjunction, which is the main connective.

| P | Q | ~P | Q&P | ~Pv(Q&P) |
| --- | --- | --- | --- | --- |
| T | T | F | T | ? |
| T | F | F | F | ? |
| F | T | T | F | ? |
| F | F | T | F | ? |

- Now, we can fill in the disjunction.

| P | Q | ~P | Q&P | ~Pv(Q&P) |
| --- | --- | --- | --- | --- |
| T | T | F | T | T |
| T | F | F | F | F |
| F | T | T | F | T |
| F | F | T | F | T |

- The number of rows in any table is $$2^n$$, where $$n$$ is the number of atomic sentences.

### 6.3: Semantics, Syntax, and Pragmatics

```
Semantics = meaning.

Syntax = grammar.

Pragmatics = use.
```

---

## Chapter 7: Using BOOL to Study Reasoning

### 7.1: Tautologies and Taut-Falsities
- An atomic sentence `P` might be true or false, but the complex sentence `Pv~P` cannot possibly be flase.
- Tautologies - logical truths, a sentence that is logically true because of the truth-functional connectives.
  - Can be identified when a sentence's truth table has all `T`s.
- `Pv~P` - law of the excluded middle; there is no third option or middle ground.
- Tautological falsities: a sentence with all Fs in its truth function.
- Tautologically contingent: a sentence with at least one T and F.

### 7.2: Equivalence (DeM and DN)
- Equivalence - two sentences already have the same truth value; they co-vary in truth value.
- Tautologically equivalent: sentences that are equivalent because of the truth-functional connectives.
- DeMorgan's Laws: `~(PvQ) ⇔ ~P&~Q`, `~(P&Q) ⇔ ~Pv~Q`.
- ⇔ is shorthand for 'logically equivalent'.
- Object language - formal language defined as part of the logical system.
- Metalanguage - language defined to talk about the language.
- Law of Double Negation: `P ⇔ ~~P`.

### 7.3: Validity
- When all the premises are true, the conclusion must also be true.
- Truth Table method: build a joint truth table to assess an argument for validity.
- Counterexample: a row on which the premises are true and the conclusion false.

---

## Chapter 8: BOOLean Algebra

### 8.1: Negation Normal Form
- Negation Normal form: any negations are in narrow scope.
- When a sentence is in NNF, the basic units are atomic sentences and negations of atomic sentences combined with disjunctions and conjunctions.
- Literals: atomic sentences and negations of atomic sentences.

### 8.2: Chain of Equivalences
- You can keep simplifying an expression using DeMorgan's laws and Double Negation.

```
~(PvQ) ⇔ ~P&~Q

~(P&Q) ⇔ ~Pv~Q

P ⇔ ~~P
```

- You must only use one principle at a time.
- Chain of equivalences: continuous transformations and simplifications as a result of DN and DeM.

```
~~~(~~(~P&~Q)v~(~R&~S))
⇔ ~((~P&~Q)v~(~R&~S))   DN
⇔ ~(~P&~Q)&~~(~R&~S)    DeM
⇔ ~(~P&~Q)&(~R&~S)      DN
⇔ ~(~P&~Q)&(~R&~S)      DeM
⇔ (PvQ)&(~R&~S)         DeM
```

### 8.3: Distribution Laws
- Distribution laws:

```
Pv(Q&R) ⇔ (PvQ)&(PvR)

P&(QvR) ⇔ (P&Q)v(P&R)
```

- Distribution changes the number of atomics in a sentence, but DeMorgan's doesn't.
- DeMorgan's law is best thought of as 'flipping' a conjunction to a disjunction and vice versa.
- Sometimes, you need to distribute with larger 'chunks'. For instance, you can distribute `(A&B)v` in `(A&B)v(C&D)` to form `((A&B)vC)&((A&B)vD)`.
- After we distribute conjunctions and disjunctions, we don't have disjunctions with wide scope around conjunctions.

### 8.4: Three More laws
- BOOL obeys laws that have algebraic counterparts.
- Associativity

```
(P&Q)&R ⇔ P&(Q&R)

(PvQ)vR ⇔ Pv(QvR)
```

- Commutativity

```
P&Q ⇔ Q&P

PvQ ⇔ QvP
```

- Idempotence:

```
P&P ⇔ P

PvP ⇔ P
```



























