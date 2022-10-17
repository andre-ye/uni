---
layout: default
title: Reading Notes
parent: PHIL 401C
grand_parent: Philosophy
nav_order: 2
---

# Reading Notes
{: .no_toc }

PHIL 401C
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

## *An Introduction to Decision Theory*, Martin Peterson

### Chapter 1: Introduction
*Required reading for Week 1, Wednesday*

- Decision theory: the theory of rational decision making.
- A decision maker choses from a choice space; the outcome depends on the true state of the world, which is often only partially accessible to the decision maker.
- Decision matrix: the result of taking different actions in the action space in combination with certain environmental results.

#### 1.1: Normative and Descriptive Decision Theory**
- Descriptive theory - how people actually make decisions. Empirically informed.
- Normative theory - how people should make decisions under rational assumptions. This book focuses on normative theory, which is of particular philosophical interest. 
- Hume - decisions are made on the basis of a decision-maker's beliefs and desires.

#### 1.2: Rational and Right Decisions**
- A decision's rightness and its rationality are not necessarily associated. Decision theorists are concerned with rational decisions, since understanding right decisions requires a degree of retroactive perspective.
- **Right**: the actual outcome is at least as good as every other possible outcome.
- **Rational**: iff the decision maker chooses the most reasonable decision at the _point in time_ at which the decision is being made.
- Instrumental rationality - a decision maker has a goal, this goal being external to decision theory.
  - Can a goal for irrational?
  - Sets of goals certainly can be irrational.

#### 1.3: Risk, Ignorance, and Uncertainty
- **Decisions under risk**: the DM knows the probability of the possible outcomes.
- **Decisions under ignorance**: such probabilities are unknown or not knowable by the DM.
- **Principle of maximizing expected value**: the total value of an act is a probabilistically-weighted sum of the values of the individual outcomes.

#### 1.4: Social Choice Theory and Game Theory
- Some decisions are made collectively by a group rather than by a single DM. Two important subfields of DT emerge.
- **Social choice theory**: establish how decisions involving multiple DMs should be made.
- Game theory - understanding how rational players play games in which decisions affect each others' action fields and outcomes.

#### 1.5: A Very Brief History of Decision Theory
- Three periods - Old, Pioneering, Axiomatic
- Old - begins with Greece. Began early interest into principles of decision theory, although there was no rigorous work in it.
- Pioneering - begins in 1654 with Blaise Pascal and Pierre de Fermat, the creation of modern probability theory. Bernoulli - introduces moral value, utility.
- Axiomatic - aattempts to axiomatize the principles of rational decision making. Frank Ramsey - "Truth and Probability"; sets forth eight axioms for rational decision making. Neumann and Morgenstern - presented another set of axioms. Axiomatic analyses of maximizing expected utility flowered. The 1950s was the golden age for decision theory.

### Chapter 2: The Decision Matrix
- We must decide the game (the environment) before we determine the moves to make in it. We must define what states, acts, and outcomes are. We must formalize the problem.
- The decision matrix is a useful structure for arranging information about an environment.
- Decision trees represent sequential decisions.
- Three levels of abstraction:
  1. The decision problem
  2. A formalization (e.g. decisions under risk or under ignorance)
  3. A visualization (e.g. matrix, tree, JSON)

#### 2.1: States
- A state is a part of the world which is not an outcome or an act.
- Not all states are relevant to decision making - only relevant states which may affect decision making are taken into account.
- States cannot be causally dependent on an action. Another approach is to completely abandon the concept of a state.
- Ignoring states in decisions under ignorance makes little sense.
- If a formalization is underspecified, we need to add more information to the outcome. States should be chosen such that the value of the outcomes under all states is independent of whether the state occurs or not.

