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

---

## Lecture 7: Abstraction Functions and Testing
- Representation exposure -- copy in/out, immutable, unmodifiable, etc.
    - Wrappers can be used to enforce wrappability
- Specifying an ADT -- `creators`, `observers`, `producers`, `mutators` -- acts as an abstraction barrier
- Abstraction function provides an interpretation from a concrete state to an abstract representation
- How to ensure correctness?
    - Tools
    - Inspection
    - Testing, usually 40-50% of the work
- Edsgar Dijkstra -- testing can only be used to show the presence of bugs, but never their absence
- Only reasoning can prove that there are no bugs
- Donald Knuth -- beware of bugs: I have only proved this code correct, not tried it
- You will be expected to test your own code
- Quality/assurance, test teams -- but now nonexistent
- Easier to update products after shipping, but also lowers quality expectations
- It's hard to test your own code
    - Confirmation bias
    - Operant condtioning
- You can get around confirmation bias by writing most of your tests before the code.
- Testing is about writing test cases -- units of code which decide whether or not the functions have performed the exepcted behavior
- A test case for the function consists of test inputs and a test oracle
- We want to check if `f(a, b) == c`
- Different types of testing
    - Unit vs integration vs system/end-to-end
    - Clear box vs opaque-box/black-box
    - Specification vs. implementation
- Unit test -- focuses on one class / module, could write a single test for a single method
- Integration test -- modules fit together properly
- System test -- runs on the entire system. Useful to help catch bigger problems -- preconditions don't match postcondition, etc.
- We want to test many things but find as mall number of tests which cover a large space
- partitino the input sapce into subdivisions / partitions, identify sets with the same behavior (actual and expected), and test at least one input from each set (the subdomain)
- Two problems: notions of same behavior si subtle
    - Naive approach: execution equivalence.
        - Assumes that the code itself can be correct
        - You can't just picks ome element, yu need to pick outhers
    - Better approach: revealing subdomains
        - A more precise definition
        - A subdomain sia  subset of possible inputs
        - A subdomain is revealing for error E if either
            - every input in that subdomain triggers error E or
            - no input in that subdomain triggers error E
        - Needs test at least one input from a revealing subdomain to find bug
        - Guess revealing subdomains for the errors present
- Discovering all sets requires perfect knowledge -- if we had it, we wouldn't need to test. So we should use different heuristics.
- Testing is heuristics
    - Testing is essential
- A good heuristic gives
    - for all erorrs in some class of errors E, high probability that the subdomain is revealing
    - but is also not absurdly large
- Opaque-box approach: visible specification, internals hidden
    - Not influenced byt he impelemtnation at all -- you can write specification tests without writing any code
- Clear-box testing
    - Focus on features not described by specification, like control-flow details, performance optimiztions, etc.
    - Clear-box testing can catch subdomains that opaque-box testing does not, i.e. in cacheing situations
    - Finds an important class of boundaries
- Common off-by-one error heuristics: boundary cases, include examples on each side of the boundary
- Don't confuse volume with quality -- we want tests in every revealing subdomain, not just a torrent of tests

---

## Lecture 8: Testing
- Kinds of testing  -- all fall along a single dimension, want to test certain kinds
- Dimensions: scope, information about the code itself, how the actual code should function
- Consider `find(int[] a, int value) throws MissingException`. What do we need to test?
    - Throwing `MissingException` if `value` $$\notin$$ `a`
    - Test with other arrays
- Clear-box testing heuristic
- Heuristic: boundary cases -- test on each side of the boundary
    - A point is on the boundary if there exists an adjacent point in a different subdomain or if there is no adjacent point in some direction
    - You need a notion of adjacent inputs.
    - Identify basic operations on input points; two points are adjacent if they are one basic operation apart.
    - An empty data structure is usually a boundary case
- Heuristic: special cases.
    - null objects
    - Same object passed as multiple arguments
    - Try `Integer.MIN_VALUE` and `Integer.MAX_VALUE` for integers
    - Actually `Math.abs` cannot give you the true absolute value of `Integer.MIN_VALUE`
    - Your precondition should include "your inputs should not be null"
