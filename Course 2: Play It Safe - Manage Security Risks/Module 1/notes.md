# Course 2, Module 1 – Security Domains

## Overview

This module introduced the eight CISSP security domains, then covered core threat/risk/vulnerability concepts, ransomware and the layers of the web, the impacts of cyber threats, the NIST Risk Management Framework's seven steps, and risk management strategies.

---

## Learning Objectives

After completing this module, I can:

- Describe all eight CISSP security domains and how they organize security work
- Differentiate threats, risks, and vulnerabilities
- Explain ransomware, the layers of the web, and the financial/reputational impacts of cyber threats
- Walk through the seven steps of the NIST RMF
- Identify common risk management strategies and today's most common threats/vulnerabilities

---

## Video: The First Four Security Domains

### Security and Risk Management

Focuses on defining security goals, mitigating risks, ensuring regulatory compliance, and establishing business continuity plans — reducing risk to critical assets/data (like PII) and adhering to ethical behavior to prevent negligence or fraud.

### Asset Security

Securing both digital and physical assets, including proper data handling throughout its lifecycle — emphasizing secure storage, maintenance, retention, and destruction so sensitive information (PII/SPII) stays protected from unauthorized access.

### Security Architecture and Engineering

Optimizing data security through effective tools, systems, and processes. A core concept is **shared responsibility** — all individuals contribute to lowering risk and maintaining physical/virtual security.

### Communication and Network Security

Managing/securing physical networks and wireless communications — protecting data and communications on-site, in the cloud, or connecting remotely, by preventing vulnerabilities from insecure connections.

**Key takeaway:** These first four domains cover the foundational "what to protect and how to structure that protection" — risk management, asset handling, architecture, and network/communication security.

---

## Video: The Last Four Security Domains

### Identity and Access Management (IAM)

Controls access/authorization to keep data secure, ensuring users follow established policies through **identification** (verifying who a user is), **authentication** (proving identity), **authorization** (determining access levels), and **accountability** (monitoring user actions).

### Security Assessment and Testing

Conducting security control testing, collecting/analyzing data, and performing security audits to monitor for risks/threats/vulnerabilities. Regular testing and analysis help identify/mitigate threats and improve or implement controls, like MFA.

### Security Operations

Conducting investigations and implementing preventative measures once an incident is identified — mitigating active attacks, conducting forensic investigations, and determining areas for improvement.

### Software Development Security

Using secure coding practices throughout the software development lifecycle — integrating security reviews at each phase (secure design reviews, secure code reviews, penetration testing) to embed security into the product from the start.

**Key takeaway:** These last four domains cover the "who gets access, how do we verify it's working, and how do we respond and build securely" side of the security lifecycle.

---

## Reading: CISSP's Eight Security Domains

### Domain One: Security and Risk Management

Impacts an organization's **security posture** through security goals/objectives, risk mitigation processes, compliance, business continuity plans, legal regulations, and professional/organizational ethics. Related to **information security (InfoSec)** — the set of processes established to secure information, which may include playbooks and training. InfoSec design processes include incident response, vulnerability management, application security, cloud security, and infrastructure security. Example: adjusting how PII is handled to comply with the EU's GDPR.

### Domain Two: Asset Security

Manages the cybersecurity processes of organizational assets — storage, maintenance, retention, and destruction of physical/virtual data. Since lost/stolen assets increase organizational risk, tracking assets and their data is essential; security impact analysis, recovery plans, and data exposure management all depend on each asset's risk level. Analysts may create backups to ensure environment restoration is possible after an incident.

### Domain Three: Security Architecture and Engineering

Focuses on managing data security through effective tools/systems/processes, created by security architects/engineers. Core concept: **shared responsibility** — everyone takes an active role in lowering risk during system design. Related design principles (covered later in the program): threat modeling, least privilege, defense in depth, fail securely, separation of duties, keep it simple, zero trust, trust but verify. Example: using a SIEM tool to monitor for unusual login/user activity that could indicate a threat actor.

### Domain Four: Communication and Network Security

Manages/secures physical networks and wireless communications — on-site, remote, and cloud. Organizations with remote/hybrid/on-site environments must ensure data stays secure while managing external connections; designing controls like restricted network access helps protect users and the network when employees travel or work outside the main office.

### Domain Five: Identity and Access Management

Keeps data secure by ensuring user identities are trusted/authenticated and access to physical/logical assets is authorized — preventing unauthorized users while letting authorized users do their jobs. Uses the **principle of least privilege**: granting only the minimal access/authorization needed for a task. Example: a customer service rep can view only a customer's phone number while resolving their issue, with access removed once resolved.

