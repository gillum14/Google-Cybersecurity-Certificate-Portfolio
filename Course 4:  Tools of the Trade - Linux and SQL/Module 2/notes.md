# Course 4, Module 2 – Linux Architecture, Distributions, and Package Managers

## Overview

This module covered how the Linux architecture is organized from user to hardware, additional Linux distributions beyond Kali, and how package managers handle application installation across different distributions.

---

## Learning Objectives

After completing this module, I can:

- Describe each component of the Linux architecture and how a task flows through it
- Compare common Linux distributions and their intended use cases
- Explain how package managers and package management tools work across distributions

---

## Reading: Linux Architecture Explained

A request flows from the user through applications, the shell, the Filesystem Hierarchy Standard, the kernel, and finally the hardware.

- **User:** The person interacting with the computer. Linux is multi-user, meaning multiple users can access the same resources simultaneously.
- **Applications:** Programs performing specific tasks — some pre-installed (calculators, calendars), others installed via a package manager, which helps install/manage/remove packages (pieces of software that combine to form an application).
- **Shell:** The command-line interpreter — a text-based translator between the user and the kernel, converting entered commands into instructions the computer can execute.
- **Filesystem Hierarchy Standard (FHS):** Organizes where data is stored in the OS. A directory ("folder") organizes where other files are stored; the FHS defines how directories and their contents are structured so the OS knows where to find data.
- **Kernel:** Manages processes and memory, and communicates with applications to route commands. Unique to Linux and critical for allocating system resources efficiently.
- **Hardware:** The physical components — categorized as **peripheral devices** (monitors, printers, keyboard, mouse — not core to running the system) and **internal hardware** (the motherboard and attached components):
  - **CPU:** The main processor, executing program instructions.
  - **RAM:** Short-term memory, holding data temporarily while tasks run; cleared when a program closes or the computer powers off.
  - **Hard drive:** Long-term memory, storing programs/files that persist across power cycles; a computer can have multiple hard drives.

**Key takeaway:** Understanding how the user, applications, shell, FHS, kernel, and hardware are organized makes it easier to understand how the Linux system as a whole functions.

---

## Reading: More Linux Distributions

- **Kali Linux:** An open-source, Debian-based distribution widely used in security, pre-installed with tools for penetration testing and digital forensics (collecting/analyzing data to determine what happened after an attack).
- **Ubuntu:** An open-source, user-friendly, Debian-derived distribution with both CLI and GUI, widely used across industries — including cloud computing — with a large community resource base and downloadable security-focused tools via its package manager.
- **Parrot:** An open-source, Debian-based distribution similar to Kali, pre-installed with penetration testing/digital forensics tools, with a GUI many find easy to navigate.
- **Red Hat Enterprise Linux:** A subscription-based (not free) distribution built for enterprise use, offering dedicated vendor support.
- **CentOS:** An open-source distribution closely related to Red Hat, using Red Hat's published source code but supported by the community rather than a dedicated support team.

**Key takeaway:** Kali, Ubuntu, Parrot, Red Hat, and CentOS are all widely used Linux distributions that a security analyst is likely to encounter.

---

## Reading: Package Managers for Installing Applications

A package is a piece of software (sometimes large enough to be an application on its own) that combines with others to form an application, containing the files — including dependencies — necessary for installation. Package managers help resolve dependency issues and perform other management tasks; using the most recent package version keeps bug fixes and security patches current.

### Types of Package Managers

Distributions trace back to a parent: Kali, Ubuntu, and Parrot derive from Debian; CentOS derives from Red Hat. This matters because certain package managers pair with certain distributions:

- **RPM (Red Hat Package Manager):** Used with Red Hat-derived distributions; files use the `.rpm` extension.
- **dpkg:** Used with Debian-derived distributions; files use the `.deb` extension.

### Package Management Tools

Tools that make working with packages easier through the shell:

- **APT (Advanced Package Tool):** Used with Debian-derived distributions to manage, search, and install packages via the CLI.
- **YUM (Yellowdog Updater Modified):** Used with Red Hat-derived distributions to manage, search, and install `.rpm` packages via the CLI.

