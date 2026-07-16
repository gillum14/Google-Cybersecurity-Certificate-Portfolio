# Course 6, Module 1 – Incident Response Roles, Detection Tools, and SIEM Technology

## Overview

This module introduced the NIST Incident Response Lifecycle in more depth through the lens of team structure — CSIRT and SOC roles — then covered detection tools (IDS/IPS/EDR) and how SIEM technology processes and analyzes security data.

---

## Learning Objectives

After completing this module, I can:

- Describe CSIRT and SOC roles and their responsibilities
- Compare IDS, IPS, and EDR detection tools
- Explain the SIEM process: collection, normalization, and analysis

---

## Reading: Roles in Response

The **NIST Incident Response Lifecycle** has four phases: Preparation; Detection and Analysis; Containment, Eradication, and Recovery; and Post-incident activity. Effective response requires clear **command** (leadership/direction), **control** (managing technical aspects like resources/tasks), and **communication** (keeping stakeholders informed).

### Roles in CSIRTs

A **computer security incident response team (CSIRT)** is a specialized group trained in incident management and response, either a dedicated team or an as-needed task force. CSIRTs include nonsecurity professionals (HR, PR, management, IT, legal) and three key security roles:

- **Security analyst:** Continuously monitors the environment, analyzes/triages alerts, performs root-cause investigations, and escalates or resolves them.
- **Technical lead:** Manages the technical response — determines root cause, implements containment/eradication/recovery strategies, and aligns priorities with business needs (e.g., minimizing customer disruption).
- **Incident coordinator:** Coordinates with relevant external departments to keep communication open and all personnel informed of incident status.

Other roles can include a dedicated communications lead, legal lead, or planning lead, and titles vary by organization (e.g., incident commander/manager instead of incident coordinator).

### Security Operations Center (SOC)

An organizational unit dedicated to monitoring networks, systems, and devices for threats/attacks — often called the "blue team." A SOC may exist separately or within a CSIRT, structured in tiers:

- **Tier 1 (L1) analysts:** Monitor/review/prioritize alerts, create and close tickets, and escalate to Tier 2/3.
- **Tier 2 (L2) analysts:** Conduct deeper investigations on escalated tickets, configure/refine security tools, and report to the SOC lead.
- **Tier 3 (L3) SOC leads:** Manage team operations, perform advanced detection techniques (malware/forensics analysis), and report to the SOC manager.
- **SOC manager:** Hires/trains/evaluates the team, sets performance metrics, develops incident/compliance/audit reports, and communicates findings to stakeholders.

Other specialized SOC roles include **forensic investigators** (L2s/L3s who collect/preserve/analyze digital evidence) and **threat hunters** (typically L3s who proactively detect/analyze/defend against new threats using threat intelligence).

**Key takeaway:** Recognizing the organizational structure of a CSIRT or SOC — and how incidents move through their lifecycle — helps analysts collaborate effectively and understand where their own role fits during a response.

---

## Reading: Overview of Detection Tools

Detection tools function like a home security system, monitoring networks/systems and triggering alerts on suspicious activity so security professionals can investigate and respond.

### Comparison Chart

| Capability | IDS | IPS | EDR |
|---|---|---|---|
| Detects malicious activity | ✓ | ✓ | ✓ |
| Prevents intrusions | — | ✓ | ✓ |
| Logs activity | ✓ | ✓ | ✓ |
| Generates alerts | ✓ | ✓ | ✓ |
| Performs behavioral analysis | — | — | ✓ |

### IDS (Intrusion Detection System)

Continuously monitors network events and generates alerts on possible intrusions, but doesn't stop or prevent the activity — security professionals must act on the alert. Examples: Zeek, Suricata, Snort, Sagan.

**Detection categories:**

- **True positive:** An alert that correctly detects an attack.
- **True negative:** No detection, and no malicious activity actually exists.
- **False positive:** An alert incorrectly detects a threat that isn't real — wastes team time/resources.
- **False negative:** A real threat that goes undetected — dangerous, since the team remains unaware of an actual attack.

### IPS (Intrusion Prevention System)

Works like an IDS but also takes action to stop and minimize the intrusion's effects (e.g., modifying an access control list to block specific traffic). Many IDS tools (Suricata, Snort, Sagan) can also function as an IPS.