- Regression testing
- Common goal is to achieve high code coverage -- make sure that most of the behavior is tested.
- You can have high code coverage and still be shitty.
- Branch coverage -- make sure that every branch is taken
- Mutation testing -- make small changes to the code and see if the tests catch it
- Path coverage is not enough

---

## Lecture 9: Modular Design
- You can't build arbitrarily large physical structures so quickly
- What prevents arbitrarily large software?
- People are the limitation -- no individual or AI can look at 2 million lines of code and understanding what it does
- Force of friction in software: interdependence. How can you understand one part of the code without understanding all of it?
- Using modularity
- Many goals of modular software
    - Decomposable
    - Composable
    - Understandable
    - Continuity
    - Isolation
- Important design issues
    - Coupling -- how much dependency is there between components?
    - Cohesion -- how well do parts of the component fit and work together?
- Decrease coupling, increase cohesion
- Separation of concerns
    - A module should represent a single concept
    - All the methods which have one concern in one method; others for another
- Coupling -- how are modules dependent on one another?
- Coupling leads to spaghetti code -- changing one component may require changes to another
- Recommendation -- throw away your code and restart
- Throw away your code if it's too coupled!
- Regression testing -- if you make a change to your code, you want to implement changes
- After refactoring your code, change it
- Coupling is the path to the dark side
- God class: hoards most of the data or the functionality of a system
    - Depends on and is depended on by every other module
    - Instance of an anti-pattern: a bad way of doing things. 
- Class design ideals
    - Completeness -- every class should present a complete interface
    - Consistency -- in names, parameters/returns, etc.
- Avoid unnecessary work, have consistency in behavior, anems, etc.
- Methods should do one thing well:
    - compute a value but let client decide waht to do with it
    - Don't print as a side effect
    - observe or mutate, dont' do both
    - etc.
- A client might come to rely on particular principles
- Flag variables are often a symptom of poor method cohesino
- Effective Java: design method signatures carefully
    - avoid long parameter lists
- Use overloading judiciously; it can be useful with the same number of parameters
- Constructor design -- constructors should have all the arguments needed to initialize the object's state, no more and no mless
- You shouldn't need to call other methods to 'finish' the initialization
    - You can do complex initializations with a 'builder' pattern
- A variable shold be made into a field iff the value retains meaning throughout the object's life
- Rule: favor `int` and `long` for most numeric computations
    - Avoid `float / double`
    - Don't keep numbers inside strings
- `enums` -- a type-safe way to represent a fixed set of constants
- Style guides exist
- Use comments
- Bad names -- understand what it is about
- it's important to read nice software to write good software
- Break into paragraphs

---

## Lecture 10: Software Tools
- Software tool -- a piece of software which helps us write high-quality software
- Git is a software tool which accepts a set of files and then produces artifacts (suggestions, etc.)
- How do people build software tools?
    1. Identify a problem
    2. Understand how developers solve it
    3. Attempt to automate the process
- To autmoate, you need to define the solution precisely
- Code coverage
- We use testing heuristics to make tests
- Different heuristics: random fuzzy testing, user inputs, specification, etc.
- Does the order in which we execute test cases matter.
- Running time matters first -- determines order. 
- Code coverage is a navie attempt: how many lines of code did we run successfully? 
- We care about error-revealing subdomains -- we need to check if our test suite covers possible bugs
- Mutation testing
    - Begin with a correct program
    - Introduce bugs into our code by making mutant programs. Define mutations on your code
- Tools for testing
    - Fault localization, where is the bug?
    - Program verification -- is your code correct?
    - Program synthesis

---

## Lecture 11: Equality and Hashcode
- Rest of the course -- looking at libraries. This reduces bugs in most cases
- `java.lang` and `java.util` should be familiar for all Java programmers
- Correctness is dependent on knowing default tools
- We can't use `==` to compare objects generally. Rather, use `.equals`
- Expected properties of equality: reflexivity, symmetricity, transitivity
    - This is the smallest notion of equality: each object can only be equal to itself
- Every object in Java inherits from `Object`
- Consistency in equality. Although this goes out the window for mutable objects.
- No object should be equal to null.
- Make sure to *override* rather than *overloading* (just modifying the argument types to change the signature)
- Method calls order
    - Signature of method call si chosen at compile time
    - Java looks at the actual class at runtime
