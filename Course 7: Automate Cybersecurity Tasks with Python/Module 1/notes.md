# Course 7, Module 1 – Python Basics: Environments, Data Types, Variables, Conditionals, and Loops

## Overview

This module introduced Python fundamentals: how programming and interpreters work, the environments used to write Python (notebooks, IDEs, CLI), core data types, variables, conditional statements, and iterative statements (loops).

---

## Learning Objectives

After completing this module, I can:

- Explain how Python code is interpreted and where it's used in cybersecurity
- Compare Python environments: notebooks, IDEs, and the command line
- Identify Python's core and additional data types
- Assign, reassign, and follow naming conventions for variables
- Write conditional statements using if/elif/else and logical operators
- Write for and while loops, including break and continue

---

## Reading: Get to Know Python

### How Programming Works

**Programming** creates a specific set of instructions for a computer to execute tasks. Programming languages are ultimately converted to binary (0s and 1s) that a CPU can execute — Python makes this process far more efficient for humans to write than communicating in binary directly.

### Using Python to Program

Python is a general-purpose language usable for websites, data analysis, and task automation. Python code passes through an **interpreter**, which translates it into runnable instructions line by line. Multiple versions of Python exist (this course uses Python 3) with differing **syntax** — the rules for correctly structuring code in a given language.

### Python in Cybersecurity

Python is especially valuable for **automation** — using technology to reduce manual/repetitive effort. Common security use cases: log analysis, malware analysis, access control list management, intrusion detection, compliance checks, and network scanning.

**Key takeaway:** Python's readability and automation capabilities make it one of the most valuable languages for a security analyst to know, particularly for reducing manual, repetitive work.

---

## Reading: Python Environments

### Notebooks

An online interface for writing, storing, and running code, containing **code cells** (for writing/running code, typically with a play button to execute) and **markdown cells** (for describing code using the markdown formatting language). Common notebook environments: Jupyter Notebook and Google Colaboratory (Colab).

### Integrated Development Environments (IDEs)

Software applications for writing code that provide editing assistance and error correction, typically with a GUI offering extensive customization options.

### Command Line

A **command-line interface (CLI)** is a text-based interface for interacting with the computer. Entering commands gives access to all files/directories on the hard drive, including Python files, and lets you open a file editor to create new Python files.

**Key takeaway:** Analysts access Python through a variety of environments — this course uses notebooks specifically, which combine runnable code cells with plain-text markdown documentation.

---

## Reading: More About Data Types

A **data type** is a category for a particular type of data item. Core types covered in this course:

- **String:** An ordered sequence of characters (letters, numbers, symbols, spaces) placed in quotation marks — e.g., `"updates needed"`. An empty string is `""`.
- **List:** A collection of data in sequential form, placed in square brackets with elements separated by commas — e.g., `[12, 36, 54, 1, 7]`. Elements can be any data type, including other lists. An empty list is `[]`.
- **Integer:** A number without a decimal point (e.g., `-100`, `20`, `500`), not placed in quotation marks.
- **Float:** A number with a decimal point (e.g., `-2.2`, `0.34`), not placed in quotation marks. Dividing with `/` always returns a float; dividing with `//` rounds down to a whole number (returning an integer if both operands are integers, or a float if either is a float).
- **Boolean:** Either `True` or `False` — not placed in quotation marks. Can result from comparisons (e.g., `9 > 10` evaluates to `False`).

### Additional Data Types

- **Tuple:** A collection of data that cannot be changed after creation, placed in parentheses (e.g., `("wjaffrey", "arutley", "dkot")`) — useful when data (like software identifiers) needs to stay fixed, and more memory-efficient than lists for large datasets.
- **Dictionary:** One or more key-value pairs, with a colon between key and value, separated by commas, enclosed in curly brackets (e.g., `{1: "East", 2: "West"}`) — useful for predictable storage/retrieval.
- **Set:** An unordered collection of unique values (no duplicates), enclosed in curly brackets, elements separated by commas (e.g., `{"jlanksy", "drosas", "nmason"}`).

**Key takeaway:** String, list, integer, float, and Boolean are the core data types used throughout this course, while tuple, dictionary, and set serve more specialized purposes worth knowing as you go further.

---

## Reading: Assign and Reassign Variables in Python

A **variable** is a container that stores data, automatically assigned a data type based on its value when the code runs — like a labeled box whose contents can change while the label (variable name) stays the same.

### Assigning and Reassigning

```python
username = "nzhao"      # assign
username = "zhao2"      # reassign
```

Variables can also be assigned to other variables:

```python
username = "nzhao"
old_username = username  # old_username now holds "nzhao"
```

### Best Practices for Naming Variables

**Required syntax rules:**

- Use only letters, numbers, and underscores (e.g., `date_3`, `interval2`)
- Start with a letter or underscore, never a number
- Names are case-sensitive (`time`, `Time`, `TIME` are three different variables)
- Don't use Python's built-in keywords/functions as variable names (e.g., `True`, `if`)

**Stylistic guidelines:**

