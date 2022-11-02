---
layout: default
title: Lecture Notes
parent: PHIL 401C
grand_parent: Philosophy
nav_order: 1
---

# Lecture Notes
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

## Week 1 Wednesday
- Game thoery - study of strategic interactions between multiple DMs, almost anything counts as a game.
- Descriptive GT - is; Normative GT - ought.
- Equilibrium concepts - used to characterize how agents interact or should interact.
- Ultimatum game $$\in$$ bargaining game - dividing resources. 
- Subgame perfect equilibrium of the ultimatum game - proposal offers lowest possible amount of money and the second accepts.
- What happens when players carry about things other than money?
- Theories of individual rationality and how it can transfer to group decision-making.
- Check participation instructions.
- In the decision matrix:
  - Actions - row headers, what is within the DM's control.
  - States - column headers, states of the world, what is not within the DM's control.
  - Outcomes - cells in the matrix; represent the result of performing an action at a state.
- We assume a DM has preferences over the outcome space.
- Can you attach numbers to preferences to preserve ordering? Philosophically, this should give us pause. 
- One act dominates another if it is preferable in all states of the world.
- Weak dominance - an action weakly dominates another if it is preferred to the other in at least one state and not dispreferred in any state.
- Principle of strict/weak dominance - it is irrational to perform a strictly/weakly dominated action.
- Act-State Dependence - the decision maker can influence the chance of various states coming true. If the decision matrix does not have act-state independence, we can end up with bizarre results (e.g. party or study with pass or fail states)

---

## Week 2 Monday
- Decisions under ignorance - ignorance of objective probabilities.
- What is objective probability?
- What is the probability of a nonrepeatable event?
- What rules can you derive without assigning objective states?
- Maximin - pick the action with the maximum minimal outcome. A pessimistic position.
- Minimax regret - find the decision with the minimum maximum regret - weight
- Principle of insffucueitnr easoning, optimism-pessk9m ri;ze - wait undethe frture/
- Optimism-Pessimism - choose the action which maximizes the weighted average.
  - How to understand alpha? Heuristic for weighting cases, don't think about it past abstraction.
- Principle of Indifference - equally indifferent/unknown certainties are treated as equal.
- 

Discussion
- How do disentangle state from action? Can write using conditional statements.

---

## Week 2 Wednesday
- What object is probability applicable to?
- Why can we assume that things we ascribe probability to have those mathematical properties?
- Decisions under ignorance do not consider the probability of states of the world.
- Intuitively, we want to weight probabilities.
- There are many different ways to think about probability.

```
Survey Says
1/6, 1/6
1/3
90%
100%
95%
1%
1e-10%
50%
95%
Sure
Maybe
No
Maybe
```

- Discussions about likelihood and probability are everywhere - applied to both observable and unobservable events.
- Some events are repeatable, others are oe-time.
- Probabilities can be applied to propositions and events.
- Probability can be 'objectively subjective' or objective.
- Strength of evidence - changes to probabilities are made proportionality to evidence.
- Comparability - numbers can be compared. Can probability be compared? Can probability assessments be precise?

> Random idea - infinitely nesting probability distributions. Individual probabilities have probability distributions.

- Probability is bounded. Is there a maximum and minimum probability? Is 0 or 1 probability possible?
- Additivity - probabilities can be added.
- An interpretation of probability answers three questions - how it is measured, its mathematical properties, and its use.
- Interpretations
  - Frequency - some percentage of events occur in some population. Nicely explains matheamtical properties of probabilities.
  - Hypothetical frequency view - addresses infinite problems
- Propensity - probabilities are properties of objects which cause them to behave or tend towards certain behavior.
- Logical - probability is a measure of an argument's strength. Probability quantifies the strength of evidence for a conclusion given the premises of an argument.
- Subjective (Personalist)  - measure of how strongly we believe in particular propositions.
- Principal Principle - if you know the objective probability of an event is some quantity, you should be confident proportional to that degree.
- Kolmogorov - set of states. A probability assigns numbers to subsets of the state set. 

---

## Week 3 Monday
- To be rational, you must act as if you follow certain calculations.
- Act as if you associated states with probabilities.
- Expected utility - weight outcomes by probability of the state.
- Why is it rational to maximize expected utility? Why do we act as if we assign numerical utilities?
- Where do utilities come from and what do they represent?
- Utilities - strength of preference. Probabilities - strength of belief, or 'objective' frequencies.
- Expected Utility Theory is used both as normative and perspective theories.
  - "We should act like EU maximizers"