#### 2.2: Outcomes
- Rational DMs are mainly concerned with outcomes. Outcomes need to be ranked. 
- Outcomes are comprehensive - ceteris paribus. 
- Outcome ranking is largely subjective. 
- **Utilities** - values used for comparative evaluations.
- **Ordinal scale** - are invariant up to positive monotone transformations; the relative ranking between values is maintained, but the values themselves do not matter: and therefore the only thing that matters is the relationship.
- **Cardinal scale** - embody more specific information.
  - **Interval scale** - accurately reflect the distance between measured objects. Invariant up to positive linear transformations. Reflect distances, but not ratios.
  - **Ratio scale** - accurately reflects ratios. Invariant up to scaling transformations. Preserves proportions.

#### 2.3: Actions
- An action is a function from a set of states to a set of outcomes.
- Decision theory is concerned with a generic act, which can be instantiated by different agents. Particular acts are constrained by agent and time.
- Alternative acts: a rational DM can only choose one act.
- $$A$$ is an alternative-set iff $$\forall i \in A$$ is a particular act, $$\|A\| \ge 2$$, and $$\forall i \in A$$ all elements of $$A$$ are identical across identity and time, and moreover are performable and incompatible in pairs.
  - Bergstrom 1966: some particular acts are members of multiple different alternative sets.
  - **Finding an alternative set is partially a normative problem.**

#### 2.4: Rival Formalizations
- The DM may face multiple rival formalizations of the same DP. This is especially problematic if the resulting rational choice differs by framework.
- Transformative decision rules: do not recommend an/ action/s,  but perform a transformation of information. Effective decision rules include the principle of maximizing expected utility and the dominance principle.
  - Principle of insufficient reason - uniform probability distribution assumed in the absence of known probabilities. Transofrmative rule.
  - Merger of states - states which yield identical outcomes $$\forall A$$ can be collapsed.
- Let $$\pi = \langle A, S, O \rangle$$ represent a problem. $$A = $$ set of alternative acts, $$S = $$ set of world states, $$O = $$ set of outcomes.
- Let $$t: \pi \to \pi'$$; let $$\Pi$$ represent the set of decision problems: then $$(\pi \in \Pi) \wedge (t(\pi) \in \Pi)$$.
- We can composite multiple transformation rules. What sequence should be used to determine the initial decision problem?
- $$\pi \succcurlyeq \pi'$$ iff $$\pi$$ is at least as reasonable as $$\pi'$$. Order-independence:

$$(u \circ t)(\pi) \succcurlyeq t(\pi) \succcurlyeq (t\circ t) (\pi)$$

- Theorem: If OI holds for all $$\pi \in \Pi$$, then $$\forall u, t; (u \circ t)(\pi) \sim (t \circ u)(\pi)$$. Provable by making chaining substitutions.
  - For instance, $$ (\text{IR} \circ \text{MS})(\pi) \sim (\text{MS} \circ \text{IR})(\pi)$$.

### Chapter 3: Decisions Under Ignorance
*Required reading for Week 2, Monday*
- Ignorance - the DM knows the alternative actions and the outcomes but cannot assign probabilities to the states corresponding to the outcomes.
- A structured way to reason for one alternative over another is needed.

#### 3.1: Dominance
- Dominance principle - dominated acts should be chosen.
- The probabilities do not matter here: what matters is the outcome.
- The dominance principle provides only a partial answer in cases where there is no dominance.

#### 3.2: Maximin and Leximin
- Maximin - focus on the worst possible outcome; maximize the minimal value obtainable with each act. All we need is an ordinal scale; distance is irrelevant.
- Lexical maximin: find the maximin; if there is a tie, apply lexical maxmin in the next level.
- Justification - the DM does not know what the actual outcome will be, but they know the worst possible outcome.
- The number of states does not correspond to a probability in decisions under ignorance.

