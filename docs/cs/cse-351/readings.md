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

---

## 15. Buffer Overflow
- Buffer: a region of the memory (usually array) used for temporary data storage.
- Buffer overflow: writing data past the end of the buffer. 
- Sometimes buffer overflow causes program execution to break or goes unnoticed.
- Stack smashing - write past the end of a local array in the stack. The buffer moves towards higher addresses. Stack smashing overwrites the return address in previous stack frames.
- If a user enters a string longer than can be held in the buffer, we will get buffer overflow.
- Code injection: can be used to take advantage of the fact that all data is stored in memory. 
Code injections: use buffer overflow to overwrite instructions and change the returna ddress to execdute the injected code.

---

## 16. Memory and Caches I
- IEC prefixes - refer to powers of 1024.
- Caches - memory with short access time, used to store frequently or recently used data, including instructions.
- Data is transferred in blocks - machine-specific fixed units of data transfer.
- The CPU will always check the caches first when accessing memroy.
- Cache hit - data is found in the cache. Cache miss - not found, fetch from real memory adn copy into cache.
- Principle of locality: programs tend to use data at addresses near those which have been used recently.
- Temporal locality - recently referenced items likely to be referenced again
- Spatial locality - items in nearby addresses likely to be refereced again
- Copy data into the cache on a cache miss to maximize cache hits
- Metrics: hit time (how long a cache hit takes), miss penalty (how long it takes to find a blcok fo data from memory, hit rate (fraction of memory accesses resulting in cache hits).
- Average memory access time (AMAT): Hit time $$+$$ Miss Rate $$\times$$ Miss Penalty
- Timing reported in clock cycles

---

## 17. Memory and Caches II
- The memory hierarchy: local data storage and remote/external data storage.
- Each level is a cache of the level below it - faster way to access a subset of available data.
- Blocks are formed from 0 to $$K - 1$$, $$K$$ to $$2K - 1$$, and so on.
- We can determine which block an address is in by taking the floor of $$\frac{A}{K}$$: this is the block number.
- $$A % K$$ is the block offset.
- Cache size - measures capacity of the cache. Defined as a multiple of block size.
- Where to place blocks on a cache miss? 
- Direct-mapped cache placement - use a hash function, block number % (C/K) to determine where to put a block. 

---

## 18. Memory and Caches III
- $$m$$-bit address: TIO. $$t$$ bits for the tag, $$s$$ bits for the index selection, $$k$$ bits for the byte offset selection.
- Widths: $$k = \log_2(K)$$, $$s = \log_2(C / K)$$, $$t = m - s - k$$.
- A direct-mapped cache always maps blocks to a single index. What if we alternate between different blocks which map to the same index? We lose temporal locality's benefits. 
- Associative cache - each block fits in a set of locations.
- $$E$$-way set associative cache: each block can be put in a set $$E$$ ways. 
  - Direct-mapped cache: 1-way
  - Fully-associative cache: $$C/K$$ way
- Caches - there will always be data present. Is it program data or mystery data? Valid bit lets us tell the difference. Management bit - stored in the cache for each block.
- Cache line - block and management bits.
- Cold cache: no valid program data.
- Cache: number of sets $$S$$, associativity $$E$$, block size $$K$$. Cache size is the product of these three.
- Cache miss categorization:
  - Compulsory misses: we have to have a cache miss if we access something for the first time.
  - Conflict misses: more references map to the same set than we can allow to coexist.
  - Capacity misses: we don't have enough space to keep all the data.
- Larger block size $$\to$$ fewer compulsory misses
- Higher associativity $$\to$$ fewer conflict misses
- Larger cache size $$\to$$ fewer capacity misses

---

## 19. Cache Writes and Data Consistency
- Writes change data, not just reading it.
- Write-hit and write-miss
- Write-hit:
  - Write-through cache writes the change into the block in the cache and in the level below
  - Write-back cache writes the change only to the block in the cache but makes a note that it changed; dirty bit must be stored
- Write miss:
  - Write allocate cache loads the block into cache before executing a write-hit
  - No-write allocate cache skips the cache and sends the write to the level below
- Write-back, write-allocate: avoid going to the lower level as much as possible
- How to optimize code based on memory hierarchy?
- Spatial and temporal locality
- Cache blocking - block operations on a large data structure so chunks fit into the cache.

---

## 20. Processes I
- Control flow - your computer is executing multiple programs concurrently.
- Exceptional control flow - trasnfer control and react to external signals.
- Exception - transfer of control to the kernel in response to an event. An event handler will deal with the event. 
- Three possible outcomes:
  - Re-execute the instruction
  - Execute the next instruction
  - Abort the process
- Asynchronous Exceptions - interrupts, external to the processor
- Synchronous exceptions - traps, faults, aborts
- Processes - instance of a running program/executable.
  - Logical control flow - each process 'thinks' it has exclusive use of the CPU
  - Private address space - each process 'thinks' it has exclusive memory usage
- Program vs process
- Multiple processes run on the computer with few CPUs.
- Processes run concurrently if their instructions overlap in time.
- Context switching -  pause the currently executing process, restore the process to another state
- Fork-exec model. Fork is a system call which duplicates a process; exec overlays the current data with a new instance. Starting a new process in linux is forking, then calling exec. Processes are assigned PIDs to keep track.

---

## 21. Processes II, Virtual Memory I
- `exec*()` - overlays current process data with new instances of the given program
- Loading part of Compiler, Assembler, Linker, Loader
- Stack, Heap, Data, Code, register values
- Where does the starting state of a new program come from? Data, code, heap, stack, registers
- A process ends/terminates by executing the return statement from main, calling the library function exit, or by aborting an exception handler. 
- Reaped - the system resources are removed
- Process terminated but not reaped - zombie process
- Parent process - responsible for reaping a child. Implicity (parent terminates) or explicitly (parent invokes `wait(pid)()` system call
- An orphaned child is passed to a background process called `init` with a PID of 1.
- Virtual memory - process abstraction of a private address space. Hides the actual amount of RAM installed on the machine.
- Virtual vs physical address space.
- Swap space: a part of the disk to temporarily hold additional memory.

---

## 22. Virtual Memory II
- Virtual memory must be able to make efficient use of limited physical memory.
- Page: $$P = 2^p$$, page size denoted in bytes.
- Physical page numbers and virtual page numbers.
- Most processes do not need to use most of the virtual address space. Unused virtual pages never have space allocated.
- Physical memory as cache
- Page tables - maps VPN to PPN
- Page table entry - valid bit, dirty bit, access rights bits
- Memory protection - protect and share memory between processes when desired. Page tables (managed by OS) do this for us.
- Access rights - mimic Linux file access perms

---

## 23. Virtual Memory III
- Page hit - if the requested page does live in physical memory.
- Page fault - the requested page is not in physical mmeory (in swap space on the disk)
- Translation lookaside buffer (TLB) - hardware cache, reduce the number of memory accesses needed during address translation
- TLB hit - page entry table found, MMU can do address translation without ever accessing the page table.
- Virtual address: first, TLB lookup
  - TLB hit: protection check
    - Access permitted: physical address
      - Check cache: miss or hit
    - Access denied: protection fault, SIGSEGV
  - TLB miss: check page table
    - Page in memory: update TLB and do protection check
    - Page not in memory: find in the swap space and do protection check
- 




