- Separate multiple words with underscores (e.g., `login_attempts`)
- Avoid similarly named variables that could be confused (e.g., `start_time` vs. `starting_time`)
- Avoid unnecessarily long names
- Use descriptive names, not random words (e.g., `num_login_attempts`, not `x`)

**Key takeaway:** Variables are reusable containers whose value can change over time — following naming conventions (syntax rules plus stylistic guidelines) keeps code both functional and readable for other analysts.

---

## Reading: More on Conditionals in Python

A **conditional statement** evaluates code to determine whether it meets specified conditions, executing associated actions when the condition is `True`.

### if Statements

```python
if status == 200:
    print("OK")
```

The header (`if <condition>:`) must end in a colon; the body must be indented consistently.

### else and elif

- **`else`:** Runs when all preceding conditions evaluate to `False`.
- **`elif`:** Checked only if the preceding condition(s) evaluated to `False`; multiple `elif` statements can chain together, and once one matches, Python skips the rest.

```python
if status == 200:
    print("OK")
elif status == 400:
    print("Bad Request")
elif status == 500:
    print("Internal Server Error")
else:
    print("check other status")
```

### Logical Operators for Multiple Conditions

- **`and`:** Both conditions must be `True` (e.g., `status >= 200 and status <= 226`).
- **`or`:** Either condition can be `True` (e.g., `status == 100 or status == 102`).
- **`not`:** Negates a condition, inverting `True`↔`False` (e.g., `not(status >= 200 and status <= 226)` — parentheses matter here, since Python evaluates the inner condition first, then applies `not` to the whole result).

**Key takeaway:** `if`/`elif`/`else` structure decision-making in code, and `and`/`or`/`not` let those decisions depend on more than one condition at a time.

---

## Reading: More on Loops in Python

An **iterative statement** repeatedly executes a set of instructions, running zero or more times depending on the criteria.

### for Loops

Iterate through a specified sequence. The **loop variable** (part of the loop header) takes on each value in the sequence in turn:

```python
for i in ["elarson", "bmoreno", "tshah", "sgilmore"]:
    print(i)
```

`for` loops can iterate through lists, strings (character by character), or a numeric sequence via `range(start, stop, increment)` — the start point is inclusive, the stop point is exclusive. If start defaults to 0 and increment defaults to 1, they can be omitted (e.g., `range(5)`).

### while Loops

Iterate based on a condition rather than a fixed sequence, continuing as long as the condition is `True`:

```python
i = 1
while i < 5:
    print(i)
    i = i + 1
```

Unlike a `for` loop, the loop variable is initialized outside the loop and must be manually updated inside the loop body — otherwise the loop can run forever. Conditions can be based on integers, Booleans, or other comparisons.

### Managing Loops: break and continue

Used inside a conditional statement within a loop body:

- **`break`:** Exits the loop entirely once the condition is met.
- **`continue`:** Skips the current iteration and moves to the next one.

### Infinite Loops

A loop that never exits (an **infinite loop**) can be stopped with `CTRL-C` or `CTRL-Z` — this can happen intentionally, e.g., when running a service that continuously processes incoming data.

**Key takeaway:** `for` loops are best for iterating a known/predetermined number of times (or through a sequence); `while` loops are best for iterating based on a condition — and `break`/`continue` give finer control over how a loop runs based on additional logic.

---

## Glossary Terms from Module 1

| Term | Definition |
|------|------------|
| Automation | The use of technology to reduce human and manual effort to perform common and repetitive tasks |
| Boolean data | Data that can only be one of two values: either True or False |
| Command-line interface | A text-based user interface that uses commands to interact with the computer |
| Comment | A note programmers make about the intention behind their code |
| Conditional statement | A statement that evaluates code to determine if it meets a specified set of conditions |
| Data type | A category for a particular type of data item |
| Dictionary data | Data that consists of one or more key-value pairs |
| Float data | Data consisting of a number with a decimal point |
| Integer data | Data consisting of a number that does not include a decimal point |
| Integrated development environment (IDE) | A software application for writing code that provides editing assistance and error correction tools |
| Interpreter | A computer program that translates Python code into runnable instructions line by line |
| Iterative statement | Code that repeatedly executes a set of instructions |
| List data | Data structure that consists of a collection of data in sequential form |
| Loop variable | A variable that is used to control the iterations of a loop |
| Notebook | An online interface for writing, storing, and running code |
| Programming | A process that can be used to create a specific set of instructions for a computer to execute tasks |
| Set data | Data that consists of an unordered collection of unique values |
| String data | Data consisting of an ordered sequence of characters |
| Syntax | The rules that determine what is correctly structured in a computing language |
| Tuple data | Data structure that consists of a collection of data that cannot be changed |
| Type error | An error that results from using the wrong data type |
| Variable | A container that stores data |

---

## Personal Reflection

Coming into this module with no real programming background, the variable-as-a-labeled-box analogy did more for my understanding than the formal definition did — it made reassignment intuitive right away. The distinction between `for` loops (known sequence) and `while` loops (condition-based) also gave me a clear decision rule I can apply going forward: am I iterating through something I already have, or am I iterating until something becomes true?
