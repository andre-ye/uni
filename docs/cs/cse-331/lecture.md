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

---

## Lecture 3: Specification
- Prefer while loops over for loops
- Reasoning over loopsi s impossible without a loop invariant
- Loop invariant: add some documentation describing what the loop invariant is -- how ought the loop to work?
- Invariants hold in multiple places. 

```
{{ P }}
{{ Inv: I }}
while (cond)
    S
{{ Q }}
```

- Invariant needs to be true at the top and bottom of the loop
- If our invariant is a weakening of the postcondition, this is not hard, because the invariant implies the postcondition
- A triple is valid iff
    - The invariant holds initially
    - The invariant holds each time we execute S
    - Q holds when I holds and cond is false
- When does the loop invariant satisfy the postcondition? It gives you the loop condition
- Loop invariant gives you the initialization code
- Invariant update gives you the loop body
- You can use loop invariants to generate code for a problem. 
- The algorithm idea -- loop invariant. Should generally be a weakning of the postcondition. 
- Invariant and progress step is the essence of the algorithm idea -- an important idea
- An invariant is a personal choice -- there are different ways to solve the same problem. An invariant is basically a way of going from `P` to `Q`
- Dutch National Flag
    - Given an array of red, white,a nd blue pebbles, sort the array so all red objects are at the beginning, then white objects, then blue pebbles
    - Pre: list of colors; post: sorted
    - Number of ilines of code doesn't matter
- Checking correctness can be mechanical
- Large codebases tend to also have loop invariants for non-trivial code
- If your loop uses for-each loops, you probably don't need a loop invariant, but even a little bit more complex you should write your loop invariant.
- Correctness is the chief concern of high-quality software

---

## Lecture 4: Specifications
- To check correctness, we need a specification and we can apply reasoning
- We want our code to be correct, easy to change, easy to understand, and easy to scale
- A specification is a contract, a set of requirements agreed to by the user and the manufactorer of the product
- Facilitates simplicity via two-way isolation (modularity)
    - As long as the client meets the precondition, they get the postcondition
- Specification sare essential to correctness, but also changeability, understandability, and modularity
- ISn't the interface enough? Defines method signifiers for what an object which wants to be called a [...] should have
    - However, interfaces don't guarantee behavior.
- Code gives you more information than what the client needs
- Code is ambiguous and concrete -- what parts of the code are essential vs incidental?
- Implementer needs to know which features the client needs and which can be changed
- Comments are important, but they can be vague and ambiguous. How can you reduce ambiguity?
- Need to do a more careful approach which accounts for caveats
- Better to simplify than to describe complexity.
- Javadoc: start with `/**`, each new line starts with `*`, end with `*/`
    - Add Javadoc comments
    - `@param` describes what gets passed in
    - `@return` describes what gets returned
    - `@throws` describes what gets thrown
- Additional specifications
    - `@requires` describes what needs to be true before the method is called (precondition)
    - `@modifies` describes what gets modified -- objects which may be changed, any object not listed is guaranteed not to be touched (postcondition)
    - `@effects` give sugarantees on the final state of modified objects (postcondition)
- Should the required clause be checked? If the client calls a method without meeting the precondition, the code can do whatever, including passing corrupted data, but to be nice you should identify the error and fail fast
- Rule of thumb: check if it is cheap to do so
- Satisfaction of a specification: M is an implementation, and S is a specification. M satisfies S if for every input allowed by the precondition, M produces an output allowed by the spec postcondition
- Stronger and weaker specifications:
    - An implementation satisfying a stronger satisfaction can be used anywhere a weaker specification is required
    - Specification S2 is stronger than S1 iff the precondition of S2 is weaker than that of S1 and the postcondition of S2 is stronger than that of S1
- Strengthen a spec by promising more or by asking less of the client.

---

## Lecture 5: ADTs
- Backwards and forward reasoning for assignment, if statements, and while loops. 
- In order to reason with function calls and higher-order statements

```java
static int f(int a, int b) {
    @requires P(a, b)
    @return   R(a, b, c)
}
```

Forward reasoning:
```
{{ A }}
f(a, b);
{{ A & R(a, b, c) }}
```

Backwards reasoning (if `R(a, b, c)` $$\to$$ `Q(a, b, c)`):
```
{{ B and P(a, b) }}
c = f(a, b);
{{ B and Q(a, b, c) }}
```

- Manipulating and managing data is very important
- An abstract data typedefines a class of abstract objects which is completely characterized by the operations available upon / over it
- Procedural abstraction: abstract from implementation details of procedures (functions), specification is the abstraction, satisfy the specification with an implementation
    - Basically a function
