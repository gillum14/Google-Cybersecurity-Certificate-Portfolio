# Course 2, Module 2 – Frameworks, Controls, the CIA Triad, OWASP, and Security Audits

## Overview

This module went deeper into how frameworks and controls work together, applied the CIA triad from an analyst's perspective, expanded on OWASP's secure design principles, and covered the goals, scope, and process behind conducting a security audit.

---

## Learning Objectives

After completing this module, I can:

- Explain how specific frameworks (CTF, ISO/IEC 27001) and controls work together
- Apply the CIA triad from a working analyst's perspective
- Describe additional OWASP secure design principles
- Explain the goals, scope, and checklist process of a security audit

---

## Reading: The Relationship Between Frameworks and Controls

### Frameworks and Controls

Security frameworks are guidelines for building plans to mitigate risk and threats to data and privacy, and support compliance with laws like HIPAA. Security controls are the safeguards used alongside frameworks — for example, requiring MFA to help a hospital stay HIPAA-compliant.

### Specific Frameworks and Controls

- **Cyber Threat Framework (CTF):** Developed by the U.S. government to provide a common language for describing and communicating cyber threat activity, improving information sharing across organizations.
- **ISO/IEC 27001:** An internationally recognized framework enabling organizations to manage the security of assets — financial information, intellectual property, employee data, third-party information. Doesn't require specific controls but provides a collection organizations can use.

### Controls

Used alongside frameworks to reduce the possibility and impact of a threat, risk, or vulnerability. Categories:

- **Physical:** Gates, fences, locks, security guards, CCTV, access cards/badges
- **Technical:** Firewalls, MFA, antivirus software
- **Administrative:** Separation of duties, authorization, asset classification

**Key takeaway:** Frameworks and controls are typically voluntary but strongly encouraged — together they establish an organization's security posture and support meeting compliance obligations.

---

## Reading: Use the CIA Triad to Protect Organizations

### Confidentiality

Only authorized users can access specific assets or data. Enhanced through design principles like the principle of least privilege — limiting users' access to only what's needed for their job.

### Integrity

Data is verifiably correct, authentic, and reliable. Verified through cryptography (transforming data so unauthorized parties can't read or tamper with it) and encryption.

### Availability

Data is accessible to those authorized to use it — for example, allowing remote employees network access to do their jobs, while still limiting access based on role (an accounting employee might not need access to development project data).

**Key takeaway:** Maintaining an acceptable level of risk while designing systems and policies around confidentiality, integrity, and availability establishes a successful security posture.

---

## Reading: More About OWASP Security Principles

### Previously Covered Principles

Minimize attack surface area, principle of least privilege, defense in depth, separation of duties, keep security simple, fix security issues correctly.

### Additional OWASP Principles

- **Establish secure defaults:** The optimal security state should be an application's default state — it should take extra effort to make it insecure.
- **Fail securely:** When a control fails, it should default to its most secure option (e.g., a failed firewall should block all new connections, not accept everything).
- **Don't trust services:** Don't assume a third-party partner's systems are secure just because you're working with them — verify before sharing/trusting shared data.
- **Avoid security by obscurity:** Security should rely on strong design (password policies, defense in depth, transaction limits, network architecture, audit controls) — not on keeping source code or details secret.

**Key takeaway:** These principles are used daily by analysts — while monitoring SIEM dashboards, analyzing logs, or running vulnerability scanners — to promote safe development practices and reduce risk to companies and users.

---

## Reading: Security Audits (Scope, Goals, and Process)

### Audit Scope and Goals (Example)

**Summary:** An internal audit aligns business practices with industry standards, provides mitigation recommendations for "high risk" vulnerabilities, and presents an overall strategy to improve security posture. **Scope:** assess user permissions, identify existing controls/procedures/protocols, account for technology in use. **Goals:** adhere to the NIST CSF, establish compliant policies and procedures, fortify system controls.

### More About Security Audits

A security audit is an independent review evaluating whether an organization is meeting internal criteria (policies, procedures, best practices) and external criteria (regulatory compliance, laws). Audits help ensure security checks are happening (e.g., daily SIEM dashboard monitoring) and that a remediation process exists for issues found.

**Goals and objectives:** Ensure IT practices meet industry/organizational standards, identify and address areas for remediation and growth, and safeguard data to avoid penalties/fines. Audit frequency depends on local laws and federal compliance regulations.

**Factors that affect audits:** Industry type, organization size, ties to government regulations, geographic location, and voluntary regulatory compliance decisions.

**Role of frameworks and controls:** NIST CSF and ISO 27000 help organizations prepare for regulatory compliance audits, saving time on both internal and external reviews. The three main control categories reviewed during an audit are administrative/managerial, technical, and physical.

### Audit Checklist

1. **Identify the scope** — list assets to be assessed, note how the audit supports organizational goals, indicate audit frequency, and evaluate whether policies/protocols are being followed.
2. **Complete a risk assessment** — evaluate risks tied to budget, controls, internal processes, and external standards.
3. **Conduct the audit** — assess the security of the identified assets.
4. **Create a mitigation plan** — a strategy to lower risk level and potential costs/penalties.
5. **Communicate results to stakeholders** — a detailed report of findings, suggested improvements, and applicable compliance regulations.

**Key takeaway:** This introduction to security audits — what they are, why they're conducted, and the role frameworks/controls/compliance play — supports being able to complete a full audit of one's own later in the program.

---

## Glossary Terms from Module 2

| Term | Definition |
|------|------------|
| Asset | An item perceived as having value to an organization |
| Attack vectors | The pathways attackers use to penetrate security defenses |
| Authentication | The process of verifying who someone is |
| Authorization | The concept of granting access to specific resources in a system |
| Availability | The idea that data is accessible to those who are authorized to access it |
| Biometrics | The unique physical characteristics used to verify a person's identity |
| Confidentiality | The idea that only authorized users can access specific assets or data |
| CIA triad | A model that helps inform how organizations consider risk when setting up systems and security policies |
| Detect | A NIST core function related to identifying potential security incidents and improving monitoring capabilities |
| Encryption | The process of converting data from a readable format to an encoded format |
| Identify | A NIST core function related to management of cybersecurity risk and its effect on an organization's people and assets |
| Integrity | The idea that the data is correct, authentic, and reliable |
| NIST CSF | A voluntary framework of standards, guidelines, and best practices to manage cybersecurity risk |
| NIST S.P. 800-53 | A unified framework for protecting the security of information systems within the U.S. federal government |
| OWASP | A non-profit organization focused on improving software security |
| Protect | A NIST core function used to implement policies, procedures, training, and tools that mitigate cybersecurity threats |
| Recover | A NIST core function related to returning affected systems back to normal operation |
| Respond | A NIST core function related to containing, neutralizing, and analyzing security incidents |
| Risk | Anything that can impact the confidentiality, integrity, or availability of an asset |
| Security audit | A review of an organization's security controls, policies, and procedures against a set of expectations |
| Security controls | Safeguards designed to reduce specific security risks |
| Security frameworks | Guidelines used for building plans to help mitigate risk and threats to data and privacy |
| Security posture | An organization's ability to manage its defense of critical assets and data and react to change |
| Threat | Any circumstance or event that can negatively impact assets |

---

## Personal Reflection

This module connected the dots between abstract frameworks like CTF and ISO/IEC 27001 and the day-to-day controls analysts actually configure. Walking through the audit checklist end-to-end — scope, risk assessment, conducting the audit, mitigation plan, stakeholder communication — gave me a much clearer mental model of what a real audit engagement looks like in practice, not just in theory.
