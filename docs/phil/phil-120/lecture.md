---
layout: default
title: Lecture Notes
parent: PHIL 120
grand_parent: Philosophy
nav_order: 1
---

# Lecture Notes
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

## Week 1 Monday - Syllabus and Introduction

Course Structure
- Lectures will be recorded
- Quiz section is about being with a small group.
- If you miss quiz section, talk to your TA as soon as possible.
- There's a lot of technical work on the course.
- There are problem sets due every weekend. Succeed by practicing and going to course section.

Starting the course
```
{Premise}
1. All witches burn.
2. All wood burns.

{Conclusion}
Therefore,
3. Witches are made of wood.
```

- Premises are sets of claims. 
- Something will always follow from those premises.
- A conclusion is built from the premises.
- Two properties of arguments:
  - Valid: if the premises are true, the conclusion must be true
  - Invalid: not valid, the truth of the premises doesn't guarantee the truth of the conclusion
- Argument:
```
{Premise}
1. If she weighs the same as a duck, then she's made of wood.
2. If she's made of wood, then she's a witch.
3. She weighs the same as a duck.

{Conclusion}
Therefore,
4. She's a witch.
```
> This argument is valid. The premises logically lead to the conclusion. Good: it's valid. Bad: premises are false.
- We want arguments to be good both in validity and veracity of premises.

```
{Premise}
1. All humans are mortal.
2. Socrates is human.

{Conclusion}
Therefore,
3. Socrates is mortal.
```
> This argument is valid.

- Syllogism: two premises and a conclusion. At least one premise is a generalization.
- Soundness: valid argument *and* true premises. The gold standard of arguments.
  - The conclusion must be true.

```
{Premises}
1. All grudumps are lumps.
2. Mump is a grudump.

{Conclusion}
Therefore,
3. Mump is a lump.
```

- You can assess the validity of the argument without knowing the veracity of the premises *or what the premises even mean.*

**Schema/Form:**
1. All `A`s are `B`.
2. `n` is an `A`.
Therefore,
3. `n` is a `B`.

- Validity is a property of the *form* of an argument, rather than the argument itself.
- We can do logic with symbols even if we don't understand their meaning, or even if they don't mean anything!
- You cannot assess the validity of the premises, and therefore the soundness of the argument, without knowing what symbosl mean.
- Validity, however, is a formal argument.

```
{Premises}
1. Tom Cruise is a Martian.
Therefore,
2. Tom Cruise is a Martian.
```
- Circular reasoning - the premise is the same as the conclusion. Technically a valid argument, but not really quite meaningful. The argument could never persuade someone to believe the conclusion on the basis of the premise because the conclusion is the premise.
- Fallacy - tempting but problematic reasoning. Circular reasoning is a fallacy, but valid. 

```
{Premise}
1. There are 1 million tickets in the lottery.
2. Pia has one ticket.

{Conclusion}
Therefore,
3. Pia will not win.
```
- Two different types of logic:
  - *Deductive logic*: the study of deductive validity. If the prmeises are true, the conclusion must be true with 100% certainty.
  - *Inductive logic*: the study of probabilistic reasoning - if the premises are true, the conclusion is probably true.

*Why take this class?*
- The textbook is entirely online and free.
- The textbook is interactive. Textbook problems are no-stakes practice.
- Problem sets are Canvas quizzes. These can be taken 10 times.
  - Don't have too much pressure taking the quiz. Only your highest score will be kept.
  - The quiz will tell you how many you got wrong, but not which questions you got wrong.
- Exams are closed-book and closed-note.
- People always use logic, regardless of their discipline or career.
- You will always be using logic and subject to other people's logic.

---

## Week 1 Wednesday

```
1. Pia is looking at Quinn.
2. Quinn is looking at Neela.
3. Pia is married.
4. Neela is not married.
Thus,
5. A married person is looking at an unmarried person.
```

A valid argument!


- Logic - a system of knowledge. Logic can both be how we reason, 'natural logic' - as well as the study of how we reason.
- We will build formal logical systems.
- There are multiple different formal logical systems. 
- Logical systems have several features:
  1. Formal language
  2. Semantics
  3. Proof theory
