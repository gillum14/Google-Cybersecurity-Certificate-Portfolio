# Course 4, Module 4 – SQL Querying, Filtering, and Joins

## Overview

This module compared SQL filtering to Linux filtering, then covered core SQL querying — SELECT/FROM/ORDER BY, the WHERE clause with LIKE and wildcards, comparison operators for dates/numbers, logical operators (AND/OR/NOT), and the four types of table joins.

---

## Learning Objectives

After completing this module, I can:

- Explain when to use SQL filtering vs. Linux filtering
- Write basic SQL queries using SELECT, FROM, and ORDER BY
- Filter query results using WHERE, LIKE, wildcards, and comparison/logical operators
- Compare INNER, LEFT, RIGHT, and FULL OUTER joins

---

## Reading: SQL Filtering Versus Linux Filtering

### Accessing SQL

SQL can be accessed through many interfaces, including the Linux command line — e.g., entering `sqlite3` to access SQLite, after which command-line input is directed to SQL instead of Linux commands.

### Differences Between Linux and SQL Filtering

- **Purpose:** Linux filters data in the context of files/directories on a system (searching files, managing permissions/processes). SQL filters data within a database management system (querying/manipulating data in tables).
- **Syntax:** Linux uses various command-line tools (find, sed, cut, grep) with tool-specific syntax. SQL uses a standardized language with keywords/clauses (WHERE, SELECT, JOIN) consistent across SQL databases.
- **Structure:** SQL organizes data into columns, making it easier to select and analyze a specific field; Linux prints data as unstructured lines of text.
- **Joining tables:** SQL can join multiple tables together when returning data; Linux doesn't support connecting data to other information this way.

### Best Uses

Much cybersecurity data lives in a database format compatible with SQL, but some logs are stored as plain text and aren't SQL-compatible — in those cases, Linux filtering is the right tool.

**Key takeaway:** Linux filtering focuses on files/directories on a system, while SQL filtering focuses on structured data manipulation within databases — both matter depending on where the data lives.

---

## Reading: Query a Database

### Basic SQL Query

**SELECT** and **FROM** are the two essential keywords in any SQL query — used together to tell SQL which data to return and from which table. This module uses the **Chinook database** (sample data resembling a digital media company) for practice queries, including tables like `employees`, `customers`, and `invoices`.

- **SELECT:** Indicates which columns to return (e.g., `SELECT customerid, city`); use `SELECT *` to return all columns (not advisable on very large tables, since output can be slow/hard to read).
- **FROM:** Indicates which table to query, typically written on a new line after SELECT (e.g., `SELECT * FROM customers;`). A semicolon ends the query. Line breaks aren't required but improve readability.

### ORDER BY

Sequences returned records based on a specified column, in ascending order by default (smallest-to-largest for numbers, A-to-Z for text). Add `DESC` after `ORDER BY <column>` to sort in descending order instead. Multiple columns can be specified (e.g., `ORDER BY country, city`) — SQL sorts by the first column, then breaks ties using the second.

**Key takeaway:** SELECT and FROM are the foundation of every SQL query; ORDER BY organizes the output and supports more advanced querying skills to come.

---

## Reading: Resources for Completing SQL Labs

Covers using the Qwiklabs platform for this course's SQL labs — launching a lab, the lab control dialog (timer, Open Linux Console), checking task progress, copy/pasting into the terminal, and ending a lab properly. Includes MariaDB-specific navigation notes (e.g., `CTRL+L` to clear the screen instead of `clear`, and reconnecting to the database with `sudo mysql organization` if accidentally disconnected).

**Key takeaway:** Knowing the Qwiklabs environment and its MariaDB-specific shortcuts supports getting the most out of the course's hands-on SQL labs.

---

## Reading: The WHERE Clause and Basic Operators

### WHERE

Creates a filter condition in a query — e.g., `WHERE title = 'IT Staff'` returns only rows matching that condition, using the equals (`=`) operator.

### Filtering for Patterns

Requires a **wildcard** and the **LIKE** operator:

- **`%`:** Substitutes for any number of characters (e.g., `'a%'` matches "apple123," "art," "a").
- **`_`:** Substitutes for exactly one character (e.g., `'a_'` matches "as," "an," "a7").

**LIKE** replaces the equals sign to enable wildcard matching — e.g., `WHERE title LIKE 'IT%'` returns both "IT Staff" and "IT Manager"; `WHERE state LIKE 'N_'` returns two-character state abbreviations starting with "N" (NY, NV, NS, NT).

**Key takeaway:** WHERE filters query results to a specific condition, and combining it with LIKE and wildcards enables pattern-based filtering beyond exact matches.

---

## Reading: Operators for Filtering Dates and Numbers

