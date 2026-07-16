# Course 5, Module 3 – OWASP Top 10, OSINT, Vulnerability Management, and Threat Actors

## Overview

This module covered the OWASP Top 10 vulnerabilities, open source intelligence (OSINT), approaches to vulnerability scanning, the importance of patching, penetration testing, applying an attacker mindset, types of threat actors, and defenses against brute force attacks.

---

## Learning Objectives

After completing this module, I can:

- Describe the OWASP Top 10 and how it differs from the CVE list
- Explain OSINT and name common OSINT tools
- Compare types of vulnerability scans
- Explain patch deployment strategies and the risk of end-of-life software
- Describe penetration testing strategies and team types
- Apply an attacker mindset through proactive and reactive simulations
- Categorize threat actors and hacker types by motivation and intent
- Explain tools and prevention measures related to brute force attacks

---

## Reading: The OWASP Top 10

OWASP (Open Worldwide Application Security Project) is a nonprofit that shares security information, tools, and events focused on securing the web. The **OWASP Top 10**, published since 2003, spreads awareness of the most-targeted web vulnerabilities and mainly applies to new/custom software development — unlike the CVE list, which tracks vulnerabilities in existing programs. It's updated every few years based on discovery frequency and risk level, and auditors also reference it for regulatory compliance checks.

**Common vulnerabilities in the Top 10:**

- **Broken access control:** Failures in mechanisms that limit what users can do, potentially leading to unauthorized disclosure, modification, or destruction.
- **Cryptographic failures:** Failing to encrypt sensitive data (e.g., PII) or using weak algorithms like MD5.
- **Injection:** Malicious code inserted into a vulnerable application (e.g., via a login form) that gives attackers a backdoor.
- **Insecure design:** Missing or poorly implemented security controls baked in during development.
- **Security misconfiguration:** Settings not properly configured or maintained, such as leaving default settings on deployed equipment.
- **Vulnerable and outdated components:** Using unmaintained open-source libraries in application development.
- **Identification and authentication failures:** Failing to properly recognize who should have access and what they're authorized to do.
- **Software and data integrity failures:** Inadequately reviewed updates/patches, which can enable supply chain attacks (e.g., the 2020 SolarWinds attack).
- **Security logging and monitoring failures:** Insufficient logging/monitoring/incident response, making it hard to trace events.
- **Server-side request forgery (SSRF):** Attackers manipulate a vulnerable server-side app to read/update other server resources.

**Key takeaway:** Staying informed via resources like the OWASP Top 10 helps defend against attacks and prepare for future risks throughout a security career.

---

## Reading: Open Source Intelligence

**OSINT** is the collection and analysis of information from publicly available sources to generate usable intelligence.

### Information vs. Intelligence

Information is raw data/facts; intelligence is the analysis of that information to produce insights that support decision-making — e.g., researching news about an OS update to decide whether to install it organization-wide.

### Intelligence Improves Decision-Making

OSINT supports InfoSec by generating insights into threats/vulnerabilities — for example, monitoring hacker forums for a newly discovered software weakness to prioritize patching. Uses include providing insight into attacks, detecting data exposures, evaluating existing defenses, and identifying unknown vulnerabilities.

### OSINT Tools

- **VirusTotal:** Analyzes suspicious files, domains, URLs, and IP addresses for malicious content.
- **MITRE ATT&CK:** A knowledge base of adversary tactics/techniques based on real-world observations.
- **OSINT Framework:** A web-based interface pointing to OSINT tools for nearly any source or platform.
- **Have I Been Pwned:** Searches for breached email accounts.

**Key takeaway:** Gathering both information and intelligence is central to cybersecurity — familiarity with common OSINT tools makes research faster when generating evidence-based intelligence.

---

## Reading: Approaches to Vulnerability Scanning

A **vulnerability scanner** is software that automatically compares known vulnerabilities/exposures against an organization's technologies, scanning each of the five attack surfaces (perimeter, network, endpoint, application, data layers) and flagging findings against a reference database. Scanners are non-intrusive (they don't exploit systems like an attacker would), though a scan can occasionally cause unintended issues like a crash.

### Types of Scans