- Weird cases of validity:
  1. Circular reasoning
  2. Contradictory premises
  3. Logically true conclusion
- Ask: is it possible for the premises to be True and the conclusion False?
- Contradictory premises - logical falsehoods (Every student eats meat every day, Some students never eat meat.)
- We must know what logical truth and falsity is.
- Logical truths
- Equivocation: one symbol being used to refer to multiple meanings.
- Not all truths are logical truths.
- Principle of the excluded middle - certain traits we assume are binary.
- Necessary truths: guaranteed to be true because of some law.
- Logical truths: Pia = Pia. Law of logic: everything is itself.
- It is not always true that necessary truths are logical truths.
- A necessary truth is a truth that couldn't possibly be false. Other laws can guarantee the truth of a statement. Laws of physics, chemistry, economics, etc.
- However, in the context of this class, necessary truths derive their status as necessarily true as a result of being logically true.
- Mathematics and logical roots.
- Contingency - the statement cannot be logically true or false. (Pia likes movies, If Pia likes movies then Raquel likes Pia.)
- The reason why statements might not be logically true is because they are contingent.
- A contingent statement might be true, but it's not logically wired to be true or false.
- Some things are not logically possible - these are logical falsehoods.


---

## Week 1 Friday
- Augmentation: only adding premises. By adding premises, you change the argument.
  - You can add irrelevant information. This doesn't impact the validity of the argument.
- Augmentation never changes the validity of an argument.
- Inductive confirmation is not necessarily preserved under augmentation. You can destroy inductive validity with additional augmentation.
- Bool: `either Pia likes logic and philosophy or she likes history and stats` $$\to$$ `(L & P) v (H & S)`.

---

## Week 2 Monday
- Last week: discussed components of the logical system.
- We can give meaning to truth values and begin analyzing argument.
- Understanding truth values and how connectives have truth values.
- Syntax vs Semantics vs Pragmatics
- Logical systems have different dimensions or perspectives. 
- Syntax: grammar, symbols, form, formal proofs.
- Semantics: anything to do with meaning, content, interpretation, truth, informal proofs.
- Pragmatics: use, how words can be used to say things other than their semantic meaning.
- Ryle's review of Heidegger's *Being and Time*. Pragmatics:

> "*Being and Time*, it is worth mentioning, is most beautifully printed and the pages have generous margins." -Ryle

- Truth Functional: the truth value of the complex sentence deepnds only on the truth values of the atomic sentences.
- Truth tables - used to compute all possible output states of a logic expression
- Functions
  - Binary functions
- Logical equivalence
- Lost in translation: any meaning that's not truth functional.
- We can manipulate logical equivalences.
- DeMorgan's Laws: `~(PvQ) ⇔ ~P&~Q, ~(P&Q) ⇔ ~Pv~Q`.

---

## Week 2 Wednesday
- Logical equivalence - two statements covary in truth value.
- Validity is a syntactic property.
- BOOL isn't all of logic - what can you do with BOOL? Prove some sentences are equivalent, prove some sentences are not equivalent, for any equivalent sentences, prove they are equivalent, prove some sentences are necessarily true/false, for any logical truth, prove it is necessarily true, prove any tautology fo BOOL is necessarily true, prove some arguments are (in)valid, prove any valid argument is valid.
- Bivalence - finite. We can prove truth functions are logically equivalent.
- Limitations to the truth table method: BOOL only covers a part of logic, truth-functional logic. It doesn't cover things that cannot be understood truth-functionally. BOOL cannot prove things without boolean connectives.
- Tautology: all Truths. Taut-falsity: all Falses. Contingent: at least one Truth or Falsity.
- There is a technique you can use that goes beyond what BOOL alone can do: but it goves above Boolean logic to delete rows of the truth table. If you are assessing if a statement is a tautology or not, you can use the 'delete rows method'.
- BOOL does not know anything about the atomic sentences, but you may. You can imagine rows with stupid/illogical atomic value sentences just don't exist. 
- A logical truth is not necessarily a tautology - it is a logical truth by other areas of logic or reasoning.
- Tautologies: a type of necessary truth. Logical truths that depend for their truth just on the truth-functional connectives. The truth table is all Ts.