- Data bastraction: abstract from details about data representation, ways of thinking about programs and designs
- People often wrote very procedural code
- Abstract Data Type, Barbara Liskov in 1970s -- reduced data abstraction to procedural abstraction
- Object-oriented programming really is sucha n important idea
- Fields private, methods public
- An ADT abstracts from the organization to the meaning of data -- hide details of data structures
- Abstraction barrier -- a good thing to have and not cross / violate -- prevents clients from depending onimplementation details
- A barrier between higher-level work done by clients and the implementation. Implementer can cross the barrier because the implementers are the ones writing the specification, so focus on the translation.
- If clients are forced to respect data abstractions, they can change how data is stored, can change algorithms, can delay decisions on how the ADT is implementation.
- Your initial implementation only needs to be correct, you can change it later
- you can use a creator or a producer
- Immutable things are less memory efficient -- we end up having a lot of duplicates, although it's not that much of a concern.
- Reasoning about mutators is difficult, so actually it's nice theoretically to work with immutable objects.
- A constructor doesn't return anything or modify, but it has the side effect of creating a new object, a `new Poly = 0`.
- For constructors, parameter types are fine, but return types are not.
- Observers -- never modify the bastract state.
- Producers -- creates other objects of the same type, give a new object which is a variant
- We want to verify information via observers, they only have returns, 
- Mutators: `modifies // effects`, have to actually modify the abstract state of the object
- Mutators shouldn't return anything -- they should either be a producer or be a mutator or something, "do one thing and do it well"
- Different types of methods -- creators, observers, producers, mutators
- Specifications are a lot of work -- described in terms of how they change the fundamental abstract state.
- Two tools to reason over DTs: representation invariant and abstraction function
- Representation invariant: maps an object to a boolean
    - Clients think in terms of abstractions, implementers think in terms of implementation -- clients should never have to go from the abstract to the concrete
    - Abstraction function: a relationship between an ADT specification and an implementation
    - Representation invariant (RI): relationship between implementation fields, an assertion about something in the program, asserts something about the representation we just got.
    - No object should ever violate the representation invariant -- an object should always look something like

---

## Lecture 6: Representation Invariant
- ADTs abstract from the organization to the meaning of data
- The details of the data structures are hidden from the client
- We can delay decisions about data structures
- We first write specficiations for what we want functions to do, and then we write code according to that
- Representation invariant which maps an object to a boolean which defines a set of valid concrete values; no object should ever violate the representation invariant, as such object has no useful meaning.
- Basically outlines the proper domain of the object
- A representation invariant holds directly before and after an instance call
- We should check a representation invariant if it's inexpensive
- It's hard to justify turning the safety checks off -- maybe if it makes code run faster and makes the code easier to understand
- Things might change the producer method or whatever, so it's important to call the checker function basicallye verywhere. 
- Defensive programming -- Will you make mistakes? You will. But can you catch mistakes before users do?
- Check the rep invariant on entry of mutators, check rep invariant on exit of mutators and creators, check preconditions, and check postconditions
- Defensive programming guards against subtle bugs; these can occasionally cause problems and sneak out, and you want to be defensive against these
- Don't expose your representation to the client -- don't give them a list they can modify which will break our representation
- Avoiding representation exposure
    - Understand what it is
    - Design ADTs so it doesn't happen
    - Treat rep exposure as a bug
    - Test for it with adversairal clients -- pass values to methods and then mutate them
- `private` is not enough: making it private does not suffice; the issue is the aliasing of mutable data outside the abstraction. `private` is a hint to you.
- Easy way to do this -- make copies of all data that cross the abstraction barrier -- copy in parameters that become part of the implementation, copy out results that are part of the implementation
- In Java, strings are immutable
- Collections unmodifiable list -- throws an exception for all of the underlying methods -- if a user is trying to set an element, it will be violated

```java
Collections.unmodifiableList(elts);
```

- We can restrict our user to only using mutator functions
- You can also give an immutable version of yourself to the client
- `unmodifiableList` is a wrapper around the old `List` which only allows certain types of access
- Has a slightly different specification.
- Different from copy-out, which is a snapshot, whereas a wrapper stays up to date.
- Different types of operations
- Representation invariant -- just really for implementers, a client never really sees that
- Abstraction function -- maps an object to an abstract state
- A representation invariant only tells us what is true about our fields, but not how to interpret it.
- The abstraction function tells us the representation, how to interpret the representation
- Abstraction function is purely conceptual, not a Java function -- lets us check correctness
- Consider int deque: a list that allows only insert/remove at the ends. 
- One possibility is that the list only allows insert/remove at the ends