#### 3.3: Maximax and the Optimism-Pessimism Rule
- We can attempt to maximize the best possible outcome. It has few followers but is as good theoretically as the maximin rule.
- Optimism/pessimism rule (alpha-index rule): the decision maker identifies the best and worst possible outcomes, then chooses the outcome depending on the tolerance of pessimism-optimism.
  - Let $$a \in \mathbb{R}; 0 < a < 1$$ represent optimism; thus the value of some action proposal $$p$$ is $$a \cdot \max(p) + (1 - a) \cdot \min(p)$$.
  - Value must be measured on an interval scale.
- Should we consider the intermediates? This would seem to involve probabilistic reasoning.
- Still - why is it rational to focus only on the best and worst outcomes? We might assign $$\alpha$$-values to all outcomes; these are not probabilities but rather distributive weights.

#### 3.4: Minimax Regret
- Minimax regret - the best alternative is one which minimizes the maximum amount of regret. Regret is the difference between the best outcome and the outcome in question.
- Regret matrix - formed by calculating all outcomes in the decision matrix.
- Objection from irrelevant alternatives: a non-optimal alternative added to the alternative set can completely change the ordering. Therefore it is considered by some to be irrational / illegitimate.

#### 3.5: The Principle of Insufficient Reason
- Principle of insufficient reason - if one has no reason to think one stte of the world is more probable than the other, then all states should be given equal probability.
- The principle of insufficient reason does not recommend any act; it is a transformational operation, but is often used to make decisions under risk.
- How sensitive are individual states indiviuated?
- Symmetric states as a requirement for PIR
- It is completely arbitrary to assign equal probability: any other distribution would be equally good (and bad).

#### 3.6: Randomized Acts
- Instead of choosing one act over the other, we might randomize actions.
- Different decision rules yield different action prescriptions.
- Arguing on the basis of rules is a normative discussion.
- Decision theorists seek to show the superiority of one rule over another with axiomatic analysis: formulate a set of axioms and demonstrate which rules follow them.
- Milnor's ten axioms: ordering, symmetry, strict dominance, contuinty, interval scale, irrelevant alternatives, column linearity, column dupliction, randomization, special row adjunction.