---

## Week 2 Friday 
- To be a literal, a sentence cannot be equivalent to an atomic sentence - it must be an atomic sentence or its negation.
- Interchangeable languages - there are other sets of symbols. Pipes, wedges, up-wedges, double pipes, exclamation marks.
- The Chart:
  - Contingent truths > logical truths > tautologies
  - Contingent falsities > logical falsities > taut-falsities
- Contingent properties - depend on knowledge about the world.
- Necessarily true vs logically true
- Tautologies - a type of necessary truth. 
- `~(a<a)` is a logical truth, but not a tautology; `a<a` is an atomic sentence.
- Tautologies - `Pv~P`; logical truths - `~(a<a)`, `~Y`.; contingent truths - `L`, `~S`, `~LvS`
- `W` - Seattle is in WA - a contingent truth. `~W` - Seattle is not in WA - a contingent falsity.
- Delete rows method. `Seattle isn't in WA and Pia = Pia`: a contingent falsity. `Seattle isn't in WA or Pia = Pia`: logical truth.
- Conjunctions are a liability, disjunctions with a truth are logical truths. For some logically true statement `P` and a contingent statement `Q`, `PvQ` is a logical truth and `P&Q` is contingent.
- Properties of arguments: prove some arguments are valid or invalid.
- Logical equivalence is the same as bi-directional entailment.

---

## Week 3 Monday
- Proofs - an important application of BOOL. We can add a computational proof-making system that gives BOOL a lot of power to prove (in)validity.
- This property of BOOL is essential in terms of the import of logic to our everyday lives.
- Negation Normal Form (NNF): sentences made of &, v, and literals in which all `~` are in narrow scope, just operating on atomics.

```
~((P&~Q)v~(R&S))
~(P&~Q)&(R&S)
(~PvQ)&R&S)
```

- Chain of equivalences
- You don't have to use all of the premises in a proof.
- In the proof space, we begin with `Proof:` and end with `Done.`
- Proof: a step-by-step demonstration of validity or invalidity; it is not an argument. Every step must be both valid and obvious.
- Characteristics of proofs: restating a premise, intermediary conclusions, final conclusion.
- Formal: in BOOL using syntactic inference rules - intro, elim, reit. Informal: in English using 'obviously' valid inferences. Valid (Truth Table Method, Other methods) and Invalid (Counterexample).
- Formal proofs cannot prove that an argument is invalid. Proofs of an invalid argument must be informal.

---

## Week 3 Wednesday
- The position of the gates doesn't matter - it is the architecture/relationship between the possible truth values of each that matter.
- History of computing: finding better engineering solutions for the engineering problem of negation.
- Fluid computers: make fluid the basic state and run bubbles through the computation system.
- Problem of unstated assumptions for informal proofs in English - proving something requires disambiguating concepts.
- Counterexample: a specific case in which the premises are true and the conclusion is false. Giving a counterexample is a type of informal proof.
- Venn Diagrams - encoding information from a truth table using Venn Diagrams. We could do this task entirely with pictures rather than with symbols.

---

## Week 3 Friday
- Venn diagrams for more than three atomics: ellipse-like/rainbow-like, or three-dimensional surfaces.
- Next week - most important material in the entire quarter. Formal proofs are the most difficult in the class, and it's not going away. We are going to make a larger system beyond BOOL called PROP, then another system called FOL. All the Boolean bits are in the system.
- Mastering the system of doing computations and proofs will need to be done in progressively more complex applications. You must get comfortable with these soon.
- Midterm - Wednesday of Week 5

```
1. ~~A&B                  Premise
2. ~~A                    &Elim;1
3. A                      ~Elim;2
4. AvC                    vIntro;3
5. AvCvD                  vIntro;4
6. B                      &Elim;1
7. (AvCvD)&B              &Intro;5,6
```

