# Course 5, Module 2 – Least Privilege, Data Lifecycle, Privacy Regulations, Cryptography, and IAM

## Overview

This module covered the principle of least privilege and account auditing, the data lifecycle and data governance, major privacy regulations, symmetric/asymmetric encryption, the evolution of hash functions, SSO and MFA, and identity and access management frameworks.

---

## Learning Objectives

After completing this module, I can:

- Explain the principle of least privilege and common account auditing approaches
- Describe the data lifecycle, data governance roles, and legally protected data types
- Differentiate information privacy from information security and name key regulations
- Compare symmetric and asymmetric encryption and common algorithms
- Explain how hash functions, salting, and rainbow tables relate to password security
- Explain how SSO and MFA strengthen authentication
- Describe IAM/AAA frameworks and common authorization models

---

## Reading: Principle of Least Privilege

The **principle of least privilege (PoLP)** grants a user only the minimum access/authorization needed to complete a task — a fundamental control supporting the CIA triad. It's closely related to **separation of duties**, which divides tasks among multiple people so no single person has complete control over a critical function.

### Limiting Access Reduces Risk

Least privilege reduces risk by limiting access to sensitive information, reducing accidental data modification/tampering/loss, and supporting system monitoring/administration.

### Determining Access and Authorization

Two questions: who is the user, and how much access do they need? Common account types: **guest** (external users like customers/vendors), **user** (staff, based on job duties), **service** (applications/software), and **privileged** (elevated/admin access). Appropriate access can change moment to moment (e.g., a support rep's access to a customer's data should end once the interaction ends).

### Auditing Account Privileges

- **Usage audits:** Review which resources an account accesses and how — checks for policy compliance and revocable unused permissions.
- **Privilege audits:** Assess whether a user's access still matches their current role, addressing **privilege creep** (accumulated, unnecessary access over time, e.g., after a promotion or team change).
- **Account change audits:** Review directory service logs for suspicious activity (e.g., repeated password change attempts) to confirm changes were made by authorized users.

**Key takeaway:** Setting up accounts with the right access level is the first step; routinely auditing usage, privileges, and account changes is what keeps least privilege effective over time.

---

## Reading: The Data Lifecycle

### The Data Lifecycle

Five stages describe how data flows through an organization: **Collect → Store → Use → Archive → Destroy.** Protecting data at each stage keeps it accessible and recoverable.

### Data Governance

A set of processes defining how an organization manages information — keeping it private, accurate, available, and secure across its lifecycle. Key roles:

- **Data owner:** Decides who can access, edit, use, or destroy the information.
- **Data custodian:** Responsible for the safe handling, transport, and storage of information (this is typically the security analyst's role).
- **Data steward:** Maintains and implements the data governance policies an organization sets.

### Legally Protected Information

- **PII:** Personally identifiable information — can be used to contact or locate someone.
- **PHI:** Protected health information — regulated by HIPAA in the U.S. and (with a similar definition) by GDPR in the EU.
- **SPII:** Sensitive PII, under stricter handling guidelines (e.g., bank account numbers, login credentials), accessed only on a need-to-know basis.

**Key takeaway:** A documented data governance policy — with clear ownership, custodianship, and stewardship — is essential to protecting information across its full lifecycle, especially the legally protected categories.

---

## Reading: Information Privacy: Regulations and Compliance

### Information Security vs. Information Privacy

**Information privacy** is about protecting against unauthorized access/distribution of data and giving people control over how their data is collected/used. **Information security (InfoSec)** is about keeping data in all states away from unauthorized users — i.e., protecting the choices privacy establishes.

### Why Privacy Matters in Security

As data collection scaled in the late 1990s/2000s, concerns grew about whether organizations had the right to collect/share personal data, and increased data collection meant increased vulnerability to abuse, misuse, or theft.

### Notable Privacy Regulations

- **GDPR:** EU rules giving data owners control over their personal information (name, address, phone, financial, medical); applies to any business handling EU residents'/citizens' data, regardless of where the business operates.
- **PCI DSS:** Financial-industry security standards protecting credit/debit card transactions against theft and fraud.
- **HIPAA:** A U.S. law requiring protection of sensitive patient health information, prohibiting disclosure without consent.

### Security Assessments and Audits

Compliance is validated through a continual two-part process: **security audits** (formal reviews of controls/policies/procedures against expectations, typically ~annual, performed internally and externally) and **security assessments** (checks of how resilient current implementations are against threats, typically every 3–6 months, usually performed internally as audit prep).

**Key takeaway:** Privacy is about giving people control over their data; security is about protecting that control. Regular audits and assessments are how organizations verify they're actually meeting the regulations (like GDPR, PCI DSS, HIPAA) that govern this.

---

## Reading: Symmetric and Asymmetric Encryption

### Types of Encryption

- **Symmetric encryption:** Uses a single secret key for both encryption and decryption — sender and receiver must both know the key.
- **Asymmetric encryption:** Uses a public/private key pair — the public key encrypts, the private key (given only to authorized users) decrypts.

### The Importance of Key Length

Ciphers are vulnerable to brute force attacks; longer key lengths mean more possibilities to try, making them more secure but slower to process — a tradeoff between speed and security.

### Approved Algorithms

**Symmetric:**
- **Triple DES (3DES):** A block cipher tracing back to DES, generating 192-bit keys; being phased out due to data-encryption limits but likely to remain for backwards compatibility.
- **AES:** One of the most secure symmetric algorithms today, generating 128/192/256-bit keys — brute forcing a 128-bit AES key is estimated to take billions of years.

**Asymmetric:**
- **RSA:** One of the first asymmetric algorithms, producing a public/private key pair with 1,024/2,048/4,096-bit keys — mainly used for highly sensitive data.
- **DSA:** Introduced by NIST in the early 1990s, generating 2,048-bit keys, often used alongside RSA in public key infrastructure.

### Generating Keys

OpenSSL is a common open-source command-line tool for generating public/private keys and verifying digital certificates. In 2014, OpenSSL disclosed the Heartbleed bug, which exposed sensitive memory data — later patched, underscoring the importance of up-to-date software.

### Obscurity Is Not Security

Per Kerckhoff's principle, a cryptographic algorithm's details (aside from the private key) should be knowable without compromising security — AES's inner workings are public, yet it remains unbreakable. Custom, secret encryption schemes have historically been cracked quickly once made public.

**Key takeaway:** Websites commonly combine both types — asymmetric encryption for small, critical data like login credentials, then symmetric encryption for the speed needed during the rest of a session — and both are increasingly required by regulations like FIPS 140-3 and GDPR.

---

## Reading: The Evolution of Hash Functions

### Origins of Hashing

Hash functions convert data of any size into a small, fixed-size value (digest) using a hash table for efficient storage/reference. **MD5**, developed by Ronald Rivest in the early 1990s, converts data into a 128-bit value (32-character string) — but its limited output size makes it vulnerable to **hash collision**, where different inputs produce the same hash value, similar to identity impersonation.

### Next-Generation Hashing

The **SHA (Secure Hashing Algorithm)** family — SHA-1, SHA-224, SHA-256, SHA-384, SHA-512 — was developed to generate longer, more collision-resistant values (the number indicates bit size), though none are entirely invulnerable to other exploits.

### Secure Password Storage

Passwords are typically stored hashed (not plaintext) so that even if an attacker accesses the database, the values can't be reversed into the original credentials.

### Rainbow Tables

A file of pre-generated hash values and their associated plaintext — essentially a dictionary of weak passwords an attacker can compare against a stolen password database.

### Adding "Salt"

**Salting** adds a random string of characters to data before hashing, producing a more unique hash and making salted data resistant to rainbow table attacks — even identical passwords ("password") will hash to different values if salted differently.

**Key takeaway:** Hashing helps validate file/document integrity and protect stored passwords, but algorithm choice matters — MD5's short digest remains vulnerable to rainbow table attacks, which is why longer SHA algorithms and salting are recommended.

---

## Reading: The Rise of SSO and MFA

### A Better Approach to Authentication

**Single sign-on (SSO)** combines several logins into one, addressing **password fatigue** (reusing passwords across services). Benefits: improved user experience, lower service-management costs, and reduced attack surface (fewer access points to target).

### How SSO Works

SSO automates trust between a user and a service provider using a trusted third party, exchanging encrypted access tokens between an identity provider and service provider — typically via **LDAP** (on-premises) and **SAML** (cloud/off-premises) protocols, often used together.

### Limitations of SSO

A single compromised password can still expose access across multiple connected services.

### MFA to the Rescue

**Multi-factor authentication (MFA)** requires two or more forms of identity verification — comparable to an ATM requiring both a card and a PIN. Verification factors:

- **Something you know:** username/password
- **Something you have:** a one-time passcode (OTP) via SMS
- **Something you are:** fingerprint or facial scan

**Key takeaway:** SSO reduces the number of access points but doesn't eliminate single-password risk on its own; combining SSO with MFA offers a streamlined user experience while keeping unauthorized users out, especially valuable in cloud environments.

---

## Reading: Identity and Access Management

Two fundamental principles: the **principle of least privilege** (minimum access needed) and **separation of duties** (dividing authorization so no one person can misuse a system alone) — together, least privilege limits individual access while separation of duties distributes responsibility.

### Identity and Access Management (IAM)

A collection of processes/technologies helping organizations manage digital identities. Both **IAM** and the earlier **AAA (authentication, authorization, accounting)** framework are designed to authenticate users, determine access privileges, and track activity — ensuring the right user gets the right resources at the right time for the right reasons.

### Authenticating Users

Verified through the three factors: knowledge, ownership, and characteristic (also remembered as "something you know, have, and are"), commonly implemented with SSO and MFA.

### User Provisioning

**User provisioning** is the process of creating and maintaining a user's digital identity (e.g., a new employee's account, configured for the access their role requires). Analysts are also involved in **deprovisioning** — removing access rights a user should no longer have.

