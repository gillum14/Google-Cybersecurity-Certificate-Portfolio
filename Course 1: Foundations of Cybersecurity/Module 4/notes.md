# Course 1, Module 4 – Tools, Operating Systems, and Managing Common Threats

## Overview

This module introduced the programming languages, operating systems, and tools used by entry-level security analysts, then covered how to manage common threats, risks, and vulnerabilities to business operations.

---

## Learning Objectives

After completing this module, I can:

- Describe how programming and operating systems support security work
- Identify common tools analysts use, including antivirus software, IDS, encryption, and pen testing
- Explain risk management strategies and frameworks
- Identify today's most common threats, risks, and vulnerabilities

---

## Reading: Use Tools to Protect Business Operations

### Programming

Programming creates instructions for a computer to execute tasks. Security analysts use languages like Python for automation — using technology to reduce manual effort on repetitive tasks and reduce human error. SQL is used to create, interact with, and request information from a database.

### Operating Systems

An operating system is the interface between computer hardware and the user. Linux, macOS, and Windows each offer different functionality. Linux is open source and uses a command-line interface, where commands are entered to instruct the computer.

### Other Tools

- **Web vulnerability:** A flaw in a web application that a threat actor could exploit for unauthorized access, data theft, or malware deployment. The OWASP Top 10 tracks the most critical web application risks.
- **Antivirus software:** Prevents, detects, and eliminates malware and viruses, sometimes by scanning device memory for malware patterns.
- **Intrusion detection system (IDS):** Monitors system activity and alerts on possible intrusions by scanning and analyzing network packets.
- **Encryption:** Converts data from a readable (plaintext) format to a cryptographically encoded (ciphertext) format to ensure confidentiality. Distinct from encoding, which uses a public conversion algorithm to let systems share information.
- **Penetration testing:** A simulated attack that identifies vulnerabilities in systems, networks, websites, applications, and processes — a thorough risk assessment of external and internal threats.

**Key takeaway:** Every organization uses its own set of tools, so the more tools an analyst knows, the more valuable they are — tools help analysts complete tasks more efficiently and effectively.

---

## Reading: Manage Common Threats, Risks, and Vulnerabilities

### Risk Management

A primary organizational goal is protecting assets — digital (SSNs, dates of birth, bank account numbers, mailing addresses) and physical (payment kiosks, servers, desktop computers, office spaces). Risk management strategies include:

- **Acceptance:** Accepting a risk to avoid disrupting business continuity
- **Avoidance:** Creating a plan to avoid the risk altogether
- **Transference:** Transferring risk to a third party to manage
- **Mitigation:** Lessening the impact of a known risk

Frameworks like NIST RMF and HITRUST help formalize these processes.

### Threats

Any circumstance or event that can negatively impact assets. Common types include insider threats (staff/vendors abusing authorized access) and advanced persistent threats (APTs — unauthorized access maintained over an extended period).

### Risks

Anything that can impact confidentiality, integrity, or availability of an asset — risk equals the likelihood of a threat occurring. Factors affecting likelihood include external risk, internal risk, legacy systems, multiparty risk (third-party vendor access to IP), and software compliance/licensing gaps. OWASP's Top 10 tracks the most critical web application risks and is updated regularly to reflect the evolving threat landscape.

### Vulnerabilities

Weaknesses that can be exploited by a threat. Notable examples covered:

- **ProxyLogon:** A pre-authenticated vulnerability affecting Microsoft Exchange server, allowing remote malicious code deployment.
- **ZeroLogon:** A vulnerability in Microsoft's Netlogon authentication protocol.
- **Log4Shell:** Allows attackers to run Java code remotely or leak sensitive information via internet-connected devices.
- **PetitPotam:** Affects Windows NTLM, allowing a LAN-based attacker to initiate an authentication request.
- **Security logging and monitoring failures:** Insufficient logging/monitoring lets attackers exploit vulnerabilities undetected.
- **Server-side request forgery (SSRF):** Allows attackers to manipulate a server-side application into accessing or updating backend resources, or stealing data.

Vulnerability management — monitoring systems to identify and mitigate vulnerabilities — is critical, since patches that exist but aren't applied still leave systems exposed. The NIST National Vulnerability Database and CISA Known Exploited Vulnerabilities Catalog are useful resources.

**Key takeaway:** Risk management strategies and frameworks help develop organization-wide policies to mitigate threats, risks, and vulnerabilities. Understanding today's most common ones better prepares analysts to protect organizations and the people they serve.

---

## Glossary Terms from Module 4

| Term | Definition |
|------|------------|
| Antivirus software | A software program used to prevent, detect, and eliminate malware and viruses |
| Database | An organized collection of information or data |
| Data point | A specific piece of information |
| Intrusion detection system (IDS) | An application that monitors system activity and alerts on possible intrusions |
| Linux | An open-source operating system |
| Log | A record of events that occur within an organization's systems |
| Network protocol analyzer (packet sniffer) | A tool designed to capture and analyze data traffic within a network |
| Order of volatility | A sequence outlining the order of data that must be preserved from first to last |
| Programming | A process that can be used to create a specific set of instructions for a computer to execute tasks |
| Protecting and preserving evidence | The process of properly working with fragile and volatile digital evidence |
| Security information and event management (SIEM) | An application that collects and analyzes log data to monitor critical activities in an organization |
| SQL (Structured Query Language) | A query language used to create, interact with, and request information from a database |

---

## Personal Reflection

This module made it clear how much of an entry-level analyst's toolkit overlaps with general IT fundamentals — programming, operating systems, and databases — before layering in security-specific tools like IDS and pen testing. Walking through named vulnerabilities like Log4Shell and ProxyLogon helped make the abstract idea of "vulnerability" more concrete, and reinforced why continuous monitoring matters even after a patch exists: an unapplied patch is still an open door.
