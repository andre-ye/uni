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

---

## Week 6 Wednesday - Caches
- Caches - firmly in the hardware side.
- IEC prefixes - unambiguously base 2.
- 512 GB really means 512 times $$10^9$$ for marketing. 
- Average memory access time (AMAT): Hit Time + Miss Rate $$\times$$ Miss Penalty
- How does execution time grow with size? We would expect a linear function, but there is a piecewise linear function. The size of the cache determines the switchpoint. 
- Moore's Law - we had exponential growth for many years - the processing process doubles roughly every 1.5 years, arguably is dead now. 
- The CPU is just one component of the overall computer.
- Memory is important - memory also improves performance exponentially over time, but at a slower rate.
- Processor-Memory performance gap: grows 50% each year.
- Registers can be accessed very quickly, but there is not very much data there.
- A single memory access can take several clock-seconds
- Cache - storage location for useful memory - obtain more than what you need and keep necessary materials nearby.
- Data will be copied in the unit of a block - contains a range of addresses.
- Hit - the desired item is in the cache. Data is returned to CPU directly: no need to involve the memory.
- Miss - the cache does not have the desired data. 
- Locality - you tend to use data and insturctions near rcecently  ussed one
- Temporal locality - recently referenced items are likely to be referenced again, for loosp, while loops.
- Spatial locality: items with nearby addresses tend to be grouped together over time, e.g. elements of an array.
- Stride - how many elements forward moving most of the time?

---

## Week 7 Monday - Caches II
- Higher up the memory hierarchy - smaller, faster, costlier per byte. 
- Caches and main memory are hardware-focused. The programmer has control over the registers.
- How to make memory access fast?
- Cache organization 
- Cache parameters - block size and cache size
- Block offset field - $$k$$ bits wide, for addresses
- Block size - $$K$$ - unit of transfer between the cache and memory. Will always be a power of 2.
  - Blocks are adjacent bytes.
  - Every byte is uniquely part of a block.
- A block size as an even power of two is a nice address split.
- How many bits do I need to represent every byte in a block?  Offset field. 
- Cache size - amount of data that the cache can store.
- Hash tables for fast loopul
- We want to use buckets well.'
- We have a limited cache capacity; we can only hold so many blocks. How to uniquely identify? Use a hashing address. Take modulus of block number.
- Lets adjacent blocks fit in the cache simultaneously - consecutive blocks go in consecutive cache indices, hypothetically, under certain conditions.
- What if there is a collision?
- The rest of the address (which does not give us the offset position) is stored as the tag. The remaining address bits - $$t$$ bits = $4m - s - k$$.
- If the tag matches, it's a hit; if not, it's a miss.
- We use every piece of the address in order to access the cache.

---

## Week 7 Wednesday - Caches III
- Lab 4 will be released, on caches
- Understanding how you as a programmer can make use of your knowledge about how caches work
- Associativity - how many sets
- Placement and replacement policies
- Direct-mapped cache: when you have a block number, it goes in only one slot in the cache.
- What if we repeatedly access in selective places which cause replacement every time in the cache? 
- How can we use the space in the cache better than in a direct-mapped cache?
- Associativity - each address maps to one set, each set can store a block in more than one way. 
  - 1-way - direct-mapped
  - Fully-associative: the entire cache is a single set.
- Associativity $$E$$: the number of ways for each set.
- There are $$(C / K) / E = S$$ cache sets.
- If we increase associativity, we need fewer index bits. A fully associative set has a zero-bit index set.
- If we decrease associativity, we need fewer tag bits.
- Any empty block in the correct set can be used to store a block - valid bit indicates whether each block has valid or mystery data.
- LRU (Least Recently Used) policy: kick out the oldest.
- We can completely describe the cache organization with the number of sets, the associativity, and the block size; everything else can be calculated off of that
- Cache line: $$K \times E \times S$$ data bytes, not including the valid bit or the tag. 
- Layers of the cache: blocks, lines, sets, cache

