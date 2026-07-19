# Incident Report Analysis – ICMP Flood Denial-of-Service (DoS) Attack

| Project | Incident Report Analysis |
|----------|--------------------------|
| Organization | Multimedia Company (Fictional) |
| Framework | NIST Cybersecurity Framework (CSF) |
| Incident Type | ICMP Flood Denial-of-Service (DoS) |
| Course | Google Cybersecurity Professional Certificate |
| Skills | Incident Response, NIST CSF, Network Security, Firewall Configuration, IDS/IPS, SIEM, Technical Documentation |

---

# Executive Summary

This incident report analyzes an **ICMP Flood Denial-of-Service (DoS) attack** against a fictional multimedia company using the **National Institute of Standards and Technology Cybersecurity Framework (NIST CSF)**.

The attack exploited an improperly configured firewall, allowing excessive ICMP echo request packets to overwhelm the organization's internal network. As a result, internal network services became unavailable for approximately two hours, disrupting normal business operations.

The incident response team successfully restored critical services by blocking malicious ICMP traffic, temporarily disabling non-essential services, and implementing additional security controls. This report evaluates the incident and outlines recommendations to improve the organization's security posture and resilience against future attacks.

---

# Objective

Analyze the network security incident using the **NIST Cybersecurity Framework (CSF)** and develop recommendations to improve network security, incident detection, response procedures, and organizational resilience.

---

# Scope

This assessment evaluates:

- The ICMP Flood DoS attack
- Firewall configuration weaknesses
- Network security controls
- Detection capabilities
- Incident response procedures
- Recovery planning

---

# Framework

**National Institute of Standards and Technology Cybersecurity Framework (NIST CSF)**

The incident is analyzed using the five CSF functions:

- Identify
- Protect
- Detect
- Respond
- Recover

---

# Incident Summary

## Attack Type

**Denial-of-Service (DoS) — ICMP Flood**

## Attack Vector

A malicious external actor exploited an improperly configured firewall by sending a large volume of ICMP echo request packets (ping flood), exhausting network resources and preventing legitimate traffic from reaching internal services.

## Root Cause

- Firewall allowed unrestricted inbound ICMP traffic
- No ICMP rate limiting
- No IDS/IPS protection
- Limited network traffic monitoring

## Affected Assets

- Internal corporate network
- Firewall
- Network infrastructure
- Internal business services
- Employee access to shared resources

## Business Impact

- Internal network unavailable for approximately two hours
- Temporary disruption of business operations
- Employees unable to access internal resources
- No evidence of data compromise or unauthorized access

## Initial Response

- Blocked incoming ICMP traffic
- Disabled non-critical network services
- Restored critical business services
- Investigated firewall configuration
- Implemented additional security controls

---

# NIST CSF Analysis

## 1. Identify

### Security Event

External ICMP Flood Denial-of-Service attack targeting network availability.

### Risks Identified

- Misconfigured firewall
- Lack of ICMP rate limiting
- Absence of IDS/IPS
- Limited visibility into network traffic
- Insufficient monitoring capabilities

### Assets at Risk

- Network availability
- Business operations
- Employee productivity
- Organizational reputation

---

## 2. Protect

### Recommended Security Controls

- Configure firewall rules to restrict unnecessary ICMP traffic
- Enable ICMP rate limiting
- Implement source IP verification
- Segment critical network resources
- Maintain secure firewall configuration baselines
- Conduct regular firewall configuration audits
- Establish formal change management procedures
- Provide administrator security training

### Long-Term Improvements

- Perform routine vulnerability assessments
- Maintain documented security baselines
- Periodically review firewall rules
- Apply the Principle of Least Privilege for network administration

---

## 3. Detect

### Monitoring Enhancements

Implement:

- Continuous network traffic monitoring
- Intrusion Detection and Prevention System (IDS/IPS)
- Security Information and Event Management (SIEM)
- Firewall log monitoring
- ICMP threshold alerts
- Network performance monitoring
- Automated anomaly detection

### Detection Objectives

Monitor for:

- Excessive ICMP traffic
- Spoofed IP addresses
- Unauthorized network access attempts
- Network performance degradation
- Abnormal bandwidth utilization

---

## 4. Respond

### Containment

- Block malicious source IP addresses
- Apply emergency firewall rules
- Enable ICMP rate limiting
- Isolate affected network segments when necessary

### Eradication

- Eliminate malicious traffic
- Verify firewall configurations
- Confirm IDS/IPS functionality
- Inspect affected systems for additional compromise

### Investigation

Collect and analyze:

- Firewall logs
- IDS/IPS alerts
- Packet captures
- Event logs
- Source IP information
- Attack timeline

### Lessons Learned

- Conduct post-incident reviews
- Improve incident response documentation
- Strengthen detection capabilities
- Refine firewall configuration standards

---

## 5. Recover

### Recovery Objectives

Restore:

- Internal network services
- Critical business applications
- Employee network access
- Normal network performance

### Recovery Activities

- Verify network stability
- Confirm firewall protections
- Validate IDS/IPS operation
- Monitor for recurring malicious activity
- Communicate recovery status
- Document incident findings

### Recovery Improvements

- Develop a Disaster Recovery Plan (DRP)
- Create a Business Continuity Plan (BCP)
- Regularly test incident response procedures
- Conduct tabletop exercises
- Maintain current network documentation
- Schedule recurring security audits

---

# Recommendations

| Priority | Recommendation | Expected Benefit |
|-----------|---------------|------------------|
| High | Configure ICMP rate limiting | Prevent future ICMP flood attacks |
| High | Deploy IDS/IPS | Improve detection and automated response |
| High | Implement SIEM | Centralized monitoring and faster incident response |
| High | Conduct firewall configuration audits | Reduce configuration-related vulnerabilities |
| Medium | Implement network segmentation | Limit impact of future attacks |
| Medium | Provide administrator security training | Reduce configuration errors |
| Medium | Conduct regular vulnerability assessments | Identify weaknesses before exploitation |
| Low | Perform annual incident response exercises | Improve organizational preparedness |

---

# Skills Demonstrated

- Incident Response
- Network Security
- NIST Cybersecurity Framework (CSF)
- Firewall Security
- Intrusion Detection & Prevention (IDS/IPS)
- Security Information and Event Management (SIEM)
- Network Monitoring
- Risk Assessment
- Technical Documentation
- Security Recommendations

---

# Lessons Learned

This project provided hands-on experience analyzing a network-based denial-of-service attack using the **NIST Cybersecurity Framework (CSF)**. I applied structured incident response principles to identify the root cause, evaluate organizational risk, recommend security improvements, and document recovery procedures. The exercise reinforced the importance of defense-in-depth, proactive monitoring, secure firewall configuration, and comprehensive incident response planning in protecting organizational assets.

---
