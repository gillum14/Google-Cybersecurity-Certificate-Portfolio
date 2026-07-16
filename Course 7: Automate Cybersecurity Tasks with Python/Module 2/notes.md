# Course 7, Module 2 – Functions, Built-in Functions, Modules/Libraries, and Style

## Overview

This module covered defining and calling functions, parameters/arguments/return statements, global vs. local variables, key built-in functions, importing modules and libraries, and following the PEP 8 style guide for readable, correctly formatted code.

---

## Learning Objectives

After completing this module, I can:

- Define and call user-defined functions and explain their value for automation
- Differentiate parameters, arguments, and return statements
- Differentiate global and local variables and avoid common pitfalls
- Use built-in functions: print(), type(), max(), min(), sorted()
- Import modules from the Python Standard Library and external libraries
- Apply PEP 8 conventions for comments, indentation, and syntax

---

## Reading: Python Functions in Cybersecurity

A **function** is a section of reusable code, valuable because it automates repetitive parts of a program. In cybersecurity, functions are especially useful for processes analysts repeat often — e.g., a function that takes a log as input and returns potentially malicious logins, reusable across multiple logs.

### Defining a Function

Requires a **function header** and a **function body**:

```python
def display_investigation_message():
    print("investigate activity")
```

The `def` keyword starts the definition, followed by the function name, parentheses, and a colon; the indented body follows. Pro tip: name functions to indicate what they do.

### Calling a Function

Using a function after defining it — write its name followed by parentheses:

```python
display_investigation_message()
```

Note: calling a function from inside its own definition without a stopping condition creates an infinite loop.

**Key takeaway:** Defining a function once and calling it wherever needed avoids duplicating the same code throughout a program — especially valuable given how often security processes repeat.

---

## Reading: Functions and Variables

### Parameters and Arguments

- **Parameter:** A variable included in a function's definition, for use within that function (e.g., `maximum_attempts` and `total_attempts` in a function header).
- **Argument:** The actual data passed into a function when it's called (e.g., the values `3` and `2` passed into `remaining_login_attempts(3, 2)`), which pass into the parameters by position.

### Return Statements

The `return` keyword sends information back from a function — placed before the value/expression to return, with no parentheses needed since it's a keyword, not a function:

```python
def remaining_login_attempts(maximum_attempts, total_attempts):
    return maximum_attempts - total_attempts
```

The returned value can be stored in a variable for later use (e.g., in a conditional). Once Python hits a `return` statement, it exits the function immediately — any code after it in that function won't run.

### Global and Local Variables

- **Global variable:** Assigned outside a function, accessible throughout the entire program.
- **Local variable:** Assigned inside a function (including parameters) — only accessible within that function; created temporarily when the function runs and deleted from memory afterward.

**Best practice:** Avoid reusing a variable name as both a global and a local variable — doing so creates two separate variables with the same name and different values, which can cause confusing bugs. Passing values into a function via a parameter (rather than relying on a global variable) is the better approach when a function needs to handle different input values.

**Key takeaway:** Parameters/arguments control what data flows into a function, `return` controls what flows back out, and keeping global and local variable names distinct avoids subtle, hard-to-diagnose bugs.

---

## Reading: Work with Built-in Functions

**Built-in functions** exist within Python and can be called directly, without being defined first.

- **`print()`:** Outputs specified object(s) to the screen; accepts any number of comma-separated arguments.
- **`type()`:** Returns the data type of its single argument — useful for tracking variable types and avoiding errors. Often nested inside `print()` to display the result (e.g., `print(type("This is a string"))` → `str`).
- **`max()` / `min()`:** Return the largest/smallest numeric value from multiple arguments or an iterable (e.g., a list) — e.g., finding a user's longest/shortest login session from a list of session times.
- **`sorted()`:** Sorts the elements of an iterable (list, string, etc.) and returns them as a new list, in ascending order by default (smallest-to-largest numbers, or A-to-Z strings). Does not modify the original iterable, and cannot sort a list/string with mixed data types.

