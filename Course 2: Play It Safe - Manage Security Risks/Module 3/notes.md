# Course 2, Module 3 – SIEM Tools, Open-Source vs. Proprietary Tools, and Dashboards

## Overview

This module covered how SIEM tools work today and where they're headed, the difference between open-source and proprietary security tools, and a closer look at specific Splunk and Chronicle dashboards analysts use to monitor organizational data.

---

## Learning Objectives

After completing this module, I can:

- Describe current SIEM capabilities and where the technology is evolving
- Differentiate open-source and proprietary tools, and address common misconceptions
- Identify Splunk and Chronicle dashboards and their purposes

---

## Reading: The Future of SIEM Tools

### Current SIEM Solutions

A SIEM tool collects and analyzes log data to monitor critical organizational activity, offering real-time monitoring and tracking of security event logs across multiple dashboards. Current SIEM tools still require human interaction to analyze security events.

### The Future of SIEM Tools

SIEM tools are increasingly moving to cloud-hosted and cloud-native environments. Cloud-hosted tools are maintained by vendors and accessed via the internet — ideal for organizations that don't want to build their own infrastructure. Cloud-native tools are also vendor-managed but built to take full advantage of cloud computing (availability, flexibility, scalability).

As the Internet of Things (IoT) grows, the attack surface and volume of exploitable data grow with it. AI/ML are expected to enhance SIEM capabilities around threat-related terminology, dashboard visualization, and data storage. Security orchestration, automation, and response (SOAR) — a collection of tools/workflows that automates response to security events — is expected to handle more routine incidents, freeing analysts for complex, uncommon ones.

**Key takeaway:** Cloud computing, SIEM-application integration, and automation are the major forces shaping the next generation of SIEM tools.

---

## Reading: More About Cybersecurity Tools

### Open-Source Tools

Often free and user-friendly, built collaboratively by the public, which can make them more secure and highly customizable. Source code and training materials are available to all users, subject to license terms.

### Proprietary Tools

Developed and owned by a person or company; users typically pay for usage and training. Only the owner can access/modify source code, so users wait on vendor updates (sometimes for a fee). Examples include Splunk and Chronicle.

### Common Misconceptions

Open-source tools are sometimes wrongly assumed to be less secure than proprietary ones. In practice, wide exposure to well-intentioned developers makes it harder for malicious actors to succeed, since issues can be identified and fixed quickly by the community.

### Examples of Open-Source Tools

- **Linux:** A widely used open-source operating system, customizable via command-line interface.
- **Suricata:** An open-source network analysis and threat detection tool, developed by the Open Information Security Foundation (OISF), that inspects network traffic for suspicious behavior and integrates with many SIEM tools.

**Key takeaway:** Both open-source and proprietary tools are widely used in the profession — understanding the tradeoffs of each helps in choosing (or working with) the right tool for a given organization.

---

## Reading: Use SIEM Tools to Protect Organizations

### Splunk

Offered as Splunk Enterprise (self-hosted) and Splunk Cloud (cloud-hosted). Key dashboards:

- **Security posture dashboard:** Shows the last 24 hours of notable security events/trends for SOC use — helps determine if infrastructure and policies are performing as designed.
- **Executive summary dashboard:** Analyzes overall organizational health over time; used to brief stakeholders with high-level incident/trend summaries.
- **Incident review dashboard:** Highlights higher-risk items needing immediate review and provides a visual timeline of events leading up to an incident.
- **Risk analysis dashboard:** Shows changes in risk-related activity per risk object (user, computer, IP address) — used to prioritize mitigation efforts.

### Chronicle

A cloud-native Google SIEM tool that retains, analyzes, and searches log data by asset, domain, user, or IP address. Key dashboards:

- **Enterprise insights dashboard:** Highlights recent alerts and suspicious domain names (IOCs), each with a confidence score and severity level.
- **Data ingestion and health dashboard:** Shows event log counts, log sources, and processing success rates — used to confirm log sources are configured correctly.
- **IOC matches dashboard:** Surfaces top threats/risks/vulnerabilities by tracking domain names, IP addresses, and device IOCs over time to identify trends.
- **Main dashboard:** A high-level summary of data ingestion, alerting, and event activity — used to spot trends like a spike in failed login attempts.
- **Rule detections dashboard:** Statistics on incidents with the highest occurrence, severity, and detection frequency, tied to specific detection rules.
- **User sign-in overview dashboard:** Tracks user access behavior, such as simultaneous sign-ins from multiple locations.

**Key takeaway:** SIEM dashboards let analysts organize and focus their efforts, identifying and remediating the highest-priority items in a timely manner.

---

## Glossary Terms from Module 3

| Term | Definition |
|------|------------|
| Chronicle | A cloud-native tool designed to retain, analyze, and search data |
| Incident response | An organization's quick attempt to identify an attack, contain the damage, and correct the effects of a security breach |
| Log | A record of events that occur within an organization's systems |
| Metrics | Key technical attributes such as response time, availability, and failure rate used to assess software performance |
| Operating system (OS) | The interface between computer hardware and the user |
| Playbook | A manual that provides details about any operational action |
| Security information and event management (SIEM) | An application that collects and analyzes log data to monitor critical activities in an organization |
| Security orchestration, automation, and response (SOAR) | A collection of applications, tools, and workflows that use automation to respond to security events |
| SIEM tools | A software platform that collects, analyzes, and correlates security data across IT infrastructure to identify and respond to threats in real time |
| Splunk Cloud | A cloud-hosted tool used to collect, search, and monitor log data |
| Splunk Enterprise | A self-hosted tool used to retain, analyze, and search an organization's log data to provide security information and alerts in real time |

---

## Personal Reflection

This module made the differences between Splunk and Chronicle dashboards much more concrete than just knowing "SIEM tools exist." Seeing the specific purpose of each dashboard — security posture for real-time SOC monitoring vs. executive summary for stakeholder briefings vs. IOC matches for trend prioritization — helped me understand how an analyst would actually navigate between them during a shift rather than treating a SIEM as one big undifferentiated tool.
