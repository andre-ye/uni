---
layout: default
title: Style Notes
parent: CSE 143
grand_parent: Computer Science
nav_order: 100
---

# Style Notes
{: .no_toc }

CSE 143
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

## Formatting
- Include a header comment with your name, section, TA, and brief description of program functionality.
- Use pre/post format. `Pre:` represents parameter specifications and requirements with exceptions noted; `Post:` represents method return or output functionality.
- No more than 80 characters per line.

---

## Commenting Language
- Say **what the method does** directly ("calculates a sum" instead of "this method calculates...").
- Write in a client-oriented manner. Avoid mentioning local variable names, private field names, loops, recursion, etc. - these concern *how* the program works.
- Explicitly write the inputs (parameters) and outputs (output or return) for a method.

---

## Naming

| Variable Type | Formatting | Example |
| --- | --- | --- |
| Class | Capitalized | `ClassName` |
| Method/Variable | camelCase | `className` |
| Class Constant | UPPER_CASE | `CLASS_CONSTANT` |

---

## Variable and Field Guidelines
- Fields should always be `private` unless stated otherwise.
- Class constants can be `public`.
- Avoid static global variables.
- **Always declare fields above their constructor, but do not initialize outside of constructor.** Instead, initialize fields inside the constructor.

---

## Miscellaneous 
- Adhere by Boolean zen.
- Make helper methods private.

---

## References
- [Official CSE 143 Java Style Guide](https://courses.cs.washington.edu/courses/cse143/22wi/homework/cse143-style-guide2/javaguide.html#s8.2-inappropriate-if-else){:target="_blank"}
- [Unofficial CSE 143 Java Style Guide](https://courses.cs.washington.edu/courses/cse143/22wi/homework/style-guide.pdf){:target="_blank"}
- [Unofficial CSE 143 Guide to Commenting](https://courses.cs.washington.edu/courses/cse143/22wi/homework/commenting-guide.pdf){:target="_blank"}

---