- Is EUT a good descriptive theory? Maybe, maybe not, probably not.
- Normative question - why should a DM behave as if they maximized expected utility?
- Why should a decision-maker's preferences be represented by numerical utiltiies?
- Utility - strength of preference of a particular decision-maker.
- Utility is not money. St. Petersberg Paradox
  - Preferences of money may have certain feature: weigh losses higher than gains, diminishing returns.
- When does a utility assignment adequately represent a DM's strength of preferences?
- Possible solution: ordinal assignment. 
- Maximin, domination, etc. can function only with ordinal preference. This does not apply to minimax regret, optimism-pessimism, PIR, etc.
- Interval Scales - represents ordinally, and are linearly transformable into each other.
- If we can measure a decision maker's strength of preference on an interval scale & know what decision rule they use, we can predict the decision maker's outcome. 
- The stronger your preference for something, the more you will tolerate a reduction in its probability of uccrrence.
- Lottery - probability outcomes (also called roulettes or Von Neumann Morgenstern lotteries).
- If a decision-maker's preference over lotteries have certain mathematical properties, we can measure the DM's preferences on an interval scale.
- Probabilities are objective probabilities; not the probabilities of states. Rather, the probability of outcomes.
- vNM's theorem is intended to justify replacing outcomes with numbers. It is not a justification for assigning subjective probabilities to states or using probabillistically weighted averages.

---

## Week 3 Wednesday
- Why should a DM behave as if they maximized expected utility?
- Lottery - a gamble premised on probability, interpreted as the objective type (propensities, frequencies)
- If a decision maker's preferences among lotteries have certain mathematical properties, then we can measure the decision maker's preferences on an interval scale.
- Properties of preference - we assume a decision maker's preference relation has the following properties:
  - Transitivity
  - Completeness: there must be a relationship between options.
  - Independence: $$\forall p \in [0, 1]: (A \ge B) \to (ApC \ge BpC)$$
  - Continuity - $$(A \ge B \ge C) \to \exists p \in [0, 1] : B \sim ApC$$. Preference relations are not infinitely strong.
- Utility as a latent vector?
- vNM's theorem: the utility function assigns outcomes to an interval scale and all such functions are derivable through positive linear transformation.
- Reduction of compound lotteries - lotteries of lotteries can function as a single lottery.
- There is controversy in how to compare utilities between different agents. The currently described theory does not let you do this - you cannot compare utilities between people.
- How to justify certain axioms? Often derived from the methods of measurement.
- Some aixioms - psychology verified empirical facts about the human condition. Continuityh can be psychologically verified. 
- A normative defense of transitivity - some decision theorists assert that intransitive preferences are irrational. Money pump argument - intransitivity can lead to indefinite loss of money. 
- Common tactic in normative decision theory - suppose an axiom is violated, suppose that behavior is linked to the axioms; show that this violation makes you exploitable.
- Normative argument for the independence axiom - dutch book.
- Rationality in normative theory does not necessarily contribute to decision theory as a descriptive theory.
- Normativ erationality with vNM: preferences satisfy the completeness accent; empirically preferences follow continuity; our preferences should satisfy transitivity and independence for the skae of rationality. By vNM, we should act like we are choosing outcomes as if we were maximizing expected utility. This is invalid. 

---

## Week 4 Wednesday
- Why shold a decision maker behave as if they maximized expected utility?
- Importance of as-if. Could reconstruct behavior as if you maximized expected utility.
- Why behave as if you assign numerical utilities to options? vNM - if options are roulette lotteries. Why assign subjective probabilities? Anscombe and Aumann's theorem can help us answer the second or third questions.
- Why should beliefs be represented by probabilities?
- Even if we should act like EU maximizers, does anyone really act like it? - Sometimes not.
- St. Petersberg Paradox
- Money has diminishing marginal utility - people do not behave as expected monetary value optimizers.
- Monetary loss incurs a steep drop in utility.
- Don't people still maximize utility even given diminishing marginal value of utility?
- Prospect - prizes and associated probabilities.
- Regular prospect - has a possibility of zero, or there is heterogeneity in the rewards in terms of loss / gain.
- Value of regular prospect - weighted sum.
- Irregular prospect - sum to one or homogenous
- Prospect theory as normative?

---