![image](https://user-images.githubusercontent.com/73039742/193466520-e7686f81-b966-4ef4-afc4-0f98d68c0197.png)

### Chapter 4: Decisions Under Risk
- The DM knows the probabilities of the outcomes in decisions under risk.
- Principle of maximizing expected value may suggest certain actions, but it does not necessarily describe rationality. 
- There is virtually no agreement on how to make decisions under risk.
- How to articulate the principle of maximizing expected value?
- Many decisions in real life are made under risk.

#### 4.1: Maximizing What?
- Maximizing expected monetary value is not the same as maximizing expected value.
- Maximizing expected value is not the same as maximizing expected utility. Utility is a more precise version of value.
- Expected monetary value - probabilistically weighted average of states.
- Marginal value - how much an increase of value gives.
- Maximizing expected value makes more sense from a normative point of view than merely maximizing expected monetary value.
- Utility - an entity which cannot be directly observed. It depends on how valuable the outcome is from the DM's perspective.

#### 4.2: Why is it rational to maximize expected utility?
- Law of large numbers - show that in the long run, you will be better off if you maximize expected utlity.
- Derive the expected utility principle from more fundamental axioms in rational decision making.
- Law of large numbers - everyone who maximizes expected utility will almost certainly be better in the long run. Keynes - "in the long run we are all dead".
  - NO decision is made/faced an infinite number of times.
- Gambler's ruin
- Will decision makers ever face the same deicion problem several times?

#### 4.3: The Axiomatic Approach
- Not based on the law of large numbers: instead, show how maximizing expected utility principle can be derived from independently held axioms. It can be applied to nonrepeatable problems.
- The decision maker states a set of preferences over risky acts. Decisions can be described as if utilities were assigned to outcomes.
- Axioms:
  1. The utility of an act is $$u$$ if all outcomes of that act have utility $$u$$.
  2. Dominance principle. If one act is certain to lead to higher-utility outcomes than another, then it has higher utility.
  3. Every decision problem can be transformed into equiprobable states without affecting the overall utility of any of the acts.
  4. Trade-off principle. If two outcomes are equally probable and the best outcome is slighlty made worse, some utility can be added to the other outcome to compensate.
- The utility of an act is the expected utility of its outcomes.
The act with the highest utility will have the higehst expected utility.

#### 4.4:

#### 4.5: 

#### 4.6: The St. Petersburg Paradox
- St. Petersburg game: the value can rise reciprocally to the probability such that the expected utility becomes infinite.
- Upper limit on utility scale: utility should be bounded, made finite.
- Jeffrey - there is a finitude of resources (money)

### Chapter 5: Utility
- Utility has many different technical meanings.
- Utility can be represented with different scales.
- Arguably utility cannot be revealed by introspection.

#### 5.1: How to Construct an Ordinal Scale
- Assume that the decision maker makes pairwise preferences between pairs of objects. 
- Completeness axiom - you must be able to state preference between every pair of objects. Preferences are asymmetric and negatively transative. 
  - Transativity has previously been questioned.
- How can we construct the ordinal utility scale? We will need a utility function $$u: O \to \mathbb{R}$$ for your object-set $$O$$.
  - This could not be constructed for cyclic preference relations.

#### 5.2: von Neumann and Morgenstern's interval scale
- Ordinal utility scales might not allow us to analyze a decision problem effectively.
- von Neumann & mOrgenstern's theory: ask the decision maker to state preferences over risky acts.
- Acts - "lotteries", outcomes are randomly determined by events,
- We can infer utility based on stated preferences based on probabilistic reasoning.
- Constraints on rational preferences are imposed which imply that the DM behaves like they are making decisions by calculating expected utilities. 
- von Neumann and Morgenstern assume completeness, transativity, independence (preference for a lottery remains constant even if probabilistic lotteries are run between another alternative), continuity
- von Neumann & Morgenstern's theorem: the preference relation satisfies vNM 1-4 iff $$\exists$$ $$u: L \to [0, 1]$$ and obeys monotonicity, expected utility property, all functions satisfying the previous two are linear transformations of each other.
- Crticisisms:
  - Axioms are too strong
  - No axiom guidance
  - Utility without chance

#### 5.3: Can Utility be Measured on a Ratio Scale?
- Many decision theorists assert utility can only be measured on an interval scale. (A metaphysical claim).
- Some claim that utility can be measured on a ratio scale. We need to take a different approach to measure utility.
- Probabilistic theory of utility
- Probabilistic behavior is observed, but can it be rational?
- If $$A$$ is a subset of $$B$$, the probability $$x$$ will be chosen from $$B$$ equals the probability that $$x$$ will be chosen from $$A$$ multiplied by the probability that the chosen alternative in $$B$$ is also an element of $$A$$. (Choice axiom.)
  - Alternatives must be individuated carefully.
- Probabilistic theory requires $$p \ neq 0$$. 
- You can use probabilistic measures to construct a ratio scale. 

#### 5.4: Can We Define Utility Without Being Able to Measure it?
- There are many concepts which we are valuable even as intuitively motivated (as opposed to being necessarily technically articulated); does something similar appluy to utility?
- Theories of utility are operational definitions - meaning is measurement. Utility enters troubled waters in normative applications.
- We need to obtain a true, core notion of utility.
- Philosophers - a utilitarian approach to ethics apply utility in moral contexts.
- Utility is a mental state. 
- Moments of utility. The more an agent wants to experience a moment, the higher the moment's utility. 
- Archimedean condition: even if one moment is preferred over an other, it can be outweighted by a sufficient large number of dispreferred moments.

### Chapter 14:



---

## "Philosophy of Probability", Aidan Lyon
- Two central questions of the philosophy of probability.
  1. What is the correct formal theory of probability?
  2. What do probability statements mean?

### 1. Introduction
{: .no_toc }

- Almost all branches of science use probability theory, but it also figures prominently in everyday reasoning.
- The Kolmogorov axioms constitute the orthodoxy of formal probability, but there are other competing formal theories.

### 2. Mathematical Theory of Probability
{: .no_toc }

- Absolute probabilities and conditional probabilities. Do we define absolute properties in terms of conditional probabilities, or vice versa?

#### 2.1. Absolute Probability as Primitive
{: .no_toc }

- $$\Omega$$ is the set of elementary events; from this set of events we construct subset events.
- We have $$(A \in F) \implies (\Omega \\ A \in F)$$ for any event $$A$$ and the superset $$F$$ of $$\Omega$$. A set which has this property is _closed under $$\Omega$$-complementation_. ($$F$$ is one such example.)
  - Closed under union - the union of any two events is also an element in the set
  - A set which is closed under both $$\Omega$$-complementation and union is an algebra on $$\Omega$$.
- Not every 'event' gets a probability if it is not included in the algebra.
- We can define a probability function which assigns probabilities to every element of $$F$$: $$P: F \to \mathbb{R}$$ obeys the following axioms for all events $$A$$ and $$B$$ in $$F$$.

$$P(A) \ge 0)$$
$$P(\Omega) = 1$$
$$P(A \cup B) = P(A) + P(B), \text{ if } A \cap B = \emptyset$$

