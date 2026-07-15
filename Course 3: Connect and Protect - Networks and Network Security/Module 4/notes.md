# Course 3, Module 4 – Brute Force, OS Hardening, Network Security Applications, and Cloud Security

## Overview

This module covered brute force attacks and OS hardening, an activity exemplar for applying hardening techniques, layered network security applications (firewalls through SIEM), and cloud security — including the shared responsibility model and cryptography in the cloud.

---

## Learning Objectives

After completing this module, I can:

- Explain types of brute force attacks and prevention measures
- Describe the role of VMs and sandboxes in vulnerability assessment
- Compare firewalls, IDS, IPS, and SIEM as layered network defenses
- Explain cloud security considerations and the shared responsibility model
- Describe cloud hardening techniques and how cryptography secures cloud data

---

## Reading: Brute Force Attacks and OS Hardening

### Brute Force Attacks

A trial-and-error process for discovering private information, most often login credentials — a major weak point since credentials can be stolen or guessed.

- **Simple brute force attacks:** Guessing username/password combinations directly.
- **Dictionary attacks:** Using a list of commonly used passwords or previously stolen credentials.

### Assessing Vulnerabilities

- **Virtual machines (VMs):** Software versions of physical computers that provide an isolated environment for running code, useful for investigating infected machines or testing malware safely, and can be reverted to a clean state. Some risk remains that malicious code can escape virtualization and reach the host.
- **Sandbox environments:** Testing environments for executing software separately from the network — used for testing patches, finding bugs, evaluating suspicious files, and simulating attacks. Note: some malware is written to detect a VM/sandbox and behave harmlessly to avoid analysis.

### Prevention Measures

- **Salting and hashing:** Hashing converts information into a unique, non-reversible value; salting adds random characters to increase length/complexity, making hashes harder to crack.
- **MFA / 2FA:** Requires two or more forms of identity verification (password, biometric, one-time code) to access a system.
- **CAPTCHA and reCAPTCHA:** A test proving the user is human, helping prevent automated brute forcing.
- **Password policies:** Standardize good practices — complexity requirements, update frequency, reuse restrictions, and login attempt limits before account suspension.

**Key takeaway:** Brute force attacks range from manual to fully automated with dedicated tools, and defenses like hashing/salting, MFA/2FA, CAPTCHA, and password policies work together to reduce their effectiveness.

---

## Activity Exemplar: Apply OS Hardening Techniques

A completed exemplar for a hands on activity: analyzing a DNS & HTTP traffic log to identify a network protocol, documenting a cybersecurity incident, and recommending one security measure to prevent future brute force attacks. The exemplar demonstrates one possible explanation for an end-user issue, including the network protocol identified, incident documentation, and a recommended security measure.

**Key takeaway:** Being able to analyze the protocols involved in an incident — even without knowing the exact root cause immediately — helps make an informed assumption about what happened and start resolving the issue.

---

## Reading: Network Security Applications

Defense in depth is the approach of adding layers of security to a network — from a minimum baseline (a firewall alone) up to a fully layered setup (firewall + IDS/IPS + security event monitoring).

### Firewall

Allows/blocks traffic based on rules, inspecting the packet header for port number (or, with NGFWs, the payload too). Every system should have its own firewall regardless of the network firewall.

### Intrusion Detection System (IDS)

Monitors activity and alerts admins based on known attack signatures or anomalies. Limitations: only catches known attacks/obvious anomalies, and doesn't stop the traffic itself — that's up to the administrator. Placing an IDS behind the firewall reduces false positives by only analyzing traffic that made it past the firewall.

### Intrusion Prevention System (IPS)

Like an IDS but actively stops anomalies when detected (blocking a sender or dropping packets) rather than just reporting them. Sits behind the firewall for a high level of protection, but is inline — if it fails, the connection between the private network and internet breaks — and can also produce false positives that drop legitimate traffic.

### Full Packet Capture Devices

Record and analyze all data transmitted over the network, useful for investigating alerts raised by an IDS.

### Security Information and Event Management (SIEM)

Collects and analyzes log data in real time from IDSs, IPSs, firewalls, VPNs, proxies, and DNS logs, aggregating it into a "single pane of glass" for analysts working in a Security Operations Center (SOC). A SIEM doesn't replace analyst expertise or hardening activities — it works alongside them.

**Key takeaway (summary table):**

| Tool | Advantage | Disadvantage |
|------|-----------|---------------|
| Firewall | Allows/blocks traffic based on rules | Only filters based on header information |
| IDS | Detects and alerts on possible intrusions/malicious traffic | Can only scan for known attacks/obvious anomalies; doesn't stop traffic |
| IPS | Monitors and actively stops intrusions/anomalies | Inline — failure breaks the connection; can produce false positives |
| SIEM | Aggregates and analyzes log data centrally | Only reports issues; doesn't take action to stop/prevent them |

