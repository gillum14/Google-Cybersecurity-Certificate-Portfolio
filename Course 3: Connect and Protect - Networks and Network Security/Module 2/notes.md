# Course 3, Module 2 – Protocols, Wireless Security, Subnetting, and VPNs

## Overview

This module covered common and additional network protocols, the evolution of wireless security protocols (WEP through WPA3), subnetting and CIDR, and network security tools including firewalls, proxy servers, and VPNs (WireGuard vs. IPSec).

---

## Learning Objectives

After completing this module, I can:

- Categorize network protocols as communication, management, or security protocols
- Explain the evolution and current standard of wireless security protocols
- Describe subnetting, CIDR, and their security benefits
- Compare firewalls, proxy servers, and VPN types/protocols

---

## Reading: Common Network Protocols

A network protocol is a set of rules two or more devices use to describe the order and structure of data delivery. Protocols fall into three categories:

### Communication Protocols

- **TCP:** Forms a connection via a three-way handshake (SYN → SYN/ACK → ACK) and streams data reliably; operates at the transport layer.
- **UDP:** Connectionless, less reliable than TCP but faster — used for things like DNS requests; operates at the transport layer.
- **HTTP:** An application-layer protocol for client/website server communication, using port 80. Considered insecure and being replaced by HTTPS.
- **DNS:** Translates domain names into IP addresses, normally over UDP port 53 (switches to TCP for large replies); operates at the application layer.

### Management Protocols

- **SNMP:** Monitors/manages network devices — can reset a password, change baseline configuration, or report bandwidth usage; application layer.
- **ICMP:** Used by devices to report data transmission errors; commonly used for the "ping" command to troubleshoot connectivity/latency; internet layer.

### Security Protocols

- **HTTPS:** A secure version of HTTP using SSL/TLS encryption, port 443; application layer.
- **SFTP:** A secure file transfer protocol using SSH (typically TCP port 22), commonly used with cloud storage uploads/downloads; application layer.

Note: encryption protocols don't conceal source/destination IP addresses — a malicious actor who intercepts traffic can still learn some basic information.

**Key takeaway:** Understanding how protocols function is essential for mitigating vulnerabilities and preventing future attacks.

---

## Reading: Additional Network Protocols

- **Network Address Translation (NAT):** Lets devices with private IP addresses share a single public IP address to communicate with the internet, usually configured on a router/firewall. Private IP ranges (assigned by the router, no cost, unique only within the private network) include 10.0.0.0–10.255.255.255, 172.16.0.0–172.31.255.255, and 192.168.0.0–192.168.255.255. Public IP ranges are assigned by an ISP/IANA and cost to lease.
- **DHCP:** An application-layer management protocol that assigns unique IP addresses and provides DNS/default gateway info to devices; servers use UDP port 67, clients use UDP port 68.
- **ARP:** A network-access-layer protocol translating IP addresses in packets into hardware MAC addresses, tracked in each device's ARP cache; has no specific port number.
- **Telnet:** Connects to a remote system in clear text (unencrypted) over TCP port 23 — less secure than SSH.
- **SSH:** Creates a secure connection to a remote system with encrypted authentication/communication, over TCP port 22 — a replacement for Telnet.
- **POP3:** Manages/retrieves email from a mail server; mail downloads locally and may or may not sync across devices. Unencrypted on TCP/UDP port 110, encrypted (SSL/TLS) on port 995.
- **IMAP:** Downloads email headers/content while keeping mail on the server, allowing multi-device sync. Unencrypted on TCP port 143, encrypted (TLS) on port 993.
- **SMTP:** Transmits/routes email from sender to recipient, working with MTA software to resolve addresses via DNS. Unencrypted on TCP/UDP port 25 (also commonly abused for spam), encrypted (TLS) on port 587.

**Key takeaway:** Firewalls can filter traffic based on port numbers, so knowing which protocols map to which ports is essential — both for day-to-day work and for technical interviews.

---

## Reading: The Evolution of Wireless Security Protocols