### Granting Authorization

Three common frameworks:

- **Mandatory access control (MAC):** The strictest — access granted manually by a central authority on a strict need-to-know basis (e.g., military/government/law enforcement); also called non-discretionary control since the data owner doesn't decide access.
- **Discretionary access control (DAC):** The data owner decides access levels (e.g., sharing editor/viewer/commenter access on a shared drive folder).
- **Role-based access control (RBAC):** Authorization is determined by a user's organizational role (e.g., marketing can access analytics but not network administration).

### Access Control Technologies

A typical IAM/AAA system includes a user directory, tools for managing that directory's data, an authorization system, and an auditing system — either built in-house or licensed from a third-party vendor, each with tradeoffs in cost, time, and customization.

**Key takeaway:** IAM and AAA are the common frameworks for implementing least privilege and separation of duties; analysts are often directly involved in user provisioning/deprovisioning and in choosing/configuring the right authorization model (MAC, DAC, or RBAC) for a given resource.

---

## Glossary Terms from Module 2

| Term | Definition |
|------|------------|
| Access controls | Security controls that manage access, authorization, and accountability of information |
| Algorithm | A set of rules used to solve a problem |
| Application programming interface (API) token | A small block of encrypted code that contains information about a user |
| Asymmetric encryption | The use of a public and private key pair for encryption and decryption of data |
| Basic auth | The technology used to establish a user's request to access a server |
| Bit | The smallest unit of data measurement on a computer |
| Brute force attack | The trial and error process of discovering private information |
| Cipher | An algorithm that encrypts information |
| Cryptographic key | A mechanism that decrypts ciphertext |
| Cryptography | The process of transforming information into a form that unintended readers can't understand |
| Data custodian | Anyone or anything that's responsible for the safe handling, transport, and storage of information |
| Data owner | The person that decides who can access, edit, use, or destroy their information |
| Digital certificate | A file that verifies the identity of a public key holder |
| Encryption | The process of converting data from a readable format to an encoded format |
| Hash collision | An instance when different inputs produce the same hash value |
| Hash function | An algorithm that produces a code that can't be decrypted |
| Hash table | A data structure that's used to store and reference hash values |
| Identity and access management (IAM) | A collection of processes and technologies that helps organizations manage digital identities in their environment |
| Multi-factor authentication (MFA) | A security measure that requires a user to verify their identity in two or more ways to access a system or network |
| Non-repudiation | The concept that the authenticity of information can't be denied |
| OAuth | An open-standard authorization protocol that shares designated access between applications |
| Payment Card Industry Data Security Standards (PCI DSS) | A set of security standards formed by major organizations in the financial industry |
| Personally identifiable information (PII) | Any information used to infer an individual's identity |
| Principle of least privilege | The concept of granting only the minimal access and authorization required to complete a task or function |
| Protected health information (PHI) | Information that relates to the past, present, or future physical or mental health or condition of an individual |
| Public key infrastructure (PKI) | An encryption framework that secures the exchange of online information |
| Rainbow table | A file of pre-generated hash values and their associated plaintext |
| Salting | An additional safeguard that's used to strengthen hash functions |
| Security assessment | A check to determine how resilient current security implementations are against threats |
| Security audit | A review of an organization's security controls, policies, and procedures against a set of expectations |
| Security controls | Safeguards designed to reduce specific security risks |
| Separation of duties | The principle that users should not be given levels of authorization that would allow them to misuse a system |
| Session | A sequence of network HTTP basic auth requests and responses associated with the same user |
| Session cookie | A token that websites use to validate a session and determine how long that session should last |
| Session hijacking | An event when attackers obtain a legitimate user's session ID |
| Session ID | A unique token that identifies a user and their device while accessing a system |
| Single Sign-On (SSO) | A technology that combines several different logins into one |
| Symmetric encryption | The use of a single secret key to exchange information |
| User provisioning | The process of creating and maintaining a user's digital identity |

---

## Personal Reflection

This module packed in a lot of terminology that I'd seen used loosely before — least privilege vs. separation of duties, privacy vs. security, MAC vs. DAC vs. RBAC — and it was useful to see each pair defined precisely against the other rather than in isolation. The hashing section in particular reframed something I'd taken for granted: "hashed" doesn't automatically mean "secure" if the algorithm (MD5) and lack of salting leave it exposed to rainbow tables. That distinction between hashing as a concept and hashing done well feels like an important nuance to carry forward.