Each tool carries cost and staffing tradeoffs, so decision-makers choose the appropriate security level based on cost and organizational risk.

---

## Reading: Secure the Cloud

### Cloud Security Considerations

- **Identity access management (IAM):** Manages digital identities and authorizes resource use; loosely configured cloud user roles increase risk.
- **Configuration:** More available cloud services mean more complexity — misconfigured services (especially during initial migration) are a common source of cloud security issues.
- **Attack surface:** More services/applications means more risk and a larger attack surface, though CSPs often defer to more scrutinized, secure options compared to a traditional on-premises network.
- **Zero-day attacks:** Previously unknown exploits. CSPs are often positioned to detect and patch zero-days (via hypervisor patches and workload migration) faster than a traditional IT organization.
- **Visibility and tracking:** On-premises admins have full packet visibility; in the cloud, CSPs handle infrastructure security but don't allow customers to monitor traffic on their servers directly — though CSPs offer flow logs, packet mirroring, and third-party audits.
- **Things change fast in the cloud:** CSPs update quickly, which can require organizations to adapt their processes and configurations to match.

### Shared Responsibility Model

The CSP is responsible for securing the cloud infrastructure itself (data centers, hypervisors, host operating systems); the organization using the service is responsible for the assets/processes they store or run in the cloud — including proper configuration. Problems arise when organizations assume the CSP is covering something it isn't (e.g., application configuration).

**Key takeaway:** Organizations are responsible for correctly configuring and maintaining best security practices for their cloud services, while the shared responsibility model clarifies where the CSP's obligations end and the customer's begin.

---

## Reading: Cryptography and Cloud Security

### Cloud Security Hardening

- **IAM:** Manages digital identities and authorizes resource use (as above).
- **Hypervisors:** Abstract host hardware from the software environment. Type 1 hypervisors run directly on host hardware (e.g., VMware ESXi) and are commonly used by CSPs; type 2 run on the host's software (e.g., VirtualBox). Vulnerabilities/misconfigurations can lead to VM escapes, where an attacker reaches the primary hypervisor and other VMs. As a CSP customer, you'll rarely deal with hypervisors directly.
- **Baselining:** Establishes a fixed reference point for how a cloud environment is configured, used to compare changes — e.g., restricting admin portal access, enabling password management/file encryption, and enabling SQL threat detection.

### Cryptography in the Cloud

Encryption and secure key management provide data integrity and confidentiality for cloud-stored/processed data. Encryption scrambles information into ciphertext, unreadable without the key; modern encryption relies on keeping the key secret rather than the algorithm.

### Cryptographic Erasure

A method of erasing the encryption key for encrypted data (crypto-shredding), making the data undecipherable — all copies of the key must be destroyed to prevent future access, since traditional data destruction methods are less effective in the cloud.

### Key Management

- **Trusted platform module (TPM):** A computer chip that securely stores passwords, certificates, and encryption keys.
- **Cloud hardware security module (CloudHSM):** A device providing secure storage for cryptographic keys and processing cryptographic operations.

Customers typically don't have direct access to a CSP's own encryption keys but can request audits/security reports, and most CSPs let customers supply their own keys — making the customer responsible for keeping those keys confidential (the CSP has limited ability to help if a customer's own keys are compromised or lost). FedRAMP provides a list of verified CSPs for federal contractors.

**Key takeaway:** IAM, baselining, hypervisor security, cryptography, and cryptographic erasure are all methods for further securing cloud infrastructure and are critical to assess when evaluating a public cloud environment.

---

## Glossary Terms from Module 4

| Term | Definition |
|------|------------|
| Baseline configuration (baseline image) | A documented set of specifications within a system that is used as a basis for future builds, releases, and updates |
| Hardware | The physical components of a computer |
| Multi-factor authentication (MFA) | A security measure which requires a user to verify their identity in two or more ways to access a system or network |
| Network log analysis | The process of examining network logs to identify events of interest |
| Operating system (OS) | The interface between computer hardware and the user |
| Patch update | A software and operating system update that addresses security vulnerabilities within a program or product |
| Penetration testing (pen test) | A simulated attack that helps identify vulnerabilities in systems, networks, websites, applications, and processes |
| Security hardening | The process of strengthening a system to reduce its vulnerabilities and attack surface |
| Security information and event management (SIEM) | An application that collects and analyzes log data to monitor critical activities for an organization |
| World-writable file | A file that can be altered by anyone in the world |

---

## Personal Reflection

Seeing firewall, IDS, IPS, and SIEM laid out together in a defense-in-depth progression — rather than as separate, unrelated tools — helped me understand why organizations layer multiple security products instead of relying on just one. The shared responsibility model was also a good gut-check: it's easy to assume a CSP is handling more than it actually is, and misconfiguration (not a CSP failure) is the most common source of cloud security issues.
