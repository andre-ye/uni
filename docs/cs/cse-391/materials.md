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
- Some commands don't accept standard input - you can use `xargs` to take standard input and convert it into arguments. For instance, `xargs javac < ls *.java`.
- `find` - recursively searches all files in the current folder or with the current folder as parent.
- `$(...)` - command substitution. Command line evaluates the command first.
- `2>&1` - have standard error go to wherever standard output is.
- `tee` - prints to the console and saves to the file as well.
  - e.g. `java printer.java | tee output.txt`
- `echo` - prints to the terminal.
- `cut` - helps with indexing, e.g. `-c 4` gets the fourth character in the input.
  - `-c4-6`, `-c1,3,5`
  - Cut is usually used to break input strings by delimiters. `-d, -f2`
- Pipe operators let you get pretty far pretty quick.

---

## Week 4

### Introduction to Git
- Git - version control software.
- How to work with partners?
- Repository - a location which stores a copy of all files. What should be in a file? Source code files, build files, images, general resource files - but not executables and object files.
- Everyone working on the project has a complete version of the repository.
- Remote repository - a central repository hosted on services like GitHub
- `README.md` is the standard documentation.
- `.git` subdirectory - the 'actual' repository, manages the state of the repository for us.
- `git status` - updates us about the state of changes.
- `git stage` - get ready to take a snapshot of the repository.
- `git commit` - create a snapshot of the repository.
- `git push` - push to remote repository

### Four Phases of Git
- Phases
  1. Working directory
  2. Staging Area / Index
  3. Local repository
  4. Remote repository
- `git stage` or `git add` - move into the staging area.
- `git commit` - move from the staging area to the local repository.
- `git push` - move from the local repository to the remote repository.
- `git status` - tells us about the state of the working directory.
- `git log` - tells us about the interaction between the staging area and the local repository.
- Each commit has a unique identifier.
- What is the point of a staging area? Why use an intermediate step? Git makes us be deliberate about the changes we want to make, we have to manage the history.
- Only changes which are staged get stored into the local repository during the commit. This allows you to group many different changes and push them all at once.

### Git Practice
- Git doesn't work on files, it works on diffs - changes from one file to another.
- Commits are groups of diffs
- Just typing `git commit` will open up `vim` to provide a message - can provide a message and a longer body, too.
- `git pull` - automatically merges repositories such that the repository can be pushed.
- Git histories often aren't linear: need to be repeatedly separated and merged. These are recorded all by git.
  - `git log --decorate --all --graph`
  
---

## Week 5

### Git Branching
- Continuous integration - any time you push changes, you need to do tests before you commit to the master.
- Master - single source of truth, the history of the project. SUpposed to be stable.
- To make modifications, we need to work on a separate branch.
- Commit history
- HEAD - 'current pointer', the pointer which belongs to us, the user. We can move HEAD around from branch to branch.
- Head - pointer / reference to the current git branch.
- `git branch feature` - creates a new branch called `feature`. But it does not automatically switch branches.
- Type `git checkout feature` to switch to a branch.
- `git log` can look differently depending on where `MAIN` is pointing.
- How to reconcile different histories?

### Git Merge
- `git merge feature` - merges `feature` into the current branch. 
- Git can't fix things for you - you need to go into the files and fix the conflicts. 
- After we finish editing, we need to stage / add the files with the resolved changes.
- We need to make a commit with the conflicts resolved.
- `git log --graph --oneline` will show you the history in a visual format. 

### Git Branching: Working with Remote
- How to use branches with remote repositories?
- Origin is a way of referring to the remote repository.
- If you try to `git push` when the remote has been changed since when you last updated it, you're going to get an error.
- `git fetch` - does not change your local repository, but the origin master and origin head will be missing. Downloads copy of remote repository to a new branch.
- You can try to `git merge origin/...` and resolve the issues.
- Git is built on simple foundations.
- `git pull` is `git fetch + git merge`.

### Git Merge Requests
- In practice, we often don't merge branches locally and push to remote
- GitHub / GitLab can help us handle these.
- Steps:
  1. Create a local branch and make commits
  2. Push commits to remote
  3. Open a pull/merge request on GitLab
  4. Collaborate and fix conflicts
  5. Merge into master or another branch
- We need to be very deliberate about what we put on master
- `git checkpoint -b feature`
- Merge requests - can be handled on Gitlab.
- `git branch -d feature` removes `feature` branch from your local repository.
- 















