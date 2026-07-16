# Course 6, Module 3 – Detection Methods, IoCs, Documentation, Triage, and Post-Incident Activity

## Overview

This module covered detection methods beyond automated tools (threat hunting, threat intelligence, cyber deception), the Pyramid of Pain and indicators of compromise, investigative tools like VirusTotal, documentation best practices, the triage process, business continuity planning, and post-incident review.

---

## Learning Objectives

After completing this module, I can:

- Describe threat hunting, threat intelligence, and cyber deception as detection methods
- Explain the Pyramid of Pain and differentiate IoCs from IoAs
- Use investigative tools like VirusTotal to add context to an IoC
- Apply documentation best practices and the triage process
- Explain business continuity planning and post-incident review activities

---

## Reading: Cybersecurity Incident Detection Methods

During the Detection and Analysis phase of the incident response lifecycle, teams are notified of a possible incident and work to investigate/validate it via data collection and analysis. Automated detection tools (IDS, SIEM) are limited by their configuration and by how well they keep pace with evolving threats.

### Threat Hunting

The proactive search for threats on a network, combining human analysis with technology to uncover activity that detection tools missed — including sophisticated threats like fileless malware, which hides in memory and evades traditional signature-based detection. **Threat hunters** research emerging threats/attacks and assess an organization's probability of being vulnerable, using threat intelligence, IoCs, indicators of attack (IoAs), and machine learning.

### Threat Intelligence

Evidence-based threat information providing context about existing/emerging threats, sourced from:

- **Industry reports and government advisories:** Detail attacker tactics, techniques, and procedures (TTPs).
- **Threat data feeds:** A stream of threat-related data (IP addresses, domains, file hashes) helpful against sophisticated attackers like APTs.

A **threat intelligence platform (TIP)** collects, centralizes, and analyzes threat intelligence from multiple sources to help prioritize relevant threats. Note: threat intelligence should add context to detections, not drive them entirely — it should be assessed before being applied to an organization.

### Cyber Deception

Techniques that deliberately deceive malicious actors to increase detection and improve defenses. **Honeypots** are decoy systems/resources designed to look vulnerable and attract intruders (e.g., a fake file labeled with something tempting) — once accessed, security teams are alerted.

**Key takeaway:** A mix of detection methods — automated tools, human-driven threat hunting, threat intelligence, and cyber deception — helps organizations adapt to a constantly evolving threat landscape rather than relying on any single approach.

---

## Reading: Indicators of Compromise

### IoCs vs. IoAs

**Indicators of compromise (IoCs)** are observable evidence of a potential security incident — like noticing a valuable is missing from a car after the fact. **Indicators of attack (IoAs)** are the series of observed events indicating a real-time incident, focused on an attacker's behavioral methods/intentions. IoCs answer the "who and what" after an attack; IoAs answer the "why and how" during one. Note: IoCs aren't always confirmation of an incident — they can also result from human error or system malfunction.

### The Pyramid of Pain

Created by security researcher David J. Bianco, this concept captures the relationship between an IoC type and how much "pain" (difficulty) it causes an attacker when blocked — the higher up the pyramid, the harder it is for the attacker to work around:

1. **Hash values:** Unique references to malware samples or intrusion-related files.
2. **IP addresses:** Easy for attackers to rotate/change.
3. **Domain names:** Web addresses.
4. **Network artifacts:** Observable evidence on a network (e.g., User-Agent strings).
5. **Host artifacts:** Observable evidence on a host (e.g., a malware-created filename).
6. **Tools:** Software used by the attacker (e.g., John the Ripper for password cracking).
7. **Tactics, techniques, and procedures (TTPs):** The attacker's behavior — tactics (high-level), techniques (detailed behavior descriptions), procedures (highly detailed technique descriptions). The hardest to detect and disrupt.

**Key takeaway:** Not all IoCs carry equal value — blocking indicators higher on the Pyramid of Pain (like TTPs) causes far more disruption to an attacker's operations than blocking low-value indicators like a single IP address.

---

## Reading: Analyze Indicators of Compromise with Investigative Tools

### Adding Context to Investigations

Focusing on a single IoC (like one suspicious IP) misses the bigger picture — like fixating on one section of a painting. **Threat intelligence** helps expand a single IoC into a fuller narrative by connecting it to related artifacts (e.g., other suspicious network communications or unusual processes tied to that IP).

### The Power of Crowdsourcing

**Crowdsourcing** — gathering information via public input and collaboration — lets threat intelligence platforms pool data from the global cybersecurity community (vendors, government agencies, cloud providers) rather than each organization working in isolation. **Information Sharing and Analysis Centers (ISACs)** collect/share sector-specific threat intelligence (energy, healthcare, etc.). OSINT can also be used to gather intelligence on threat actors, threats, and vulnerabilities.

