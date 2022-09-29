---
layout: default
title: Cheat Sheet
parent: CSE 351
grand_parent: Computer Science
nav_order: 100
---

# Cheat Sheet
{: .no_toc }

CSE 351
{: .fs-6 .fw-300 }

---

This page is a quick reference of commands and information I found helpful for CSE 351.

## Copying a file from remote $$\to$$ local
Use the `scp` command in a convenient folder such as `Downloads`:
```
scp andreye@attu.cs.washington.edu:~/test/file.txt .
```
The generalized syntax for remote-to-local is:
```
scp username@server:file_to_send place_to_send
```

## Data Sizes
- A two-digit hexadecimal can be represented in a byte ($$2^8 = 256$$).
- 
