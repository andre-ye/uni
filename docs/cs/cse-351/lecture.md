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
- `movz` and `movs` - zero extension and sign extesnion, copies from a smaller source to a larger destination.
- Any instruction which generates a 32-bit (long, 4 bytes) value will zero out the upper portion of the register to zero.
- GDB
  - Start with `gdb <file>`.
  - Set breakpoints - stop things and look around.
  - `break main`
  - `asm` - shows the assembly code
  - `layout regs`
  - `run` - allows you to run until the breakpoint.
  - `stepi` - move to the next assembly instruction.
  - `print` - can print out the values of registers, add format specifiers to convert to hex.
  - `x` will dereference.
- Condition codes -c ount as part of the processor state. These need to be known to understand execution. We will look at `CF, ZF, SF, OF` - `F` stands for flag (zero or one). Other letters - carry, zero, sign, overflow.
- Condition codes will update after every operation.
- `lea` does not change the condition codes.
- Subtraction isa also infuenced as nh==hrardware residingi n software.
- Labels - a jump changes the program counter (`%rip` - tells CPU the address of the enxt instruction). Every instruction has an address.
- Labels are placeholders for an instruction defined later on.
- C has a `goto` method which replicates labels.
- In loops, we want to identify when the condition is false to determine when to exit.

---

## Week 4 Friday - x86-64 Assembly
- Instructions themselves are data stored in memory
- Jump table - structure used to store code blocks.
- Ordering code blocks allows for fall-through.
- If cases are not shown, they go to the default case.
- The jump table is only as large as it needs to be.
- Direct jump - `jmp .L9`, indirect jump: `jmp *.L4(,%di,8)`. Start of jump table at `.L4`, must scale by factor of 8, fetch target at EA `.L4 + x*8`.
- How are programs created and executed on a CPU?
- Subtracting the stack pointer increases the stack size
- `rax` - return pointer
- `callq memset` - pushes the return address onto the stack, changing `%rsp`.
- `rip` - instruction pointer, updated all the time.
- Mechanisms required for procedures - passing control, passing data, managing memory.
- Stack - high addresses in the address space. Local variables and procedure context.
- Heap - dynamic data, variables allocated with `new` or `malloc`.
- The stack is managed automatically by the compiler; the heap is maanged dynamically by the programmer; the static data, literals, and instructions remain static in memory.
- Segmentation fault - impermissible memory access, valid memory addresses accessed in ways which are not allowed (e.g. overwriting instructions in code).
- Growing goes down; shrinking goes up.
- `push` and `pop` are multi-part instructions.
- When you `pop`, the bits are still there but the stack no longer contains that data.
- Calling convention - where to leave or find things
- After calling `call`, the return address is the instruction immediately after the call instruction.
- Procedure return - `ret`. Pop the returned address from the stack and jump to it.
- The first 6 arguments are stored in registers; the seventh onwards are stored in the stack / memory. 
- Languages support recursion with the stack. 
- Code must be re-entrant - it can be instantiated in many places in the same instantiation.
- Frames - get put out but not removed immediately always

---

## Week 5 Monday - Stack Frames and Processes
- The return address is part of the callee's stack frame for the purposes of this class' calling conventions.
- `%rbp` - sometimes used as the frame pointer, store the last stack frame's version. `%rsp` - stack pointer.
- The return address is already pushed on the stack when we begin defining a process.
- We need to deallocate our space after we allocate space.
- Minimal stack frame - just 8 bytes given by the return address.
- The stack pointer should be pointing at the return address by the time that `ret` is called; all modificatios to `rsp` need to be oundone.
- 16 registers are being saved by all applications. 
- - Who is responsible for saving and returning original values? Caller-saved and callee-saved, a combination of both are used.
- Register usage: `%rax`, arguments, `%r10` & `%r11` for caller; others are callee-saved.
- Complications emerge for intermediate functions which are both callers and callees.
- Why bother with only caller or callee saved? In certain edge cases, using both can help with stack efficiency.

---