### EDR (Endpoint Detection and Response)

Installed on endpoints (computers, phones, tablets), EDR monitors, records, and analyzes endpoint activity, using behavioral analysis (machine learning/AI) to identify threat patterns and automation to stop attacks without manual intervention. Examples: Open EDR, Bitdefender EDR, FortiEDR.

**Key takeaway:** The value of detection tools lies in their ability to detect, log, alert, and — for IPS/EDR — stop malicious activity, giving security teams the awareness needed to protect networks and systems.

---

## Reading: Overview of SIEM Technology

A **SIEM** tool collects and analyzes log data to monitor critical organizational activity, supporting **log analysis** — the process of examining logs to identify events of interest.

### SIEM Advantages

- **Access to event data:** Ingests real-time activity data from potentially hundreds of connected systems/devices.
- **Monitoring, detecting, and alerting:** Continuously analyzes collected data against detection rules and generates alerts on matches.
- **Log storage:** Acts as a data retention system, providing access to historical data per organizational requirements.

### The SIEM Process

1. **Collect and aggregate data:** Event data (logs) is gathered from sources like firewalls, servers, and routers, then consolidated (aggregated) into one centralized location — eliminating the need to manually check individual data sources. **Parsing** can occur here too, mapping raw log data into readable fields and values (e.g., turning a raw log line into `host=`, `process=`, `source_user=`, etc.).
2. **Normalize data:** Converts data from many differently formatted sources into a single, standard, structured format that's easily searchable.
3. **Analyze data:** Applies detection logic (rules/conditions) to the normalized data; matching activity triggers alerts. **Correlation** — comparing multiple log events to identify common patterns — is part of this analysis step.

### SIEM Tools

Commonly used tools include AlienVault OSSIM, Chronicle, Elastic, Exabeam, IBM QRadar Security Intelligence Platform, LogRhythm, and Splunk.

**Key takeaway:** Understanding the SIEM process — collect/aggregate, normalize, analyze — supports being able to investigate log data, identify threats, and contribute to incident response even as an entry-level analyst.

---

## Glossary Terms from Module 1

| Term | Definition |
|------|------------|
| Computer security incident response teams (CSIRT) | A specialized group of security professionals that are trained in incident management and response |
| Documentation | Any form of recorded content that is used for a specific purpose |
| Endpoint detection and response (EDR) | An application that monitors an endpoint for malicious activity |
| Event | An observable occurrence on a network, system, or device |
| False negative | A state where the presence of a threat is not detected |
| False positive | An alert that incorrectly detects the presence of a threat |
| Incident | An occurrence that actually or imminently jeopardizes, without lawful authority, the confidentiality, integrity, or availability of information or an information system; or constitutes a violation or imminent threat of violation of law, security policies, security procedures, or acceptable use policies |
| Incident handler's journal | A form of documentation used in incident response |
| Incident response plan | A document that outlines the procedures to take in each step of incident response |
| Intrusion detection system (IDS) | An application that monitors system activity and alerts on possible intrusions |
| Intrusion prevention system (IPS) | An application that monitors system activity for intrusive activity and takes action to stop the activity |
| National Institute of Standards and Technology (NIST) Incident Response Lifecycle | A framework for incident response consisting of four phases: Preparation; Detection and Analysis; Containment, Eradication, and Recovery; and Post-incident activity |
| Playbook | A manual that provides details about any operational action |
| Security information and event management (SIEM) | An application that collects and analyzes log data to monitor critical activities in an organization |
| Security operations center (SOC) | An organizational unit dedicated to monitoring networks, systems, and devices for security threats or attacks |
| Security orchestration, automation, and response (SOAR) | A collection of applications, tools, and workflows that uses automation to respond to security events |
| True negative | A state where there is no detection of malicious activity |
| True positive | An alert that correctly detects the presence of an attack |

---

## Personal Reflection

Seeing the SOC tier structure (L1 → L2 → L3 → manager) laid out clearly helped me picture a realistic career progression path, not just "SOC analyst" as one flat role. The IDS/IPS/EDR comparison table was also useful for cutting through what can feel like overlapping acronyms — each tool answers a slightly different question (detect vs. detect-and-block vs. detect-and-automate-response-with-behavioral-analysis), and knowing that distinction will help me reason about which tool applies to a given scenario.