- When $$F$$ contains an infinite number of points, we generalize the third expression across an infinite number of samples/subslices in some event $$A$$. Known as countable additivity and is controversial.
  - Finetti's objection: (page 4) all items in a countably infinite set has a positive probability $$\epsilon$$; thus the total sum is $$\to \infty$$. Alternatively, the probability is 0; thus the total sum is 0.
- Kolmogorov's axioms are incompatible with many other philosophical interpretations of probability. The formal theory is sensitive to how it will be used.
- Popper's axiomatic system across sentences: define probability functions on sentences - a language $$L$$ rather than an algebra $$F$$; $$L$$ is a set of atomic sentences and Boolean combinations.
- Let $$P: L \to \mathbb{R}$$ which satisfies Kolmogorov's three axioms across sentences:
  
$$P(A) \ge 0$$
$$P(A) = 1 \text{ if } \vdash A$$
$$P(A \vee B) = P(A) + P(B) \text{ if } \vdash \neg(A \and B)$$

- The trouble is within infinite samples. How do we have a countable additivity axiom for probabilities attahced to sentences? We don't have infinite disjunction in our logic.
- Formalizing conditional probability. The following conditional probability demonstration leaves many conditional probabilities undefined. e.g. "What is the probability that the point chosen is in the western hemisphere given that it lies on the equator?"

$$P(A, B) = \frac{P(A \wedge B)}{P(B)} \text{ where } P(B) \neq 0$$

- Any probability space with an uncountably infinite number of events must assign uncountably many events to zero probability, otherwise in violation of probability axioms.
- There are reasons to treat conditional probability as the fundamental notion of probability: $$P(A \wedge B)$$ and $$P(B)$$ are undefined; but the conditional probability $$P(A \| B)$$ is.

#### 2.2. Conditional Probability as Primitive
- Alfred Renyi - a formal theory of probability where conditional probability is the fundamental concept.

| Symbol | Meaning |
| --- | --- |
| $$\Omega$$ | nonempty set |
| $$\mathcal{A}$$ | algebra on $$\Omega$$ |
| $$\mathcal{B}$$ | non-empty subset of $$\mathcal{A}$$ |

- Let $$P$$ be a Renyi conditional probability function $$P: \mathcal{A} \times \mathcal{B} \to \mathbb{R}$$ which obeys the following axioms, where $$A \in \mathcal{A}$$ and $$B \in \mathcal{B}$$:

$$P(A, B) \ge 0$$

$$P(B, B) = 1$$

$$P(A_1 \cup A_2, B) = P(A_1, B) + P(A_2, B)$$