- To modify: check if object is instance of desired class and return false if not
- Immutability: no representation exposure, equals consistency is not violated
- Reference equality stronger than behavioral equality srtronger than observational equality

---

## Lecture 12: Exceptions
- Last time -- equality
- Key properties of equals: reflexive, symmetric, transitive, consistent, non-null
- Consistency ensures reflexivity across time
- `@Override` technically optional but strongly recommended -- tells Java you think you are overriding a method
- Not all errorrs should be failures -- client misuses code, implementer has an error, unexpected resource problems (should not be a failure)
- Fail fast and fail friendly: prevent harm and give inofrmation about the problem
- Defensive programming: use assertions about your code to verify precondition, postcondition, representation invariant, etc.
- Check these statically with reasoning and tools
- Check dynamically with assertions.
- When not to use assertions -- don't clutter your code with useless assertions
- - Don't perform side effects, e.g. `list.remove(x)` changes the actual underlying list.
- `checkRep()` is another dynamic check -- checks if the representation invariant actually holds, have a private void private method to ensure that the fields are actually in the right statte.
- Remove expensive assertion checks -- create a global level debug level variable which can be disabled by the client
- Java checked/unchecked distinction
- Checked exceptions vs unchecked exceptions -- typically ones which crash the program but we want it to crash the program. Subclasses of `RuntmimeException` and `Error`
- Class `Throwable` has two implementations: `Exception` (all checked exceptions and an unchecked one) and `Error` (`assertionError`, `OOMError`)
- Options:
    - propagate the error to the client
    - use try-catch  -- can use `e.printStackTrace();`
- Catching with inheritance
- Finally block execuses at the end -- you don't know what will happen at the end
- The last thing to end a method is not a return statement, it's actually a `finally`
- Two distinct uses of eceptions
    - Errors that should be failures
    - Special cases
- When you propagate an excpetion, make sure to keep the user's intelligiblity of the error. 
    - Exception translation: `catch` the exception and throw a new exception
    - Don't ignore exceptions, empty catch block is poor style, at the very minimum print a stake trace and do a system exit.

---

## Lecture 13: Inheritance, Subtyping and Subclasses
- Assertions check your reasoning, exceptions are part of the specification and used in dynamic and unpredictadble concepts, special values are a common case and clients are likely to remember to check for it.
- Open-Closed principle -- software should be open for extension, but closed for modification. 
- Subtyping -- "every B is an A", B is a subtype of A, B is a strenghtening of A
- If the client expects something of type A, you can give them a subtype and the subtype can masquerade as the supertype they care about.
- Liskov substitution principle -- subtypes are substitutable for supertypes, instances of subtypes won't surprise the client by failing to satisfy the supertype's specification or with more expectations than the supertype's specification.
- B is a true subtype of A if B has a stronger specification than A or is equally strong. This is not the same as a Java subtype (i.e. a subclass), so it becmoes a source of a lot of bugs
- Substitution is a matter of specifications, inheritance is a  matter of implementation
- Inheritance: your subclass inherits all of the method signatures (part of the spec) and inherits all the implementation behaviors (which can be overriden)
- Java trusts that you implement a true subtype, but it can't verify that you do so -- cuz that requires a specification.
- Subtyping is about the specification but in Java you copy over all of the specifications
- Benefits of subclassing and inheritance: don't repeat unchanged fields and methods, you can have modularity, ignore a lot of private fields in the superclass.
- Inheritance makes small extensions small
- `Hashtable` and `HashMap`
- Immutability gets around a lot of issues, evoids representation exposure, equals consistency violations, subtyping relationships
- Working with immutable objections is very nice

---

## Lecture 14: Subtypes II
- if B is a subtype of A, then a B can always be substituted for an A. 
- Any property guaranteed by A must be guaranteed by B, antyhing provable about an A is provable about a B
- We cna add additional properties, B can do more than a, and allowed to do things differently than A as long as it still satisfies the specification.
- B is not permitted to weaten the spec, that is overriding methods with a weaker spec or removing methods.
- Subtyping guarantees, type checking
- Java expects to ensure all subtypes are true subtypes, asks you to ensure the specification, if you don't do this there is a huge class of bugs you will encoutner
- Cannot gaurantee a lot of shit

