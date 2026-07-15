# Course 4, Module 1 – Operating Systems, Request Flow, Virtualization, and CLI vs. GUI

## Overview

This module compared common operating systems and the risks of legacy OS use, walked through how a request flows from user to hardware and back, introduced virtual machines and hypervisors, and compared command-line and graphical interfaces from a security analyst's perspective.

---

## Learning Objectives

After completing this module, I can:

- Compare common operating systems and identify risks of legacy OS use
- Describe how a task moves through the user, application, OS, and hardware
- Explain virtual machines, their benefits, and how they're managed
- Compare CLI and GUI and explain why analysts favor the CLI

---

## Reading: Compare Operating Systems

### Common Operating Systems

Windows, macOS, Linux, ChromeOS, Android, and iOS are all relevant to the security industry.

- **Windows (1985) and macOS (1984):** Both widely used in personal/enterprise computing. Windows is closed source; macOS is partially open source (e.g., its kernel) with some closed-source components.
- **Linux (1991):** Completely open source, allowing community collaboration; some distributions are built specifically for security work.
- **ChromeOS (2011):** Partially open source, derived from the fully open-source Chromium OS; frequently used in education.
- **Android (2008) and iOS (2007):** Mobile operating systems used on phones/tablets/watches. Android is open source; iOS is partially open source.

### Operating Systems and Vulnerabilities

Keeping a system and its components updated is essential. A **legacy operating system** is outdated but still in use — sometimes kept around because dependent software isn't compatible with newer OS versions (common in industries using embedded software). Legacy OSes are vulnerable because they're no longer supported or patched, leaving them exposed to new threats.

**Other vulnerability resources:** Microsoft Security Response Center (MSRC), Apple Security Updates, the CVE Report for Ubuntu, and the Google Cloud Security Bulletin.

**Key takeaway:** Staying current is the primary defense, but analysts must also understand legacy OS risk since it can't always be avoided.

---

## Reading: Requests to the Operating System

### Booting the Computer

On boot, a BIOS or UEFI microchip activates. **BIOS** is older and common on legacy systems; **UEFI** replaced it around 2007 on most new computers and offers enhanced security features. Both contain loading instructions (e.g., verifying hardware health) and ultimately activate the **bootloader**, the software that boots the operating system.

### Completing a Task (Four-Part Process)

1. **User:** Initiates a task they want to accomplish.
2. **Application:** The software the user interacts with to complete the task (e.g., a calculator or word processor).
3. **Operating system:** Interprets the request and routes it to the applicable hardware.
4. **Hardware:** Does the actual processing (e.g., the CPU calculates, the hard drive saves a file) and sends output back through the OS to the application.

This is analogous to ordering food at a restaurant: you (the user) place an order (the application request), and the kitchen (the OS) does unseen work before returning what you asked for (the hardware's output).

### Example: Downloading a File from a Browser

The user clicks download → the browser communicates the action to the OS → the OS sends the request to the appropriate hardware → the hardware downloads the file and the OS relays status back to the browser, which informs the user.

**Key takeaway:** Although it operates in the background, the OS is the essential connector between applications and hardware that lets a user complete a task.

---

## Reading: Virtualization Technology

### What Is a Virtual Machine?

A virtual machine (VM) is a virtual version of a physical computer — one form of virtualization, the process of using software to create virtual representations of physical machines. A VM uses software-defined (not dedicated) hardware, meaning it's essentially code with its own virtual CPU, storage, etc. Multiple VMs can share the physical resources of a single host, each running its own OS.

### Benefits of Virtual Machines

- **Security:** VMs act as isolated "guest" environments, separated from the host and from each other — useful for containing malware infections or intentionally testing malware in a controlled space. Note: malicious code can still escape virtualization and reach the host, so VMs shouldn't be fully trusted.
- **Efficiency:** Multiple VMs can run and be switched between easily on one machine, streamlining tasks like testing/exploring applications — similar to how a city bus moves many people more efficiently than everyone driving separately.

### Managing Virtual Machines

Managed via a **hypervisor**, which connects virtual and physical hardware and allocates shared resources. **KVM (Kernel-based Virtual Machine)** is an open-source hypervisor built into the Linux kernel and supported by most major Linux distributions, usable without additional software.

### Other Forms of Virtualization

Not all virtualization involves operating systems — for example, multiple virtual servers can be created from one physical server, and virtual networks can be created to more efficiently use physical network hardware.

**Key takeaway:** Virtualization is key to the security industry, offering isolation and efficiency benefits, but virtualized systems still carry some risk of a malicious program escaping to the host.

---

## Reading: The Command Line in Use

### CLI vs. GUI

A **GUI** uses icons to manage tasks and only allows one request at a time. A **CLI** is text-based and can accept multiple requests at once.

### Advantages of a CLI in Cybersecurity

- **Efficiency:** A GUI may be easier for beginners, but a CLI is faster once you're comfortable with it and is more powerful for performing multiple tasks (e.g., creating many new files at once).
- **History file:** The Linux CLI records a history file of commands/actions, which a GUI doesn't provide by default. This is useful for verifying that playbook steps were run correctly, or for tracing an attacker's actions if a system is suspected to be compromised.

**Key takeaway:** Analysts should be comfortable with both interfaces, but the CLI's ability to handle multiple tasks simultaneously and retain a command history makes it especially valuable in security work.

---

## Glossary Terms from Module 1

| Term | Definition |
|------|------------|
| Application | A program that performs a specific task |
| Basic Input/Output System (BIOS) | A microchip that contains loading instructions for the computer and is prevalent in older systems |
| Bootloader | A software program that boots the operating system |
| Command-line interface (CLI) | A text-based user interface that uses commands to interact with the computer |
| Graphical user interface (GUI) | A user interface that uses icons on the screen to manage different tasks on the computer |
| Hardware | The physical components of a computer |
| Legacy operating system | An operating system that is outdated but still being used |
| Operating system (OS) | The interface between computer hardware and the user |
| Random Access Memory (RAM) | A hardware component used for short-term memory |
| Unified Extensible Firmware Interface (UEFI) | A microchip that contains loading instructions for the computer and replaces BIOS on more modern systems |
| User interface | A program that allows the user to control the functions of the operating system |
| Virtual machine (VM) | A virtual version of a physical computer |

---

## Personal Reflection

The restaurant analogy for the user → application → OS → hardware flow was the clearest mental model I've hit so far for what the OS actually "does" — it made an otherwise invisible process feel concrete. I also hadn't previously connected VM isolation directly to malware analysis; understanding that a VM can be deliberately infected and then reverted to a clean state reframes it as an active security tool, not just a convenience for running multiple environments.
