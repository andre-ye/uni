---
layout: default
title: Class Notes
parent: CSE 390HB
grand_parent: Computer Science
nav_order: 1
---

# Class Notes
{: .no_toc}

CSE 390HB
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

## Week 2
Adminstrative
- Course will be graded 7/9 weeks participation.
- 4:30 to 6:20 on Thursdays in CSE2 371.
- [Course Website](https://courses.cs.washington.edu/courses/cse143/22wi/honors.shtml){:target="_blank"}

Concepts
- *Computers*. A Turing Machine is a static machine that can perform very complex programs given the necessary symbols/instructions. However, it is not a computer. A *Universal Turing Machine* is a 'Turing Machine of Turing Machines' that contains a key property of computers: *programmability*. For this reason, a 4-function calculator is not a computer.
- *Meta-reasoning and meta-knowledge*. Humans are very good at reasoning on a meta- level, even though we may not completely understand our capacity for it. We can easily understand and build models for what others think about us, what others think about what we think about them, what other think about what we think about what they think about us, and so on. It may seem confusing when articulated in natural language, but these sorts of situations happen all the time in real life and in television/drama shows and we are able to understand it without friction.
- *Memes* - from Dawkins. Molecules in the primordial soup interact and compete in the replication competititon; they build survival apparatuses like cell membranes and become *survival machines*. Similarly, cultural phenomena and ideas engage in the replication game.
- *What defines a story?* A sequence or description of events (e.g. "I ate breakfast, I watched television, I worked") generally does not constitute a story. **The Reges Law**: every story must have a *meme*; this can be a moral (e.g. Aesop's fables). *Stories are the 'cell membrane'/survival machine mechanism of memes.*
- *Robert Frost and The Road Not Taken*: often read as a moral to take the path less trodden - *but neither path is more trodden than the other*. What is this a story of? Meta-dynamics, the human ego, our desire to wish things to be as we wish them to be and to invent a reason to support it, the longing of what the other road was.

---

## Week 3
- Concepts of race and class, prioritization/ranking of identity vs symbiosis/intersection of identity
- What makes humans unique? Passing down information from one generation to another
- Competition of memetic material
- Crossing of genetic evolution ('hardware', Turing machine) to memetic cultural evolution ('software', Universal Turing Machine).

---

## Week 4
- Developments in mathematics: Russell, Cantor, Godel, Turing
  - 1900 and the questions for the next century
  - The Continuity Problem
  - The Stability of Mathematics
- Cantor and the diagonalization argument, different sizes of infinity (countable vs uncountable sets)
- Understanding Reges' perspective in the Stanford drug incident
  - How should drug use be characterized and regulated?
- Interesting quasi-scandalous story of Reges, Peter Thiel, and homosexuality

---

## Week 5
- Race, class, and education
- Role of education in a new understanding of class (as opposed to traditional Marxist understandings)
- Reges' experience in education from Case Western to Stanford
- Godel's incompleteness theorem
- Turing and the Halting Problem
- Card trick

---

## Week 6
- Question of media and separation of 'facts' and 'interpretation'
- Two stories: the Joe Rogan story and the Canadian Trucker story
- The Overton window; the nature of discussion
- What did Trump do to change the journalism model?
- Explaining the card trick combinatorial problem from the previous class.
- Turing and computable numbers: any program used to compute a number is represented in binary; this binary representation corresponds to an integer. If for every real number there exists a computer program that can compute it, then the set of reals is on a one-to-one comparison with the set of integers. We know from set theory and the diagonalization argument that this is not true. Therefore, many numbers are not computable - but we can't express any of them, because if we could express them they would be computable!
- Rubik's cube properties:
  - If we 'melted off' the colored tiles/stickers on a Rubik's cube and put them back on, is the cube still solvable (i.e. revertable back to its original state)? The answer is clearly no. How would we write a computer program to determine if a cube is solvable or not? Look at relationships between edges, corners, centers, etc.
  - If we took off entire blocks (i.e. retaining the relationships between colored tiled/stickers are the same) and reattached them, is the cube guaranteed to be solvable? The answer is also no.
  - If we attach an orientation number from 0 to 2 for each corner orientation, the sum of orientation numbers for all corners in a Rubik's cube must be divisble by 3. Discovered by Stuart Reges and the graduate students at Stanford's Problem Solving seminar!

---

## Week 7
- Gossip about the CSE course restructuring; Reges and Hunter agree to grade 'from the same distribution' - different grading practices (e.g. retakes vs no retakes), different exam policies, etc. INconsistency across different quarters.
  - When UW CSE was interviewing Reges in 2003, there were two questions: a) should there be a tsar to manage introduction courses? b) if so, should it be Stuart Reges? The first barely passed and the second passed with less contention. Reges built the introduction courses up and was incredibly consistent throughout that time.
  - UW CSE introduction courses will be split into three rather than two starting next fall. Reges prefers the courses that he built - as one may expect - but notes that the "younger instructors should take charge" with guiding and shaping the future of UW CSE introduction classes. He notes that all systems favor some people over others, and that both systems have advantages and disadvantages.
