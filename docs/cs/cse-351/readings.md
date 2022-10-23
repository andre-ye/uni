---
layout: default
title: Readings Notes
parent: CSE 351
grand_parent: Computer Science
nav_order: 2
---

# Readings Notes
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

## 1. Binary Reading
- A numeral is a number represented using a series of digits in a particular base.
- Convert to decimal using $$d \times b^i$$ for all indices $$i$$, base $$b$$, and digit $$d$$ at index $$i$$.
- Convert from decimal into another base by recursive division.
- Common bases - binary (base-2), decimal (base-10), hex (base-16).
  - You can directly convert from binary to hexadecimal and vice versa.

## 2. Memory and Data I
- CPU - executes computer instructions.
  - Word size - fixed width of data used by the CPU to execute instructions.
- Memory (RAM) - stores data for the CPU while instructionsa re being executed. Memory is a large array of bytes.
- Every byte in memory is given a hexadecimal address. Addresses are a fixed-length quantity. Address sapce - set of all addresses in memory.
- Data is moved and manipulated in fixed-length chunks. Leading zeros are therefore significant.
  - Leftmost bit - most-significant bit (MSB)
  - Rightmost bit - least-significant bit (LSB)
- Multibyte data in memory covers several addresses; the address of the first byte (smallest) is used by convention.
- Any chunk of data can be specified by its address and its size.
- Endianness - choice of ordering.
  - Big-endian - LS byte stored in the highest address
  - Little-endian - LS byte stored in the lowest address
- Pointers are variables that store addresses; the size of the pointer is the word size.
  - The pointer must also encode the size information.

## 3. Memory & Data II
- Pointers are special variables of word size which store addresses. 

```cpp
type* ptr;
```

- The address-of operator `&` goes in front of a variable, e.g. `int q; int*p = &q;`.
- Dereference operator `*` used to access the data pointed to by the pointer.
- Null - symbolic constant used for pointers. 
- Pointers can be represented with bow-and-arrow memory diagrams. Every box has a value, address, and variable name.
- Pointer arithmetic - automatically scale the arithmetic operation across the minimum data size (4 bits for ints, 8 bits for longs).
- Arrays: sets of contiguous locations in memory.`array[n]` referenced through `*(array + n)`. There is no bounds checking in C.
- C does not support an explicit string dataset. In C, strings are arrays of characters terminated by the null character.
- 1 byte per character.

## 4. Memory & Data III
- Bitwise operators apply boolean operations across bits of the operand(s) and can only be used on primitive/integral data types.
- Logical operators (`&&`, `||`, `!`) apply boolean operations to the value of the operands; `0` is False and anything else is true.
- C uses short-circuit evaluation
- Unsigned integers - nonnegative integers. 

| `unsigned char` | 1 byte |
| `unsigned short` | 2 bytes |
| `unsigned int` | 4 bytes |
| `unsigned long` | 8 bytes |

- Signed integers represent positive and negative integers. The most common encoding is two's complement: the most significant bit is kept as negative; all other bits are unsigned. Can represent from $$-2^{n-1}$$ to $$2^{n-1} - 1$$.
- To negate, flip all the bits and add one.

## 5. Integers II
- Signed and unsigned integers are different interpretations of data; nothing about the data itself is changed.
- Literals and constants can be changed into unsigned by appending `u` to the end.

