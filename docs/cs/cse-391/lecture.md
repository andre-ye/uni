---
layout: default
title: Lecture Notes
parent: CSE 391
grand_parent: Computer Science
nav_order: 1
---

# Lecture Notes
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

## Week 2
- Most of the tools will be in Linux and *nix systmes.
- Knowing that tools exist can help you navigate projects. 
- Unix - initially developed in 1970 at Bell Labs; many of these key ideas are still used today.
  - Everything is a file
  - Hierarchical file systems
  - Multiple users
  - Input / output streams
- macOS is a disguised unix OS.
- Linux vs Shell - shell is an interactive program which allows the user to interact with the operating system.
- Why use shells over GUIs?
  - Complicated tasks are easier on the command line
  - Useful for remote servers
  - Programmable
  - Customizable
- Bash shell will be used in this class, but there are many others.
- One dot - current directory. Two dots - parent directory.
- `/query` to search, press `n` to keep going.
- `-a` will show hidden files - things starting with a dot.
- `touch` will create a file.

---

## Week 3
- You can use `touch` to change file timestamps and to create files.
- Forward slash - helpful way to searcht rogh file.
- Sort 
- Redirect into outputs with `>`

---

## Week 4
- `uniq` only removes duplicates when they're next to each other - make sure to pipe through `sort` before `uniq`.
- Command substitution
- `stdout | tee name.txt` prints out and to a file.
- `cut` - accept delimeter and field (one-indexed)

---

## Week 5
- `git status` keeps you updated on the state of the repository.
- If you're not in a git repo, you're going to get a fatal error.
- `git add` and `git stage` do the same thing.
  - `git add .` adds everything.
- `git diff` - show differences.
  - `git diff --staged`, shows differences between current repository and the local staging area
- When you commit, you only commit to your local repository. `git commit -m "..."`.
  - Alternative: just typing `git commit` opens up the default text editor where you can type a more in-depth message.
  - When completed, save and quit.
- `git status` is focused on tracking files, `git log` is focused on tracking commits.
- `git diff --staged`

