### Domain Six: Security Assessment and Testing

Identifies/mitigates risks, threats, and vulnerabilities. Security assessments determine whether internal systems are secure; organizations may employ **penetration testers ("pen testers")** to find exploitable vulnerabilities. This domain emphasizes security control testing, data collection/analysis, and security audits — e.g., analysts auditing user permissions to validate correct access levels.

### Domain Seven: Security Operations

Focuses on investigating a potential data breach and implementing preventative measures afterward, using strategies/tools like training and awareness, reporting and documentation, intrusion detection/prevention, SIEM tools, log management, incident management, playbooks, post-breach forensics, and reflecting on lessons learned. Teams here handle active attacks (e.g., large amounts of data being accessed outside normal working hours) and work to keep private data safe once a threat is identified.

### Domain Eight: Software Development Security

Uses secure programming practices/guidelines to create secure applications, protecting organizations and users through reliable services. Security must be incorporated into every stage of the software development lifecycle — design, development, testing, release — rather than treated as an afterthought. Application security tests, QA, and pen testers help ensure programming conventions, executables, and embedded security measures meet standards. Example: an analyst at a pharmaceutical company confirming encryption is properly configured for a new medical device storing patient data.

**Key takeaway:** Being familiar with all eight CISSP domains — and related concepts like InfoSec and least privilege — provides a structured map of the entire cybersecurity field and where a given task or role fits within it.

---

## Video: Threats, Risks, and Vulnerabilities

### Understanding Assets and Their Exposures

**Assets** are items of value to an organization — physical spaces, computers, customer data (PII), intellectual property (patents). Organizations constantly face threats, risks, and vulnerabilities that can impact these assets.

### Differentiating Threats, Risks, and Vulnerabilities

- **Threats:** Circumstances/events that can negatively affect assets, such as social engineering attacks like phishing.
- **Risks:** The likelihood of a threat occurring and impacting confidentiality/integrity/availability — often categorized low/medium/high based on potential damage.
- **Vulnerabilities:** Weaknesses a threat can exploit (outdated software, weak passwords, unprotected confidential data). Both a vulnerability and a threat must be present for a risk to exist.

### Mitigating Risks and Strengthening Security

People can themselves be a vulnerability, so educating/empowering employees to be security-conscious is a key entry-level analyst responsibility. Organizations must continuously identify and mitigate vulnerabilities, with analysts playing a role in monitoring/documenting access to critical assets.

**Key takeaway:** A risk only exists where a vulnerability and a threat intersect — reducing either one reduces the overall risk, which is why analysts work on both technical vulnerabilities and human/process weaknesses.

---

## Video: Ransomware, the Web, and Cyber Threat Impacts

### Ransomware and the Web

**Ransomware** encrypts an organization's data and demands payment for restoration, which can freeze systems, disable devices, and lock confidential data. The web has three layers: the **surface web** (accessible via standard browsers), the **deep web** (requires authorization, like an organization's intranet), and the **dark web** (requires special software, often used for illicit activity due to its secrecy).

### Impacts of Cyber Threats

- **Financial impact:** Interrupted production, service disruptions, recovery costs, and regulatory non-compliance fines.
- **Identity theft:** Storing sensitive PII creates identity theft risk — stolen data can be sold or leaked on the dark web, where threat actors often operate with a sense of anonymity.
- **Reputational damage:** Exploited vulnerabilities can drive customer loss, negative press, and legal penalties/fines.

**Key takeaway:** A single successful attack (like ransomware) can cascade into financial, identity-theft, and reputational harm simultaneously — which is why prevention is weighed against such a broad range of downstream costs.

---

## Video: The NIST Risk Management Framework (RMF)

### Understanding the NIST RMF

Provides a structured approach for managing risks, threats, and vulnerabilities. Familiarity with the framework matters for entry-level analysts even if they don't personally execute every step.

### The Seven Steps of the RMF

1. **Prepare:** Activities to manage security/privacy risks before a breach, like monitoring for risks and identifying controls.
2. **Categorize:** Develop risk management processes/tasks by considering a risk's impact on confidentiality, integrity, and availability.
3. **Select:** Choose, customize, and document controls that protect the organization (e.g., maintaining an up-to-date playbook).
4. **Implement:** Put security/privacy plans into action to minimize ongoing risk impact.
5. **Assess:** Determine if established controls are correctly implemented and meeting organizational needs, identifying potential weaknesses.
6. **Authorize:** Be accountable for security/privacy risks — may involve generating reports and developing action plans.
7. **Monitor:** Continuously assess/maintain technical operations to ensure systems support the organization's security goals and minimize risk.