- BOOL: alanguage, semantics, formal proofs.
- Proof theory - syntactic inference rules, formal proofs in contrast to previous informal proofs.
- Informal proofs are context-dependent. Each step of a good proof must be valid and obvious; each step of a proof theory makes strict what is allowed for inference rules.

```
1. ~~(P&~~(~~Q&R))        Premise
2. P&~~(~~Q&R)            ~Elim;1
3. P                      &Elim;2
4. ~~(~~Q&R)              &Elim;2
5. ~~Q&R                  ~Elim;4
6. ~~Q                    &Elim;5
7. Q                      ~Elim;6
8. R                      &Elim;5
9. Qv~P                   vIntro;7
10. (Qv~P)vT              vIntro;9
11. ((Qv~P)vT)&R          &Intro;10,8
```

---

## Week 4 Monday
Tools:
```
&Intro
&Elim
vIntro
vElim -> Proof by cases
~Intro -> Reductio/proof by contradiction
~Elim
Reit
```

- Proof by cases: iterate over each case. Temporarily assume the truth of a case. While premises hold true for the entire argument, cases only hold true for a subcase.

```
1. ~~PvQ     Premise
2. | ~~Q     Assume
3. | P       ~Elim
4. | PvQ     vIntro;3
5. | Q       Assume
6. | PvQ     vIntro;5
7. PvQ       vElim;1,2-4,5-6
```

- Knights and Knaves puzzles.
  - Knights always speak truthfully.
  - Knaves always lie.

> Two doors: one leads to safety, and the other to certain doom. Guard 1 says: Either I speak falsely or he speaks truthfully. Guard 2 says: You should enter the door on the left.

1. Case 1: Guard 1 is a knight. Either Guard 1 speaks falsely, or Guard 2 speaks truly. Guard 2 must speak truly, and we need to take the door on the left.
2. Case 2: Guard 1 is a knave. Guard 1 speaks truly and Guard 2 speaks falsely. This is a contradiction.
3. The correct door is the left door.


- Disjunctive syllogism:

```
1. PvQ
2. ~P
Thus
3. Q
```

> Guard 1: #2 tells the truth. Guard 2: #1 and #3 speak the same. Guard 3: Door 2 is the way out.

1. Case 1: Guard 1 is a Knight. Therefore, Door #2 is the way out.
2. Case 2: Guard 1 is a Knave. Therefore, Door #2 is the way out.
3. Door #2 is the way out.


- Think about: what is the most useful infromation? You want to be able to interact with other guards.
- `~Intro` - proof by contradiction, reductio ad absurdum (reduce to an absurdity/contradiction), reductio.
- `#Intro`, `#Elim`

---

## Week 4 Wednesday
- Contradictory sets:
  - `{Pia is guilty, Pia is Wanda, ~{Wanda is guilty}}`
  - `{P&#}`
  - `{Pia is guilty, Pia is Wanda, Wanda is guilty, Pia isn't Pia}`
  - `{Pia is guilty, Quinn is guilty, Wanda is guilty, Only 2 people are guilty}`
  - `{Pv#, ~P}`
- Tautological falsity and contradiction are different.
  - Every contradiction is some sort of logical contradiction.
  - A subset: tautological contradiction.
- A tautological contradiction occurs within sets, a tautological falsity occurs within a sentence itself.
- Tautological contradiction: no single row in the truth table in which all statements are true.
- A contradiction: a logical falsity, a sentence that can't be true.
- A contradictory set: a set of sentneces that cannot simultaneously be true.