Designing for inheritance
- We need to be careful to avoid issues -- inheritance requires us to be familiar with the implementation details of the classw eare inheriting from.
- use an interface: HashSet implements a Set, etc. -- all of the methods are still there, we need to implement this
- Drawback: forcing our clients to use the interface type for their variables. 
- Abstract class: can offer an implementation
- Effective Java -- eihther design for inheritance or else prohibit it with `final`.
- `String` class is final -- if someone overrides the `String` class they would fuck it up

---

## Lecture 15: Generics
- Java trusts the programmer to respect types
- Interface: declares a new type variable
- Type variables are types.
- Usually a one letter name, to instantiate a generic class/interface, supply type arguments.
- You can have `<TypeVar extends SuperType>`
- You often use this for comparason

```
public class TreeSet<T extends Comparable<T>> {

}
```

- Use a generic to treat classes as multiple stuff, do casting and shit
- The method can be generic without the class being generic
- Integer is a subtype of Number -- it is the true version of subtyping. Java doesn't allow you to pass in a list of integers for a list of numbers, despite that integers are a true subcdlass of numbers. Why?
    - Subtyping comes from the Liskov substitutability principle.
- You can't pass in a Double for a Number, but you also can't pass in a Number for a Double
- Java subtyping is invariant wrt generics
- There's no relationship between Number and Integer
- Covariance: the arrows vary in the same direction, Integer to Number, List of Integers to List of Numbers
- Read-only allows for covariance.
- Contravariance method: Integer to Number, List of Numbers to List of Integers
- Programs can us subtyping to do alright things, e.g. with arrays you can do swaps , all the things ni an array are of the same type.
- `addAll` -- for a `Set` interface.
    - You could have `Set<E> c`
    - Better: `<T extends E> void addAll (Collection<T> c)`

---

## Lecture 16: Types II
- Casting is a runtime operation.
- When you use a generic method you don't need to specify anything, just pass in something and the type is inferred.
- Generic methods are very useful, and we probably use generic methods more than classes.
- Originally -- if `B` is a subtype of `A`, then `B[]` is a Java subtype of `A[]` -- expects a covariant relationship. 
- Wildcard -- an anonymous type variable. You can reuse the type all over the place. Wildcards don't have named, which is why they're anonymous. `? extends Type`, some unspecified subtype of `Type`, `?` alone is shorthand for `? extends Object`
- Don't want to use wildcards where types are needed to express type logic more than once.
- Two wildcards are two different variables
- Use wildcards to communicate that a type's identity is not needed anywhere else
- Used as syntactic sugar, but there's one thing they can do which named variables cannot -- they can have lower bounds instead of upper bounds.
    - `? extends Type`
    - `? super Type`
- PECS: producer extends, consumer supers
    - Use extends when you get values from a producer
    - Use super when you put values, no problem if it's a supertype.

```
<T> void copyTo ...
```

- Legal operations on wildcard types
- You can always add a null value.
- Type erasure -- generics are erased at runtime, so you can't check if a list is a list of integers or a list of strings.
- Javca erases the types of things and converts them to Objects, which means that at runtime we cannot check that generic instantiations have the smae type. 
- Casting can do weird stuff, `Objects` can also be cast to any generic type and actually don't know if anything is wrong

```
public static <T> T badCast (T t, Object o) {
    return (T) o;
}
```

- Bottom-line: Java can't guarantee a `List<String>` has only `String` elements at runtime.
- As long as there are no weird casting cases, it works out fine. The compiler inserts casts to and from `Object` for generics, but assumes the programmer knows the rules of generics. 
- Don't ignore warnings, because you're violating good style and risking difficult debugging
- It's ok to do casting for `.equals` -- check instance of, and then check that the fields are equal.
- Anytime we do instanceOf or equals, we cannot us ea psecific generic, we need to use a question mark to indicate that it is some type
- We can't distinguish between a node of Strings and a node of Integers
- Callbacks: pass an object with the code in a method
- How are callbacks usded in practice? -- clients passing in defined logics
- Event-driven programming.

