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

#### 2.4: Rival Formalizations












### Chapter 2: The Decision Matrix
*Required reading for Week 1, Wednesday*