### VirusTotal

A free service (with paid enterprise options) for analyzing suspicious files, domains, URLs, and IP addresses. A VirusTotal report includes:

- **Detection:** Third-party security vendors' verdicts (malicious, suspicious, unsafe, etc.)
- **Details:** Static analysis info (hashes, file type/size, headers, submission timestamps)
- **Relations:** Related IoCs (contacted URLs/domains/IPs, dropped files)
- **Behavior:** Observed activity from executing the artifact in a sandboxed environment (tactics/techniques, network communications, file/registry actions)
- **Community:** Comments/insights from other security professionals
- **Vendors' ratio and community score:** How many vendors flagged it malicious, plus community input — higher detections/scores suggest higher likelihood of malicious content

Note: uploads to VirusTotal are shared publicly with the community, so personal information should never be submitted.

### Other Tools

- **Jotti's malware scan:** Free scanning of suspicious files against several antivirus programs.
- **Urlscan.io:** Scans/analyzes URLs and provides a detailed report.
- **MalwareBazaar:** A free repository of malware samples for research purposes.

**Key takeaway:** Crowdsourced investigative tools like VirusTotal let analysts expand a single IoC into full context, benefiting from — and contributing to — the collective knowledge of the global security community.

---

## Reading: Best Practices for Effective Documentation

**Documentation** is any recorded content used for a specific purpose — essential for supporting investigations, completing tasks, and communicating findings. Three key benefits:

- **Transparency:** Demonstrates compliance with regulations/internal processes and supports legal proceedings — e.g., **chain of custody**, the process of documenting evidence possession/control through an incident's lifecycle.
- **Standardization:** Supports continuous improvement, knowledge transfer, and onboarding — e.g., an **incident response plan**, which outlines procedures for each incident response step and establishes a consistent, repeatable process.
- **Clarity:** Helps people quickly access and act on the information they need — documenting the reasoning behind escalating or closing an alert keeps that reasoning clear to the team.

### Best Practices

- **Know your audience:** Tailor language/detail level to who's reading (e.g., a SOC manager vs. a CEO).
- **Be concise:** State the document's purpose immediately (e.g., a report's executive summary should be brief and skimmable).
- **Update regularly:** Documentation must evolve with the threat landscape — reviewing an incident after resolution often reveals process gaps that need updating.

**Key takeaway:** Effective documentation benefits everyone in an organization — creating it well is a core, ongoing analyst skill, not a one-time task.

---

## Reading: The Triage Process

**Triage** is the prioritizing of incidents by importance/urgency, helping teams evaluate and allocate resources so the most critical issues are addressed first. Three steps:

1. **Receive and assess:** An analyst receives an alert (e.g., from an IDS) and gathers information to verify its validity — is it a false positive? Has it happened before, and how was it resolved? Is it tied to a known vulnerability? What's the severity?
2. **Assign priority:** Based on the incident's impact and scope. Key factors:
   - **Functional impact:** How the incident affects existing business functionality (e.g., ransomware making data completely inaccessible).
   - **Information impact:** Effects on confidentiality/integrity/availability of data, including impact beyond the organization itself (e.g., third-party data exfiltration).
   - **Recoverability:** Whether — and how much time/effort/cost — recovery is realistically possible.
3. **Collect and analyze:** A comprehensive analysis gathering evidence, conducting research, and documenting the investigative process, potentially escalating to a level-two analyst or manager for more advanced techniques.

### Benefits of Triage

- **Resource management:** Focuses limited time/resources on the most urgent threats.
- **Standardized approach:** Documentation like playbooks moves alerts through a consistent, iterative validation process.

**Key takeaway:** Triage lets a security team apply structured, consistent judgment to prioritize incidents — an essential skill given that not every incident carries equal urgency or business impact.

---

## Reading: Business Continuity Considerations

### Business Continuity Planning

A **business continuity plan (BCP)** outlines procedures to sustain business operations during and after a significant disruption, helping critical functions resume or be quickly restored. Distinct from a **disaster recovery plan**, which focuses specifically on recovering information systems after a major disaster (hardware failure, natural disaster, etc.). Entry-level analysts typically aren't responsible for developing/testing a BCP but should understand its role.

### Consider the Impacts of Ransomware to Business Continuity

Ransomware can be devastating to critical infrastructure like healthcare — encrypting data can disable access to medical records, and at scale, attacks on critical infrastructure can threaten national security, economic security, and public health/safety. BCPs help minimize these interruptions.

### Recovery Strategies: Site Resilience

