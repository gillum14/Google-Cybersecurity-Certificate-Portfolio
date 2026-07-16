# Course 6, Module 2 – Network Monitoring, Packet Captures, Wireshark, and tcpdump

## Overview

This module covered network monitoring and baselining, the anatomy of packet captures and network protocol analyzers, how to investigate packet details (IPv4/IPv6 headers, Wireshark filtering), and using tcpdump from the command line.

---

## Learning Objectives

After completing this module, I can:

- Explain baselining and what network components to monitor
- Describe packet structure and how network protocol analyzers work
- Read IPv4/IPv6 header fields and apply Wireshark display filters
- Use core tcpdump options and expressions to capture and interpret traffic

---

## Reading: Maintain Awareness with Network Monitoring

**Network traffic** is the amount (and type) of data moving across a network; **network data** is the data transmitted between devices. Monitoring is essential for maintaining situational awareness and detecting suspicious activity — but first requires knowing what to monitor.

### Know Your Network

A **baseline** — a reference point used for comparison — helps establish what "normal" network behavior looks like (source/destination IPs, data volume, date/time), making it easier to spot abnormal behavior.

### Monitor Your Network

- **Flow analysis:** Tracks the movement of communications (packets, protocols, ports). **Command and control (C2)** refers to techniques malicious actors use to maintain communication with a compromised system — e.g., using HTTPS over an uncommon port like 8088 instead of the standard port 443. Organizations should know which ports/protocols should normally be paired and watch for mismatches.
- **Packet payload information:** The actual (often encrypted) data being transmitted; monitoring it can reveal unusual activity like sensitive data leaving the network (data exfiltration).
- **Temporal patterns:** Time-based data in packets — e.g., a North American company's baseline might be traffic flowing mainly 9 a.m.–5 p.m.; large volumes outside that window are off-baseline and worth investigating.

### Protect Your Network

A **network operations center (NOC)** monitors network performance/availability/uptime, distinct from a SOC, which focuses on security detection/response. Analysts monitor for **indicators of compromise (IoC)** by understanding the environment traffic travels through, using tools like:

- **IDS:** Monitors and alerts on possible intrusions, often by inspecting packet payload content for known malware/phishing patterns.
- **Network protocol analyzers (packet sniffers):** Capture/analyze traffic manually in detail — e.g., tcpdump and Wireshark, used to record and investigate packet captures.

**Key takeaway:** You can't protect what you don't understand — establishing a baseline and knowing which network components to monitor is what makes deviations, and therefore threats, identifiable.

---

## Reading: Learn More About Packet Captures

### Packets

A **data packet** is the basic unit of information traveling between devices — e.g., uploading an image breaks the data into multiple packets that route to their destination and reassemble on arrival. Packets contain three components:

- **Header:** Routing information (source/destination IP, packet length, protocol, ID numbers) — may include several headers depending on protocols used (Ethernet, IP, TCP, etc.).
- **Payload:** The actual data being delivered (e.g., the image itself).
- **Footer (trailer):** Used by Ethernet for error-checking; most protocols (like IP) don't use footers, and footer info may not always display depending on network configuration.

### Network Protocol Analyzers

Tools (tcpdump, Wireshark, TShark) designed to capture and analyze network traffic — used both as investigative security tools and to collect network statistics/troubleshoot performance. They can also be misused by attackers to capture sensitive data like login credentials.

**How they work:** Packets are collected via the Network Interface Card (NIC), which by default only listens to traffic addressed to it. Switching the NIC to **monitoring mode** (wireless) or **promiscuous mode** (other systems) lets it see all visible packets — but the analyzer must also be positioned in the right network segment to see traffic between different hosts. Raw binary packet data is then converted into human-readable format for analysts.

### Capturing Packets

A **packet capture (p-cap)** is a file containing intercepted data packets, which can be filtered/analyzed with a network protocol analyzer. Note: intercepting private network communications without permission is illegal in many places. Common p-cap library/file formats:

- **Libpcap:** Default for Unix-like systems (Linux, macOS); used by tools like tcpdump.
- **WinPcap:** An older, largely outdated format for Windows.
- **Npcap:** Designed by Nmap, commonly used on Windows.
- **PCAPng:** A "next generation" format that can capture packets and store data simultaneously.

**Key takeaway:** Network protocol analyzers translate raw packet data into human-readable insight into what's happening on a network — essential for defending against intrusions.

---

## Reading: Investigate Packet Details

### IPv4 Header (13 Fields)

Version, IHL, Type of Service (ToS), Total Length, Identification, Flags, Fragment Offset, Time to Live (TTL), Protocol, Header Checksum, Source Address, Destination Address, and Options.

### IPv6 Header (8 Fields)

Version, Traffic Class (similar to ToS), Flow Label (identifies packets of a flow needing special handling), Payload Length, Next Header (indicates the following header type, like TCP), Hop Limit (similar to TTL), Source Address, and Destination Address. IPv6's header is simpler than IPv4's and its growing adoption is driven by its much larger address space.

### Wireshark

An open-source network protocol analyzer with a GUI for visualizing network communications and applying **display filters** to isolate relevant packets.

**Comparison operators:** `==`/`eq` (equal), `!=`/`ne` (not equal), `>`/`gt`, `<`/`lt`, `>=`/`ge`, `<=`/`le` — combinable with `and`/`or` and parentheses for complex filters.