**Key takeaway:** Debian-derived distributions pair with dpkg/APT, while Red Hat-derived distributions pair with RPM/YUM — knowing a distribution's lineage tells you which package manager and tools apply.

---

## Reading: Resources for Completing Linux Labs

Covers how to use the Qwiklabs platform for this course's hands-on labs — launching a lab, using the lab control dialog (timer, Open Linux Console), checking task progress, copy/pasting commands into the terminal, and ending a lab properly to avoid losing work. Also includes helpful terminal navigation shortcuts (e.g., `CTRL+C` to terminate a running command, `CTRL+L`/`clear` to clear the screen, arrow keys to navigate/recall command history, `Tab` for autocomplete).

**Key takeaway:** Knowing how to navigate the Qwiklabs environment supports getting the most out of the course's hands-on practice labs.

---

## Reading: Lab Tips and Troubleshooting Steps

Covers browser compatibility (use an updated Chrome, Firefox, or Edge; clear cache/cookies or use incognito mode if issues arise) and internet connection stability as the two most common sources of lab problems. Troubleshooting steps: confirm a supported/updated browser, clear cache/cookies or use incognito mode, check/restart the internet connection, restart the lab, and — for Qwiklabs specifically — submit a support form if a quota issue persists.

**Key takeaway:** Most Qwiklabs/Jupyter Notebook issues trace back to an outdated browser or an unstable connection, and there's a clear troubleshooting order to work through before escalating to support.

---

## Glossary Terms from Module 2

| Term | Definition |
|------|------------|
| Application | A program that performs a specific task |
| Bash | The default shell in most Linux distributions |
| CentOS | An open-source distribution that is closely related to Red Hat |
| Central Processing Unit (CPU) | A computer's main processor, which is used to perform general computing tasks on a computer |
| Command | An instruction telling the computer to do something |
| Digital forensics | The practice of collecting and analyzing data to determine what has happened after an attack |
| Directory | A file that organizes where other files are stored |
| Distributions | The different versions of Linux |
| File path | The location of a file or directory |
| Filesystem Hierarchy Standard (FHS) | The component of the Linux OS that organizes data |
| Graphical user interface (GUI) | A user interface that uses icons on the screen to manage different tasks on the computer |
| Hard drive | A hardware component used for long-term memory |
| Hardware | The physical components of a computer |
| Internal hardware | The components required to run the computer |
| Kali Linux | An open-source distribution of Linux that is widely used in the security industry |
| Kernel | The component of the Linux OS that manages processes and memory |
| Linux | An open source operating system |
| Package | A piece of software that can be combined with other packages to form an application |
| Package manager | A tool that helps users install, manage, and remove packages or applications |
| Parrot | An open-source distribution that is commonly used for security |
| Penetration test (pen test) | A simulated attack that helps identify vulnerabilities in systems, networks, websites, applications, and processes |
| Peripheral devices | Hardware components that are attached and controlled by the computer system |
| Random Access Memory (RAM) | A hardware component used for short-term memory |
| Red Hat Enterprise Linux (Red Hat) | A subscription-based distribution of Linux built for enterprise use |
| Shell | The command-line interpreter |
| Standard error | An error message returned by the OS through the shell |
| Standard input | Information received by the OS via the command line |
| Standard output | Information returned by the OS through the shell |
| String data | Data consisting of an ordered sequence of characters |
| Ubuntu | An open-source, user-friendly distribution that is widely used in security and other industries |
| User | The person interacting with a computer |

---

## Personal Reflection

Tracing the Debian and Red Hat "family trees" of distributions (Kali/Ubuntu/Parrot vs. CentOS) made package managers click for me — instead of memorizing dpkg/APT and RPM/YUM as arbitrary pairings, I can now reason about which tools apply just by knowing a distribution's lineage. The Linux architecture breakdown (user → application → shell → FHS → kernel → hardware) was also a helpful complement to the general OS request-flow from the last module, since it's the same idea but with Linux-specific components named at each stage.
