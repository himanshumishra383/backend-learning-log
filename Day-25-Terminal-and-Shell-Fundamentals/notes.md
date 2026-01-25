# Day-25 – Terminal and Shell Fundamentals

## What Is the Terminal?
The terminal (CLI) is a text-based interface to interact directly with the operating system.

You type commands.
The system executes them.

No visuals. No distractions.
Only instructions and results.

---

## Why the Terminal Matters

### 1. Speed
- One command replaces multiple GUI actions
- Ideal for repetitive tasks

### 2. Precision
- Exact control over files, processes, and environments
- No hidden defaults

### 3. Automation
- Scripts turn manual work into repeatable workflows
- Essential for backend, DevOps, and system-level work

### 4. Universality
- Same commands work locally, on servers, and in CI pipelines
- GUIs don’t exist on most production servers

For real-world systems, the terminal is unavoidable.

---

## Understanding the Shell
The terminal runs a **shell** — a program that interprets your commands.

Common shells:
- bash
- zsh
- fish

The shell:
- Parses commands
- Executes programs
- Manages environment variables
- Handles piping and redirection

Knowing the shell = knowing how commands connect.

---

## Basic Terminal Commands (That Actually Matter)

### Navigation
```bash
pwd        # show current directory
ls         # list files
cd folder  # move into folder
cd ..      # move up one level