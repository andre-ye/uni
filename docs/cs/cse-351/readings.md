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



