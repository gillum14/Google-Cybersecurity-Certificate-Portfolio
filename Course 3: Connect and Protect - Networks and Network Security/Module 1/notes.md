# Course 3, Module 1 – Network Foundations: Devices, Cloud, and the TCP/IP & OSI Models

## Overview

This module built foundational networking knowledge: the devices and diagrams that make up a network, cloud computing and software-defined networks, and the TCP/IP and OSI models used to conceptualize how data moves across a network.

---

## Learning Objectives

After completing this module, I can:

- Identify common network devices and their roles
- Read and use network diagrams as a security analyst
- Explain cloud computing service categories and software-defined networking
- Compare the TCP/IP and OSI models and their layers
- Explain IPv4 packet structure and the differences between IPv4 and IPv6

---

## Reading: Network Components, Devices, and Diagrams

### Network Devices

Network devices maintain information and services for network users, connecting via wired or wireless connections and sending data packets that identify source and destination. A router connects to the internet through a modem (provided by an ISP); a firewall monitors incoming/outgoing traffic; the router then directs traffic to devices on the network. A switch is an optional device providing additional ports/connections, and multiple routers connected to a switch can be used for load balancing.

- **Devices and desktop computers:** Each has a unique MAC address and IP address, plus a network interface for sending/receiving data packets, connecting via wired or wireless connection.
- **Firewalls:** A network security device monitoring traffic to/from a network — the first line of defense, restricting specific incoming/outgoing traffic based on organization-configured rules. Sits between the secured internal network and untrusted external resources like the internet.
- **Servers:** Provide information/services to client devices (the client-server model) — e.g., DNS servers (domain lookups), file servers (store/retrieve files), corporate mail servers.
- **Hubs and switches:** Both direct local network traffic. A hub repeats all information out to all ports, making it vulnerable to eavesdropping — mostly used in limited setups like home offices. A switch forwards packets only to the intended device using a MAC address table, improving performance and security; it operates at the data link layer of the TCP/IP model.
- **Routers:** Connect networks and direct traffic based on destination IP address, operating at the network layer. Can include firewall features to block malicious traffic from entering the network.
- **Modems and wireless access points:** A modem connects a home/office to an ISP, translating internet signals into analog signals for the physical connection, then passes decoded transmissions to a router. A wireless access point sends/receives digital signals over radio waves (Wi-Fi) to create a wireless network.

### Using Network Diagrams as a Security Analyst

Network diagrams map the devices on a network and how they connect, using representative graphics and dotted lines. Studying them helps analysts develop and refine strategies for securing network architecture.

**Key takeaway:** In the client-server model, clients request information/services and servers fulfill those requests. Network devices include routers, workstations, servers, hubs, switches, and modems, and analysts use network diagrams to visualize architecture.

---

## Reading: Cloud Computing and Software-Defined Networks

### Computing Processes in the Cloud

Traditional (on-premise) networks keep devices at a company-owned physical location. Cloud computing uses remote servers, applications, and network services hosted on the internet instead. A cloud service provider (CSP) owns large data centers and sells storage/compute services, accessed via API or web console. CSPs offer three service categories:

- **SaaS (Software as a Service):** Software suites operated remotely by the CSP.
- **IaaS (Infrastructure as a Service):** Virtual computer components (containers, storage) configured remotely.
- **PaaS (Platform as a Service):** Tools for developers to build custom applications in the cloud.

### Hybrid and Multi-Cloud Environments

Using a CSP's services alongside on-premise infrastructure is a hybrid cloud environment; using more than one CSP is a multi-cloud environment. Most organizations use hybrid environments to reduce costs and maintain control.

### Software-Defined Networks (SDNs)

SDNs are made up of virtual network devices and services — virtual switches, routers, firewalls — hosted on servers at a CSP's data center. Most modern network hardware supports virtualization.

### Benefits of Cloud Computing and SDNs

- **Reliability:** Availability, secure connections, and consistent uptime with minimal interruption.
- **Cost:** CSPs' scale lets them offer virtual devices/services at a fraction of the cost of building in-house infrastructure.
- **Scalability:** Organizations pay only for what they need in an elastic utility model, avoiding over- or under-provisioning, and can configure protections (WAFs, IDS/IPS, firewalls) quickly through a CSP's API/console.

**Key takeaway:** SDNs enable dynamic, programmatically efficient network configurations to improve performance and monitoring. Organizations improve reliability, save costs, and scale quickly by using CSPs instead of building/maintaining their own infrastructure.

---

## Reading: Learn More About the TCP/IP Model

### The TCP/IP Model

A framework for visualizing how data is organized and transmitted across a network, helping analysts conceptualize where disruptions or threats occur. Has four layers:

- **Network access layer** (data link layer): Handles data packet creation/transmission and physical hardware (hubs, modems, cables). ARP maps IP addresses to MAC addresses for local communication.
- **Internet layer** (network layer): Ensures delivery to the destination host, attaching IP addresses to packets. Key protocols: **IP** (sends packets to the correct destination, relies on TCP/UDP for delivery) and **ICMP** (shares error info/status updates, useful for troubleshooting).
- **Transport layer:** Delivers data between systems and controls traffic flow. **TCP** forms a connection and reliably streams data, containing the destination port number. **UDP** is connectionless and used for performance-sensitive, real-time applications like video streaming.
- **Application layer:** Handles network requests/responses for user-facing services — HTTP, SMTP, SSH, FTP, DNS.

### TCP/IP Model vs. OSI Model

Both are conceptual models dividing network communication into layers. The TCP/IP model (4 layers) is a simplified/condensed version of the OSI model (7 layers).

**Key takeaway:** Both models help network professionals communicate about potential sources of problems or security threats.

---

## Reading: The OSI Model

Working from Layer 7 down to Layer 1:

