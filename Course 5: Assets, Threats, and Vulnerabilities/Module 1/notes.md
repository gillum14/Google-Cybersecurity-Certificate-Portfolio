# Course 5, Module 1 – Risk Fundamentals, Asset Classification, Cloud Security, and NIST CSF

## Overview

This module revisited risk/threat/vulnerability terminology in more depth, covered asset classification and its challenges, traced the emergence of cloud security as its own subfield, and walked through how the NIST Cybersecurity Framework is implemented in practice.

---

## Learning Objectives

After completing this module, I can:

- Explain the risk equation and categorize threats and vulnerabilities
- Describe common asset classification levels and the challenges of classifying information
- Explain why cloud adoption created new security considerations
- Describe the three components of the NIST CSF and how organizations implement it

---

## Reading: Understand Risks, Threats, and Vulnerabilities

### Security Risk

Risk, threat, and vulnerability are often used interchangeably in everyday language but have distinct meanings in security. One way to frame risk: **Likelihood × Impact = Risk**. Calculating risk helps organizations prevent costly/disruptive events, identify system/process improvements, determine which risks can be tolerated, and prioritize critical assets.

### Risk Factors

Two broad risk factors: **threats** and **vulnerabilities**. Using a driving analogy — a nail puncturing your tire is a threat, since tires are vulnerable to sharp objects; reducing risk means reducing the likelihood side of the equation (e.g., driving on a clean road).

- **Categories of threat:** Intentional (e.g., a hacker exploiting a misconfigured application) vs. unintentional (e.g., an employee unknowingly granting building access to a stranger).
- **Categories of vulnerability:** Technical (e.g., misconfigured software) vs. human (e.g., a forgetful employee losing an access card).

**Key takeaway:** Knowing the precise meanings of risk, threat, and vulnerability — and how they relate — builds a strong foundation for growing as a security analyst and signals credibility to future colleagues.

---

## Reading: Common Classification Requirements

### Why Asset Management Matters

Asset management is the process of tracking assets and the risks that affect them — the core idea being that you can only protect what you know you have. Organizations protect a range of assets: digital (customer data, financial records), information systems (networks, software), physical (facilities, equipment, supplies), and intangible (brand reputation, intellectual property).

**Asset classification** is the practice of labeling assets based on sensitivity and importance, which requires knowing what an asset is, where it is, who owns it, and how important it is.

### Common Asset Classifications

- **Restricted:** The highest level — reserved for extremely sensitive, need-to-know information.
- **Confidential:** Disclosure could significantly negatively impact the organization.
- **Internal-only:** Available to employees and business partners.
- **Public:** No negative consequences if released.

Note: government organizations sometimes label their most sensitive assets "confidential" rather than "restricted," so this scheme can vary by organization.

### Challenges of Classifying Information

Identifying an asset's owner isn't always straightforward — e.g., a company-issued laptop used partly for personal photo storage complicates ownership. Information can also carry multiple classification values at once (e.g., a piece of mail might have a public element like your name alongside a confidential element like your address).

**Key takeaway:** Asset classification helps organizations implement effective risk management, prioritize security resources, reduce IT costs, and stay compliant — but classifying information specifically (versus physical assets) carries unique challenges around ownership and mixed sensitivity levels.

---

## Reading: The Emergence of Cloud Security

### Soaring Into the Cloud

Cloud computing has drastically lowered the barrier to starting and scaling an online business, but it also introduced new cybersecurity challenges. Cloud-based services fall into three categories:

- **SaaS (Software as a Service):** Front-end applications accessed via a browser, with the provider hosting/managing the back end (e.g., Gmail, Slack, Zoom).
- **PaaS (Platform as a Service):** Back-end development tools accessed online for building/managing/deploying apps, with the provider hosting the underlying hardware/software (e.g., Google App Engine, Heroku, VMware Cloud Foundry).
- **IaaS (Infrastructure as a Service):** Remote access to back-end systems (data processing, storage, networking), typically licensed as needed.

