# Course 5, Module 4 – Threats to Asset Security

## Overview

This module covered social engineering and its common tactics, the evolution and types of phishing, malware types and cryptojacking, web-based exploits (XSS and SQL injection), and threat modeling frameworks (including PASTA) for proactively securing applications.

---

## Learning Objectives

After completing this module, I can:

- Explain social engineering, its stages, and common tactics
- Trace the origins and evolution of phishing and identify its common forms
- Identify common malware types and how they spread, including cryptojacking
- Explain XSS and SQL injection attacks and how to prevent them
- Describe the six-step threat modeling process and the PASTA framework's seven stages

---

## Video: Understanding Social Engineering

### Understanding Social Engineering

**Social engineering** is a manipulation technique exploiting human error to gain private information, access, or valuables. Unlike malicious hackers who rely on programming skills, social engineers use traditional manipulation tactics.

### Stages of a Social Engineering Attack

1. **Preparation:** Gathering information about the target to determine the best exploitation method.
2. **Establishing trust (pretexting):** Using gathered information and disguises to build a false sense of trust.
3. **Persuasion:** Manipulating the target into volunteering information, often by impersonating legitimate organization members.
4. **Disconnection:** Breaking communication after obtaining the desired information, to cover tracks.

### Prevention and Defense

Managerial controls — policies, standards, procedures (e.g., patch management standards) — are a crucial first line of defense. Staying informed on current trends and sharing knowledge about warning signs significantly helps prevent these threats.

**Key takeaway:** Social engineering follows a repeatable four-stage pattern (prepare, build trust, persuade, disconnect) — recognizing this structure helps in spotting an attack mid-sequence, not just after the fact.

---

## Reading: Social Engineering Tactics

### Social Engineering Risks

Preys on natural feelings of curiosity, generosity, and excitement, turning them against the target's better judgment. The 2020 **Twitter Hack** is a high-profile example: attackers phoned Twitter employees pretending to be IT, gaining access to internal tools and taking over high-profile accounts — without needing sophisticated computer skills. Defending against this requires a multi-layered approach combining technological controls with user awareness.

### Signs of an Attack

- **Baiting:** Tempts people into compromising their security (e.g., USB baiting — an infected USB drive left for someone to find and plug in).
- **Phishing:** Digital communications tricking people into revealing sensitive data or deploying malicious software — one of the most common forms, typically via email.
- **Quid pro quo:** A type of baiting promising a reward in exchange for access/information/money (e.g., impersonating a loan officer offering a lower interest rate in exchange for account details).
- **Tailgating (piggybacking):** Unauthorized people following an authorized person into a restricted area.
- **Watering hole:** Compromising a website frequently visited by a specific group (e.g., the 2020 Holy Water attack, which infected religious/charity/volunteer sites).

### Encouraging Caution

Three areas of security training: stay alert to suspicious communications/unknown people (watch for spelling errors, verify sender info), be cautious sharing information (especially on social media, which attackers mine for useful details), and control curiosity around anything that seems too good to be true. Pro tip: layering technologies like firewalls, MFA, block lists, and email filtering helps even if someone makes a mistake. Extending training beyond employees to customers, and documenting best practices, are also part of an analyst's role.

**Key takeaway:** People's natural trust and helpfulness — not a technical flaw — is what social engineering exploits, so effective controls combine technology (MFA, filtering) with ongoing human awareness training.

---

## Video: Phishing Kits and Attack Types

### Phishing Kits and Their Tools

**Phishing kits** are collections of software tools that let people with limited technical expertise launch phishing campaigns — typically including malicious attachments, fake data collection forms, and fraudulent web links mimicking legitimate sources.

### Types of Phishing Attacks

While email is the most common vector, **smishing** (via text message) and **vishing** (via voice communication) are also used, often impersonating known sources/organizations to gain trust and extract data.

### Prevention and Mitigation Strategies

Anti-phishing policies and employee training raise awareness; technical measures like email filters (blocklists/allowlists) and intrusion prevention systems detect, quarantine, and log suspicious email activity.

**Key takeaway:** Phishing kits lower the technical barrier to launching an attack, which is part of why phishing (in all its forms — email, smishing, vishing) remains so persistently common.

---

## Reading: Types of Phishing

### The Origins of Phishing