- **External vs. internal:** External scans test outward-facing systems (websites, firewalls) for things like vulnerable ports; internal scans examine internal systems (e.g., how application software handles user input).
- **Authenticated vs. unauthenticated:** Authenticated scans log in with a real user/admin account to check for issues like broken access controls; unauthenticated scans simulate external actors without access, looking for unintended exposure (e.g., an internal-only file that's actually accessible).
- **Limited vs. comprehensive:** Limited scans check particular devices (e.g., firewall misconfigurations); comprehensive scans check all connected devices. **Discovery scanning** — identifying the computers, devices, and open ports on a network — should happen before either.

**Key takeaway:** Vulnerability scan results typically lead to renewed compliance efforts, procedural changes, and system patching — analysts play an important role in this process even if senior professionals configure the scans.

---

## Reading: The Importance of Updates

Updates address security vulnerabilities that put users, devices, and networks at risk, typically following a vulnerability assessment.

### Patching Gaps in Security

A **patch update** addresses security vulnerabilities within a program/product, usually with bug fixes for common CVEs — ideally released before malicious hackers find the underlying flaw, though sometimes developed in response to a **zero-day** (a previously unknown exploit).

### Common Update Strategies

- **Manual updates:** IT departments or users obtain/install updates themselves. Advantage: control, useful if updates aren't well-tested. Disadvantage: critical updates can be forgotten or ignored.
- **Automatic updates:** The system/application finds, downloads, and installs updates itself (CISA recommends this when available). Advantage: simplified, keeps systems current. Disadvantage: instability if a vendor's patch wasn't thoroughly tested.

### End-of-Life (EOL) Software

Software that's no longer supported once a newer version is released — sometimes kept in use because dependent software isn't compatible with newer versions. CISA recommends discontinuing EOL software since it poses an unfixable risk, but replacement costs can make this hard to follow in practice, especially as more connected/IoT devices enter networks.

**Key takeaway:** The 2017 WannaCry attack — which affected 150+ countries and caused an estimated $4 billion in damages — could likely have been prevented had systems applied a patch that had already been available for months. Keeping software updated takes effort but is consistently worth it.

---

## Reading: Penetration Testing

A **penetration test (pen test)** is a simulated, authorized attack — a form of ethical hacking — that uses the same tools/techniques as malicious actors to identify vulnerabilities and determine the consequences if a system is breached. Unlike a vulnerability assessment (which finds weaknesses), a pen test exploits them to measure real impact. Organizations regulated by PCI DSS, HIPAA, or GDPR must routinely pen test to maintain compliance.

### Learning from Varied Perspectives

- **Red team:** Simulates attacks to identify vulnerabilities.
- **Blue team:** Focuses on defense/incident response, validating existing security systems.
- **Purple team:** Collaborative — combines red and blue team elements to improve overall security posture.

### Penetration Testing Strategies

- **Open-box (internal/full knowledge/white-box/clear-box):** Tester has the same privileged access as an internal developer (system architecture, data flow, network diagrams).
- **Closed-box (external/black-box/zero knowledge):** Tester has little to no internal access — closest to a real malicious hacker and tends to produce the most accurate simulation.
- **Partial knowledge (gray-box):** Tester has limited access, similar to an internal employee like a customer service rep.

### Becoming a Penetration Tester

Relevant skills: network/application security, OS experience (Linux), vulnerability analysis/threat modeling, detection/response tools, programming (Python, Bash), and communication.

### Bug Bounty Programs

Organizations offer financial rewards to freelance pen testers who find and report vulnerabilities — HackerOne is a well-known community for finding active bug bounties.

**Key takeaway:** Pen testing gives organizations a clearer picture of their defensive weaknesses by actually exploiting them, and it's a growing career path built directly on the skills covered throughout this program.

---

## Portfolio Activity Exemplar: Analyze a Vulnerable System for a Small Business

A completed exemplar for a vulnerability assessment report covering a publicly accessible database server, including: a **Purpose** section explaining the reason for the analysis, a completed **Risk Assessment** table quantifying risk (likelihood × severity) for identified threat sources/events, an **Approach** section explaining the reasoning behind identified risks, and a **Remediation** section outlining a mitigation/mitigation strategy.

**Key takeaway:** Developing risk assessment and reporting skills — identifying risk and escalating it to the right channels — is a core analyst competency; the exemplar is one possible approach, not a required template to match exactly.

---

## Reading: Approach Cybersecurity with an Attacker Mindset

### Being Prepared for Anything

Applying an attacker's mindset to discovered weaknesses — like running a controlled experiment — offers a different perspective that's valuable when building or updating a security plan.

### Simulating Threats

- **Proactive simulations (red team):** Exploit vulnerabilities and break through defenses — often involve more planning than execution, such as phishing staff with fictitious emails to test security awareness.
- **Reactive simulations (blue team):** Assume a defender role, focused on gathering information about the assets being protected, often via vulnerability scanning tools.

### Scanning for Trouble

A reactive simulation might follow the standard vulnerability assessment steps: **identification** (e.g., flagging a server on an outdated OS), **vulnerability analysis** (researching the OS's known issues), **risk assessment** (scoring severity/impact), and **remediation** (addressing the issue) — typically producing a report shared with supervisors or service providers.

**Key takeaway:** Effectively applying an attacker mindset requires more than researching known vulnerabilities — it means staying current on emerging technologies and threat trends to think innovatively about what could go wrong next.

---

## Reading: Types of Threat Actors

A **threat actor** is any person or group who presents a security risk, spanning insiders and outsiders, intentional and accidental. Categories by motivation:

- **Competitors:** Rival companies who might benefit from leaked information.
- **State actors:** Government intelligence agencies.
- **Criminal syndicates:** Organized groups profiting from criminal activity.
- **Insider threats:** Anyone with current/former authorized access who compromises assets, intentionally or accidentally.
- **Shadow IT:** Individuals using ungoverned technology (e.g., personal email for work communications).

### Types of Hackers

- **Unauthorized (unethical/malicious) hackers:** Commit crimes with their skills; skill level ranges widely, including "script kiddies" using pre-written malicious code from others.
- **Authorized (ethical) hackers:** Use their skills to improve organizational security — internal security team members or external vendors/freelancers (bug bounty participants).
- **Semi-authorized hackers:** May violate ethical norms without being malicious — e.g., a hacktivist exploiting a public utility's vulnerability to raise awareness, aiming to expose issues before a malicious actor finds them.

### Advanced Persistent Threats (APTs)

Threat actors who maintain unauthorized system access for an extended period, most associated with nation-states/state-sponsored actors surveilling targets to gather intel for manipulating government, defense, financial, or telecom services. Private businesses aren't safe from APTs either — they're often targeted first as a stepping stone toward larger entities.

### Access Points

Common attack vector categories: direct physical access, removable media, social media, email, on-premises wireless networks, cloud services, and supply chains/third-party vendors.

**Key takeaway:** Defending an attack surface starts with understanding a threat actor's likely motivation and matching it to the access points they're most likely to target — e.g., remote workers are more likely to face an email-based threat than a direct-access one.

---

## Reading: Fortify Against Brute Force Cyber Attacks

### A Matter of Trial and Error

- **Simple brute force attacks:** Guessing any combination of username/password.
- **Dictionary attacks:** Using a list of commonly used credentials.
- **Reverse brute force attacks:** Starting with a single credential and trying it across various systems.
- **Credential stuffing:** Using stolen credentials from one breach to access accounts elsewhere; a specialized variant, **pass the hash**, reuses stolen unsalted hashed credentials to trick an authentication system into creating a new session.

### Tools of the Trade

Common brute-forcing tools: Aircrack-ng, Hashcat, John the Ripper, Ophcrack, THC Hydra — sometimes used by security professionals themselves to test their own systems.

### Prevention Measures

- **Hashing and salting:** Makes password data harder to brute force or match against a dictionary.
- **MFA:** Requiring multiple verification factors makes brute forcing a single credential far less useful to an attacker.
- **CAPTCHA:** A challenge-response test proving the user is human, not automated brute-forcing software.
- **Password policy:** Standardized requirements (length, complexity, lockout after failed attempts) that expand the number of possible combinations, lengthening the time needed to brute force a password. NIST Special Publication 800-63B provides detailed guidance for building these policies.

**Key takeaway:** Brute force attacks are simple but reliable; the stronger and more resilient a password (and the controls around it) is, the longer it takes to crack — recognizing the tactics and tools used is the first step toward stopping them.

---

## Glossary Terms from Module 3

| Term | Definition |
|------|------------|
| Advanced persistent threat (APT) | An instance when a threat actor maintains unauthorized access to a system for an extended period of time |
| Attack surface | All the potential vulnerabilities that a threat actor could exploit |
| Attack tree | A diagram that maps threats to assets |
| Attack vector | The pathways attackers use to penetrate security defenses |
| Bug bounty | Programs that encourage freelance hackers to find and report vulnerabilities |
| Common Vulnerabilities and Exposures (CVE) list | An openly accessible dictionary of known vulnerabilities and exposures |
| Common Vulnerability Scoring System (CVSS) | A measurement system that scores the severity of a vulnerability |
| CVE Numbering Authority (CNA) | An organization that volunteers to analyze and distribute information on eligible CVEs |
| Defense in depth | A layered approach to vulnerability management that reduces risk |
| Exploit | A way of taking advantage of a vulnerability |
| Exposure | A mistake that can be exploited by a threat |
| Hacker | Any person who uses computers to gain access to computer systems, networks, or data |
| MITRE | A collection of non-profit research and development centers |
| Security hardening | The process of strengthening a system to reduce its vulnerability and attack surface |
| Threat actor | Any person or group who presents a security risk |
| Vulnerability | A weakness that can be exploited by a threat |
| Vulnerability assessment | The internal review process of a company's security systems |
| Vulnerability management | The process of finding and patching vulnerabilities |
| Vulnerability scanner | Software that automatically compares existing common vulnerabilities and exposures against the technologies on the network |
| Zero-day | An exploit that was previously unknown |

---

## Personal Reflection

This module tied together a lot of previously separate threads — the OWASP Top 10, OSINT, vulnerability scanning, patching, and pen testing all felt like different puzzle pieces of the same larger vulnerability management lifecycle by the end. The WannaCry example was a striking reminder that the technical fix (a patch) can exist for months before an attack, and the actual failure is organizational, not technical. Framing threat actors by motivation rather than just skill level also gave me a more useful lens for anticipating who's likely to target a given asset and why.
