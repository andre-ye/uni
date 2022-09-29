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
- 