Traceable to the 1990s, as the newly accessible internet attracted malicious actors seeking anonymity. One of the earliest instances targeted **AOL Instant Messenger (AIM)** users with emails requesting account verification/billing info, using official-looking logos/colors/fonts — an early example of **mass phishing** (sending malicious emails broadly to increase the odds of success). AOL was forced to adapt security policies and warn users in response.

### How Phishing Has Evolved

As e-commerce grew in the early 2000s, phishing techniques expanded. Five common types every analyst should know:

- **Email phishing:** Messages pretending to be a trusted person/entity.
- **Smishing:** Uses SMS/text messaging services (iMessage, WhatsApp, etc.).
- **Vishing:** Uses voice calls/messages to extract personal information.
- **Spear phishing:** A subset of email phishing targeting specific people (e.g., a small business's accountants).
- **Whaling:** Spear phishing aimed at high-ranking executives.

By late 2003, attackers were creating fraudulent websites resembling eBay/PayPal and running mass phishing campaigns to distribute malware against e-commerce/banking sites.

### Recent Trends

Starting in the 2010s, attackers shifted toward **targeted phishing** — highly customized attacks sent to specific targets to build a strong sense of familiarity. **Angler phishing**, a targeted variant, impersonates customer service reps on social media, intercepting public complaints and offering to "fix" the problem in exchange for sensitive information.

**Key takeaway:** There's no purely technological fix for phishing — awareness and training remain the most effective mitigation, and phishing's evolution (mass → targeted → angler) shows attackers consistently adapting to wherever people communicate.

---

## Video: Malware Overview

### Malware: An Overview

**Malware** (malicious software) is designed to harm devices/networks, spreading via infected USB drives or online between connected computers. Once installed, it disrupts normal operations, letting attackers take control without the user's knowledge.

### Common Types of Malware

- **Viruses:** Malicious code interfering with computer operations/damaging data; hides in trusted applications and requires user activation to spread.
- **Worms:** Self-replicating malware that spreads across networks independently, without user action.
- **Trojans:** Malware disguised as a legitimate file/program, tricking users into installing it — often used to gain access and install further malware like ransomware.
- **Ransomware:** Encrypts an organization's data and demands payment for restoration, making its presence known to collect money.
- **Spyware:** Gathers and sells information without consent, stealing sensitive data like login credentials and PINs.

**Key takeaway:** Malware types differ mainly in how they spread (user activation vs. self-replication vs. disguise) and what they're built to accomplish once inside — recognizing the mechanism helps predict the likely damage.

---

## Reading: An Introduction to Malware

- **Virus:** Interferes with operations/damages data, must be installed by the user (e.g., via a phishing link/attachment) before it spreads.
- **Worm:** Duplicates/spreads on its own after user installation, often targeting shared-access devices/drives/files over a network. Example: the **Blaster worm**, which forced Windows XP/2000 machines into a shutdown/restart loop in the early 2000s, spreading to hundreds of thousands of users; worms were more popular attacks in the mid-2000s than they are now.
- **Trojan (Trojan horse):** Looks like a legitimate file/program, hidden in downloads to trick users into installing malware that can spy on them or grant further access.
- **Adware:** Legitimate software displaying digital ads, often used to lower production costs or offer free products (freeware/shareware) — monetized via ad revenue rather than at users' direct expense. Malicious adware falls under **potentially unwanted applications (PUAs)** — unwanted software bundled with legitimate programs that can display ads, slow devices, or install other software, sometimes hijacking ad monetization even after a user declines ads.
- **Spyware:** A PUA that gathers/sells information without consent, commonly hidden in **bundleware** (extra software packaged with other applications) — a growing challenge in the open-source ecosystem since developers may overlook how their software could be misused.
- **Scareware:** A PUA using fake warnings (appearing to come from legitimate companies) to frighten users into infecting their own device, spread via email/pop-ups.
- **Fileless malware:** Doesn't require installation — uses already-installed legitimate programs, residing in memory rather than on disk, making it stealthier than file-based malware. Detected via memory analysis, which requires OS experience.
- **Rootkit:** Provides remote administrative access, often opening a backdoor for installing further malware or conducting network attacks. Commonly spread via a **dropper** (malware packed with malicious code, disguised as a legitimate file to trick a target into opening/"dropping" it) and, for multi-staged attacks, a **loader** (malware that downloads further malicious code from an external source) — loaders can be used to set up a botnet.
- **Botnet:** A collection of malware-infected computers ("bots") controlled by a single "bot-herder," typically spread via viruses/worms/trojans, then grown via file sharing, email, or social media protocols; infected bots report back to the bot-herder, who can execute remote commands.
- **Ransomware:** Encrypts an organization's data and demands payment for restoration — increasingly sophisticated per CISA. Example: **WannaCry**, which encrypted victims' computers until a cryptocurrency ransom was paid.

**Key takeaway:** Malware is complex enough to be its own specialization, but even without specializing, recognizing each type and its spread mechanism is core to defending against these attacks as an analyst.

---

## Video: Malware Evolution and Cryptojacking

### Malware Evolution and Cryptojacking

Malware has shifted from digital vandalism to a profitable criminal enterprise. **Cryptojacking** is a recent malware form that illegally installs software to mine cryptocurrencies (digital money with real-world value).

### How Cryptojacking Works

Crypto mining runs software that processes encrypted code to discover new coins, similar to mining physical resources. Cryptojacking malware gains unauthorized control of personal computers or targets vulnerable servers to run mining software in the background, often undetected.

### Detection and Prevention

IDS tools monitor for abnormal activity like unauthorized mining and alert security personnel. Subtle infection signs: system slowdowns, increased CPU usage, sudden crashes, fast-draining batteries, and unusually high electricity costs.

**Key takeaway:** Cryptojacking illustrates malware's shift toward direct financial motive — since it doesn't destroy or lock data like ransomware, it can go undetected for a long time, making physical/performance symptoms (battery drain, electricity cost) important detection clues.

---

## Video: Web-Based Exploits and XSS

### Web-Based Exploits and Injection Attacks

**Web-based exploits** leverage coding flaws in web applications for unauthorized access/control. **Injection attacks** insert malicious code into a vulnerable application, which then runs in the background without the user's knowledge.

### Cross-Site Scripting (XSS)

A common injection attack exploiting HTML/JavaScript to inject code into websites/web applications, potentially exposing sensitive data like session cookies, geolocation, or even webcam/microphone access.

### Types of XSS Attacks

- **Reflected XSS:** A malicious script is sent to the server and reflected back to the user's browser, which executes it.
- **Stored XSS:** Malicious scripts are injected directly into the server, affecting elements that load whenever a user visits the site.
- **DOM-based XSS:** Malicious scripts exist within the page's Document Object Model (DOM) and execute in the browser without ever being sent to the server.

**Key takeaway:** All three XSS variants exploit the same underlying weakness (unsanitized code execution in a browser context), but differ in exactly where the malicious script lives and how it gets triggered.

---

## Video: SQL Injection

### Understanding SQL and Web Applications

**SQL** is the programming language most web applications use to manage/retrieve database information — website menus/buttons trigger SQL queries in the background that users don't directly see.

### How SQL Injection Works

Occurs when websites don't properly sanitize user input, letting attackers insert malicious SQL code into input fields — potentially executing unexpected queries that steal data, modify information, or grant administrative control.

### Defending Against SQL Injection

The primary defense is sanitizing input — writing code that searches for and handles specific SQL characters. **Prepared statements** (a technique that executes/validates SQL statements before user input is passed to the database) are a key defense, preventing malicious code from running.

**Key takeaway:** SQL injection exploits the same root cause as most injection attacks — trusting user input without sanitizing it — which is why input handling (sanitization, validation, prepared statements) is the consistent theme across defenses.

---

## Reading: SQL Injection Deep Dive

### SQL Queries

A **database** is an organized collection of information; in SQL, this data is organized into tables. A **SQL query** is a request for data from a database (e.g., pulling employee IDs/names/titles). SQL injections can occur anywhere a vulnerable application accepts a query, typically through **input fields** (login forms, search bars, comment boxes) that aren't programmed to filter unwanted text.

### SQL Injection Categories

- **In-band (classic):** The most common type — uses the same communication channel to launch the attack and gather results (e.g., a vulnerable search box returning sensitive data directly in its own results).
- **Out-of-band:** Uses a different communication channel to launch the attack and gather results (e.g., connecting a vulnerable website to an attacker-controlled database) — uncommon, since it requires specific server features to be enabled.
- **Inferential:** The attacker can't directly see the attack's results but infers them by analyzing system behavior — e.g., using an error message from a login form to deduce the database's structure.

### Injection Prevention

Because SQL queries are often programmed assuming users will input only relevant, correctly formatted information, **escaping user inputs** is key to prevention:

- **Prepared statements:** Execute SQL statements before passing them to the database.
- **Input sanitization:** Programming that removes user input that could be interpreted as code.
- **Input validation:** Programming that ensures user input meets a system's expectations.

**Key takeaway:** SQL injection's popularity as an attack vector traces directly to SQL's popularity with developers — since developers often prioritize functionality over injection-proofing, analysts frequently need to collaborate directly with app developers to close these gaps.

---

## Video: Threat Modeling Process

### Threat Modeling Process

A detailed examination of entire systems, applications, or business processes from a security perspective — an advanced skill typically led by experienced professionals, though broader team involvement is common.

### Six Steps of Threat Modeling

1. **Define scope and identify threats:** Inventory/classify assets, identify potential threat actors (internal/external), and map threats to assets using an **attack tree**.
2. **Characterize environment and analyze threats:** Adopt an attacker mindset to understand how users (including external partners) interact with the system, then examine existing protections to identify gaps and rank threats by risk score.
3. **Mitigate risk and evaluate findings:** Develop a plan to defend against threats (avoid, transfer, reduce, or accept risk), then document the entire process, apply fixes, and record lessons learned for future threat models.

**Key takeaway:** Threat modeling isn't a one-time technical scan — it's a structured, repeatable cycle that starts with an attacker's perspective and ends with documented, applied fixes plus lessons learned for next time.

---

## Video: The PASTA Framework

### Defining Objectives and Scope

- **Stage 1 – Define business and security objectives:** Establish goals (e.g., protecting customer data) and ask how PII is handled to evaluate potential threat impacts.
- **Stage 2 – Define the technical scope:** Identify application components needing evaluation — technology for data at rest/in use, network protocols, security controls.

### Analyzing the Application and Threats

- **Stage 3 – Decompose the application:** Work with developers to build a data flow diagram, identifying existing controls protecting user data as it moves from a user's device to the company database.
- **Stage 4 – Perform a threat analysis:** Adopt an attacker mindset, researching current attack methods/vectors relevant to the application type (e.g., mobile apps), which change regularly.

### Vulnerability, Attack, and Risk Analysis

- **Stage 5 – Perform a vulnerability analysis:** Investigate potential vulnerabilities in depth, focusing on root causes.
- **Stage 6 – Conduct attack modeling:** Simulate attacks using attack trees (flowcharts) to test identified vulnerabilities (e.g., SQL injection vulnerabilities in a database).
- **Stage 7 – Analyze risk and impact:** Compile all gathered information into informed risk management recommendations for business stakeholders, aligned with their security goals.

**Key takeaway:** PASTA's seven stages walk from high-level business goals down to specific simulated attacks and back up to stakeholder-facing recommendations — a full loop connecting technical vulnerability work to business risk decisions.

---

## Reading: Threat Modeling and Application Security

### Why Application Security Matters

Web and mobile applications are central to how businesses/customers connect and exchange data, making application security key to reducing risk broadly. Example: an unpatched Log4Shell vulnerability (CVE-2021-44228) in Java-based logging libraries can allow remote code execution and full system access — a single critical vulnerability like this can impact millions of devices.

### Defending the Application Layer

Threat modeling is a primary way to ensure an application meets security requirements, usually performed by a **DevSecOps** (development, security, operations) team, in a cycle: define scope, identify threats, characterize environment, analyze threats, mitigate risks, evaluate findings. Ideally performed before, during, and after development — incorporated at every stage of the software development lifecycle (SDLC).

### Common Frameworks

- **STRIDE:** Developed by Microsoft, identifying vulnerabilities across six vectors — spoofing, tampering, repudiation, information disclosure, denial of service, elevation of privilege.
- **PASTA:** A risk-centric, evidence-based, seven-stage process developed by two OWASP leaders and supported by VerSprite, applicable to an application or its supporting environment.
- **Trike:** An open-source, security-centric methodology/tool focused on security permissions, application use cases, and privilege models.
- **VAST:** Part of the automated ThreatModeler platform, used to streamline/automate threat modeling assessments.

The "right" framework depends on the situation and the specific risks an application faces.

### Participating in Threat Modeling

Rarely done alone. Key questions to guide the process: What are we working on? What can go wrong? What are we doing about it? Have we addressed everything? Did we do a good job? Even less-experienced analysts can be valuable contributors by applying an attacker mindset and thinking critically about data handling.

**Key takeaway:** No single threat modeling framework is universally "best" — STRIDE, PASTA, Trike, and VAST each suit different situations, but all of them start from the same five guiding questions about what's being protected and what could go wrong.

---

## Glossary Terms from Module 4

| Term | Definition |
|------|------------|
| Angler phishing | A technique where attackers impersonate customer service representatives on social media |
| Advanced persistent threat (APT) | Instances when a threat actor maintains unauthorized access to a system for an extended period of time |
| Adware | A type of legitimate software that is sometimes used to display digital advertisements in applications |
| Attack tree | A diagram that maps threats to assets |
| Baiting | A social engineering tactic that tempts people into compromising their security |
| Botnet | A collection of computers infected by malware that are under the control of a single threat actor, known as the "bot-herder" |
| Cross-site scripting (XSS) | An injection attack that inserts code into a vulnerable website or web application |
| Cryptojacking | A form of malware that installs software to illegally mine cryptocurrencies |
| DOM-based XSS attack | An instance when malicious script exists in the webpage a browser loads |
| Dropper | A type of malware that comes packed with malicious code which is delivered and installed onto a target system |
| Fileless malware | Malware that does not need to be installed by the user because it uses legitimate programs that are already installed to infect a computer |
| Hacker | Any person or group who uses computers to gain unauthorized access to data |
| Identity and access management (IAM) | A collection of processes and technologies that helps organizations manage digital identities in their environment |
| Injection attack | Malicious code inserted into a vulnerable application |
| Input validation | Programming that validates inputs from users and other programs |
| Intrusion detection system (IDS) | An application that monitors system activity and alerts on possible intrusions |
| Loader | A type of malware that downloads strains of malicious code from an external source and installs them onto a target system |
| Malware | Software designed to harm devices or networks |
| Process of Attack Simulation and Threat Analysis (PASTA) | A popular threat modeling framework that's used across many industries |
| Phishing | The use of digital communications to trick people into revealing sensitive data or deploying malicious software |
| Phishing kit | A collection of software tools needed to launch a phishing campaign |
| Prepared statement | A coding technique that executes SQL statements before passing them onto the database |
| Potentially unwanted application (PUA) | A type of unwanted software that is bundled in with legitimate programs which might display ads, cause device slowdown, or install other software |
| Quid pro quo | A type of baiting used to trick someone into believing that they'll be rewarded in return for sharing access, information, or money |
| Ransomware | Type of malicious attack where attackers encrypt an organization's data and demand payment to restore access |
| Reflected XSS attack | An instance when malicious script is sent to a server and activated during the server's response |
| Rootkit | Malware that provides remote, administrative access to a computer |
| Scareware | Malware that employs tactics to frighten users into infecting their device |
| Smishing | The use of text messages to trick users to obtain sensitive information or to impersonate a known source |
| Social engineering | A manipulation technique that exploits human error to gain private information, access, or valuables |
| Spear phishing | A malicious email attack targeting a specific user or group of users, appearing to originate from a trusted source |
| Spyware | Malware that's used to gather and sell information without consent |
| SQL (Structured Query Language) | A programming language used to create, interact with, and request information from a database |
| SQL injection | An attack that executes unexpected queries on a database |
| Stored XSS attack | An instance when malicious script is injected directly on the server |
| Tailgating | A social engineering tactic in which unauthorized people follow an authorized person into a restricted area |
| Threat | Any circumstance or event that can negatively impact assets |
| Threat actor | Any person or group who presents a security risk |
| Threat modeling | The process of identifying assets, their vulnerabilities, and how each is exposed to threats |
| Trojan horse | Malware that looks like a legitimate file or program |
| Vishing | The exploitation of electronic voice communication to obtain sensitive information or to impersonate a known source |
| Watering hole attack | A type of attack when a threat actor compromises a website frequently visited by a specific group of users |
| Whaling | A category of spear phishing attempts that are aimed at high-ranking executives in an organization |
| Web-based exploits | Malicious code or behavior that's used to take advantage of coding flaws in a web application |

---

## Personal Reflection

This module tied a lot together for me — social engineering, phishing, malware, and web-based exploits all felt like separate categories going in, but seeing them side by side made clear that most of them ultimately come down to exploiting either human trust (social engineering/phishing) or unsanitized/unvalidated input (XSS/SQL injection). The PASTA framework's business-goals-to-simulated-attacks-and-back loop was also a good concrete example of how threat modeling connects deeply technical work (attack trees, vulnerability analysis) to something a non-technical stakeholder can actually act on.
