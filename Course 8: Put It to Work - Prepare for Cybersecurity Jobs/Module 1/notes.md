# Course 8, Module 1 – Data/Asset Classification, Disaster Recovery, and Business Continuity

## Overview

This module covered data and asset classification types, the relationship between disaster recovery and business continuity plans, and a case-study walkthrough (Juliana Soto) applying the information lifecycle at a fictional payment processing company.

---

## Learning Objectives

After completing this module, I can:

- Classify data as public, private, sensitive, or confidential
- Explain low-level vs. high-level asset classification
- Differentiate business continuity plans from disaster recovery plans
- Apply the information lifecycle to identify and protect an organization's key assets

---

## Reading: Data and Asset Classification

### Classifying for Safety

- **Public data:** Already accessible to the public, minimal risk if shared (e.g., press releases, job descriptions, marketing materials) — still needs protection from attacks, even though it's not confidential.
- **Private data:** Should be kept from the public; unauthorized access poses a serious risk (e.g., company email addresses, employee IDs, internal research data).
- **Sensitive data:** Must be protected from anyone without authorized access; includes PII, SPII, and PHI (e.g., bank account numbers, usernames/passwords, SSNs, medical information) — unauthorized access can significantly damage an organization's finances and reputation.
- **Confidential data:** Important to ongoing business operations, often access-limited and sometimes requiring signed non-disclosure agreements (NDAs) (e.g., trade secrets, financial records, sensitive government data).

### Asset Classification

**Asset classification** labels assets by sensitivity/importance, ranging from low- to high-level. Public data is a low-level asset (minimal impact if compromised, like a company's website address); sensitive and confidential data are high-level assets (can seriously damage competitive edge, reputation, and customer trust if leaked, like an internal email discussing trade secrets).

**Key takeaway:** Every company has its own data classification policy defining what falls into each category — familiarizing yourself with it early helps prioritize what needs the most protection and what needs the least.

---

## Reading: Disaster Recovery and Business Continuity

### Identify and Protect

Creating business continuity and disaster recovery plans is the final step in a four-part security process: **identify** the assets to protect, **determine** potential threats to those assets, **implement** tools/processes to detect threats, then **create** the business continuity and disaster recovery plans (built together to minimize the impact of an incident).

### Business Continuity Plan (BCP)

Outlines procedures to sustain business operations during and after a significant disruption. Four essential steps:

1. **Conduct a business impact analysis:** Assess the possible effects of a disruption on business functions.
2. **Identify, document, and implement recovery steps:** Create actionable steps for recovering critical functions/processes.
3. **Organize a business continuity team:** Bring together members from cybersecurity, IT, HR, communications, and operations to help execute the plan.
4. **Conduct training for the team:** Work through different risk scenarios to prepare for real security threats.

### Disaster Recovery Plan

Outlines the steps needed to minimize the impact of a security incident (e.g., a ransomware attack blocking access to needed data) and resolve the underlying threat, typically created alongside the BCP. Steps include implementing recovery strategies for software and hardware, and identifying which applications/data might be affected by an incident.

**Key takeaway:** BCPs and disaster recovery plans work together — the BCP keeps the business itself running through a disruption, while the disaster recovery plan focuses specifically on restoring the affected systems and resolving the incident.

---

## Reading: Meet Juliana Soto

Juliana Soto, newly hired as a cybersecurity analyst at Right-On-Time Payment Solutions (a fictional payment processing company), spends her first day reviewing onboarding materials to understand what data the company handles — discovering that customers provide usernames/passwords, full names or company names, EINs (for business customers), and bank/debit card information. She recognizes this as a large volume of **PII**, classified as **sensitive data**, and concludes that customer data is the company's most important asset.

### Information Lifecycle Strategy

Juliana applies the four-step information lifecycle to her new role:

1. **Identify** the important assets — sensitive customer information (PII, financial data, SSNs, EINs).
2. **Assess** the security measures already in place and review information security policies (though as a first-day hire, she recognizes she isn't yet ready to run vulnerability scans herself).
3. **Protect** the identified assets — she asks to shadow a senior analyst to learn how the team monitors systems/networks.
4. **Monitor** the security processes in place — she reports her findings to her supervisor and requests to finish the day monitoring some of the company's systems.

**Key takeaway:** Even on day one, applying a structured framework like the information lifecycle — identify, assess, protect, monitor — gives a new analyst a clear, proactive way to start understanding what matters most to an organization and how it's currently being protected.

---

## Glossary Terms from Module 1

| Term | Definition |
|------|------------|
| Business continuity plan (BCP) | A document that outlines the procedures to sustain business operations during and after a significant disruption |
| Confidential data | Data that often has limits on the number of people who have access to it |
| Disaster recovery plan | A plan that allows an organization's security team to outline the steps needed to minimize the impact of a security incident |
| Private data | Information that should be kept from the public |
| Public data | Data that is already accessible to the public and poses a minimal risk to the organization if viewed or shared by others |
| Security mindset | The ability to evaluate risk and constantly seek out and identify the potential or actual breach of a system, application, or data |
| Sensitive data | A type of data that includes personally identifiable information (PII), sensitive personally identifiable information (SPII), and protected health information (PHI) |

---

## Personal Reflection

Following Juliana through her first day made the information lifecycle feel less like an abstract four-step model and more like a realistic to-do list for starting any new security role: read the onboarding materials with an eye for what data is being collected, classify it honestly, and be upfront about what you're not yet equipped to do (like running vulnerability scans on day one) while still finding a way to contribute — in her case, by shadowing and reporting back. It's a good reminder that a "security mindset" doesn't require full technical readiness on day one, just consistent, structured thinking about risk.