**Contains and matches operators:** `contains` filters for an exact text match; `matches` filters using a regular expression (regex).

**Filter examples:**

- **By protocol:** Type the protocol name directly (`dns`, `http`, `ftp`, `ssh`, `arp`, `telnet`, `icmp`).
- **By IP address:** `ip.addr == 172.21.224.2` (either direction), `ip.src == 10.10.10.10` (source only), `ip.dst == 4.4.4.4` (destination only).
- **By MAC address:** `eth.addr == 00:70:f4:23:18:c4`
- **By port:** `udp.port == 53` or `tcp.port == 25`

**Following streams:** A **stream/conversation** is the data exchange between devices using a protocol; Wireshark can reassemble a full conversation (e.g., an HTTP request/response) into a readable format.

**Key takeaway:** Understanding IPv4/IPv6 header fields and Wireshark display filtering lets an analyst quickly isolate the specific packets relevant to an investigation instead of manually scanning an entire capture.

---

## Reading: Overview of tcpdump

**tcpdump** is a command-line network protocol analyzer used to capture traffic (optionally saved to a p-cap for later analysis), preinstalled on many Linux distributions and available on other Unix-based systems like macOS. Network traffic is often encrypted, so inspecting it may require decrypting with the appropriate private keys.

### Capturing Packets with tcpdump

Requires elevated privileges (root or via `sudo`). Basic syntax:

```
sudo tcpdump [-i interface] [option(s)] [expression(s)]
```

`-i` specifies the network interface to capture from (`-i any` captures from all interfaces); `-D` lists available interfaces.

### Key Options

- **`-w`:** Writes/saves captured packets to a p-cap file (e.g., `sudo tcpdump -i any -w packetcapture.pcap`).
- **`-r`:** Reads a saved p-cap file (e.g., `sudo tcpdump -r packetcapture.pcap`).
- **`-v` / `-vv` / `-vvv`:** Increases verbosity, printing more packet detail (e.g., IP header fields) with each added `v`.
- **`-c`:** Limits the number of packets captured/printed (e.g., `-c 3` for the first three).
- **`-n` / `-nn`:** Disables automatic name resolution (`-n` skips hostname resolution, `-nn` skips both hostname and port resolution) — considered best practice, since tcpdump's automatic port-to-service mapping isn't always accurate, and reverse DNS lookups on an attacker's system could tip them off that they're being investigated.

Options without a required parameter (like `-v` and `-n`) can be combined (e.g., `-vn`).

### Expressions

Optional filters for isolating traffic — e.g., `ip6` for IPv6 traffic, or combining filters with `and`/`or`/`not` (e.g., `'ip and port 80'`). Parentheses group and prioritize expressions for complex filters (e.g., `ip and (port 80 or port 443)`).

### Interpreting Output

Each captured packet prints as one line beginning with a timestamp, followed by source IP/port, destination IP/port, and (with `-v`) additional detail like TCP flags and sequence number.

**Key takeaway:** tcpdump's core skill set — capturing, filtering, and interpreting packets from the command line — is essential for defending against network intrusions, and pairs directly with the GUI-based skills learned in Wireshark.

---

## Glossary Terms from Module 2

| Term | Definition |
|------|------------|
| Command and control (C2) | The techniques used by malicious actors to maintain communications with compromised systems |
| Command-line interface (CLI) | A text-based user interface that uses commands to interact with the computer |
| Data exfiltration | Unauthorized transmission of data from a system |
| Data packet | A basic unit of information that travels from one device to another within a network |
| Indicators of compromise (IoC) | Observable evidence that suggests signs of a potential security incident |
| Internet Protocol (IP) | A set of standards used for routing and addressing data packets as they travel between devices on a network |
| Intrusion detection systems (IDS) | An application that monitors system activity and alerts on possible intrusions |
| Media Access Control (MAC) Address | A unique alphanumeric identifier that is assigned to each physical device on a network |
| National Institute of Standards and Technology (NIST) Incident Response Lifecycle | A framework for incident response consisting of four phases: Preparation; Detection and Analysis; Containment, Eradication and Recovery; and Post-incident activity |
| Network data | The data that's transmitted between devices on a network |
| Network protocol analyzer (packet sniffer) | A tool designed to capture and analyze data traffic within a network |
| Network traffic | The amount of data that moves across a network |
| Network Interface Card (NIC) | Hardware that connects computers to a network |
| Packet capture (p-cap) | A file containing data packets intercepted from an interface or network |
| Packet sniffing | The practice of capturing and inspecting data packets across a network |
| Playbook | A manual that provides details about any operational action |
| Root user (or superuser) | A user with elevated privileges to modify the system |
| Sudo | A command that temporarily grants elevated permissions to specific users |
| tcpdump | A command-line network protocol analyzer |
| Wireshark | An open-source network protocol analyzer |

---

## Personal Reflection

The C2 example — an attacker using HTTPS over port 8088 instead of the standard port 443 — was a really useful, concrete illustration of "look for mismatches between ports and protocols," which had otherwise felt abstract. Working through the parallel between Wireshark's display filters and tcpdump's CLI expressions also reinforced that they're two interfaces onto the same underlying skill: knowing exactly what field (IP, port, protocol) you're filtering for and why.