## Week 5 Monday
- Last class - violations of EUT from the perspective of a normative theory.
- The Ellsberg paradox - people's preferences are inconsistent with EUT, but really decision making under ambiguity.
  - Urns and balls
  - Ambiguity - there are objective probabilities but they are not known to the decision maker.
  - We end up choosing certain probabilities even when they are inconsistent with EUT.
- Decision making under uncertainty - choosing between horse lotteries, subjective probabilities.
  - Objective probabilities don't exist.
- Next up - _philosophy_ philosophy.
- _Should_ one behave as if they are an expected utility maximizer? To be rational, one must maximize one's subjective expected utility.
  - Subjective probabilities - personal likelihoods attached to states
  - Utility - strength of preference
- To be rational is to maximize the expected satisfaction of one's preferences.
- Why not maximize other things?
  - Value
  - Welfare
  - Interest
- What is the relationship between preferences, values, welfare, interests?
- How do we measure these things?
- Value and choice - how direct is the line?
- Economic theory - preferences are revealed by choices.
- Chernoff's condition / Sen's alpha - independence of irrelevant alternatives. Even if your option set is contracted, you should still choose the best option you would have chosen before.
- Menu depedence
- Cocaine and tea - the addition of cocaine affects your decision.
- The addition of an option adds new information which changes our understanding about the thing itself.
- We also see the Chernov Condition violated in plurality voting.

---

## Week 5 Wednesday
- Past two weeks - studied arguments for normative EUT (to be rational, a decision maker must maximize subjective expected utility.
- Utility should represent a single decision maker's strength of preference.
- This implies that we should be preference maximizers.
- What is a preference?
- Descriptive questions:
  - How do preferences influence choice behavior?
  - How do we determine what a decision-maker prefers and the strength of preferences?
- Normative questions:
  - Does rationality require maximizing something other than preference?
  - Are third parties required to help a decision maker from maximizing their preferences?
- Logical positivism - movement in the 1920s in Europe and the United States. Core tenet - the verification theory of meaning. The meaning of a sentence is the set of conditions under which the sentence would be true; that is, its verification conditions (verification principle of meaning).
- What is the meaning of words?
- Logical positivists get a bad rap in the history fo science.
Logical positivism renders a lot of discourse as meaningless - people think about a lot of things which are in fact meaningless. We could avoid political conflict if we just got clearer on particular ideas.
- Behaviorism - mental states are states of behavior.
  - Feelings are demonstrable by different behaviors.
- Revealed Preference Theory - some versions are equivalent to behaviorism.

---

## Week 6 Monday
- Primary sources - Hausmann, Thoma, Dietrich & List, among others.
- Goal - to understand whether or not we can interpret expected utility theory as a normative theory.
- Thoma's paper - primary focus is scientific / social-scientific.
- Does it make sense to interpret preference as behaviorism / revealed to model social behavior?
- Thoma and Hausman - what notion of preference is the one which is good for economists?
- Not interested in understanding what the pretheoretic concept of preference is.
- Normative questions - how should people make decisions as individuals, and how should they behave collectively?
- The discussion of what preferences are informs these discussions - we need to assume and move forward with what subjects are.
- Game matrices populated by preferences as total subjective comparative evaluations vs. actual measured preference will vary.

---

## Week 6 Wednesday
- A game consists of: players, actions, preference relation or utility function for each player. 
- Strategic profile - specifies what actions every player in the game takes. 
- Equilibria are strategic profiles - we need to specify an action for every profile
- Two equilibria - Nash equilibria for normal-form games and subgame perfect equilibrium, refinement of Nash equilibria.
- Game theory is full of other equiilibrium concepts.
- Normatively, equilibria describe how agents should behave.
- Descriptively, equilibria describe how players do choose.
- Nash equilibrium - a strategic profile in which
  - Each player's action is a best response to the other players' actions
  - No player is better off by taking a different action.
- Identifying Nash equilibria with two-player games, the quick way: underline best responses for each player. Nash equilibria are action profiles with all responses underlined.
- No pure strategy Nash equilibrium - for games without Nash equilibria.
- Equilibrium selection problem - how to normatively understand which option equilibrium players should choose?
- Mixed strategy Nash equilibrium - randomly choose with probability
- Nash's Theorem: any game with finitely many players and actions has a a mixed strategy Nash equilibrium.
  - There is a way for players to choose randomly such that no agent is better off using a different strategy.
- Is there something wrong with thinking about rationality? Are the sexist problems in game theory inherent to or external to games?
- Elizabeth Anderson - feminism and rational choice theory




