## Week 5 Wednesday - 
- Every stack frame has a return address.
- `backtrace` - tells you what your current stack looks like. Begins from the most recent call down.
- `info frame <framenum>` - frame 0 by default.
- ISC vs RISC. With CISC, we want to m=maximizze
- Tech monpolization
- Executables - how are programs created and executed on a CPU? How does it become something that the computer can understand?
- CALL - compiler, assembler, linked, loader
- Assembler - accept the compiled assembly code and output a binary machine code object file. Object/machine code.
- Assembly directives - `.text`, `.data`, `.quad`, etc.
- Two information tables - symbol table and relocation table.
- ELF format.
- `a.out` - gcc's default executable name.
- Linking stitches together multiple object files.
- Disassembly - how to examin object code? `objdump -d sum`. How to interpret the output? Comes in three columns: address code, machine code bytes, interpreted assembly
- An array name is not a variable; not exactly different from pointers; different in sublte ways. An array name is read-only because it is literally a label in assembly.
- Arguments to an array are actually passed as the argument (`%rdi` can only hold 8 bytes); so we always need both the array as well as the size information.
- Multidiimensional array - memory is one-dimensional but we put multiple differerent rows. Row-major-ordering: each individual row will be contiguous and different rows come after each other.

---

## Week 5 Friday - Structs and Alignment
- Multidimensional array - row-major ordering, it is guaranteed that all rows are arranged together. 
- Multilevel array - layers of layers of pointers, which each point to a subarray. 
- Multidimensional - only one memory access. Multilevel - need to access and follow pointers.
- `->` - dereference a pointer. `.` - reference an attribute of a struct.
- No objects in C (not object oriented) - just a group of variables.
- A struct is a statement in C - it must end iwth a semicolon.
- When using the variable, `struct name`.
- After being defined, struct acts like a primitive.
- `typedef` - can be used to create an alias for another existing data type.
- You don't need to declaree a name when using an alias.
- Make sure to know wha the slides are talking about.
- Struct pointers - pointers store addresses which look all the same. Same width, store addresses.
- When pointing to a struct, this struct has fields. A struct pointer doesn't need to point towards the declared instance of the struct.
  - Some struct fields might be meaningless.
- Alignment - if it is a multiple of $$K$$, dividing by $$K$$ should give me a remainder of 0.
- Each individual field has its own alignment requirements. 
- Arrays are treated by their elements - if the first element is aligned, then all following elements in the array will be aligned.
- The size of the overall struct must be a multiple of the maximum size. External fragmentation added after fields. If we want to use an array of structs, we need to make sure that following structs in the array are also aligned.
- Alignment of structs is completely deterministic
- Programmers can save space by re-ordering elements.

---

## Week 6 Monday - Buffer overflow
- Memory layout: stack, heap, statically-allocated data, literals, instructions
- Buffer - array use dto temporarily store data.
- Streaming - just obtain data for the next few frames. Buffering - waiting for the next data.
- Buffers can also store user input.
- Buffer - array defined within a function.
- When we keep on running upwards past the end of the array, we can run into overwriting non-buffer data.
- C does not check boudns: it's easy to go past the end of the array.
- Data and instructions are stored in the same stack
- Buffer overflow can overwrite interesting data
- Stack smashing - unchecked length on string input into bounded array causes the overwriting of stack data.
- Number 1 technical cause of security infiltrations.
- There is a lot of vulnerable code out there - `gets()`.
- Code injection attack - input string as ar represetnation of cdode to be aset.
- Explotis based on buffer overflows - allow attackers to execute arbitrary code
- Root shell - able to open a shell with admin privileges and can do anything
- 1988 Internet worm, Heartbleed, Cloudbleed, embedded devices
- New contexts for buffer overflow and unintended consequences
- How to deal with buffer overflow attacks
  - System-level protections - non-executable code segments, read-only/writable/executable, stack is non-executable, randomizing stack offsets - allocate a random amount of space on the stack.
  - Avoid overflow vulnerabilities - related functions are safer and can set limits, don't use C
  - Stack Canaries - place a special value (canary) on the stack just beyond the buffer, check to see if the canary message has changed before we return




