**Key takeaway:** These built-in functions cover common, everyday needs — printing output, checking types, finding extremes, and sorting — without requiring any custom function definitions.

---

## Reading: Import Modules and Libraries in Python

A **module** is a Python file containing additional functions/variables/classes/runnable code; a **library** is a collection of modules providing reusable code.

### The Python Standard Library

An extensive collection of modules that typically ships with Python, including `re` (pattern searching), `csv`, `glob`/`os` (command-line interaction), `time`/`datetime` (timestamps), and `statistics` — which includes `mean()` (average) and `median()` (middle value) for numeric data.

### Importing Modules

- **Import an entire module:** `import statistics` — then call functions with the module name prefix, e.g., `statistics.mean(...)`.
- **Import specific functions:** `from statistics import mean, median` — then call the functions directly without the module prefix, e.g., `mean(...)`.

### External Libraries

Libraries like Beautiful Soup (`bs4`, for parsing HTML) and NumPy (`numpy`, for arrays/math) must first be installed (e.g., `%pip install numpy` in a notebook), then imported with the same `import` keyword used for Standard Library modules.

**Key takeaway:** The Python Standard Library covers a lot of common analyst needs out of the box, and external libraries extend Python's capabilities further — both are accessed via `import`, with syntax varying slightly depending on whether you need a whole module or just specific functions from it.

---

## Reading: Ensure Proper Syntax and Readability in Python

### Comments

A **comment** explains the intent behind code, starting with `#` for a single line. Per PEP 8, lines (including comments) should stay under 79 characters. **Multi-line comments** either repeat `#` across multiple lines, or use triple-quoted **documentation strings (docstrings)** (`""" ... """`) without assigning them to a variable. Comments are especially important for more complex code (functions, multiple loops/conditionals) and optional for simpler code (a single variable reassignment).

### Correct Indentation

**Indentation** (space at the start of a line) is required for the body of conditionals, loops, and function definitions — both for Python to interpret the code correctly and for readability. PEP 8 recommends 4 spaces per indentation level; nested structures (e.g., a conditional inside a loop) stack indentation accordingly.

### Maintaining Correct Syntax

Common syntax pitfalls:

- **Data types:** Strings need quotation marks; integers/floats/Booleans don't; lists need brackets with comma-separated elements.
- **Colons in headers:** The header of a conditional, loop, or function definition must end in a colon (`:`).

**Key takeaway:** The PEP 8 style guide's recommendations around comments and indentation aren't just stylistic preference — correct indentation is required for code to run at all, and clear comments make code readable for you and other analysts down the line.

---

## Glossary Terms from Module 2

| Term | Definition |
|------|------------|
| Argument (Python) | The data brought into a function when it is called |
| Built-in function | A function that exists within Python and can be called directly |
| Comment | A note programmers make about the intention behind their code |
| Function | A section of code that can be reused in a program |
| Global variable | A variable that is available through the entire program |
| Indentation | Space added at the beginning of a line of code |
| Library | A collection of modules that provide code users can access in their programs |
| Local variable | A variable assigned within a function |
| Module | A Python file that contains additional functions, variables, classes, and any kind of runnable code |
| Parameter (Python) | An object that is included in a function definition for use in that function |
| PEP 8 style guide | A resource that provides stylistic guidelines for programmers working in Python |
| Python Standard Library | An extensive collection of Python code that often comes packaged with Python |
| Return statement | A Python statement that executes inside a function and sends information back to the function call |
| Style guide | A manual that informs the writing, formatting, and design of documents |
| User-defined function | A function that programmers design for their specific needs |

---

## Personal Reflection

The global-vs-local variable naming pitfall was the part of this module I'll most likely trip over in practice — the idea that reusing a name inside a function quietly creates a second, separate variable (rather than an error) feels like exactly the kind of bug that's confusing to debug later. Learning `import` syntax for both the Standard Library and external libraries also made Python feel less like a closed toolset and more like something I can keep extending as I pick up new libraries relevant to security work.