---

## Lecture 17: Event-driven Programming
- An event-driven program is designed to wait for events: the progrma initialized and enters the event loop.
- This is different from the programs we have specified so far
- Register event, and then start an event loop.
- HTML / CSS / JavaScript
- TypeScript: a version of JavaScript which adds type safety
- React: a UI library which handles the interactions between TS and HTML.
- Mozilla working with IEEE, Brenden Eich creates JavaScript in 1995 in 10 days, used to make web pages interactive
- No relation to Java other than trying to piggyback on the Java hype at that time
- React combined HTML / CSS / TypeScript, compiles into JavaScript, which goes into HTML.
- Tree data structure lives in the browser and is called a DOM, Document Object model
- `let` allows rebind, `const` is like Java's final, and it can't change after creation.
- Types of values: `number`, `boolean`, `string`, `undefined`, `object` -- doesn't require specifying types even though there are types internally.
- Any value can be used as a boolean, e.g. `false`, `0`, `""`, `null`, `undefined`, `NaN` behave as `false`; everything else is `true`.
- Functions can exist outside of classes / objectrs and are values; you can pass them in variables and pass them to functions.
- Objects are basically key/value pairs, values can be functions

---

## Lecture 18: React
- Write mostly TypeScript
- The webpage is made up of Components, a class which extends the `Component` class. Components contain each other and form a tree structure like HMTL tags
- HTML has a DOM tree data structure
- HTML doesn't let you make your own tags. 
- The contract: react is "in charge" of the creation of the webpage, calls methods in components to do that
- React built by Facebook, React understands the data used to display the website. When data changes, it updates the page efficiently.
- `index.html`, a small amount of necessary HTML, `index.tsv`, starting point of code, `App.tsx` -- first component, App component
- `npm install` -- installs all the dependencies
- `npm start` -- starts the server
- `Component` is a generic class so we need to use geneirc-like syntax
    - First: props interface, second: state interface

---

## Lecture 19: React II
- In React, we build components
- React promises it is very fast and efficient, when you update a component state you need to test `setState` to update the state
- How to pass data from a parent into a child? 
- How to pass data from the child to the parent?
- 

---

## Lecture 20: React III
- Props are a requirement to make a component.
- States are the fields of the components. 
- Override the constructor to provide initial values for fields.
- Event-handlers: onchange lambda function, triggers a change.

---

## Lecture 21: Debugging
- Bug removal process:
    1. Find a repeatable test case which produces a failure
    2. Narrow down a location and cuase
    3. Fix the defect
    4. Run all of the tests, including the new one
- Design pattern: a standard solution to a comon programming problem. 
- GoF patterns: creational, structural, behavioral patterns
    - Creational: object creation process
    - Structural: how objects are composed
    - Behavioral: how objects interact
- Factory methods should usually be static methods.

---

## Lecture 22: Spark
- A browser sends a web request to the URL and asks if there are web pages to load.
- React recieves the request and returns it HTML, CSS< and JS.
- Spark Java Server operates on another port and allows you to respond to web requests and return different things depending on what it should. Wrapper around HW7 which responds to requests.
- Anonymous inner classes: helps put code closer to where it's used, especially used for `Comparator`s
- Inner classes: can access fields of the outer class, can be instantiated only with an instance of the outer class
- Anonymous inner classes help when I'm only using a class one time. -- just use an anonymous inner class syntax, define all of the methods in the interface right there
- JSON: JavaScript Object Notation
    - Built to work with JS
    - A way to represent data in a string
    - Many languages can serialize and deserialize frmo these strings
    - GSON lets you convert to a JSON string
- HW9
    - Execute Java code which produces a Java object
    - Use GSON to turn Java into JSON
    - Send JSON over network
    - Convert JSON into Javascript object to use data

Spark Java
- Spark $$\neq$$ Apache Spark
- Creates teh server by creating routes in the main method of your program
- A route is an instruction which tells the server what to do when it gets a request.
- Requests are bascially URLs. A GET request simply retrieves from the server.
- Forming a request
















