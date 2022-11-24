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

#### 4.4: Allais' paradox
- Maurice Allais - directed against expected utility theory and certain axioms used in its axiomatization.
- There is no utility function such that maximizing utility is consistent for preferring Gamble 1 over Gamble 2 and Gamble 4 over Gamble 3. The relative utility is the same.

![image](https://user-images.githubusercontent.com/73039742/196567807-bb2adf0e-7666-4e35-b24a-34d36af06882.png)

- Savage's point: states which are the same should be ignored.
- Shows that guarantees can lead to violations of the independence axiom.

#### 4.5: Ellsberg's Paradox
- Daniel Ellsberg
- Urn contains 90 balls, 30 red and 60 black or yellow balls. Should you choose a gamble for 100 if the red ball is drawn or if the black ball is drawn? Then, what about if a red or yellow ball is drawn vs if a black or yellow ball is drawn?
- Shows that knowledge about probabilities can lead to violations of the independence axiom.

> "The Ellsberg paradox arises because we wish to avoid epistemic uncertainty about probabilities, whereas the Allais paradox arises because we wish to avoid uncertainty about outcomes."

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

### Chapter 14: Overview of Descriptive Decision Theory

#### 14.1. Observed Violations of the Expected Utility Principle
- We can empirically observe violations of EUP for various certainties.
- Certainty is important: probability is variable.
- Reflection effect: a preference for certain gains is often the complement of aversion to certain losses.
- Gamblers violate EUP.

#### 14.2: Prospect Theory
- Kahneman & Tversky - descriptive theory of decisions under risk, Prospect Theory.
- EUP should be modified by introducing a weighting function for value and another for probability.
- Prospect theory can be used to provide precise predictions about choice strategies.

#### 14.3: Violations of Transitivity and Completeness
- Other fundamental principles of rational choice are also often violated.
- Many students state cyclic preferences, violating transitivity. 
- Some preferences are essentially probabilistic.

#### 14.4. The Relevance of Descriptive Decision Theory
- People are irrational.
- No normative conclusion can be derived from purely descriptive / factual premises. 
- Descriptive theory can be valauble ffor other purposes. 
- Assertion - any plausible normative thoery must provide prescriptions people can follow.

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

## *Preference, Value, Choice, and Welfare*, Hausman
 
### Chapter 1: Preferences, Comparative Evaluations, and Reasons
- Four preference concepts:
  - Enjoyment comparisons
  - Comparative evaluations
  - Favoring.
  - Choice ranking.
- Folk psychology - a theory used to explain and rationalize human actions in terms of beliefs and desires.

> Among those philosophers who grant that beliefs and desires help explain actions, most would argue that taking actions to be merely the causal consequence of beliefs, desires, and constraints falsifies the character of rational deliberation.

- Deliberation forces decision-makers to regard values as realities.
- Beliefs are linked to reasons.
- Preferences function as reasons for actions. Theories of choice which attempt to identify reasons for choice must be theories of rational choice.
- Preferences are rankings which express total subjective comparative evaluations.
- Problems:
  - Arbitrariness
  - Self-interest
  - Revealed preference.
  - Division of theoretical labor.
  - Welfare as preference satisfaction.

### Chapter 2: Preference Axioms and Their Implications
- Ordinal utility theory - core of positive economic theory.
  - Completeness - preferences exist for all pairs of items
  - Transitivity
- Are these axioms claims about people's choices or of rationality itself?
- Ordinal representation theorem - when people's preferences obey certain rational axioms, they can be represented by a continuous utility function.
- How does a utility function represent preferences? Utility is merely an indicator.
- Choice determination - Agents will choose the top-ranked choice by preference.
  - Implies consistency in behavior.
- Context independence - preference is stable across contexts.
- Preferences are always comparative - they do not express information about 'objective' or 'absolute' desire.
- Axioms place large cognitive burdens on agents: finding out preferences is seriously difficult.
- Axioms of ordinal utility theory do not tell us what people prefer.
- Axioms governing preferences can be read as conditions for rational choice.
- Economists regard ordinal utility theory as a fragment of positive theory.
- How do economists understand preference?
- Revealed preference - preference as choice ranking.
- 'Usual sense' of preference - betterness.
- Expected advantage rankings - partial comparative evaluations of alternatives
- Don't conflate choice rankings and expected advantage rankings.
- Expected advantage is not a tenable meaning of preference, given that we often have many other motivations - harm, malice, and so on.
- Theory of revealed preference!

### Chapter 3: Revealed-Preference Theory
- How to understanding preference rankings? Rankings are choices or self-interested benefits.
- Gul & Pesendorfer - Utility maximization and choice are essentially synonymous.

> Economists who maintain that preferences are revealed by choices are more concerned with making inferences about preferences from data concerning choices than with how preference should be defined.

- What is meant by revealed preference?
- "Actual revealed-preference theory" - preferences are observed through observable choices.
- "Hypothetical revealed-preference theory" - would an agent choose $$x$$ over $$y$$, even if they never actually encountered it? Preferences are made in a hyptothetical state.
- Choices are evidence of preferences - we can infer preferences from choices.
- Belief-dependent revealed-preference: preferences cannot be defined in terms of choices, but by choices and beliefs.
- Actual revealed-preference theory
  - Preferences are identified with actions. 
  - Weak axiom of revealed preference: if two actions are alternatives in a set but only one is the choice set, then there is no other set containing both alternatives where the other alternative is in the choice set.
  - Revelation Theorem: WARP implies that a relationship is complete, transitive, and that it implies the agent's choice.
  - Can we just dispense with preference altogether? Anything economists need to say about behavior can e explained in terms of choice.
- Critique of actual revealed-preference theory
  - Implied: when there is no choice, there is no preference.
  - Preferences are limited to only choosable alternatives.
- Preferences influence choices through beliefs: we cannot just look at the choice set and make an optimal decision inference (Romeo).
- Why not redefine preferences in terms of choice?
- Beliefs mediate how choices and preferences relate to each other.
- Hypothetical Revealed-Preference Theory: define preferences in terms of hypothetical worlds. Abandon empricist ideals. But is it still too restrictive? Preferences range more widely than just hypothetical choices.
  - Are hypothetical choices even choices?
- Beliefs must be part of analysis.
- Belief-dependent revealed preferences: inferences about preferences can be drawn from choices given premises about belief.
- Preferences are subjective states which cause and justify behavior.

### Chapter 4: Preferences, Decision Theory, and Consequentialism
- Preferences - entail a complete and transitive ranking (according to ordinal utility theory).
- Prescriptive usage of 'preference' in economics.
- Preferences - understood as total subjective rankings as opposed to choice rankings to relate choices to beliefs.
- Standard model of choice - choices depend on preferences, beliefs, and facts.
- Expected utility theory: preferences are calculated directly from beliefs about state probabilities.
- EUT says nothing about causation, even though relations can be understood as typically causal. 
- Expected utilities represent preferences, but nothing about what determines them.
- EUT does not need to imply how preferences are formed, but applications do provide us insight into how preferences are formed too.
- A model of choice is consequentialist iff the agent's final preferences come from beliefs and preferences, and choices causally depend on the beliefs and final preferences.
- Consequentialism - explains and predicts final preferences.
- Multi-attribute utility theory - consequentialist. Actions and consequences are attribute bundles.
- How to understand what preferences are?

---

## "Mentalism versus Behaviorism in Economics", Deitrich & List
- Behaviorism - preferneces, beliefs, and other mental states are constructs redescribing choice / behavior.
- Mentalism - preferences, beliefs, mental states capture real phenomena.
- Mental states are ascribed from choices in economics, according to a commonly used paradigm.
- Economic DT can be interpreted as a more scientific reconstruction of folk psychology.
- How to understand ascribed mental states? Are they redescreiptions of behavioral patterns or representations of real psychological phenomena?
- Deitrich & List suggest the altter.
- Behaviorism used to be dominant, but has since been replaced by mentalism.

### 2. The Case for Mindless Economics
- Three claims made by Gul & Pesendorfer:
  - The only evidence used to test economic theories is evidence about people's choices
  - The content of any economic theory is solely its behavioral implications
  - An economic theory should specify choice behavior
- Psychological behaviorism - behavior should be explained solely on the basis of behavioral evidence.

### 3. Four Misconceptions
- Misconception of a fixed evidence base
  - Why should the evidential base of economics be restricted to choice behavior?
- Evidence / content conflation
  - Assume the evidential base was restricted to observable choice
  - Why should the content of economic theory consist solely of choice implications?
- Unobservable therefore nonexistent fallacy
- Maximization digma
  - Why should theories of economic behavior be necessarily premised upon maximization?

### 4. A Primer on the Philosophy of Science
- Theory - a theory is a set of sentences closed under implications and expressible as the implications of a finite set of axioms.
  - Interpreted theory - endowed with an intended interpretation.
- Semantic interpretation - assignment of truth-values to sentences in the language.
- Model - a semantic interpretation in which all sentences are true.
  - A world consistent with the theory.
- 'Thin' interpretation - most well-defined models are admissible; 'thick' - a single concrete model is considered admissible.
- Empirical adequacy - sentences describing empirical observations are part of a theory.
  - Not the same as the truth of a theory.
  - Correspondence theory - a theory is ture if it matches reality and its underlying unobservable features.
- Ontological commitments - minimally committed objects, properties, relations in all models.
  - Admissible models do not need to be isomorphic.
- Underdetermination of theory by evidence - there can be multiple logically incompatible theories which satisfy observable implications.
- The question of what our evidence for a theory is is not to be conflated with what a theory's ontological commitments are.

### 5. Two Kinds of Revealed Preference Approaches
- One approach to revealed preference - epistemological; the other - ontological.
- Epistemological revealed preference - body of evidence is restricted to agent's choice behavior.
- Ontological revealed preference - we are restricted to choices and behavioral patterns, excluding mental states.
- Ontoloigical thesis - apparently harder to defend than the epistemological thesis. 
- Behaviroism holds that if a theory if committed to functions representing belief, they are instrumental but not real. 
- It is not necessary to ask whether an entity exists after it has been established as an ontological commitment.
- Mental states are states which play a certain role for an agent.
- Choice behavior leads towards underdetermination.
- Paramorphic model - describes the empirical phenomena correctly; homeomorphic - paramorphic but also internally correct.
- Supervenience implies explanatory reducibility fallacy

---

## "In Defense of Revealed Preference Theory", Johanna Thoma
- The theory for ational choice in economics is formulated in terms of preferences.
- Measures for the empirical measurement of demand functions presuppose agents are EU maximizers.
- Committed to a behavioral understadngin of preference - preference is actual or hypothetical choice behavior.
- Revealed preference theory:
  - uses past choice data to ascribe preferences to agents
  - use preference and utility to make predictions about unobserved choices
  - lay foundations for mapping choice behavior to preference
- No inference about mental states are made.
- Revealed prefernece is widely rejected - associated with behaviorism and positivism.
- A charitable interpretation of RPT can be faithful to economic practice.
- Revealed preference theorists need only to concede some minimal amount of mentalism.

### Revealed Preference Theory
- vNM's theorem cited for EUT
- Savage's representation theorem cited for subjective EUT when probabilities cannot be assumed to ahve been given
- Utility - perceived as just a useful device for representing preferences. 
- We can define a technical notion of preference which reduce to choice. Does this track ordinary preference?
- Revealed Preference is committed to empirical methodology. Preferences need to be understood behaviorally. 
- Allow us to understand a general type of mechanism which can be applied to many different economic settings.

### The Anti-Behaviorist Challenge to Revealed Preference Theory
- No science can acknowledge without positing unobservable entities.
- The identification of preferences and patterns of choice can be isolated from ppositivist theses. 
- One issue: preference attribution is linked to the attribution fo mental states.
- The specification of the problem deterines whether or not it is problematic that we have not directly attributed beliefs.
- How to define revealed preference theory? It seems either incoherent or appeals to mental states.

### Mentalism about Options
- Representation theorems for EUT begin with a model of decision situation.
- We need to describe agents' choice behavior consistently to make predictions of future choice behavior.
- DWe need to describe the choice situation in terms of states of the world.
- Standards for specification are needed. We need full knowledge of the agent's hypothetical choice behaviors and beliefs.
  - Description of options should be consistent with the agent's beliefs.
  - A perceived feature of a choice situation should be included in the description of the agent's options.
- Agents may display instability in choice behavior.
- Avoids the problem of false beliefs, e.g. wasabi case.
- We never have full knowledge of hypothetical choice behaviors and beliefs.
- Some appeal to mental states must be made in order to understand the specification of choice options.
- Preference is a mere convenient representation of choice. 
- Allows us to capture unintentional choices
- Behavioral choice - lets us accurately capture and predict behavior, and nothing more. Does not need to comment on the origins of behavior.
- Dietrich and List - functionalist, we have always understood preference through functional mentalism which ascribes mental states.
- Preference and choice are both belief-dependent but deserve the label of being behavioral.

### Mentalism about Options in Practice
- Probabilities are asserted as 'known' within vNM-style work. All authors insist on a behavioral interpretation of preference.
- Economists must describe options in a way which is consistent with their beliefs.

### The Appeal of Revealed Preference THeory
- Four core motivations of contemporary revealed preference theory.
  - Black-boxing is attractive because it allows for clearer disciplinary boundary.
  - Black-boxing allows us to operate without needing to deal with specific pschological processes.
  - Black-boxes can help expected utility theory achieve greater generality.
  - There is a tighter connection between data about choices and theoretical constructs.
- None of the four motivations are undermined by a partially mentalistic theory of options.

---

## _An Introduction to Game Theory_, Osborne

### 1. Introduction
- Game theory helps us understand situations in which decision-makers interact.
- Game theory is a collection of models - abstractions from observations and experiences.
- Theory of rational choice - a DM chooses the best action according to their preferences among all available actions.
- Payoff function: associates a utility to each action.
- Theory of rational choice: the action chosen by a decision maker is at least as good, according to her preferences, as every other available action.
- No general theory challenges the supreamcy of rational choice theory.

### 2. Nash Equilibrium: Theory
- Strategic game: a model of interacting decision-makers.
- Each player has a set of possible actions. Eac h player has preferences about the action profile.
- Models don't consider time: each player chooses actions once and for all, simultaneously. Strategic game - 'simultaneous-move game'. 
- Prisoner's dilemma: there are gains from cooperating, but each player has the incentive to 'free ride', regardless of the other prisoner's move.
- Nash equilibrium - what actions will be chosen by players in a strategic game?
- We assume that players choose the best available action. Any player must form a belief about other players' actions.
- Each player views each play of the game in isolation: she is not aware of the effects of her actions or the opponent's strategy.
- Nash equilibrium: an action profile such tht no player can do better by choosing a better action, ceteris paribus other players.
- A Nash equilibrium is a 'steady state' - it is a social norm. No one wants to deviate from it if everyone else adheres to it.
- Prisoner's dilemma: (Fink, Fink) is the Nash equilibrium because each player is better off finking than remaining quiet.
- Tragedy of the commons

### 5. Extensive Games with Perfect Information: Theory
Page 173. 5.1 - 5.3 assigned.
- An extensive game with perfect information needs specification of a set of players and their preferences. 
  - Players
  - Terminal histories - sequences, no sequence is a proper subhistory of any other sequence
  - Player function - assigns a player to every sequence
  - Preferences for the players - over the set of terminal histories
- A proper subhistory of a terminal history cannot be a terminal history.
- Payoff function - represents a player's preferences
- If the length of the longest terminal history is finite, the game has a finite horizon.
- Backward induction - choose the action which yields the most preferred terminal history.
- Backward induction cannot be applied to every extensive game with perfect information - there is often an open case.
Games with infinitely long histories have no end to begin backwards induction from.
- Strategy - specifeis the action the player chooses for every history.
- Nash equilibrium - a strategic profile from which no player wishes to deviate holding all other players' actions constant.
- Steady state - nonequilibrium actions are taken, perturbations allow each player to eventually observe every other player's actions.
- Nash equilibria ignore the sequential structure of an extensive game. Strategies are terated as made simultaneously and finally before the game begins.
- Subgame - a subhistory and its corresponding players, playe rfunctions, and preferences.
- Proper subgame - not the entire game.
- No. subgames $$=$$ no. nonterminal histories
- Subgame perfect equilibrium - a strategy profile with the property that in no subgame can a player do better by choosing a different strategy, holding all other players' actions constant.
- Every subgame perfect equilibirum is a Nash equilibrium.
- A subgame perfect equilibrium is a strategy profile which induces a Nash equilibrium in every subgame.
- Principle of optimality, dynamic programming
- Nash equilibria assume that long experience allows players to develop correct beliefs about other players' options.
- Subgame perfect equilibrium - players can take nonequilibrium actions to eventually form correct beliefs about other players' strategies.
- Subgame perfect equilibrium - players' rational calculations about each others' strategies.
- This definition is not helpful when there is more than one optimal action.
- Backwards induction - finding subgame perfect equilibria of finite horizon games
- Backwards induction - fuind the optimal actions of players moving in subgames of length 1, then length 2, ..., $$k$$, given the optimal actions of previous games.
- When there is more than one possible outcome, we need to trace out combinations of optimal actions.
- A finite extensive game does not necessarily have a single subgame perfect equilibrium.


### 6. Extensive Games with Perfect Information: Illustrations
- The ultimatum game
- The holdup game
- Agenda control

### 12. Rationalizability
Page 397 in PDF

- How can we understand players' introspective analysis of others' rational behavior?
- A player's action is rational if it maximizes their payoff given beliefs about the other players' actions.
- Introspection: do you believe that the other player is rational?
- A rational player forms a probabilistic belief about other players' actions.
- Belief: a probability distribution over possible combinations of other players' actions.
  - An action can be rational for the belief $$\mu$$.
- Nash equilibrium requires rational strategoy and correct belief.
- An action is rationalizable if it is rational, there is a belief which makes it rational that assigns positive probabiliteis only to rational actions of another player, the other player assigns positive probability only to rational actions of mine.

![image](https://user-images.githubusercontent.com/73039742/200136518-e80d913a-7d8e-45bf-854d-f9fbdb07bbfa.png)

- Every action in a mixed strategy Nash equilibrium is rationalizable.
- Never-best responses: for every belief of another player, there exists a mixed strategy in which the player's expected payoff is less than another.
- A strictly dominated action is a never-best response.
- An action profile is rationalizable iff it survives iterated elimination of strictly dominated actions.
- Mark actions of each player which are weakly dominated; remove all marked actions; repeat until no actions can be eliminated.
- Dominance solvability - if players are indifferent between action profiles which survive when we perform iterated elimination of all weakly dominated actions, the game is dominance solvable.

### 14. Repeated Games
- When interaction is repeated, members can condition actions on previous actions. We can represent this as an extensive game.
- Players may be deterred from exploiting short-term advantage by punishment.
- Grim trigger strategy - if the player chooses confess, then you play confess for every other game.
- Another Nash equilibrium - each player chooses $$D$$ after every history.

Preferences
- Discounted summing - why do people value future payoffs less than others?
- Discounted average - 
- In preferences over atemporal lotteries, equivalent payoff functions are closed under linear transformation.

Repeated Games
- Repeated game - extensive game with perfect information and simultaneous moves, a discount factor $$\delta$$, $$T$$ periods
- Infinitely repeated games

Finitely repeated Prisoner's Dilemma
- Every Nash equilibrium generates the same outcome path - in the case of the Prisoner's Dilemma, (D, D).
- Every subgame perfect equilibrium of an extensive game is a Nash equilibrium

Infinitely repeated Prisoner's dilemma
- Every outcome path has a last period in which at least one player chooses C. 
- The fixed finite horizon exerts a large influence on players' behavior. 

---

## "Knowledge and Equilibrium in Games", Adam Brandenburger
- Economists use game-theory in a variety of cases.
- Non-cooperative game theory
- Nash equilibrium - when to use it?
- Strategic form - each player must decide a particular strategy in ignornace of the other strategies chosen.
- A player in a game should assign subjective probabilities to all uncertainty.
- Common knowledge - everyone knows it, everyone knows everyone knows it, everyone knows that everyone knows that everyone knows it, etc.
- Any strategy whcih does not maximize expected payoff for any probabilistic assessment over the other players' choices should be removed from consideration.
- A strategy is strongly dominated iff $$\neg \exists p(x)$$ such that with $$p(x)$$ the strategy maximizes the expected payoff.
- Iteratively undominated - the strategy remains after all the strongly dominated strategies have been removed from the game.
- If the structure of the game and the rationality of the players are common knowledge; then each player chooses an iteratively undominated strategy.
- Pure strategy: no attempt to randomize. Can also choose mixed strategies.
- The assumption of independence is questionable in decision theory.

### Pure-Strategy Nash Equilibrium
- Mutual knowledge - everyone knows something. 
- Common knowledge - mutual knowledge at multiple different laws.
- Pure-strategy Nash equilibrium: each player's choice is optimal given the choices of the others.
- Common knowledge is not needed for Nash equilibrium

### Mixed-Strategy Nash Equilibrium
- Some games do not possess pure-strategy Nash equilibria.
- We can augment players' choices to include mixed strategies: randomized choices over sets of pure strategies. Using expected utility theory we can maximize the expected payoff.
- Every finite game has a mixed-strategy Nash equilibrium.
- Mixed strategies are mathematically convenient but conceptually troubling: why randomize? 
- Conjecture - a player's probability assessment over the strategy choices of the other players. A mixed strategy is a common conjecture held by other players.
- Interactive belief system - formal description of players' choices and conjectures about beliefs.

### Correlated Equilibrium
- All nash equilibrium distributions are correlated equilibrium distributions.

### Solution Concepts
![image](https://user-images.githubusercontent.com/73039742/200722108-c3c54d8a-b7c8-4869-b2d4-6fa9854456a2.png)

---

## "Unstrapping the Straitjacket on Preference", Anderson

I. AMARTYA SEN'S CRITIQUE OF THE CONCEPT OF PREFERENCE
- Preference dominates economic theory.
- The rational act is the act which maximally satisfies an individuals' preferences.
- Conversion of dogma into tool
- Distinct usages of 'preference' -- choices, motives, welfare
- A person may not choose in a way to maximally satisfy preferences. 
- Prisoner's dilemma: person can be motivated by moral principle.
- Preference is used in normative economics to make judgements about individ. welfare, the good of society, and principles of rational choice.
- People have motives wider than just self-interest.
- Utility is insufficient to ground ethical or socially rational evaluation. We need to enrich the information provided in our evaluations of individual and social welfare.
- Argument: we must enrich rational theory beyond individual preference.
  - Reasons for action
  - Collective agency, individual identity
- Committed action becomes action on principles which are rational for any group of people as a collective agent to adopt; therefore, any individual who identifies as a member of that collective group can rationally act as such.

II. WHY THE ECONOMIC THEORY OF RATIONAL CHOICE CANNOT
GROUND A GENERAL SOLUTION TO PRISONER'S DILEMMAS

- Non-cooperation dominates cooperation, even though cooperation is a better outcome.
- Proposal: incorporate sympathetic or altruistic preferences, or that cooperation is valued intrinsically. These do not show that it is rational to cooperate in prisoner's dilemmas, but just that payoffs to parties do not have the structure of prioner's dilemmas anymore.
- Prisoner's dilemmas emerge when an isolated action has marginal effect in socially determined outcomes, such as democratic voting -- even when we have altruistic preferences.
- Sen: people enjoy voting in itself, therefore it is rational. Anderson: doesn't make sense. 
- Anti-consequentialism towards rule-consequentialism: any measure of an individual's sole marginal causal impact will result in prisoner's dilemmas.

III. THE RATIONAL BASIS OF COMMITTED ACTION

- Cooperation can only be rationalized in a non-consequntialist principle of rational choice. We cannot justify cooperation on maximum satisfaction of preferences. _Committed action._
- Parties of a prisoner's dilemma identify with each other as common members of a social group. Discussion allows for deliberation upon unified bases.
- Universalization principle - rules out maximizing expected utility.
- Socialized plural first-person: rules out apathy from marginal gains.

> The Priority of Identity to Rational Principle: what principle of choice it is rational to act on depends on a prior determination of personal identity, of who one is.

Page 10