**Resilience** is the ability to prepare for, respond to, and recover from disruptions. **Site resilience** ensures availability of networks/data centers/infrastructure during a disruption, using three recovery site types:

- **Hot sites:** Fully operational duplicates of the primary environment, activated immediately.
- **Warm sites:** Fully updated/configured but not immediately operational — can be made ready quickly.
- **Cold sites:** Have some necessary infrastructure but require additional work before use.

**Key takeaway:** BCPs help organizations understand and mitigate the operational impact of serious incidents — analysts may not build these plans, but they'll often implement preventative measures once next steps are determined by response leadership.

---

## Reading: Post-Incident Review

### Post-Incident Activity

The final phase of the NIST Incident Response Lifecycle, reviewing an incident to identify areas for improvement.

### Lessons Learned

A **lessons learned meeting** (post-mortem) brings together all involved parties after a major incident — ideally scheduled within two weeks of remediation — to evaluate what happened, assess the response, and identify improvements (not to assign blame). Common questions covered: what happened, when, who discovered it, how it was contained, what recovery actions were taken, and what could have been done differently. Not every incident needs its own meeting — size/severity dictates this — but major incidents like ransomware attacks should always get one. A meeting agenda and assigned roles (moderator, scribe) help keep the meeting productive.

### Recommendations

Lessons learned meetings should result in a list of prioritized, actionable recommendations to improve incident handling and overall security posture — e.g., updating playbook instructions or implementing new tools — ensuring the organization doesn't remain vulnerable to a repeat of the same incident.

### Final Report

Incident response documentation should at minimum cover the 5 W's: who, what, where, why, and when. The **final report** provides a comprehensive review of an incident, format varies by organization, and multiple versions may exist for different audiences. Common elements:

- **Executive summary:** A high-level summary of key findings/facts.
- **Timeline:** A detailed chronological sequence of events.
- **Investigation:** A compilation of detection/analysis actions taken (e.g., packet capture analysis findings).
- **Recommendations:** Suggested actions for future prevention.

**Key takeaway:** Post-incident activity — lessons learned meetings, recommendations, and a final report — is where a security team turns a resolved incident into concrete improvements for the future, and often the report's audience (technical vs. non-technical) shapes how it should be written.

---

## Glossary Terms from Module 3

| Term | Definition |
|------|------------|
| Analysis | The investigation and validation of alerts |
| Broken chain of custody | Inconsistencies in the collection and logging of evidence in the chain of custody |
| Business continuity plan (BCP) | A document that outlines the procedures to sustain business operations during and after a significant disruption |
| Chain of custody | The process of documenting evidence possession and control during an incident lifecycle |
| Containment | The act of limiting and preventing additional damage caused by an incident |
| Crowdsourcing | The practice of gathering information using public input and collaboration |
| Detection | The prompt discovery of security events |
| Documentation | Any form of recorded content that is used for a specific purpose |
| Eradication | The complete removal of the incident elements from all affected systems |
| Final report | Documentation that provides a comprehensive review of an incident |
| Honeypot | A system or resource created as a decoy vulnerable to attacks with the purpose of attracting potential intruders |
| Incident response plan | A document that outlines the procedures to take in each step of incident response |
| Indicators of attack (IoA) | The series of observed events that indicate a real-time incident |
| Indicators of compromise (IoC) | Observable evidence that suggests signs of a potential security incident |
| Intrusion detection system (IDS) | An application that monitors system activity and alerts on possible intrusions |
| Lessons learned meeting | A meeting that includes all involved parties after a major incident |
| Open-source intelligence (OSINT) | The collection and analysis of information from publicly available sources to generate usable intelligence |
| Playbook | A manual that provides details about any operational action |
| Post-incident activity | The process of reviewing an incident to identify areas for improvement during incident handling |
| Recovery | The process of returning affected systems back to normal operations |
| Resilience | The ability to prepare for, respond to, and recover from disruptions |
| Standards | References that inform how to set policies |
| Threat hunting | The proactive search for threats on a network |
| Threat intelligence | Evidence-based threat information that provides context about existing or emerging threats |
| Triage | The prioritizing of incidents according to their level of importance or urgency |
| VirusTotal | A service that allows anyone to analyze suspicious files, domains, URLs, and IP addresses for malicious content |

---

## Personal Reflection

The Pyramid of Pain reframed how I think about IoCs entirely — I'd been treating them as roughly interchangeable pieces of evidence, but understanding that blocking a TTP costs an attacker far more than blocking an IP address gives a much clearer sense of where to focus limited investigative time. The triage factors (functional impact, information impact, recoverability) also gave me a concrete framework for a question I'd been fuzzy on: how do you actually decide which of several open incidents to work first?