- Race and racism - what is racism? What is defined as racism? How are concepts of intersectionality relevant? Is there rampant racism on campus? What is the Overton window distribution on the discussion of racism? How does ideology and culture affect our understanding and heightening of what racism means and is?
- Discussed Reges' talk "The Mystery of b := (b = false)"
  - Reges was the principal reader for the AP CS Exam one year in the 1980s
    - (Reges actually holds the record for failing the most number of students out of any principal reader - 2/3s under a score of 3!)
  - Reges was interested in correlations between different questions on the test - multiple choice, open response
  - If a correlation is larger than 0.2, it is considered significant in this concept.
  - Discovered a set of 5 'power questions' - question #23 was the most significant. This question had high correlation/predictive power with many other multiple choice questions - even questions covering much more advanced content - as well as the free response.

```
Question #23. If b is a Boolean variable, then the statement b := (b = false) has what effect? (Java-fied: boolean b = ...; b = (b == false);. Python-fied: b = ...\n b = (b == False).)

A) It causes a compile-time error message.
B) It causes a run-time error message.
C) It causes b to have value false regardless of its value just before the statement was executed.
D) It always changes the value of b.
E) It changes the value of b if and only if b has value true just before the statement was executed.
```

| The correct answer is $$2\left((6t^3 + 1)^3 - (6t^3 - 1)^3 - (6t^2)^3 \right)$$ for any value of $$t$$, where each integer corresponds to a letter alphabet letter (1 = A, 2 = B, etc.). |

  - Why is this question #23 such a good predictor? Reges' hypothesis: to solve it, you need to think like a computer and evaluate counterintuitive facts.

*After class, a group of 5-6 students stayed after for an extended discussion lasting slightly under an hour after class. Here are some highlights from that conversation.*
- Why is there such a gender imbalance in computer science? Reges notes that he has seen so many bright young women in STEM that he does not believe that there are necessarily biological interest differences structured in different sexes (as another student suggested), but put forth that women may find other interests elsewhere (i.e. it is a matter of interest rather than competence).
- Don Knuth suggested that around 2% of the world's population was naturally gifted at computer science - thinking and reasoning algorithmically in a way that Question #23 requires. Those people, Knuth suggested, should do computer science and nothing else due to their gift.
- Immigration and the question of nativism; Bannon vs Reges' different perspectives. Bannon believes that immigration should be restricted to prioritize American workers; Reges believes that he operates more by skill and supports immigrants to come to the United States, get their degrees, and settle as American citizens.
- The Fourth Turning; The End of History and the Last Man - will there be another war? What will it look like? What will the next revolution be like? Tensions between Russia and Ukraine, America and China. Francis Fukuyama and the question of opposing ideology.
- Martin Luther King suggested that "the arc of the moral universe is long, but it bends toward justice" - Reges believes that cyclic models on human progress and civilization may be more apt.

---

## Week 8
- Questions around moral panics and censorship
- Who has a right to speak? What are the justifications for censorship?
- Stuart Reges was offered a faculty position by Stanford in his early 20s - a dream job, but only under the condition that he would never be allowed to write anything about his homosexuality. He accepted (under temporary terms) then, but wishes he didn't now.
- Stuart Reges and the controversy over the winter 2022 Indigenous Land Acknowledgement in the syllabus: free speech in academia.
  - It seems that indigenous land acknowledgements are inherently political; if a professor is allowed to write favorably in one political direction, then another professor should be allowed to write favorably in a different political direction.
  - Reges wishes that there were not indigenous land acknowledgements on syllabi at all; this incident was planned to test how 'far' he could go with expressing the alternative to political opinions in the common academic mainstream.
  - Magdalena Balazinska, head of the Allen School, had IT take down Reges' syllabus; Reges put it back up; IT put it back down the following day and disabled Unix permissions. Reges notes that he *could* have put it back up through clever means but decided not to.
- Comparison of indigenous land acknowledgements to the pledge of allegiance (which Reges has disdain for) - both are ritualistic in nature, intended as a say-and-repeat prayer rather than necessarily anything really substantive.
- Diversity statements - when you apply to the Allen School and you are asked, "How do you contribute to the diversity of this school?" - what do you say? There is probably a clear answer that you know - something that you are *supposed* to say.
  - Should you say what you are supposed to say? Here, Reges became emotional and shared a quote from a novel - approximating "not talking about my life left a void where a life should have been"
- Demonstrated building a Turing machine to recognize binary palindromic sequences