**Key takeaway:** The RMF's seven steps move from preparation through categorization, control selection, implementation, assessment, authorization, and ongoing monitoring — a full lifecycle rather than a one-time checklist.

---

## Reading: Manage Common Threats, Risks, and Vulnerabilities

### Risk Management

Organizations protect **assets** — digital (SSNs, dates of birth, bank account numbers, mailing addresses) and physical (payment kiosks, servers, desktop computers, office spaces). Common risk management strategies:

- **Acceptance:** Accepting a risk to avoid disrupting business continuity.
- **Avoidance:** Creating a plan to avoid the risk altogether.
- **Transference:** Transferring risk to a third party to manage.
- **Mitigation:** Lessening the impact of a known risk.

Frameworks like NIST RMF and HITRUST help formalize these processes.

### Today's Most Common Threats, Risks, and Vulnerabilities

- **Threats:** **Insider threats** (staff/vendors abusing authorized access) and **advanced persistent threats (APTs)** (unauthorized access maintained over an extended period).
- **Risks:** A basic formula: risk equals the likelihood of a threat (analogous to being late to work — the risk — because of traffic, an accident, or a flat tire — the threats). Factors affecting likelihood: external risk, internal risk, legacy systems (e.g., an old vending machine or workstation still tied to a legacy accounting system), multiparty risk (third-party vendor access to IP), and software compliance/licensing gaps. OWASP's Top 10 web application risks list is updated regularly, reflecting the field's constant evolution — the 2017–2021 update added insecure design, software/data integrity failures, and server-side request forgery.
- **Vulnerabilities:** ProxyLogon (pre-authenticated Microsoft Exchange vulnerability), ZeroLogon (Netlogon authentication protocol vulnerability), Log4Shell (remote code execution/data leak via internet-connected devices), PetitPotam (Windows NTLM theft technique), security logging/monitoring failures, and server-side request forgery (SSRF). **Vulnerability management** — monitoring to identify/mitigate vulnerabilities — matters because unapplied patches still leave systems exposed even when a fix exists.

**Key takeaway:** Risk management strategies and frameworks (like NIST RMF and HITRUST) give organizations a structured way to manage today's most common threats, risks, and vulnerabilities — and constant monitoring/patching remains essential even after a fix is available.

---

## Glossary Terms from Module 1

| Term | Definition |
|------|------------|
| Assess | The fifth step of the NIST RMF that means to determine if established controls are implemented correctly |
| Authorize | The sixth step of the NIST RMF that refers to being accountable for the security and privacy risks that may exist in an organization |
| Business continuity | An organization's ability to maintain their everyday productivity by establishing risk disaster recovery plans |
| Categorize | The second step of the NIST RMF that is used to develop risk management processes and tasks |
| External threat | Anything outside the organization that has the potential to harm organizational assets |
| Implement | The fourth step of the NIST RMF that means to implement security and privacy plans for an organization |
| Internal threat | A current or former employee, external vendor, or trusted partner who poses a security risk |
| Monitor | The seventh step of the NIST RMF that means be aware of how systems are operating |
| Prepare | The first step of the NIST RMF related to activities that are necessary to manage security and privacy risks before a breach occurs |
| Ransomware | A malicious attack where threat actors encrypt an organization's data and demand payment to restore access |
| Risk | Anything that can impact the confidentiality, integrity, or availability of an asset |
| Risk mitigation | The process of having the right procedures and rules in place to quickly reduce the impact of a risk like a breach |
| Security posture | An organization's ability to manage its defense of critical assets and data and react to change |
| Select | The third step of the NIST RMF that means to choose, customize, and capture documentation of the controls that protect an organization |
| Shared responsibility | The idea that all individuals within an organization take an active role in lowering risk and maintaining both physical and virtual security |
| Social engineering | A manipulation technique that exploits human error to gain private information, access, or valuables |
| Vulnerability | A weakness that can be exploited by a threat |

---

## Personal Reflection

Seeing all eight CISSP domains laid out together — rather than encountering each concept individually across the program — gave me a much clearer map of where everything I'll learn later actually fits. The "risk = threat × vulnerability, and both must be present" framing was also a genuinely useful mental shortcut: it means I can always ask "is this a threat, a vulnerability, or genuinely both" when assessing a situation, rather than treating the three terms as loosely interchangeable.
