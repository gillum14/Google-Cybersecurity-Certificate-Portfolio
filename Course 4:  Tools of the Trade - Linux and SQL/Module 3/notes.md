# Course 4, Module 3 – Linux Navigation, Filtering, File Management, Permissions, and Sudo

## Overview

This module covered navigating the Linux file system and reading file content, filtering for specific information, managing directories and files, working with permissions and the principle of least privilege, responsible use of sudo for authentication/authorization tasks, and Linux community/support resources.

---

## Learning Objectives

After completing this module, I can:

- Navigate the Linux file system and read file content using core commands
- Filter for specific information using grep, piping, and find
- Create, modify, and remove directories and files
- Read and change file/directory permissions in line with least privilege
- Use sudo responsibly for authentication and authorization tasks
- Use Linux's built-in and community support resources

---

## Reading: Navigate Linux and Read File Content

### Filesystem Hierarchy Standard (FHS) Structure

The FHS organizes data under a **root directory** (`/`), from which all subdirectories branch. A file's location is described by its **file path**. Standard FHS directories include `/home` (each user's own directory), `/bin` (binary/executable files), `/etc` (system configuration files), `/tmp` (temporary files — commonly targeted by attackers since anyone in the system can modify them), and `/mnt` (mounted media like USB/hard drives). `man hier` provides more detail on the FHS.

Under `/home`, each user has personal subdirectories; a user's home directory can be shortened using `~` (e.g., `/home/analyst/logs` = `~/logs`). An **absolute file path** starts from root (e.g., `/home/analyst/projects`); a **relative file path** starts from the current directory, using `.` for the current directory or `..` for its parent.

### Navigation Commands

- **`pwd`:** Prints the working (current) directory's absolute path. `whoami` returns the current username.
- **`ls`:** Lists files/directories in the current directory; add a path argument to list a different directory's contents.
- **`cd`:** Changes directories — to a subdirectory name, an absolute path, or `cd ..` to move up one level.

### Reading File Content Commands

- **`cat`:** Displays a file's full content.
- **`head`:** Displays the first 10 lines by default (use `-n` to specify a different number, e.g., `head -n 5`).
- **`tail`:** Displays the last 10 lines by default — useful for reading the most recent entries in a log file.
- **`less`:** Displays content one page at a time, navigable with space bar (forward), `b` (back), arrow keys (line by line), and `q` (quit).

**Key takeaway:** `pwd`, `ls`, and `cd` are the core navigation commands, while `cat`, `head`, `tail`, and `less` are the core commands for reading file content.

---

## Reading: Filter Content in Linux

Filtering means selecting data that matches a certain condition — for example, isolating files affected by a specific virus, or filtering by file extension or a text string.

### grep

Searches a specified file and returns all lines containing a specified string, taking two arguments: the string to search for and the file to search. Example: `grep error time_logs.txt` returns all lines containing "error."

### Piping

Accessed via the pipe character (`|`), located on the same key as backslash on many keyboards. Sends the standard output of one command as standard input to another, for further processing. Example: `ls /home/analyst/reports | grep users` lists file/directory names in `reports` containing "users." Piping is a general redirection tool usable for tasks beyond filtering.

### find

Searches for directories/files meeting specified criteria (name pattern, file size, last-modified time). The first argument after `find` indicates where to start searching; without a specific criterion, results can be extensive. Options modify a command's behavior and typically begin with a hyphen.

- **`-name` / `-iname`:** Match a string in a file/directory name, in quotes; `-name` is case-sensitive, `-iname` is not. `*` is a wildcard for zero or more unknown characters (e.g., `find /home/analyst/projects -iname "*log*"`).
- **`-mtime`:** Finds files modified within a time frame in days (e.g., `-mtime -3` = modified within the last 3 days; `+1` = more than one day ago; `-1` = less than one day ago). `-mmin` performs the same search based on minutes instead of days.

**Key takeaway:** grep, piping, and find are key commands for customizing data to an analyst's needs while navigating and filtering the file system.

---

## Reading: Manage Directories and Files

### Creating and Modifying Directories

- **`mkdir`:** Creates a new directory (via absolute or relative path).
- **`rmdir`:** Removes an empty directory; cannot delete a directory containing files or subdirectories.

### Creating and Modifying Files

- **`touch`:** Creates a new, empty file.
- **`rm`:** Removes (deletes) a file — used carefully, since deleted files are not easily recovered.
- **`mv`:** Moves a file/directory to a new location (removing it from the original location); can also rename a file by passing a new name as the second argument instead of a new location.
- **`cp`:** Copies a file/directory to a new location while keeping the original in place.

### nano Text Editor

A command-line file editor available by default in many Linux distributions, widely used in security for creating/editing files. Open or create a file with `nano <filename>`. Since nano doesn't auto-save, use `Ctrl+O` to save and `Ctrl+X` to exit. Vim and Emacs are other popular CLI text editors.

### Standard Output Redirection

Beyond piping (`|`), the `>` and `>>` operators redirect standard output when used with `echo`. `>` **overwrites** the existing file's contents (used carefully — not easily recoverable); `>>` **appends** to the end of the file without overwriting. Both operators create a new file if one doesn't already exist with the specified name.

**Key takeaway:** `mkdir`, `rmdir`, `touch`, `rm`, `mv`, and `cp` cover core file/directory management, while nano and the `>`/`>>` operators cover writing to files directly.

---

## Reading: Permission Commands

### Reading Permissions

Linux permissions are represented as a 10-character string. Permissions are **read** (view file contents / list directory contents), **write** (modify file contents / create new files in a directory), and **execute** (run a program file / enter a directory and access its files) — granted to three owner types: **user** (file owner), **group** (a larger group the owner belongs to), and **other** (all other system users).

