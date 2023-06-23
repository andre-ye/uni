---
layout: default
title: Lecture Notes
parent: CSE 331
grand_parent: Computer Science
nav_order: 1
---

# Lecture Notes
{: .no_toc }

CSE 331
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

## Lecture 1:
- Skills for contributing to a modern software project
- High quality code
    - Correctness
    - Easy to change
    - Easy to understand
- How do we ensure correctness when people are involved? The problem is usually people
- How to ensure correctness?
    - Tools
    - Inspection
    - Testing
- Scale makes quality harder to achieve; writing an n-line program grows faster than linear -- e.g. `O(N^1.05)`
- Small probability cases become high quality cases
- Modularity -- split code into pieces that can be built independently
- We want to support the code ofh higher quality and modularity

Reasoning
- We will learn a set of formal tools to prove correctness
- Formalisms are teachable, mechanical, and necessary for hard problems
- Robert Floyd, Sir Anthony Hoare
- Floyd logic
    - program state: values of all relevant variables
    - assertion: t/f claim about the state at a given point in execution
    - assertion holds for a program state if the claim is true when the variables have those values. 
    - Precondition: assertion before the code
    - Postcondition: assertion after the code 
    - Hoare triple: `{P} S {Q}`: precondition, code, postcondition.
    - A Hoare triple is valid if $$P \to_S Q$$
- Notes on assertions
    - Assertions are math, not Java -- use the usual math notation
    - e.g. `{{ w >= 1 }} x = 2 * w; {{ x >= 2 }}`
    - Java has assertions but are different
- If P1 implies P2, then P1 is stronger than P2 and P2 is weaker than P1
- Suppose `{P} S {Q}` is valid. Then `{P'} S {Q}` is valid iff `P'` is stronger than `P`; and `{P} S {Q'}` is valid iff `Q` is stronger than `Q'`
- OK to strengthen a precondition and weaken a postcondition but you lose information
- Is `{P} ; {Q}` valid? NO code in between -- this means that P is stronger than Q
- Forward reasoning -- start with the given precondition and work your way through the code
    - Simplify when needed
    - You cannot substitute an undetermined varialbe (even if bounds are provided)
- Backward reasoning: start from the required postcondition and code, and fill in the weakest precondition.
    - Do replacements instead of learning facts
    - Simply substitute as needed and work backwards as information is learnt.
- Correctness by forward: check if the last result impliest he postcondition; by backward: check if the derived precondition is implied by the given precondition
- It is ok to reason forward from a precondition and backwards from a postcondition
- Forward reasoning can fail if applied blindly. You need to consider that values can be changed. Can use subscripts to represent different values.

---

## Lecture 2: Reasoning about loops
- Hoare and Floyd: how do I tell if my code is running correctly? You can use a Hoare triple, I can tell you if your code is correct given this specification.
- Forward reasoning: start with given precondition, fill in strongest postcondition
    - Need to enforce simplifications
- Backward reasoning: start with required postcondition, fill in weakest precondition
    - Only use subsitutions

| Forward | given precondition | strongest postcondition |
| Backward | given postcondition | weakest precondition |

- To enforce validity:
    - Forward, show the strongest postcondition implies the given postcondition
    - Backward, show the precondition implies the weakest precondition
    - Make sure top implies bottom
- Conditionals
    - Inside both branches, consider $$P \wedge \text{cond}$$
    - We need to show that whichever branch we go towards satisfies the postcondition.
    - Backwards reasoning, though: cond and Q1 or cond and Q2.
- All code can be written with assignment, conditionsl, and loops
- It's not possible to do loop reasoning with = and if because of Rice's theorem: chcecking any non-trivial semantic property about programs is undecidable. We need more help -- we need a loop invariant to reason about this.
    - Correctness is a nontrivial semantic property of programs
- Loop invariants can help us reason -- an assertion that holds whenever the loop condition is evaluated
    - Holds when we first get to the loop
    - Holds each time we execute the loop body and come back to the top

```
{{ Inv }}
while (cond) {
    {{ Inv and cond }}
    S1
    {{ ... }}
    S2
    {{ Inv and ... }}
}
{{ Inv and not cond}}
```

```
{{ }}
s = 0;
i = 0;
{{ Inv: s = b[0] + ... + b[i-1]}}
while (i != n) {
    s = s + b[i];
    i = i + 1;
}
{{ s = b[0] + ... + b[n-1] }}
```

Three checks
```
(s = 0 and i = 0) implies I
{{ I and i != n }} S {{ I }}
{{ I and i = n }} implies Q
```

- We haven't argued that the code terminates
- You can combine forward and backward reasoning as long as you check top implies bottom when two directions meet.
- Loop invariants are crucial infromation, they represent the geist of the loop -- need to be provided before mechanical reasoning.
- With a good loop invariant, code is easy to write.