```
1. ~~P&(~P&Q)    Premise
2. ~~P           &Elim;1
3. P             ~Elim;2
4. ~P&Q          &Elim;1
5. ~P            &Elim;4
6. #             #Intro;3,5
7. R             #Elim;6
````

```
1. | P&~P      Assume
2. | P         &Elim;1
3. | ~P        &Elim;1
4. | #         #Intro;2,3
5. ~(P&~P)     ~Intro;1-4
```

---

## Week 5 Monday

Prove `A&B` $$\to$$ `~(~Av~B)`
```
1. A&B         Premise
2. | ~Av~B     Assume
3. || ~A       Assume
4. || A        &Elim;1
5. || #        #Intro;3,4
6. || ~B       Assume
7. || B        &Elim;1
8. || #        #Intro;6,7
9. | #         vElim;2,3-5,6-8
10.~(~Av~B)    ~Intro;2-9
```

Equivalences: bidirectional equivalences.

Which ones are true?

| Statement | Truth |
| --- | --- |
| A contingent truth can entail a contingent truth. | True. Circular logic is a trivial example. |
| A contingent falsehood can entail a contingent falsehood. | True. Circular logic is also an example. |
| A contingent falsehood can entail a contingent truth. | True. `A&B`, where `A` is not true but `B` is true. |
| A contingent truth can entail a contingent falsehood. | False. If we have a contingent truth that entails a contingent falsehood, then the argument isn't valid. |
| A contingent truth can entail a necessary truth. | True. Necessary truths can be entailed by anything. |
| A necessary truth can entail a contingent truth. | False. There are cases in which the necessary truth is true (always) but the contingent truth is sometimes false. Thus, the argument is invalid. |
| A contingent truth can entail a necessary falsehood. | False. Nothing matters, because the rpemise is true but the conclusion is always false. This is the definition onf invalidity. |
| A necessary flasehood can entail a contingent truth. | True. The premises are never true; therefore we can conclude anything. |

- Don't confuse truthhood and falsehood with validity.
- Is there a way to obtain a tautology without using any disjuncts?

```
1. ~(P&Q)      Premise
2. | ~(~Pv~Q)  Assume
3. || ~P       Assume
4. || ~Pv~Q    vIntro;3
5. || #        #Intro;3-4
6. || ~Q       Assume
7. || ~Pv~Q    vIntro;6
8. || #        #Intro;6-7
9. | P         ~Intro;3-5
10.| Q         ~Intro;6-8
11.| P&Q       &Intro;9-10
12.| #         #Intro;1,11
13.~Pv~Q       ~Elim;2-12
```

```
1. ~P                      Premise
2. ~(Q&(~P&~R))            Premise
3. | ~(~QvR)               Assume
4. || ~Q                   Assume
5. || ~QvR                 vIntro;4
6. || #                    #Intro;3,5
7. || Q                    ~Intro;4-6
8. || R                    Assume
9. || ~QvR                 vIntro;8
10.|| #                    #Intro;3,9
11.|| ~R                   ~Intro;8-10
12.||~P&~R                 &Intro;1,11
13.||Q&(~P&~R)             &Intro;

4. || R                    Assume
5. || ~QvR                 vIntro;4
6. || #                    #Intro;3,5
7. | ~R                    ~Intro;4-6
8. | ~P&~R                 &Intro;1,7
9. || Q                    Assume
10.|| Q&(~P&~R)            &Intro;9,8
11.|| #                    #Intro;2,10
1
13.~QvR                    ~Intro;3-12

rip
```

## Week 5 Friday
- Antecedent, consequent, conditional
- Conditional vs biconditional
- PROP - short for 'propositional logic'. 
- Conditional and biconditional both get eliimination rules.
- Conditionals are not necessarily causal; even though causalities form conditionals.
- If $$P$$, then $$Q$$: $$P$$ is the antecedent.
- $$Q$$ if $$P$$: $$P$$ is the antecedent.
- $$P$$ only if $$Q$$: $$P \to Q$$
- $$A \iff B = (A \to B) & (B \to A)$$
- 'if and only if', 'just in case': synonyms for bidirectionality.
- `H->M`: `H` is sufficient for `M`, `M` is necessary for `H`
- `P->Q` is trivially/vacuously true if `P` is false.

```
~(P->~Q)
T T FFT
F T TTF
F F TFT
F F TTF
```

```
~Q->~P
F  TF
F  TT
T  FF
T  TT
```

- Contrapositive: $$P\to Q \iff ~Q \to ~P$$
- `~PvQ` is the key equivalent to `P->Q`.
- `~(P->Q) <-> ~(~Q->~P)`

$$A \iff B = (A \to B) & (B \to A)$$

- $$\if$$ does not possess commutativity; $$A\to(B\to C) \neq (A\to B)\to C$$



