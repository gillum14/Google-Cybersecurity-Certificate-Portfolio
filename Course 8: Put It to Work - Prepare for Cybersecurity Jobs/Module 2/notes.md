# Course 8, Module 2 – Incident Escalation

## Overview

This module focused on the purpose and process of security incident escalation, and on how entry-level analysts build the confidence and judgment to decide when and how to escalate.

---

## Learning Objectives

After completing this module, I can:

- Explain the purpose of incident escalation and the risk of failing to escalate
- Differentiate low-level security issues from significant incidents
- Describe the factors used to prioritize incident escalation

---

## Reading: Escalate with a Purpose

**Security incident escalation** is the process of identifying a potential security incident and transferring it to a more experienced department or team member. Entry-level analysts are expected to recognize potential issues (e.g., excessive failed login attempts) and report them appropriately, following the organization's specific escalation processes.

### Notification of Breaches

Many countries have breach notification laws requiring companies/government entities to notify individuals of security breaches involving PII (identification numbers, medical records, addresses, and other sensitive data). Analysts need to stay aware of applicable laws, since they're regularly updated.

### Low-Level Security Issues

Security risks that don't result in PII exposure — e.g., one failed login attempt, or an employee downloading unapproved software. These aren't major threats on their own, but still warrant investigation: a handful of failed logins could indicate a compromise attempt, and unapproved downloads could carry malware. Low-level issues should still be investigated to ensure minimal impact.

### The Escalation Process

Every company has its own protocols — who to notify, who to contact if the first responder is unavailable, and how to escalate (IT desk, incident management tool, direct communication).

**Key takeaway:** Both small and large security issues should be escalated appropriately — a company's specific escalation policy determines exactly how and to whom.

---

## Reading: Escalation Timing

### Your Decisions Matter

Security analysts make daily decisions about which events to escalate before they become major incidents — a core part of the entry-level analyst role.

### Trust Your Instincts and Ask Questions

Learning an organization's escalation policy builds the confidence to make sound decisions quickly. Asking questions when uncertain is a sign of commitment to doing the job well, not a weakness.

### All Security Events Are Not Equal

Understanding which assets/data matter most to an organization (via onboarding materials, direct conversation with a supervisor, or security policies) helps prioritize incidents correctly. Recap of incident classification types:

- **Malware infections:** Malicious software designed to disrupt a system infiltrates computers/networks.
- **Unauthorized access:** An individual gains digital or physical access to a system, data, or application without permission.
- **Improper usage:** An employee violates the organization's acceptable use policies.

Incidents directly impacting business-critical assets should always be prioritized over incidents affecting non-critical systems (e.g., unauthorized access to a manufacturing application outranks malware on a legacy system that doesn't touch business operations).

### Quick Escalation Tips

Familiarize yourself with the organization's escalation policy, follow it consistently, and ask questions whenever uncertain.

**Key takeaway:** Confident, well-prioritized escalation decisions come from knowing both the organization's escalation policy and which assets matter most — and from being willing to ask questions rather than guess.

---

## Glossary Terms from Module 2

| Term | Definition |
|------|------------|
| Data controller | A person that determines the procedure and purpose for processing data |
| Data processor | A person that is responsible for processing data on behalf of the data controller |
| Data protection officer (DPO) | An individual that is responsible for monitoring the compliance of an organization's data protection procedures |
| Escalation policy | A set of actions that outlines who should be notified when an incident alert occurs and how that incident should be handled |
| Improper usage | An incident type that occurs when an employee of an organization violates the organization's acceptable use policies |
| Incident escalation | The process of identifying a potential security incident, triaging it, and handing it off to a more experienced team member |
| Malware infection | An incident type that occurs when malicious software designed to disrupt a system infiltrates an organization's computers or network |
| Unauthorized access | An incident type that occurs when an individual gains digital or physical access to a system or an application without permission |

---

## Personal Reflection

The framing that even a single failed login "might not be of concern, but 15 attempts in 30 minutes might be" was a useful, concrete way to think about where the line sits between noise and a real signal — it's not about the event type alone, it's about frequency and context. I also appreciated the direct acknowledgment that asking questions is a sign of commitment, not incompetence; that's a reassuring thing to carry into a first analyst role where escalation judgment calls will come up constantly.
