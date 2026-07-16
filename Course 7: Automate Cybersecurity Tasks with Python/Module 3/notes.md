# Course 7, Module 3 – Strings, Lists, and Regular Expressions

## Overview

This module covered working with strings and lists via indices, bracket notation, and their respective methods, then introduced regular expressions for pattern-matching within strings.

---

## Learning Objectives

After completing this module, I can:

- Use bracket notation and indices to extract and modify string/list data
- Apply core string methods (.upper(), .lower(), .index()) and functions (str(), len())
- Apply core list methods (.insert(), .remove(), .append(), .index())
- Build regular expression patterns and use re.findall() to search strings

---

## Reading: Strings and the Security Analyst

**String data** — an ordered sequence of characters — is one of the most common data types analysts encounter, used for data that isn't manipulated mathematically: IP addresses, usernames, URLs, employee IDs.

### Working with Indices in Strings

An **index** marks each character's position in a sequence, starting at 0 (or counting backward from -1 for the last character).

**Bracket notation:** Extracts a character or a slice using indices in square brackets:

```python
device_id = "h32rb17"
device_id[0]        # "h"
device_id[0:3]       # "h32" — a slice; the second index is excluded
```

### String Functions and Methods

- **`str()`:** Converts an object (e.g., a numeric ID) into a string, useful when you need to search/slice a value that isn't inherently string data.
- **`len()`:** Returns the number of elements in an object (e.g., verifying a device ID has exactly 7 characters).
- **`.upper()` / `.lower()`:** Return a copy of a string in all uppercase / all lowercase.
- **`.index()`:** Returns the index of the first occurrence of a character or substring; raises an error if not found, and only returns the first match if the value appears multiple times.

**Key takeaway:** Bracket notation plus these string functions/methods cover the core ways analysts will extract, verify, and search string data like device IDs, IP addresses, and usernames.

---

## Reading: Lists and the Security Analyst

**List data** — a collection of data in sequential form — lets analysts store multiple elements (usernames, IPs, URLs, device IDs) in a single variable.

### Working with Indices in Lists

Like strings, list elements are indexed starting at 0.

**Bracket notation:**

```python
username_list = ["elarson", "fgarcia", "tshah", "sgilmore"]
username_list[2]        # "tshah"
username_list[0:2]      # ["elarson", "fgarcia"] — a sublist
```

Unlike strings, lists are *not* immutable — bracket notation can also reassign an element directly: `username_list[1] = "bmoreno"`.

### List Methods

- **`.insert(index, element)`:** Inserts an element at a specific position, shifting later elements over.
- **`.remove(element)`:** Removes the first occurrence of a specified element, shifting later elements to fill the gap.
- **`.append(element)`:** Adds an element to the end of the list — often used with a `for` loop to populate an empty list one element at a time.
- **`.index(element)`:** Returns the index of the first occurrence of an element (a distinct method from the string version, despite sharing a name — methods are defined per data type).

**Key takeaway:** Lists support both extraction (bracket notation, `.index()`) and modification (`.insert()`, `.remove()`, `.append()`, direct reassignment via bracket notation) — a flexibility strings don't have, since strings are immutable.

---

## Reading: More About Regular Expressions

A **regular expression (regex)** is a sequence of characters forming a pattern, used to search strings for things like IP addresses, emails, or device IDs. Access regex via `import re`; patterns are strings passed into functions like `re.findall(pattern, string)`, which returns a list of all matches.

### Symbols for Character Types

- **`\w`:** Any alphanumeric character (plus underscore)
- **`.`:** Any character, including symbols
- **`\d`:** Any single digit `[0-9]`
- **`\s`:** Any single space
- **`\.`:** A literal period character

### Symbols to Quantify Occurrences

- **`+`:** One or more occurrences
- **`*`:** Zero or more occurrences
- **`{n}`:** Exactly `n` occurrences (e.g., `\d{2}` matches exactly two digits in a row)
- **`{n,m}`:** Between `n` and `m` occurrences (e.g., `\d{1,3}` matches one to three digits)

Note: Python scans left-to-right, matching the first expected character and continuing through the rest of the pattern before restarting; matches don't overlap.

### Constructing a Pattern

Building a regex means breaking the target string down into smaller chunks and representing each with the appropriate symbol. For example, to extract a username and login count from a string formatted like `"1001 bmoreno: 12 Marketing"`, the pattern `\w+:\s\d+` matches a variable-length word, a colon, a space, and a variable-length number — pulling out just `"bmoreno: 12"`.

Testing regex patterns is important, since they carry the risk of returning unneeded information or missing needed matches.

**Key takeaway:** Regular expressions let analysts search for patterns — not just exact strings — making them essential for extracting structured information (like usernames or login counts) out of larger, messier text.

---

## Glossary Terms from Module 3

| Term | Definition |
|------|------------|
| Algorithm | A set of rules that solve a problem |
| Bracket notation | The indices placed in square brackets |
| Debugging | The practice of identifying and fixing errors in code |
| Immutable | An object that cannot be changed after it is created and assigned a value |
| Index | A number assigned to every element in a sequence that indicates its position |
| List concatenation | The concept of combining two lists into one by placing the elements of the second list directly after the elements of the first list |
| List data | Data structure that consists of a collection of data in sequential form |
| Method | A function that belongs to a specific data type |
| Regular expression (regex) | A sequence of characters that forms a pattern |
| String concatenation | The process of joining two strings together |
| String data | Data consisting of an ordered sequence of characters |
| Substring | A continuous sequence of characters within a string |

---

## Personal Reflection

The distinction between strings being immutable and lists not being immutable was a small detail that ended up explaining a lot — it's why `.remove()`/`.append()`/`.insert()` exist for lists but strings instead rely on creating new strings via slicing and methods like `.upper()`. Regular expressions were the most conceptually demanding part of this module, but breaking a target pattern into small pieces (a word, then a colon, then a space, then digits) rather than trying to write the whole regex at once made it much more approachable.
