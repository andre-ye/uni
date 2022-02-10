---
layout: default
title: Lecture Notes
parent: CSE 142
grand_parent: Computer Science
nav_order: 1
---

# Lecture Notes
{: .no_toc }

CSE 142
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

## Week 1 Wednesday Lecture

### About CSE 142
- Learning Objectives
  - **Functionality/Behavior** - write functionally correct Java programs that meet a provided specification and/or solve a specified problem.
  - **Functional Decomposition** - break down problems into subproblems that are modular and reusable, and define methods to represent those subproblems.
  - **Control Structures** - select and apply control structures (e.g. methods, loops, conditionals) to manage the flow of control and information in programs.
  - **Data Abstraction** - select and apply basic data abstractions to manage and manipulate data in programs.
  - **Code Quality** - define programs that are well-written, readable, maintainable, and conform to established standards.
- 1/5 is about if the code works - it is not enough for the code to work. Code is for people, not computers. Code must be readable, well-written, and maintainable.

### Other Similar Courses

| Course | Attributes |
| --- | --- |
| CSE 142 | No programming and major in CS, CE, EE. |
| CSE 143 | Programming in Java before or AP CS in high school. |
| CSE 143x | You have programmed in a lanugage other than Java and are confident you can pick up new concepts. |
| CSE 160 | Interested in data science and analysis and learning Python over Java. |

### Course Components
- Lessons on MWF 11:30 in KNE; recordings will be released afterwards. First introduction to course concepts. Mix of content presentation and activity/problem practice. *There will be some required pre-work*.
- Sections on Thursday in various times. Led by TAs; held live in person and *not* recorded. Additional review, discussion, and practice; mostly practice problem. Double-check your MyUW again before section because rooms may change. Materials will be released after section.
- No attendance is taken; there is no need ot notify absences.

### Pedagogy
- You didn't learn how to ride a bike by being taught how to ride a bike.
- Learn by doing; do not expect to sit down and write code the first time successfully. Practice and expect failure.

### Learning in CSE 142
1. Exposure - lessons, video, textbook. Encounter concepts for the first time.
2. Guided practice - lesson activities, sections, labs. Practice with support from course staff.
3. Independent/Group Practice - checkpoints, section problems, additional practice.
4. Assessment - take-home assessments. Build upon steps 1-3 scaffolding, learn by doing and demonstrate mastery.
- Expect to practice, make mistakes, and do things more than once.
- Question-oriented.

---

## Week 1 Friday Lecture

### Java
- Programs begin with `public class`.
- All lower-case letters in keywords.
- Only allowed to use letters, numbers, underscores, and dollar signs.
- Conventions for this class - use pascal casing (e.g. `HelloWorld`, `ByeNow`).
- Program names must be descriptive.
- Use tabbing and indentation.
- `public stratic void main(String[] args)` - entry point, will use in the beginning of most every Java program.
- Command, method call - tells the program to do something.
- String - text, indicated by double quotes.
- Most lines in Java (statements) end w/ a semicolon.
- Methods - take a chunk of code and give it a name. Adds structure to the code and allows for repeated code to be called easily.
- Method names **begin with a lower letter**, whereas program names **begin with an upper letter**.

### Assessment and Grading
- The goal of the course is to master the concepts and skills being taught.
- Work assessments are a proxy for mastery, and the final grade should reflect the extent to which you have demonstrated course objective mastery.
- Take-home assessments (weekly, 8), checkpoints (checkpoints, 9-10), culminating assessments (2), reflections (8-10)

---

## Week 2 Monday Lecture

### Administrative
- Large programming assignments to assess mastery of the week's concepts. Make up the bulk of assignments.
- Credit for a checkpoint is to get the small-check mark.
- Culminating assessments (series of problems overing all material up to that point)
- Reflections with other assignmentsaa - put some time and thought into it
- ESNU grading: final grades will be assigned based on the amoutn of work at each level.
  - Visit the syllabus for ESN table.
  - Count how many reflections, checkpoints, etc. - compute the bundle and find the highest of guaranteed grades that you completely qualify for.
  - After the bundles, there will be bumps; credit will be given and adding it to the base grade.
  - The bumps are not given by a preset grading distribution. Accounts for changes in the course.