Security analysts regularly work with **numeric data** (login attempt counts, data volume) and **date and time data** (timestamps, login dates, patch dates, connection duration) in addition to string data.

### Comparison Operators

| Operator | Use |
|----------|-----|
| `<` | less than |
| `>` | greater than |
| `=` | equal to |
| `<=` | less than or equal to |
| `>=` | greater than or equal to |
| `<>` (or `!=`) | not equal to |

`>` and `<` are **exclusive** (don't include the comparison value itself); `>=` and `<=` are **inclusive** (do include it).

### BETWEEN

Filters for numbers or dates within a range and is inclusive of both endpoints — e.g., `WHERE hiredate BETWEEN '2002-01-01' AND '2003-01-01'` includes records dated on either boundary date.

**Key takeaway:** Understanding exclusive vs. inclusive operators — and using BETWEEN for ranges — is essential for accurately filtering numeric and date/time data.

---

## Reading: More on Filters with AND, OR, and NOT

These are **logical operators** that refine queries to return specific, security-relevant information:

- **AND:** Requires both conditions to be true simultaneously (e.g., `WHERE supportrepid = 5 AND country = 'USA'`).
- **OR:** Requires either condition (or both) to be true (e.g., `WHERE country = 'Canada' OR country = 'USA'`) — note that even conditions on the same column must each be written out in full.
- **NOT:** Negates a single condition, returning all records that don't match it (e.g., `WHERE NOT country = 'USA'`) — more efficient than listing every other country individually. `<>` or `!=` can achieve the same result as `NOT column = value`.

Logical operators can be combined — e.g., `WHERE NOT country = 'Canada' AND NOT country = 'USA'` excludes both countries at once.

**Key takeaway:** AND, OR, and NOT — used alone or combined — let analysts build precise filters targeting the exact security-relevant records they need.

---

## Portfolio Activity Exemplar: Apply Filters to SQL Queries

A completed exemplar demonstrating how to apply the module's filtering concepts to a given scenario, including screenshots/typed queries, explanations of each query, a project description, a summary, and specific coverage of LIKE pattern-matching, date/time filtering, AND/OR for multi-condition filters, and NOT.

**Key takeaway:** The exemplar represents one possible way to complete the activity — what matters is demonstrating an understanding of how to apply SQL filters, not matching the exemplar exactly.

---

## Reading: Compare Types of Joins

### Inner Joins

`INNER JOIN` returns only rows with matching values in a specified column that exists in more than one table (plus all specified columns from the joined tables). Syntax:

```sql
SELECT *
FROM employees
INNER JOIN machines ON employees.device_id = machines.device_id;
```

The left table follows `FROM`; the right table follows `INNER JOIN`; matching columns are specified after `ON`, written as `table.column`. A column present in both tables must be qualified with its table name to specify which one to return.

### Outer Joins

Return all rows from one or both tables, in addition to matching rows.

- **LEFT JOIN:** Returns all records from the first (left) table, and only matching records from the second (right) table.
- **RIGHT JOIN:** Returns all records from the second (right) table, and only matching records from the first (left) table. Swapping table order between a LEFT JOIN and a RIGHT JOIN can produce identical results.
- **FULL OUTER JOIN:** Returns all records from both tables — effectively merging them. Table order doesn't affect the result, similar to INNER JOIN.

**Key takeaway:** INNER JOIN returns only matches; LEFT/RIGHT JOIN return all records from one specified side plus matches from the other; FULL OUTER JOIN returns everything from both tables.

---

## Glossary Terms from Module 4

| Term | Definition |
|------|------------|
| Database | An organized collection of information or data |
| Date and time data | Data representing a date and/or time |
| Exclusive operator | An operator that does not include the value of comparison |
| Filtering | Selecting data that match a certain condition |
| Foreign key | A column in a table that is a primary key in another table |
| Inclusive operator | An operator that includes the value of comparison |
| Log | A record of events that occur within an organization's systems |
| Numeric data | Data consisting of numbers |
| Operator | A symbol or keyword that represents an operation |
| Primary key | A column where every row has a unique entry |
| Query | A request for data from a database table or a combination of tables |
| Relational database | A structured database containing tables that are related to each other |
| String data | Data consisting of an ordered sequence of characters |
| SQL (Structured Query Language) | A programming language used to create, interact with, and request information from a database |
| Syntax | The rules that determine what is correctly structured in a computing language |
| Wildcard | A special character that can be substituted with any other character |

---

## Personal Reflection

Comparing SQL filtering to Linux filtering side by side clarified something I hadn't fully articulated before: it's not that one is "better," it's that they operate on fundamentally different kinds of data — structured tables vs. files/directories. The join types took a little longer to click, but visualizing LEFT vs. RIGHT as just "which table do I want everything from" made the syntax much less intimidating than it first looked.
