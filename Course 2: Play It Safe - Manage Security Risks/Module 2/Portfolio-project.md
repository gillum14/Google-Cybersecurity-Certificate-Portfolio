# Internal Security Audit – Botium Toys

## Executive Summary

This internal security audit was conducted for the fictional organization **Botium Toys** using the **National Institute of Standards and Technology Cybersecurity Framework (NIST CSF)**. The purpose of the assessment was to evaluate the organization's current security posture, identify weaknesses in administrative, technical, and physical controls, and assess compliance with applicable industry standards.

The assessment identified several critical security gaps, particularly in identity and access management, data protection, incident detection, and business continuity planning. While the organization has implemented several effective physical and technical safeguards, additional controls are required to reduce organizational risk and achieve compliance with regulatory standards.

**Overall Risk Rating:** 🔴 **High (8/10)**

---

# Objective

Evaluate Botium Toys' existing security controls and regulatory compliance to identify risks, prioritize remediation efforts, and provide recommendations for improving the organization's overall cybersecurity posture.

---

# Scope

The assessment evaluated:

- Administrative security controls
- Technical security controls
- Physical security controls
- Regulatory compliance
- Organizational risk exposure

The audit was performed using guidance from the **NIST Cybersecurity Framework (CSF)**.

---

# Framework

**Security Framework**

- National Institute of Standards and Technology Cybersecurity Framework (NIST CSF)

---

# Security Controls Assessment

## Administrative Controls

| Control | Status | Recommendation |
|---------|--------|----------------|
| Least Privilege | ❌ Not Implemented | Implement Role-Based Access Control (RBAC) to restrict access based on job responsibilities. |
| Disaster Recovery Plan | ❌ Not Implemented | Develop and regularly test disaster recovery and business continuity plans. |
| Password Policy | ⚠️ Partially Implemented | Require strong passwords (minimum 12 characters), complexity requirements, and MFA where possible. |
| Access Control Policy | ❌ Not Implemented | Develop formal access control policies based on least privilege and separation of duties. |
| Account Management | ❌ Not Implemented | Implement centralized account lifecycle management for provisioning, modifying, and disabling accounts. |
| Separation of Duties | ❌ Not Implemented | Separate critical responsibilities to reduce insider threats and fraud. |

---

## Technical Controls

| Control | Status | Recommendation |
|---------|--------|----------------|
| Firewall | ✅ Implemented | Continue monitoring firewall rules and conduct periodic rule reviews. |
| Intrusion Detection / Prevention (IDS/IPS) | ❌ Not Implemented | Deploy IDS/IPS to monitor and respond to suspicious network activity. |
| Encryption | ❌ Not Implemented | Encrypt payment card and sensitive customer data both at rest and in transit. |
| Backups | ❌ Not Implemented | Implement automated backups with secure offsite or cloud storage and regularly test restoration procedures. |
| Password Management System | ❌ Not Implemented | Deploy centralized password management for secure credential storage and enforcement of password policies. |
| Antivirus Software | ✅ Implemented | Continue maintaining antivirus protection and automatic signature updates. |
| Legacy System Monitoring | ⚠️ Partially Implemented | Develop documented maintenance schedules and migration plans for legacy systems. |

---

## Physical Controls

| Control | Status | Recommendation |
|---------|--------|----------------|
| CCTV | ✅ Implemented | Continue regular maintenance and testing. |
| Physical Locks | ✅ Implemented | Existing controls are sufficient. |
| Fire Detection & Prevention | ✅ Implemented | Continue regular inspection and testing of fire protection systems. |
| Locking Cabinets for Network Equipment | ❌ Not Implemented | Secure networking equipment in locked cabinets to prevent unauthorized physical access. |
| Time-Controlled Safe | ❌ Not Implemented | Secure sensitive documents, backup media, and cash receipts within a time-controlled safe. |
| Adequate Exterior Lighting | ⚠️ Not Verified | Assess and improve exterior lighting around entrances and loading areas. |
| Alarm Service Signage | ⚠️ Not Verified | Install monitored alarm signage to deter unauthorized access. |

---

# Compliance Assessment

| Compliance Standard | Applicability | Current Status | Recommendation |
|--------------------|--------------|----------------|----------------|
| PCI DSS | ✅ Applicable | ❌ Not Compliant | Encrypt payment data, implement strong authentication, deploy IDS, and strengthen access controls. |
| GDPR | ✅ Applicable | ⚠️ Partially Compliant | Improve encryption, access controls, and breach notification procedures for EU customer data. |
| SOC 1 | ⚠️ Potentially Applicable | ⚠️ Limited | Improve controls surrounding financial reporting and payment processing. |
| SOC 2 | ✅ Applicable | ❌ Not Compliant | Strengthen controls related to Security, Availability, Confidentiality, Processing Integrity, and Privacy. |

---

# Key Findings

The assessment identified several significant security weaknesses:

- Excessive employee access to sensitive information
- Lack of encryption for customer payment data
- No disaster recovery or business continuity plan
- No intrusion detection or intrusion prevention capability
- Weak password requirements
- No centralized password management solution
- Undefined maintenance procedures for legacy systems

---

# Risk Assessment

**Overall Organizational Risk:** 🔴 **High (8/10)**

Primary factors contributing to the elevated risk include:

- Unauthorized access to sensitive data
- Potential payment card compromise
- Increased ransomware exposure
- Regulatory non-compliance
- Limited incident detection capability
- Potential operational disruption due to inadequate disaster recovery planning

---

# Recommendations

## High Priority

- Implement Role-Based Access Control (RBAC) following the principle of least privilege.
- Encrypt all customer payment information both at rest and in transit.
- Deploy an Intrusion Detection and Prevention System (IDS/IPS).
- Implement automated backups and establish disaster recovery procedures.
- Strengthen password policies and deploy centralized password management.

---

## Medium Priority

- Develop formal account lifecycle management procedures.
- Establish documented maintenance schedules for legacy systems.
- Secure networking equipment within locking cabinets.

---

## Low Priority

- Improve physical security through monitored alarm signage.
- Verify adequate exterior lighting around facilities.
- Consider implementing a time-controlled safe for sensitive materials.

---

# Skills Demonstrated

- Security Auditing
- Risk Assessment
- NIST Cybersecurity Framework (CSF)
- Administrative Security Controls
- Technical Security Controls
- Physical Security Controls
- Compliance Assessment
- PCI DSS
- GDPR
- SOC 1
- SOC 2
- Identity and Access Management (IAM)
- Risk Prioritization
- Technical Documentation

---

# Lessons Learned

This project provided practical experience applying the **NIST Cybersecurity Framework (CSF)** to assess an organization's security posture. I evaluated administrative, technical, and physical controls, identified areas of elevated risk, assessed compliance with industry standards, and developed prioritized remediation recommendations. The exercise reinforced the importance of layered security controls, least privilege, business continuity planning, and clear technical documentation in reducing organizational risk.
