---
layout: default
title: Lecture Notes
parent: CSE 351
grand_parent: Computer Science
nav_order: 1
---

# Lecture Notes
{: .no_toc }

CSE 351
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

## Week 1 Wednesday - Introduction, Binary and Hex
- Why do we have powerful machines and how can they run a wide variety of software?
- The goal of the course is to present key abstractions under the hood. 
- Layers of computing: software applications (14x, 331, 332), programming languages and libraries (341), operating systems (451), hardware. 351 is between operating systems and hardware: the HW/SW interface.
- Topic groups:
  1. Data - memory, data, integers, arrays, structures, etc.
  2. Programs - x86-64 assembly, procedures, stacks, executables
  3. Scale and Coherence - cahces, processes, virtual memory, memory allocation
- Grading
  - Pre-lecture - for completion
  - Homework - unlimited submission attempts
  - Labs - graded for correctness
  - Exams - midterm and final, take-home, individual
  - EPA - effort, participation, altruism.
- Get machine access to the CSE Linux environment (SSH into attu for CSE majors) ASAP.
- Relationship between binary and hex: every digit in hex corresponds to a four-length binary string. 
- Computers compute generally in base 2.
- We need to agree on an encoding - equivalent representation of numbers. 
- With $$n$$ binary digits, you can represent $$2^n$$ things.
- Binary digit - a bit. A hex digit (4 bits) - nibble. Two hex digits (8 bits) - byte.

---

## Week 2 Wednesday - Pointers
- The data type tells the size; pointers with different types indicate different sizes (but the same memories).
- Assume a 64-bit machine and little-endian.
- `a[i]` is syntactic sugar for `*(a+i)`; an array is not an object, the size is not stored. 
- The array name is not a variable - it is an expression which will evaluate to the address of the array. 
- Every time you add to a pointer, you increment by the minimum data size, not in bytes. 
- Use a Makefile - `make clean; make`. Run `ptest` and the rule/syntax checker to check.
- Lab synthesis questions
- Bitmasking - allow us to perform an operation using a bitmask and an operator, such as negating or setting to zero/one.
- How to represent a deck of cards?
  - Binary encoding using 6 bits. Works but other encodings may be more efficient.
  - Make two fields - two bits for the suit and four bits for the number. 
- Unsigned - only non-negatives; signed - positive and negative.
- Sign and Magnitude: we designate the MSB as the sign bit and others as the magnitude field; however there are redundant representations for zero and it 'breaks math'.
- Two's complement representation
  - Flip negative encodings so incrementing works
  - Shift negative numbers to eliminate `-0`
  - The MSB is still 1 if it is negative.

---

## Week 2 Friday - Integers
- Limits imposed by memory affect representation size.
- In casting, bits are unchanged, but just interpreted differently. (For integers, at least.)
- USe explicit casts.= rather than implicit casts.
- Integers are considered signed by default; `u` can force agreement.'
- Shifting counts as multiplication and division.
- Left shifting can cause overflow and other problems - signed overflow.
- Right shifting - there is no overflow because you are dividiing. Always rounds down.










