# Course 3, Module 3 – Intrusions, tcpdump, DDoS, and Interception Attacks

## Overview

This module covered how network intrusions compromise systems (interception and backdoor attacks), how to read tcpdump logs, a real-world DDoS case study, and common interception tactics like packet sniffing, IP spoofing, on-path attacks, and smurf attacks.

---

## Learning Objectives

After completing this module, I can:

- Explain network interception and backdoor attacks and their business impact
- Interpret basic tcpdump output
- Describe how a real-world DDoS attack unfolded
- Differentiate packet sniffing, IP spoofing, on-path attacks, smurf attacks, and DoS attacks

---

## Reading: How Intrusions Compromise Your System

### Network Interception Attacks

Work by intercepting network traffic to steal information or interfere with a transmission. Malicious actors use hardware/software to capture and inspect data in transit (packet sniffing) and can alter intercepted traffic — for example, redirecting a bank transfer to an account they control. Related tactics covered later in the course include on-path attacks and replay attacks.

### Backdoor Attacks

A backdoor is a weakness intentionally left by programmers or admins that bypasses normal access controls, usually meant to help with troubleshooting or admin tasks — but it can also be installed by an attacker after compromising a system to ensure persistent access. Once inside via a backdoor, an attacker can install malware, perform a DoS attack (flooding a network/server with traffic), steal information, or change security settings to leave the system more vulnerable.

### Possible Impacts on an Organization

- **Financial:** Taking systems offline (e.g., via DoS) prevents revenue-generating operations; rebuilding infrastructure and paying ransomware demands is costly, and stolen customer data can lead to litigation/settlement costs.
- **Reputation:** Public knowledge of an attack can erode customer trust and drive customers to competitors.
- **Public safety:** Attacks on government or critical infrastructure networks (power grid, water systems, defense communications) can pose a risk to public safety and national security.

**Key takeaway:** Attackers constantly seek to exploit new vulnerabilities via backdoors and interception, and the resulting damage can hit an organization financially, reputationally, and even at the level of public safety — making network security a continuous priority.

---

## Reading: Read tcpdump Logs

A network protocol analyzer (packet sniffer/packet analyzer) captures and analyzes data traffic within a network, commonly used to monitor and investigate suspicious activity. Common tools: SolarWinds NetFlow Traffic Analyzer, ManageEngine OpManager, Azure Network Watcher, Wireshark, and tcpdump.

### tcpdump

A command-line, lightweight (low memory/CPU) network protocol analyzer using the open-source libpcap library, text-based and run in the terminal. Preinstalled on many Linux distributions and installable on other Unix-based systems like macOS.

### Interpreting Output

tcpdump prints sniffed packets to the command line (and optionally a log file). Key fields:

- **Timestamp:** Hours, minutes, seconds, fractions of a second
- **Source IP:** The packet's origin
- **Source port:** Where the packet originated
- **Destination IP:** Where the packet is being sent
- **Destination port:** Where the packet is being delivered

By default, tcpdump resolves host addresses to hostnames and port numbers to commonly associated services.

### Common Uses

Establishing baselines for traffic patterns/utilization, detecting/identifying malicious traffic, creating custom alerts, and locating unauthorized IM traffic or wireless access points. Attackers can also misuse network protocol analyzers to capture sensitive information like usernames and passwords.

**Key takeaway:** tcpdump is a lightweight, cross-platform way to monitor traffic and investigate suspicious activity — but the same tool can be turned against an organization if used maliciously.

---

## Reading: Real-Life DDoS Attack

### A DDoS Targeting a Widely Used DNS Server

DNS servers translate domain names into the IP addresses hosting a website. On October 21, 2016, a major DNS service provider used by many large companies was hit by a DDoS attack.

**Leading up to the attack:** A group of university students had created a botnet (a collection of malware-infected computers controlled by a single "bot-herder") intended for attacking gaming servers/networks, then posted its code online — both making it widely accessible and helping avoid traceback. This made it possible for other malicious actors, including those behind the DNS attack, to control the botnet remotely.

**The day of the attack:** At 7:00 a.m., the botnet sent tens of millions of DNS requests to the service provider, overwhelming and shutting down the service. Websites relying on the provider became unreachable across North America and Europe. The provider restored service after two hours of downtime and was prepared enough to mitigate subsequent waves of the attack.