The string breaks down as: character 1 = file type (`d` for directory, `-` for a regular file); characters 2–4 = user's read/write/execute (`r`/`w`/`x` or `-`); characters 5–7 = group's read/write/execute; characters 8–10 = other's read/write/execute.

### Exploring Existing Permissions

- **`ls -a`:** Displays hidden files (starting with `.`).
- **`ls -l`:** Displays permissions plus owner name, group, file size, and last modification time.
- **`ls -la`:** Combines both — permissions for all files, including hidden ones.

### Changing Permissions with chmod

The **principle of least privilege** means granting only the minimal access needed to complete a task. `chmod` takes two arguments: how to change permissions, and the file/directory to change.

- Add permissions: `chmod u+rwx,g+rwx,o+rwx login_sessions.txt`
- Remove permissions: `chmod u-rwx,g-rwx,o-rwx login_sessions.txt`
- Set permissions exactly (overwriting existing ones): `chmod u=r,g=r,o=r login_sessions.txt`

Character meanings: `u` (user), `g` (group), `o` (other), `+` (add), `-` (remove), `=` (assign exactly). Multiple owner-type changes are separated by commas with no spaces.

**Example — principle of least privilege in action:** A file `bonuses.txt` (owned by an HR employee) has group permissions `-rw-rw----`, meaning the whole HR group can read/write it — but only the owner should have access. Running `chmod g-rw bonuses.txt` removes the group's read/write access, restricting the file to just the person who needs it.

**Key takeaway:** `ls -l`/`ls -la` reveal current permissions, and `chmod` lets you bring them in line with the principle of least privilege.

---

## Reading: Responsible Use of Sudo

### Responsible Use of Sudo

Managing authorization/authentication requires root user ("super user") privileges. Logging in directly as root is discouraged in Linux — it creates risk if the account is compromised, makes irreversible mistakes easier, and the system can't track who ran a command. Instead, the `sudo` command ("super user do") temporarily grants elevated permissions to specific users listed in the sudoers configuration file. Even authorized sudo users carry more risk in the event of an attack, so it's best practice to use sudo only for the specific commands needed — not broadly — and to be cautious about running sudo commands copied from online sources.

### Authentication and Authorization Commands

- **`useradd`:** Adds a user (e.g., `sudo useradd fgarcia`). `-g` sets a primary group; `-G` adds supplemental/secondary groups (comma-separated for multiple).
- **`usermod`:** Modifies an existing user account. `-g` changes the primary group; `-G` (with `-a` to append rather than replace) adds a supplemental group without removing existing ones. Other options: `-d` (change home directory), `-l` (change login name), `-L` (lock the account so the user can't log in — useful instead of deleting a departed employee's account, to retain visibility into their files/permissions).
- **`userdel`:** Deletes a user (e.g., `sudo userdel fgarcia`). Does not delete the user's home directory files unless `-r` is used — back up first if needed.
- **`chown`:** Changes user or group ownership of a file/directory (e.g., `sudo chown fgarcia access.txt` for user ownership, `sudo chown :security access.txt` for group ownership — note the colon before the group name).

**Key takeaway:** Authentication verifies who someone is; authorization determines what they can access. `sudo` lets analysts perform authentication/authorization management tasks (`useradd`, `usermod`, `userdel`, `chown`) with elevated privileges only when needed, rather than logging in as root.

---

## Reading: Linux Resources

### Linux Community

The UNIX and Linux Stack Exchange is a trusted question-and-answer resource, with community voting surfacing higher-quality answers — useful for troubleshooting and learning from more advanced users.

### Integrated Linux Support Commands

- **`man`:** Displays detailed information ("man page") on a command, e.g., `man chown`.
- **`apropos`:** Searches man page descriptions for a keyword; the `-a` option searches for multiple words (e.g., `apropos -a graph editor`).
- **`whatis`:** Displays a one-line description of a command — useful as a quick reminder or after discovering a new command.

**Key takeaway:** Between the large online Linux community and built-in commands like `man`, `apropos`, and `whatis`, there are always resources available for troubleshooting or learning more as you continue using Linux.

---

## Glossary Terms from Module 3

| Term | Definition |
|------|------------|
| Absolute file path | The full file path, which starts from the root |
| Argument (Linux) | Specific information needed by a command |
| Authentication | The process of verifying who someone is |
| Authorization | The concept of granting access to specific resources in a system |
| Bash | The default shell in most Linux distributions |
| Command | An instruction telling the computer to do something |
| File path | The location of a file or directory |
| Filesystem Hierarchy Standard (FHS) | The component of the Linux OS that organizes data |
| Filtering | Selecting data that match a certain condition |
| nano | A command-line file editor that is available by default in many Linux distributions |
| Options | Input that modifies the behavior of a command |
| Permissions | The type of access granted for a file or directory |
| Principle of least privilege | The concept of granting only the minimal access and authorization required to complete a task or function |
| Relative file path | A file path that starts from the user's current directory |
| Root directory | The highest-level directory in Linux |
| Root user (or superuser) | A user with elevated privileges to modify the system |
| Standard input | Information received by the OS via the command line |
| Standard output | Information returned by the OS through the shell |

---

## Personal Reflection

The HR bonuses.txt example made the principle of least privilege feel like a real, everyday task rather than an abstract policy — `chmod g-rw` is a small, specific action with a clear rationale. I also appreciated the emphasis on why `sudo` is preferred over logging in as root: it's not just a convention, it's about limiting blast radius and keeping an accountability trail if something goes wrong. That mindset — default to the least access necessary, and be deliberate about when to escalate — feels like it'll come up constantly in this field.
