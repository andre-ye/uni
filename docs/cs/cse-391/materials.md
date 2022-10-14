---
layout: default
title: Material Notes
parent: CSE 391
grand_parent: Computer Science
nav_order: 2
---

# Materials Notes
{: .no_toc }

CSE 391
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

## Week 1

### Introduction to Linux
- Linux - another operating system, another way to interact with the computer.
- CS department has servers which can be remotely accessed with `ssh`.
- Virtual machine - put an OS within your OS.

### Flags, Arguments, and Editors
- `ls -l`: contains a flag or an option `l` which provides arguments. Long-listing format.
- Command: the command name, flags, then arguments. Flags provide optional specifications.
- `man`: pull up the manual.
  - Forward slash: can search for a word, e.g. `/long` - press `n` to cycle through the matches.
- `-a` command: do not ignore hidden files `.*`.
- Every directory has `.` and `..`: references to the current directory and the previous parent directory.
- `cd` brings you back to your home directory.

---

## Week 2

### More Unix Commands
- `cat` - print out contents to the file. It's limited to a buffer size, though
- `less filename` opens up a scrollable interface with very similar keybindings to `vim`.
- `more filename` - similar to `less`
- `head` - see the beginning of the file. Specify `-n` flag. `tail` - see the end.
- `wc` - word count
- `sort` - outputs a sorted version of the file argument
- `grep re_exp filea fileb` - performs regular expression matching on files
  - You can also specify a directory in lieu of files: `grep re_exp project/*`.
- How to run Java in the command line? Compile with `javac file.java`, then run with `java file`. `java file.java` will compile and run simultaneously.

### Input Output Redirection
- Three streams (abstracted locations): `stdin`, `stdout`, `stderr`. 
- A program accepts `stdin` and outputs to `stdout` and `stderr`.
- You can redirect `stdout` into other areas.
- You can direct `stdin` into programs.
- Ise `2>` to redirect both `stdout` and `stderr`.
- Distinguish between `stdin` and parameters.
- If no file is provided, programs will read from `stdin`.
- To append to a file, use the double wakka: `>>`.

### Pipes
- Pipes allow you to chain together commands `|`. It takes `stdout` from the left argument and puts it as `stdin` into the right argument.
- Unix philosophy - do one thing and do it well.
- You can impose repeated conditions by chaining.
- `uniq` - prints the number of repeated lines
- `sort` - sorts a file by lines
- Log file - stores progress on a file.

---

## Week 3

### I/O Redirection, xargs
- `&&` can be used to chain together commands in which commands are executed only if the previous command does not raise an error.
- `||` will only execute if the previous command fails.
- `;` - chain together commands regardless of failure or correctness.  

Left off at 8:30