**Key takeaway:** DDoS attacks can be highly damaging, but distributing important operations across dynamically scalable hosts helps operations continue even if a baseline host goes offline — and concrete mitigation strategies exist to help protect against them.

---

## Reading: Overview of Interception Tactics

### A Closer Review of Packet Sniffing

Packet sniffing is the practice of capturing and inspecting data packets across a network. A device's Network Interface Card (NIC) normally only accepts packets addressed to it, but can be set to promiscuous mode to accept all traffic on the network. Malicious actors can use tools like Wireshark to capture and store this data, then use it directly or to perform IP spoofing.

### A Closer Review of IP Spoofing

After sniffing packets, an attacker can impersonate the IP/MAC addresses of authorized devices to perform an IP spoofing attack. Firewalls can help prevent this by refusing unauthorized IP packets and suspicious traffic.

- **On-path attack:** A hacker intercepts communication between two trusted devices/servers — sometimes called a meddler-in-the-middle attack. Can be used to collect usernames/passwords or spoof a DNS lookup response to redirect a domain name to a malicious IP. The most important protection is encrypting data in transit (e.g., using TLS).
- **Smurf attack:** Combines IP spoofing with a DoS technique — an attacker sniffs an authorized user's IP address, floods it with packets (often ICMP pings) that reach the broadcast address and get sent to all devices/servers on the network, overwhelming and shutting them down. Protecting against this requires an advanced (next-generation) firewall that detects unusual/oversized traffic.
- **DoS attack:** The attacker prevents a system from performing legitimate activity or responding to legitimate traffic. Unlike IP spoofing, the attacker doesn't receive a response and everything about the packet (including the IP address) is legitimate/authorized — the attacker just keeps sending packets with fake IP addresses until the server crashes.

**Pro tip (defense in depth):** No single strategy stops every kind of attack — layering defenses (e.g., combining industry-standard encryption with other controls) strengthens protection against DoS and related attacks on multiple levels.

**Key takeaway:** Whether it's an on-path attack, IP spoofing, or a smurf attack, analysts need mitigation strategies in place to limit the threat and prevent security breaches.

---

## Glossary Terms from Module 3

| Term | Definition |
|------|------------|
| Active packet sniffing | A type of attack where data packets are manipulated in transit |
| Botnet | A collection of computers infected by malware that are under the control of a single threat actor, known as the "bot-herder" |
| Denial of service (DoS) attack | An attack that targets a network or server and floods it with network traffic |
| Distributed denial of service (DDoS) attack | A type of denial of service attack that uses multiple devices or servers located in different locations to flood the target network with unwanted traffic |
| Internet Control Message Protocol (ICMP) | An internet protocol used by devices to tell each other about data transmission errors across the network |
| Internet Control Message Protocol (ICMP) flood | A type of DoS attack performed by an attacker repeatedly sending ICMP request packets to a network server |
| IP spoofing | A network attack performed when an attacker changes the source IP of a data packet to impersonate an authorized system and gain access to a network |
| On-path attack | An attack where a malicious actor places themselves in the middle of an authorized connection and intercepts or alters the data in transit |
| Packet sniffing | The practice of capturing and inspecting data packets across a network |
| Passive packet sniffing | A type of attack where a malicious actor connects to a network hub and looks at all traffic on the network |
| Ping of death | A type of DoS attack caused when a hacker pings a system by sending it an oversized ICMP packet that is bigger than 64KB |
| Replay attack | A network attack performed when a malicious actor intercepts a data packet in transit and delays it or repeats it at another time |
| Smurf attack | A network attack performed when an attacker sniffs an authorized user's IP address and floods it with ICMP packets |
| Synchronize (SYN) flood attack | A type of DoS attack that simulates a TCP/IP connection and floods a server with SYN packets |

---

## Personal Reflection

The 2016 DNS DDoS case study made the abstract idea of a "botnet" concrete for me — the fact that it started as students targeting gaming servers, then spiraled into a large-scale attack on critical internet infrastructure once the code went public, was a good illustration of how quickly a tool's intended use can get away from its creator. Walking through on-path, smurf, and DoS attacks side by side also helped me see how the same underlying technique (packet sniffing → IP spoofing) can branch into very different attack types depending on what the attacker does next.