### Cloud Security

A growing subfield focused on protecting data, applications, and infrastructure in the cloud. In a traditional on-premise model, security responsibility sits entirely with the internal team; in the cloud, responsibility is split via the **shared responsibility model** — clients are commonly responsible for identity and access management, resource configuration, and data handling, with the amount of client responsibility varying by service type (SaaS/PaaS/IaaS).

### Cloud Security Challenges

- Misconfiguration (often from unmodified out-of-the-box settings)
- Cloud-native breaches, frequently tied to misconfigured services
- Difficulty monitoring access depending on service level
- Meeting regulatory standards (HIPAA, PCI DSS, GDPR) in a cloud context

**Key takeaway:** Cloud security is a growing, in-demand specialization as more organizations shift to cloud-based services and face a corresponding range of new risks.

---

## Reading: Security Guidelines in Action

### Origins of the Framework

NIST developed the Cybersecurity Framework (CSF) in 2014, originally to protect U.S. critical infrastructure, then adapted it to be flexible enough for public/private organizations of any size — including those lacking resources to build their own security plans from scratch.

### Components of the CSF

- **Core:** A set of desired cybersecurity outcomes organized into five functions — Identify, Protect, Detect, Respond, and Recover — used to identify important assets, protect them, detect attacks, and plan response/recovery.
- **Tiers:** Measure the sophistication of an organization's cybersecurity program on a scale of 1 (limited controls) to 4, used to assess security posture and identify areas for improvement.
- **Profiles:** Pre-made templates developed by industry experts, tailored to specific organizational or industry risks, used to establish a baseline or benchmark against industry standards.

### Implementing the CSF

Compliance is the process of adhering to internal standards and external regulations; the CSF itself is a voluntary framework organizations can use toward achieving compliance. Regulations must be followed; frameworks are optional resources. CISA provides guidance for implementation, summarized as: create a current profile and outline business needs, perform a risk assessment against current standards, analyze/prioritize existing security gaps, and implement an action plan.

**Key takeaway:** The NIST CSF is a flexible, evolving resource shaped by industry best practices worldwide — implementing it can be challenging due to its level of detail, but CISA's guidance provides a practical starting point, and it can also support regulatory compliance shared with business partners.

---

## Glossary Terms from Module 1

| Term | Definition |
|------|------------|
| Asset | An item perceived as having value to an organization |
| Asset classification | The practice of labeling assets based on sensitivity and importance to an organization |
| Asset inventory | A catalog of assets that need to be protected |
| Asset management | The process of tracking assets and the risks that affect them |
| Compliance | The process of adhering to internal standards and external regulations |
| Data | Information that is translated, processed, or stored by a computer |
| Data at rest | Data not currently being accessed |
| Data in transit | Data traveling from one point to another |
| Data in use | Data being accessed by one or more users |
| Information security (InfoSec) | The practice of keeping data in all states away from unauthorized users |
| NIST Cybersecurity Framework (CSF) | A voluntary framework that consists of standards, guidelines, and best practices to manage cybersecurity risk |
| Policy | A set of rules that reduce risk and protect information |
| Procedures | Step-by-step instructions to perform a specific security task |
| Regulations | Rules set by a government or other authority to control the way something is done |
| Risk | Anything that can impact confidentiality, integrity, or availability of an asset |
| Standards | References that inform how to set policies |
| Threat | Any circumstance or event that can negatively impact assets |
| Vulnerability | A weakness that can be exploited by a threat |

---

## Personal Reflection

The Likelihood × Impact framing of risk gave me a much cleaner mental model than just memorizing definitions — it makes clear why an analyst's day-to-day work concentrates on the likelihood side (closing vulnerabilities, reducing threat exposure) rather than trying to control impact directly. The asset classification challenges section also stuck with me: the idea that a single piece of information (like a piece of mail) can hold multiple classification levels at once complicates what initially sounds like a simple labeling exercise.