![image](https://user-images.githubusercontent.com/73039742/193429178-d214e25c-be7b-4477-8177-b14f96665e80.png)

- The data type of a variable determines the data behavior.
- Type casting - conversion of data from one data type into another. Implicit cast - done automatically by the compiler to avoid problems.
- An explicit cast can be done with `(data_type) expression`.
- Casting does not change the data, it changes the representation.
- Zero extension - pads unsigned data with more zeros; sign extension - pads signed data with copies of the most significant bit
- When mixing signed and unsigned values, implicit casting to unsigned is done.
- Arithmetic on fixed-width binary numbers is modular; all bits after the end are dropped.

$$x-y = x + (-y) = x + (\sim y + 1)$$

- Arithmetic overflow - a calculation cannot be represented by the encoding scheme.
  - Unsigned overview vs signed overflow
- Shift operators - shift a bit vector by a specified number of digits, which falls the cut-off bits to 'fall off' and be lost; the remaining bits are filled by $$\forall$$ 1s or 0s.
  - left shift - `x << n`, zero padding
  - logical right shift - `x >> n`, `x` unsigned, zero padding
  - arithmetic right shift - `x >> n`, `x` signed, MSB padding
- Shifting can be interpreted as multiplying or dividing by powers of 2.
  - Right shifting always rounds down (floor operation).

---

## 6. Floating Point I
- Scientific notation: we can express small and large numbers without writing large digits.
- Three different parts - sign, mantissa, exponent.
  - Float: 1-bit sign, 8-bit exponent, 23-bit mantissa.
  - Double: 1-bit sign, 11-bit exponent, 52-bit mantissa.
- Sign - `0` is positive, `1` is negative
- Exponent - biased notation, shifted by $$2^{w-1}-1$$ where $$w$$ is the width of the exponent field (`0b011...11`); convert to unsigned; this lets us represent the same number of postiive and negative exponents.
  - To encode, add the bias
  - To decode, subtract the bias
- Mantissa: must be of form `1.bbbb`$$_2$$. Implicit leading one, but this is not stored.

---

## 7. Floating Point II
- Floating point allows for special cases, given as combinations to the exponent and mantissa fields.
- 0 exponent: denormalized number; all-1s exponent and all-0s mantissa: $$+/- \infty$$, all 1s-exponent and nonzero mantissa: NaN
- Denormalized number: uses an implicit leading 0. Allows for encoding smaller numbers near 0.
- If a number is too large, it results in overfow; the result is stored as infinity. If it is too small, it results in underflow.
- We have limited precision; we cannot represent numbers between representable numbers.
- The largest normalized exponent is 127.
- Arithmetic operaitons on infinity and NaN will work but result in bizarre ways.
- Rounding breaks down certain mathematical properties of floating point arithmetic.
- Casting an integral data tpe into a floating point data type changes the bit representation.

---

## 8. x86-64 Programming I
- Instruction Set Architecture - ISA. Parts of the processor design needed to write assembly code.
- ISA - state, instruction set, effect.
- Complex Instruction Set Computer vs Reduced Instruction Set Computer.
- x86-64 is far on the end of CISC; we will look at integral data and use AT&T syntax.
- Instructions are given with an instruction name followed by operands.
- Assembly instructions: data transfer, arithmetic and logic, control flow
- Size specifier - byte, word, long, quad (1, 2, 4, 8 bytes)
- Operands are three types - immediates ($), registers (%), memory ().
  - An immediate cannot be used as a destination operand
  - You cannot use a memory to memory operation
- Register - location in CPU to store a small amount of data which can be accessed quickly. Registers are referred to by name. 16 registers; 8-byte register names.
- How to express a memory operand? 4 parts: `D(Rb, Ri, S)`. Displacement - immediate or constant; base register - name of register whose value will be the base; index register - value will be scaled and added to the base; scale factor - scales the index register by a specified number - 1, 2, 4, 8.

---

## 9. x86-64 Programming II
- Load effective address - `lea`. Source operand must be a memory operand; destination operand must be a register operand. Allows us to manipulate addresses rather than dereferencing memory.

```x86
lea D(Rb,Ri,S), R  # stores Reg[Rb]+Reg[Ri]*S+D in Reg[R]
```

- Condition codes - status bits of the CPU which give information about the history of instruction executions. Flags are set implicitly and automatically by operations, but can also be done so explicitly - `cmp` and `test`. These only update condition codes and are never stored.
- `jump` and `set` - implement all control flow.
- Flags: Carry Flag (CF), Zero Flag (ZF), Sign Flag (SF), and Overflow Flag (OF).
- `jump` - jump program to a specified target if a condition is met.
- `set` - set the value of register `dst` (1-byte) to the value of the condition.

----

## 10. x86-64 Programming III
- Extension instructions - like `mov`, but the source operand is smaller than the destination operand. Therefore, values can be extended with zero extension (`movz`) or sign extension (`movs`).
- Conditionals in assembly are made of a condition code instructor and a conditional jump instruction.
- Operand to jump instruction - label. Symbolic representation of an instruction's address.
- Loops can be freely introduced into assembly; if the name of the label is used as a target, the program will jump to the instruction.
- If/Else can be constructed by using labels and jump statements.
- Jump targets go to the beginning of the loop body to construct loops.

---

## 11. The Stack and Procedures
- Jump table - data structure used to branch to different parts of the program. Array of pointers - pointers to code blocks.
- Program counter `%rip` - holds the address of the next instruction.
- We need to update the program counter in addresses stored in the table with indirect jumps - `jmp *Loc`.
- The memory address space is arranged to optimize data usage. From low to high addresses:
  - Instructions
  - Literals
  - Static data
  - Dynamic data (heap)
  - Stack
- Stack - takes up the highest useable addresses.
- End/top of stack is stored in the stack pointer `%rsp`. 
- The stack pointer can be changed through `subq` and `addq`.
- `push` and `pop` will allocate and deallocate data from the stack.
- Calling conventions - rules to guarantee procedures and pass data and control.
- Return address - address of the caller's next instruction to execute.
- `call` is a label instruction, will push the return address onto the stack and update the program counter to the address of the label.
- `ret` will pop the return address of the stack and update the program counter to that address. 
- Return values are placed in `%rax`.
- We want to support instantiation of individual procedures to enable recursion.
- Stack frames - hold the local state of each procedure instantiation.
- LIFO stack - the caller's stack frame cannot be deallocated until the calee's stack frame is.

---

## 12. Procedures and Recursion
- Stack frame - has a return address marking the beginning of the stack frame.
- Arguments 7+ are part of the caller's argument, put on the stack before `call`.
- x86-64 Register Saving Conventions - describe how we deal with register reuse.
- Registers are callee-saved or caller-saved.
  - Callee-saved: callee's responsibility to restore the old value before returning.
  - Caller-saved: the caller must save the existing state before it passes control to the callee. The old value is restored after the callee returns.
- Recursion works without additional work due to the stack frame layout.

---

## 13. Executables, Arrays
- CALL: compile, assemble, link, load.
- Compiler: translate a text file (bytes interpreted as characters) into an assembly text file.
- Assembler - convert assembly code into a binary object file.
  - Object code: 'incomplete', we do not have addresses for labels yet.
- Linker - put together the object and static library files.
- Loader - take an executable file and start a running process from it.
- Arrays in assembly: the name is a placeholder for the starting address of the array.
- Array subscript notation is sugar for address dereferencing.
- C uses row-major ordering for multidimensional arrays.
- Multilevel arrays are created by adding additional levels of arrays of pointers to arrays.

---

## 14. Structs and Alignment
- A struct in C is a structured group of variables with various fields.
- Purpose of a struct definition is to define the size and layout of a struct.
- Fields are accessed using `.` or `->` for pointers. 
- `typedef` - allows you to create aliases to other data types, e.g. `typedef unsigned int uint;`.
- A primitive object is aligned if its address is a multiple of its size.
- Unused space between fields - internal fragmentation.
- External fragmentation: the overall size of a struct also must follow alignment requirements.

4 + 6 + 1 + 4

4 + 4 + 8 + 4






