$$P(A_1 \cap A_2, B) = P(A_1, A_2\cup B) \cdot P(A_2, B)$$

- We can define a countably infinite conditional additivity axiom:

$$P \left( \cup_{i=1}^{\infty} A_i, B \right) = \sum_{i=1}^{\infty} P(A_i, B)$$

- Absolute probability can then be defined as follows:

$$P(A) = P(A, \Omega)$$

> Question - how is $$\Omega$$ being used here? Any nonempty set or a relevant set? 

- Popper conditional probability function - is symmetric and autonomous.
  - Autonomous - probabilistic conclusions can only be derived from probabilistic premises. 
  
  #### 2.3: Other Formal Theories of Probability
  - Probabilities are assumed to be defined over classical logic. But it can also be appropriated for other logics, such as intuitionism.
 - Quantum probability - a non-distributive logic. Classical lgoci fails to understand the results of the two-slit experiemnt, for instance.
 - Probability is taken to be a set of constraints on the belief of an individual; an individual therefore must be omniscent to be rational.
- Probability - applied to negative numbers, imaginary numbers, and unbounded real numbers.

### 3. The Philosophical Theory of Probability
- Categorized into subjective and objective interpretations.
- Subjective - identify with degrees of belief.
- Objective - independent of the individual (frequencies, etc.)

#### 3.1. The Classical Interpretation
- Central idea - a calculation reduced across equally possible outcomes.
- But what does equally possible mean? For some, they are symmetric in the objective sense. For others, it is an epistemic position - they are equally possible.
- Principle of Indifference - equally uncertain alternatives have equal probability.
  - Fraught with paradoxes depending on how we observe objects.
- Many suggest we should adopt a frequency interpretation.

#### 3.2. The Frequency Interpretation
3.2.1. Actual Frequencies
- Number of instances in which an outcome occurs divided by the total number of instances.
- Reference class problem - how to disentangle properties? How to consider the 'total number' relevant to the instance?
- Frequency interpretation tied too closely to the observtion of the world.

3.2.2. Hypothetical Frequencies
- Attempts to project actual frequencies into a conceptual space. Frequency is *taken to the limit* - the number of instances is countably infinite.
- However, using this conception of limiting frequency allows for variation in frequency depending on the sequence of trials.
- The hypothetical frequency interpretion imposes necessity on the actualization of probabilities over time (`HHH...` - while it is possible that this sequence may continue on forever as `H`s, hypothetical frequency suggests it must approach a 50% frequency).

#### 3.3. The Propensity Interpretation
- Developed by Popper: an objective theory of probability which can also make sense of single-case / particular probabilities.
- A probability is a propensity for an outcome to occur.
- Probabilities are properties of conditions which generate sequences of conditions rather than the sequences themselves.
- Humphreys' paradox: propensities are not symmetric but probabilities are.
  - Some theoreis of probability are asymmetric, e.g. Renyi's axioms for conditional probability
- Long-run propensity interpretations - propensities are tendencies for certain conditions to produce frequencies identical to the probabilities in a sequence of instances.
- Single-case propensity interpretation - dispositions to produce a certain result on a specific occasion.
- Propensities are attributed not to repeatable conditions but states of the unvierse.
- Probability claims are no longer testable.

#### 3.4. Logical Probability
- $$P(B, A) = \chi$$: the extent $$\chi$$ to which $$A$$ entails $$B$$.
- Generalizing entailment to partial entailment - deduction can be generalized to induction.
- Logical probabilty shares suspicious parallels with 'multiple-worlds' reasoning of the classical interpretation.
- It is almost universally agreed that the logical interpretaton is false, but we can still develop a formal account of inductive inference.
- Probability-raising account of deduction:

$$c(H, E) = P(H, E) - P(H)$$

#### 3.5. The Subjective Interpretation
- Frequency and propensity interpretations use 'is' subjective interpretations use 'ought' - ideal epistemic rationality.