Wi-Fi (based on the IEEE 802.11 family of standards) is secured by wireless networking protocols that have evolved to address discovered vulnerabilities:

- **WEP (1999):** The oldest wireless security standard, designed to match wired-network privacy levels. Largely out of use today and considered high-risk, but analysts may still encounter it on older or misconfigured devices.
- **WPA (2003):** Improved on WEP using Temporal Key Integrity Protocol (TKIP) and larger secret keys, plus a message integrity check to reject altered/replayed transmissions. Still vulnerable to KRACK attacks, where an attacker inserts a new (often all-zero) encryption key during the handshake.
- **WPA2 (2004):** Uses AES and CCMP for encapsulation, message authentication, and integrity — the current Wi-Fi standard. Still vulnerable to KRACK, leading to WPA3. Offers **Personal mode** (simple setup, shared passphrase — best for home networks) and **Enterprise mode** (more complex setup, individualized/centralized access control — best for businesses, since users never see the encryption keys directly).
- **WPA3 (2018):** Addresses the KRACK vulnerability using Simultaneous Authentication of Equals (SAE), a password-authenticated key-sharing agreement that prevents attackers from downloading and decoding captured data. Uses 128-bit encryption (WPA3-Enterprise offers optional 192-bit).

**Key takeaway:** Knowing the history and vulnerabilities of each wireless protocol helps analysts recognize risk and push for up-to-date security technologies on any network they support.

---

## Reading: Subnetting and CIDR

### Overview of Subnetting

Subnetting is the subdivision of a network into logical groups (subnets) — essentially a network within a network, formed based on device IP addresses and network masks. It improves efficiency (switches keep same-subnet traffic local) and can be used to create security zones (uncontrolled, controlled, demilitarized, restricted).

### CIDR

Classless Inter-Domain Routing (CIDR) assigns subnet masks to IP addresses to create subnets, replacing the older classful addressing system (Class A–E) that ran out of room as internet usage grew in the 1990s. A CIDR address adds a "/" and a network prefix number (e.g., 198.51.100.0/24), which encompasses a defined range of addresses and reduces the number of entries needed in routing tables.

### Security Benefits of Subnetting

Lets organizations create internal networks without requesting a new IP address from their ISP, uses bandwidth more efficiently, and — combined with physical isolation, routing configuration, and firewalls — helps create isolated subnetworks.

**Key takeaway:** Subnetting improves network efficiency and can be used to establish security zones within a private network.

---

## Reading: Virtual Networks and Privacy

### Common Network Protocols (Recap)

Three categories again: communication (TCP, UDP, SMTP), management (ICMP), and security (IPSec, SSL/TLS). Other notable protocols: HTTP, DNS, and ARP (maps IP addresses to MAC addresses on the LAN).

### Firewalls

Network virtual appliances or hardware devices that inspect/filter traffic before it enters the private network, based on rules for port number and IP address.

- **Stateless:** Operates on predefined rules without tracking data-packet information; requires rules in two directions.
- **Stateful:** Tracks passing information and proactively filters threats using a "state table," requiring rules in only one direction to match return traffic.
- **Next Generation Firewalls (NGFWs):** The most advanced — perform deep packet inspection and intrusion prevention, are application-aware, and can block/allow traffic by application rather than just IP/port. May include malware sandboxing, network antivirus, and URL/DNS filtering.

### Proxy Servers

Add security using NAT as a barrier between internal clients and external threats. **Forward proxies** handle internal clients' requests to external resources; **reverse proxies** handle external requests to internal services. Some can be configured with rules like a firewall (e.g., blocking known-malware sites).

### Virtual Private Networks (VPNs)

Encrypt data in transit and disguise a device's IP address using encapsulation (wrapping unencrypted data inside an encrypted packet). Used by enterprises to protect device-to-corporate-resource communications and by individuals for personal privacy — a reputable VPN also minimizes its own access to user activity through strong encryption. Organizations increasingly combine VPN and SD-WAN (software-defined WAN) capabilities to securely connect users to applications across locations.