![image](https://user-images.githubusercontent.com/73039742/201489308-3d232883-4227-4022-a774-d45fe57507bc.png)

---

## Week 8 Monday - Caches IV
- Write-hit: data is already in the cache.
  - Write-through - write immediately to new level
  - Write-back - defer write to next level until the line is evicted. 
- Dirty bit - needed for write-backs.
- Write-miss - data is not in the cache.
  - Write allocate: load into cache, then execute write-hit policy.
  - No write allocate - write around, write immediately to next level.
- Two philosophies - you see Write-back + Write allocate (bring into cache), Write-through + No-write allocate (skip the cache); former used the most
- How to optimize for the memory hierarchy?
  - Write code which exhibits locality - spatial and temporal.
- The order in which you do your accesses in can totally change the performance.
- Medical access are expensive
- Process-Memroy exterior.
- All system,s regardlss of their parametrers, benefit from came from good code.
-  What is goodness here of an action?
-  Common case optimization - one of the foundations of computer vscience.

---

## Week 9 Monday - Processes I
- Average Memory Access Time (AMAT) - there are other cache performance metrics
- What is the consequence of choosing a specific metric? We tend to optimize the metrics we choose.
- We might be incentivized to do bizarre things for metrics at scale.
- Success is defined across metrics
- Minoritized participation in computing - what does success/participation look like here?
- How far to get people? What is optimization of some groups over others?
- Metrics are a 'heading'
- The way we define success shapes the systems we build
- Processes - caches were exclusively in the basement of hardware, now we will involve the operating system.
- How do we maintain logical consistency?
- Terminology and concepts
- Control flow - how to multiple programs run concurrently? # programs $$>$$ CPUs
- Exceptional control flow, based on the idea of an exception.  Transferring control between processes and the operating system.
- Jumps, calls - change program state. 
- But we also need to be able to change the system state.
- Exceptions, process context switch, signals
- Exception - transfer of control to the operating system (OS) kernel in response to an event.
  - kernel - memory resident of OS
- Three possibilities:
  - Execute the instruction again
  - Return to the next instruction
  - Abort process
- Exception table - structured like a jump data, but is an array of pointers to code (exception handlers).
- Lowrer exception numbers have greater agreement.
- Exception class
  - Asynchronous exception - interrupts
  - Synchronous exceptions - traps, faults, 
- Accessing files is a privileged access.
- `x64 -` syscall makes a system call. The number is passed into `%rax`.
- Every level is above the cache below it.
- Page fault - memory not in location. Need to go find.
- =- Process is an abstrc=action create a simple collection of ideas to bring into plaaau.
- process - way of running a program. Two abvstractions: dedicated logcal control machine. Each program achieves to have exclusive use of the CPUs.
- Computers ru many pointers and programs ++ hos go hd k /
- Start and end of processes
- Not all CPUs have all resources
- You can call functions in `C` tied to specific system calls, systemc alls are privileged. 
- `fork` - creating new processes. Creates a new child process identical to the calling parent, return 0 to the child process, return the child's PId to the parent process.

---

## Week 9 Friday - Processes II, VM I
- Parent and choice processes
- We cannot predict the execution order of the parent and the child.
- Changes to local variables are independent.
- Modeling fork with process graphs: a useful tool to capture partial ordering of statements in a concurrent program.
- `fork-exec` model: the child process calls `exec*`.
- `execv` takes in the path tot eh executable and any command line arguments needed.
- Calling `ls` creates a new process, for instance
- `exit(status)` - explicitly exits a process. `return` also ends a process in C.
- Zombies - a terminated process still consumes system resources. Various tables maintained by OS. No longer executing instructions but still consuming resources.
- Reaping - performed by a parent on a terminated child.
- `init` - process 1. Takes responsibility.
- `wait` - suspends the current process until one o fits children terminates
- Virtual memory: from supporting control flow to data access across multiple crosses
- VM = Virtual Memory
- Memory as we know it so far is virtual.
- Programs refer to virtual memory addresses.
- Virtual Memory: solving many problems
  1. How does everything fit?
  2. Memory management - how to decide where things go and where to find things
  3. How to protect private address space
  4. How to share memory sharing
- Indirection: referencing something using its name or container instead of the value itself. Refer to something without knowing exactly where it is.
- Indirection in virtual memory: each process has the illusion of its own virtual memory space. 
- In hardware, we have a mapping between the virtual address and the physical memory address.
- Virtual address can be mapped to physical memory or the disk.
- Disk - 'swap space'. Extra space which can be used to store the residual data. 
- DIstinguish between virtual and physical address space.
- Every byte in main memory has one physical address and any number of virtual addresses.
- 64-bit machine and 8 processes: $$2^{67}$$ bytes of address space.

---

## Week 10 Monday - VM II
- Finals are a three-day window.
- Virtual memory and virtual address space. 
- You can use physical addresses, but this is only practical if a system only runs one process at a time. For instance, refridgerators, small electronics, etc.
- Memory management unit - $$n$$ bits wide virtual address, mapped to a $$m$$ bits wide physical address
- VM allows us to efficiently use main memory.
- RAM used as a cache.
- Page - transfer unit for virtual and physical memory. This is analogous to a block in caching. 
- Page offset width - analogous to the virtual page number, block offset. 
- Physical page numbers: correspond to positions in address spaces.
- Page table entry - cache line
- Access rights - management bits
- Think of memory as an array of bytes split into pages. Pages are an aligned unit of memory.
- There will be a different number of physical and virtual pages.
- Another level below main memory - disk.
- Caching policies
- Large page size - 4-8 KiB or 2-4 MiB
- We assume fully associated: if there is any space, we want to use it.
- There are highly sophisticated replacement algorithms implemented in the Operating System
- Main memory is write-back rather than write-through, try not to change disk. Pages will also have a dirty bit. Only write back when there is a change.
- 'Thrashing' - performance meltdown, pages are swapped between memory and disk continuously.
- Page tables - tells you which page you are referring to. Lookup table to translate from VPN to PPN.
- A page table has to have an entry for every virtual page; they are very large. 
- Hangling a page fault.
- Every process has its own virtual address say, which is can view as a single linear array.
- We have to access physical memroy through a page table.
- If sharing is required, both page tables need to store the same page number.
- VM simplifies link & load.

---

## Week 10 Wednesday: Virtual Memory III
- Address translation: page hit. Processor sends a virtual address to the MMU, which retrieves the page table entry
- Page fault handling
- Translation is slow. Translation Loookaside Buffer (TLB) is a cache. Store page table entries instead of a block of data.
- TLB: maps VPNs to PPNs, stores page table entries for a small number of pages.
- A TLB hit eliminates a memory access.
- TLB misses are rare
- Fetching data: address translation.
  - If TLB hit, then we have the PPN, so go to it.
  - TLB miss, we need to check the page table.
- Then, fetch data (check cache): cache hit or cache miss.
- Address translation: virtual addresses to physical address to cache checking.
- Address manipulation: translation, different requests
- Context switching: all addresses look the same. So when is it virtual and when is it real?
- What happens when the CPU switches processes?
  - Registers are part of the process and need to be saved & loaded
  - Memory: don't need to do anything, pages are already protected from each other.
  - TLB: all entries need to be invalidated.
  - Cache: can leave this alone, since it is storing chunks of memory.

---

## Week 11 Monday
- Previously, we've talked a lot about static global data. 
- Stack-allocated data - known lifetime.
- Dynamic heap data -- the size is known only at runtime, based on user input.
  - C: `malloc`
  - Java: `new`
- Dynamic memory allocation: use dynamic memory allocators to acquire virtual memory at runtime
- Explicit allocators and implicit allocators (no need to free space)
- The allocator organizes the heap as a collection of variable-sized blocks -- allocated or free
- `brk` - indicates end of the heap.
- Need to `#include <stdlib.h>`. `void* malloc(size_t size)` - allocates a continuous block of `size` bytes and returns a pointer to the beginning of the allocated block. 
- GOod practice: use `sizeof` and cast the pointer value explicitly.  
- Freeing memory: frees a pointer. Doesn't actually remove the data, just affects what it points towards.
- Goals: maximize throughput and peak memory utilization. 
- Peak memory utilization defined as the maximum payload divided by the current heap size
- Internal fragmentation: payload is smaller than the block.
- Causes of internal fragmentation: overhead, padding purposes, policy decisions, etc.
- External fragmentation: really tricky, when an allocation pattern leaves holes between blocks. 
- Keep the length of a block in the word preceding the data -- header field. Requires an extra word for every allocated block. 
- Many different ways to keep track of free blocks - implicit and explicit free lists. 
- If blocks are aligned, low-order bits of `size` are always 0; use the lowest bit as an allocated / free flag.

---

## Week 11 Wednesday
- Implicit free list: each bloick begins with a header
- The payload needs to be 16-byte aligned.
- First fit - search list from the beginning
- Next fit - search list from the current location, loop back around if needed
- Best fit - look at the smallest fitting free space. Keeps fragmentation sutdent
- Allocating in a free block - splitting. All you have to do is to change the headers.
- Coalescing - combining free blocks by changing the header.
- Bidirectional coalescing - use boundary tags, allows us to traverse backwards. 
- Explicit free list: a linked list of free blocks. We also need a space for pointers. Assuming a doubly linked list requires now an additional 16 bytes. 
- Blocks can be in any order - no guarantees. 
- We can use preceding and following to refer to physical neighbors. 

---

## Week 11 Friday
- Struct pointers can be used to access field values.
- `examine_heap`: follows implicit free list searching algorithm.
- End of the heap has a one-word block with size zero but which still has tags.
- Trace files
- Explicit free list: more pointer management. Explicit free list navigation is much faster when most of memory is full. 
- Most common use of explicit lists - segregated free lists
- What data structure of blocks on the lists?
- You can store allocations in a row and coalesce.
- Wouldn't it be nice if we didn't have to free memory? We can use an implicit allocator.
- Garbage collection: automatically recliam heap-allocated storage. 
- C doesn't know if data is a pointer or not -- garbage memoory is difficult.
- Can the compiler leave notes in object files?
- Memory as graph: memory is a directed graph. 
- What is a pointer and what is not?
  - Memory allocator must distinguish pointers from non-pointers
  - All pointers point to the strt of a block in the heap
  - The application cannot hide pointers
- These assumptions are not fair for C, which is why C doesn't have garbage pointers.
- Mark and sweep: use an extra mark bit in the header of each block. Mark: start at roots and set mark bit. Sweep: scan all blocks and free nonmarked blocks.
- Anything that deals with options in Java is a reference -- highly constrained pointer. Java satisfies all three garbage collection requirements. 
- C* languages don't abstract away memory. Too much information to keep track of.
- Always start with bad/unexpected behavior and compare it to what you expect.
- `valgrind` - helps you analyze runtime execution.
- What about other languages? In memory-safe languages, most of these bugs are impossible. Memory leaks are still possible -- it may be possible that we have a pointer to something we still don't need.

---

## Week 12 Monday
- Reconnecting to Java -- connecting to a different environment.
- Java is specified different than C: Java is more abstract, only guaranteeing behavior.
- Data is stored around the same.
- Pointers are 'references' in Java - much more constrained than C's general pointers.
- `null` represented as `0`, but 'you can't tell'
- Arrays: we can use bounds-checking by storing the size.
- Strings not bounded by a null character; uses two-byte unicode instead of ASCII. Also stored as an array.
- `C` is not an object-oriented organizaiton: struct is the closest thing.
- Objects in Java are always accessed with references.
- Arrays are objects in Java: return a reference. 
- Type-safe casting in Java
- How are objects stored? Methods are just an array of function pointers. 
- Compiler creates the virtual method table -- a jump table for methods
- Subclassing: simply store and copy addresses to functions
- Dynamic dispatch
- Implementing programming languages: source code to binary executable. 
  - Alternative: source code, interpreter, produces interpreter binary.
  - Interpreter is its own executable. You are feeding your source file into the interpreter and figures out on the fly what the machine code here is.
  - NO need to compile on your part.
  - Python -- install interpreter, execute code one line at a time.
- 'Compiled' vs 'interpreted' language: there is nothing preventing us from going one way to the other. 
- Java compiled to bytecode, then is interpreted.
- Java process:
  1. Save java code
  2. Run Java compiler
  3. Execute on a Java Virtual Machine (interpreter for Java byte code)
- Disassembled bytecode looks very much like assembly.
- Other languages for JVMs: Jython, Clojure, Groovy, JRuby, Rhino, Scala
- Microsoft C+ and .NET: common language runtime.
