3.5.1. The Dutch Book Argument
- Iff an agent has credences which do not obey axioms P1-3, an agent is susceptible to a Dutch Book.
- If an agent is ideally epistemically rational, then the agent is not susceptible to the Dutch Book.
- Depragmatized dutch book arguments
- Dutch Book as a dramatization of systems which do not conform to probability calculus.
- Package principle - two individually fair bets are also fair collectively.

3.5.2. Bayesianism
- Orthodox Bayesianism: an agent's credences should
  - obey probability axioms
  - change iff new information is acquired
  - update beliefs using Bayesian conditionalization
- Bayesian conditionalization:

$$C_\text{new} (H) = C_\text{old}(H, E)$$

- Diachronic constraint
- Bayesianism assumes facts are learned with full certainty; Jeffrey Conditionalization allows us to update with partial confidence.

![image](https://user-images.githubusercontent.com/73039742/193665474-97db6570-a20d-4d1a-86a4-4cbd72a9ba92.png)

- Bayesianism is a theory of epistemic rationality: credences should obey probability calculus.

3.5.3. Objective and Subjective Bayesianism
- How should the credence function be defined before any information is obtained?
- Subjective Bayesians - no initial credence function is more rational than the other. However, any initial credence function must be regular - must obey logical systems and be probabilistic when contingent. Even if they are bizarre, they may converge to sensible solutions.
- Objective Bayesians - there are further constriants on rational initial credence functions. The initial credence function should accurately describe our epistemic state.
- Principle of Maximum Entropy - generalization of Principle of Indifference.
- Subjective Bayesianism is most popular amongst philosophers.

3.5.4. Other Norms
- Lewis' Principal Principle: credences should align with objective probabilities if they are known. Beliefs should be updated immediately upon realization.

---

## "A Definition of Subjective Probability", F.J. Anascombe & R. J. Aumann

### Introduction
- "Probability" - plausibility (belongs to logic), objective (belongs to physics).
- Personal or subjective concept of probability - defined in terms of preferences which can be calculated from observed preferences.
- Utilities can be defined in terms of chances (vNM).

### Lotteries
- A lottery is a device for deciding which price in a set of prizes you will receive.
- "roulette lottery" - uncertain events associated with a known chance
- "horse lottery" - chances cannot be associated with uncertain events
- Compounds lottery: constructed from iterations of simple lotteries; prizes are other lotteries.
  - Can be constructed from roulette lotteries or roulette lotteries and horse lotteries
  - vNM utilities operate on compound roulette lotteries

### Assumptions
- There is a most desired and least desired prize among all prizes.
- Suppose a preference ordering on a set of roulette lotteries obeys the axioms of utility theory. We can then define a utility, the utility of a simple roulette lottery.
- Subjective probability: apply utility theory twice, then connect preferences and utilities.

### Existence of Subjective Probabilities
- Subjective probability of an outcome of a race.
- There is a set of probabilities such that the total utility of the race is a probabilistically weighted sum of individual outcomes.

---

## Foundations of Causal Decision Theory, Joyce
*Chapter 3 - Savage's Theory*

- Savage attempted to justify the principle of expected utility maximization using a representation theorem.
- Impose a set of constraints on rational preference, then show that only expected utility maximization can satisfy said constraints. 
- No person proposes expected utility maximization as a decision procedure; but rather agents behave as if they follow expected utility maximization.
- Representation theorems - demands a local set of constraints on preferences.
- Relationship between local and global level.
- No currently available theorem perfectly justifies maximizing expected utility so far - 'molecular' axioms exist, unreduced axioms._Structure axioms_ - size & complexity of preference rankings.
  - Necessary axioms - axioms of pure rationality.
- Savage's theory - dependence on structure axioms which cannot be reduced.
- The existence of incommensurable goods leads to incompleteness in an agent's preferences rather than intransitivity.

---