- **Layer 7 – Application:** Protocols that directly involve everyday users (HTTP/HTTPS in a browser, SMTP for email, DNS to translate domain names to IP addresses).
- **Layer 6 – Presentation:** Data translation and encryption — formats data for the application layer on both ends. SSL encryption between web servers/browsers happens here.
- **Layer 5 – Session:** Manages when a connection (session) is established, kept open during transfer, and terminated after. Handles authentication, reconnection, and checkpoints so a transmission resumes properly if interrupted.
- **Layer 4 – Transport:** Delivers data between devices, handles transfer speed/flow, and segments data for transport (segmentation). TCP and UDP operate here.
- **Layer 3 – Network:** Receives frames from the data link layer and delivers them to their intended destination based on address info in the data packet.
- **Layer 2 – Data link:** Organizes sending/receiving of packets within a single network; home to switches and network interface cards. Protocols include NCP, HDLC, SDLC.
- **Layer 1 – Physical:** The physical hardware — hubs, modems, cables/wiring. Data is translated into a stream of 0s and 1s to travel across physical media.

**Key takeaway:** Both TCP/IP and OSI are conceptual models for understanding data transmission. Network and security professionals use the OSI model specifically to communicate about potential sources of problems or threats.

---

## Reading: Components of Network Layer Communication

### Operations at the Network Layer

The network layer organizes addressing and delivery of packets from host to destination, directing them router-to-router until they reach the destination IP address (contained in the packet header and stored in routing tables along the way).

### Format of an IPv4 Packet

An IPv4 packet has a header and data section. The header ranges from 20–60 bytes: the first 20 bytes are fixed (source/destination address, header length, total length); the remaining 0–40 bytes are the options field. The maximum possible size of an IPv4 packet is 65,535 bytes.

**The 13 fields of an IPv4 header:**

- **Version (VER):** Indicates the protocol version (e.g., IPv4).
- **IP Header Length (HLEN/IHL):** Indicates where the header ends and data begins.
- **Type of Service (ToS):** Helps routers prioritize packets for quality of service.
- **Total Length:** Total length of the packet (header + data), max 65,535 bytes.
- **Identification:** A unique identifier for fragments of an original packet, used to reassemble them.
- **Flags:** Indicates whether a packet has been fragmented and if more fragments are in transit.
- **Fragmentation Offset:** Tells routers where a fragment belongs in the original packet.
- **Time to Live (TTL):** A counter decremented at each router hop; when it hits zero, the packet is discarded and an ICMP Time Exceeded error is returned.
- **Protocol:** Tells the receiving device which protocol handles the data portion.
- **Header Checksum:** Detects corruption of the header in transit; corrupted packets are discarded.
- **Source IP Address:** The sender's IPv4 address.
- **Destination IP Address:** The receiver's IPv4 address.
- **Options:** Allows security options to be applied when HLEN is greater than five.

### Difference Between IPv4 and IPv6

IPv4 addresses are four decimal numbers (0–255) separated by periods, spanning 4 bytes (~4.3 billion possible addresses) — created before anticipating how many devices would eventually need one (IPv4 address exhaustion). IPv6 addresses are eight hexadecimal numbers separated by colons, spanning 16 bytes (340 undecillion possible addresses); consecutive zero blocks can be shortened with "::". IPv6's header is simpler (no IHL, Identification, or Flags fields, but adds a Flow Label field) and offers more efficient routing while eliminating private address collisions.

**Key takeaway:** Analyzing the fields in an IP packet reveals important security information — origin, destination, and protocol used — which supports critical decisions about the security implications of inspected packets.

---

## Glossary Terms from Module 1

| Term | Definition |
|------|------------|
| Bandwidth | The maximum data transmission capacity over a network, measured by bits per second |
| Cloud computing | The practice of using remote servers, applications, and network services hosted on the internet instead of local physical devices |
| Cloud network | A collection of servers/computers that stores resources and data in remote data centers accessible via the internet |
| Data packet | A basic unit of information that travels from one device to another within a network |
| Hub | A network device that broadcasts information to every device on the network |
| Internet Protocol (IP) | A set of standards used for routing and addressing data packets as they travel between devices on a network |
| Internet Protocol (IP) address | A unique string of characters that identifies the location of a device on the internet |
| Local Area Network (LAN) | A network that spans small areas like an office building, school, or home |
| Media Access Control (MAC) address | A unique alphanumeric identifier assigned to each physical device on a network |
| Modem | A device that connects your router to the internet and brings internet access to the LAN |
| Network | A group of connected devices |
| Open Systems Interconnection (OSI) model | A standardized concept describing the seven layers computers use to communicate and send data over a network |
| Packet sniffing | The practice of capturing and inspecting data packets across a network |
| Port | A software-based location that organizes the sending and receiving of data between devices on a network |
| Router | A network device that connects multiple networks together |
| Speed | The rate at which a device sends and receives data, measured by bits per second |
| Switch | A device that makes connections between specific devices on a network by sending and receiving data between them |
| TCP/IP model | A framework used to visualize how data is organized and transmitted across a network |
| Transmission Control Protocol (TCP) | An internet communication protocol that allows two devices to form a connection and stream data |
| User Datagram Protocol (UDP) | A connectionless protocol that does not establish a connection between devices before transmissions |
| Wide Area Network (WAN) | A network that spans a large geographic area like a city, state, or country |

---

## Personal Reflection

This module was dense but foundational — connecting the physical devices (routers, switches, modems) to the conceptual layers (TCP/IP and OSI) made both sides click better than studying them separately. Breaking down the IPv4 header field-by-field also helped me see packet inspection as something concrete rather than abstract: every field has a specific security-relevant purpose, from TTL preventing infinite forwarding to the checksum catching corrupted data.