- Resubmission: one previous take-home assessment can be resubmitted each week.
- Collaboration policy: you can discuss ideas and approachess at a high level.

#### Java
- Use `System.out.println()` instead of `System.out.println("")`.
- Use methods to capture structure; don't put all code in the main function.
- There is not one right way to write code.
- Be able to defend your choice.
- Redundancy: we don't want to repeat code unnecessarily. The more you type, the more likely you will make an error.
  - Current definition: 2 or more lines of code that are exactly the same in 2 or more places in your program.
  - A single line of code cannot be redundant.
  - We make a few exceptions to the redundancy rule, including blank lines.
- Methods can call other methods.

---

## Week 2 Wednesday Lecture

- Control Flow Construct: the order in which operations are executed.
- So far, we have used linear control flow.
- Loop - a mechanism to make a chunk of code execute an integer number of times.
- Syntax: `for (int i=0; i<n; i++) {...}`.
  - Initialization, condition, update method
- Assignment - setting a variable to a value.


---

## Week 2 Friday Lecture

- Counting loop; waiting until a condition happens.
- Initialize vcounting variable once; test the condition; repeat until condition is violated.

---

## Week 3 Monday Lecture

### Administrative
- Look at feedback and make sure you are taking advantage of given information.
- Highly important and recommended to reference resources.

### Java
- Class constants - `public static final int VAR = VAL;`.
- Truncated/floor division.
- Modulus - remainder.

---

## Week 3 Wednesday Lecture
### Administrative
- Resubmission Cycle - fill out a Google form and provide the Ed URL in addition to remarking your submission.

### Java
- Scope - where are things visibe to each other?
- A variable declared in one method is not visible in another method.
- Parameters -what we do when we call the method and what we do in the method that accepts the parameters.
- Never use global variables.
- `import java.util.*` - import directive. Put at top of script. We must ask to get access to this.
- `Scanner` is a class in Java - performs input.
- `Scanner console = new Scanner(System.in); int input = console.nextInt();` - connects to the computer input.

---


## Week 3 Friday Lecture
- Procedural programming - verb, noun structure.
- Java is designed for *object-oriented programming* rather than *procedural programming*.
- A class defines the structure of an object; an object is the thing itself.
- Scanners - `Scanner console = new Scanner(System.in); int input = console.nextInt(); String strInput = console.next()`.
- Pass the console as a parameter to a method using user input.

---

## Week 4 Monday Lecture
### Administrative
- Things are ramping up and we are getting into the meat of the coruse.
- Moving from feeling uncomfortable to unsure.

### Java
-`char` vs `String`
- Return values; we must recognize how to use the return value.
- If you want a method to return something, replace `void` with the output type.

---

## Week 4 Wednesday Lecture

- Return values - a method to pass information throughout different methods.
- Store returned values in a variable, do not assume that variables themselves have been passed.
- If you want to concatenate characters into a string, use `""+char1+char2+char3`.
- Conditionals/branches/if statements.

```java
if (condition) {
  doSomething();
}
```

- `num == 0`
- `if/else if/else`

---

## Week 4 Friday Lecture
- Pseudocode - planning programs without worrying about syntax.
- Cumulative programs.


---


## Week 5 Monday Lecture

- A method should complete one task - don't chain methods.
- Main should drive the program. Methods should complete their own work rather than dictating what should come next.
- Reading in multiple words: `console.nextLine()`; don't mix `nextLine` with anything else.
- We cannot use `==` with Strings in the way we want it to. Strings are objects (i.e. not primitives); this tests if the two objects you are comparing are exactly the same object - not if it holds the same information.
  - Use `String.equals(String)` instead.
- Use `while` loop

---

## Week 5 Wednesday Lecture
### Administrative
- Simulated Midterm - write what a midterm would have looked like.
- A key for the simulated midterm will be released; you will be asked to annotate the midterm and make notes on what you didn't do correctly.

### Java
- Fencepost problems: posts and wire.
- Also can be known as a sentinel loop.

---

*Notes discontinued after Week 5.*















