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

---

## Week 3 Monday - Floats
- We often need to encode a variety of other numbers - floating point represents real numbers, very large numbers, very small numbers, special numbers.
- IEEE floating-point standard.
- Normalized form - exactly one digit to the left of the binary point.
- Floating point - the point can float around
- Float operations - flops, can be a proxy for the performance of a computer.
- Sign bit, mantissa, exponent. 
- Exponent field: use biased notation, use both positive and negative exponents. 
- Why use biased notation and not two's complement? If we look at the exponent field and the mantissa, we can make floating point arithmetic easier. 
- We cannot represent zero with this representation. 
- Accuracy: difference between the actual value of a number & its representation. Precision: number of bits in a computer wrod used to represent a value. 
- Double precision: consumes 64 bits. The exponent increases by three fields and the mantissa increases significantly. 

---

## Week 3 Wednesday - Floaitng Point
- Because float is sign & magnitude, there are two representations for zero. 
- Overflow and underflow relate to the exponent field; rounding concerns the mantissa field.
- $$2^127$$ is the highest representable exponent.
- Special cases - $$E$$ and $$M$$ field are all zeros is represented as 0. There is $$\pm 0$$.
- `0xFE` is now the largest number: $2^{128} - 2^{104}$$ (using exponent $$2^{127}$$)
- The smallest exponent is `0x01`, or $$2^{-126}$$.
- Denormalized numbers: zero exponent and nonzero mantissa. There is no leading implicit one.
- Mathematical properties of FP operations: overflow yields $$\pm \infty$$ and underflow yields $$0$$.
- Floats with infinity and NaN can be used in operations; results are always well-specified. 
- Floating point operations lose some properties due to rounding - not associative, not distributive, not cumulative. 
- Round to nearest, ties to nearest even digit.
- Avoid using equality comparisons for floating point numbers. Instead, use a threshold epsilon.
- Casting between `int`, `float`, `double` changes the bit representation.


---

## Week 3 Friday - x86 Assembly
- Topic group 2 - programs
  - Architecture (ISA) - parts of processor design needed to write assembly code.
- Microarchitecture - implementation of the architecture.
- ISA defines the system state, instructions, effect - defining words and the effect
- Complex instruction set computing - CISC. Add more elaborate instructions. Reduced Instruction Set Computing - keep instruction set small.
- Mainstream ISAs - x86 (intel), ARM, RISC-V
- Architecture sits at the hardware interface. The compiler generates instructions and optimizations in the instruction set.
- Why write assembly code? You will probably never write a program in assembly, but understanding assembly is important to understand machine-level execution.
- Every program in your computer has some equivalent in assembly.
- Data types in x86-64 assembly: integral data (1, 2, 4, 8 bytes), floating point. No aggregate types.
- Comes with two syntaxes - AT&T, intel
- Register - a location in the CPU which stores a small amount of data and which can be accessed very quickly. Registers have names, not addresses. Registers are very important in assembly programming.
- x86-64 integer registers - 64 bits wide.
- Moving data - general form of `mov_ source, destination`. More of a copy than a move.

---

## Week 4 Monday - x86-64 Assembly II
- Memory addressing - `D(Rb,Ri,S)`. Displacement, base register, index register, scale factor.
- The scaling factor matches to the data type that we want (`char`, `short`, `int`, `long`)
- Parallel with `*(ar + i * sizeof())`
- We can dereference just with `(%reg)` - if ommitted, every field has a default value. 
- `leaq src, dst` - load effective address. We don't always want to dereference; sometimes we want to manipualte addresses. No dereference / memory access.
- To translate C programs into Assembly, rewrite such that operations are done only as modifications to existing variables.
- `lea` stops at the address, whereas `mov` dereferences it.
- We can 'cheat' and use `lea` to perform arithmetic. 
- Jump statements can be used to develop control flow.

```
if not: jump to b
do something
jump to z
b: do something
z: ...
```

- Conditional branches and unconditional branches (jump) allow us to implement all control flow. Condition codes allow us to do this.

---

## Week 4 Wednesday - x86-64 Assembly III




























