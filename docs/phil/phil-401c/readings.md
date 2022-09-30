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
Page 60


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