**Key takeaway:** Firewalls, proxy servers, and VPNs each add a distinct layer of network security, and organizations are increasingly combining them with cloud-based approaches like VPN + SD-WAN.

---

## Reading: VPN Protocols — WireGuard and IPSec

A VPN protocol (like a network protocol) is a set of rules determining how a secure tunnel is formed between endpoints (computers, mobile devices, servers).

### Remote Access vs. Site-to-Site VPNs

- **Remote access VPNs:** Connect an individual's personal device to a VPN server over the internet, encrypting data sent/received.
- **Site-to-site VPNs:** Used by enterprises to extend their network to other locations/networks — commonly using IPSec to create an encrypted tunnel between the primary and remote networks. More complex to configure/manage than remote access VPNs.

### WireGuard vs. IPSec

- **WireGuard:** A newer, high-speed protocol with advanced encryption, designed to be simple to set up/maintain. Works for both site-to-site and client-server connections; open source, using fewer lines of code for faster download speeds — good for streaming/large downloads.
- **IPSec:** An older, more complex protocol used to encrypt/authenticate data packets for secure connections. Widely supported by operating systems due to its longer history and extensive security testing.

**Key takeaway:** Choosing between WireGuard and IPSec depends on connection speed needs, compatibility with existing infrastructure, and business/individual requirements.

---

## Glossary Terms from Module 2

| Term | Definition |
|------|------------|
| Address Resolution Protocol (ARP) | A network protocol used to determine the MAC address of the next router or device on the path |
| Cloud-based firewalls | Software firewalls that are hosted by the cloud service provider |
| Controlled zone | A subnet that protects the internal network from the uncontrolled zone |
| Domain Name System (DNS) | A networking protocol that translates internet domain names into IP addresses |
| Encapsulation | A process performed by a VPN service that protects your data by wrapping sensitive data in other data packets |
| Firewall | A network security device that monitors traffic to or from your network |
| Forward proxy server | A server that regulates and restricts a person's access to the internet |
| Hypertext Transfer Protocol (HTTP) | An application layer protocol that provides a method of communication between clients and website servers |
| Hypertext Transfer Protocol Secure (HTTPS) | A network protocol that provides a secure method of communication between clients and servers |
| IEEE 802.11 (Wi-Fi) | A set of standards that define communication for wireless LANs |
| Network protocols | A set of rules used by two or more devices on a network to describe the order of delivery of data and the structure of data |
| Network segmentation | A security technique that divides the network into segments |
| Port filtering | A firewall function that blocks or allows certain port numbers to limit unwanted communication |
| Proxy server | A server that fulfills the requests of its clients by forwarding them to other servers |
| Reverse proxy server | A server that regulates and restricts the internet's access to an internal server |
| Secure File Transfer Protocol (SFTP) | A secure protocol used to transfer files from one device to another over a network |
| Secure shell (SSH) | A security protocol used to create a shell with a remote system |
| Security zone | A segment of a company's network that protects the internal network from the internet |
| Simple Network Management Protocol (SNMP) | A network protocol used for monitoring and managing devices on a network |
| Stateful | A class of firewall that keeps track of information passing through it and proactively filters out threats |
| Stateless | A class of firewall that operates based on predefined rules and does not keep track of information from data packets |
| Subnetting | The subdivision of a network into logical groups called subnets |
| Transmission Control Protocol (TCP) | An internet communication protocol that allows two devices to form a connection and stream data |
| Uncontrolled zone | The portion of the network outside the organization |
| Virtual private network (VPN) | A network security service that changes your public IP address and masks your virtual location so that you can keep your data private when using a public network like the internet |
| Wi-Fi Protected Access (WPA) | A wireless security protocol for devices to connect to the internet |

---

## Personal Reflection

The wireless security protocol timeline (WEP → WPA → WPA2 → WPA3) was a good reminder that "current standard" isn't the same as "permanently secure" — each protocol was replaced because a specific, named vulnerability (like KRACK) was found in its predecessor. Tying subnetting to security zones also made the concept click in a way that just "dividing a network into smaller pieces" hadn't — it's not only about efficiency, it's a deliberate security control.
