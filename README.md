# Networks-Project
This is my final year CMPG325 networks project.

**Name:** Nkosinhle  
**Student Num:** 44665032  
**Due Date:** 13 October 2025


---

## Table of Contents
1.  [Project Overview](#project-overview)
2.  [IP Addressing Scheme](#ip-addressing-scheme)
    1.  [IPv4 Plan](#ipv4-plan)
    2.  [IPv6 Plan](#ipv6-plan)
    3.  [VLAN Plan](#vlan-plan)
3.  [Topology Documentation](#topology-documentation)
    1.  [Bus Topology](#1-bus-topology)
    2.  [Star Topology](#2-star-topology)
    3.  [Ring Topology](#3-ring-topology)
    4.  [Mesh Topology](#4-mesh-topology)
    5.  [Extended Star Topology](#5-extended-star-topology)
4.  [Hybrid Topology](#6-hybrid-topology)
5.  [Individual Feature: IPv6 Firewall](#individual-feature-ipv6-firewall-configuration)
6.  [Video Demonstration](#video-demonstration)
7.  [References & Tools](#references--tools)

---

## Project Overview
This project involves designing, simulating, and configuring various network topologies using Cisco Packet Tracer as per the CMPG 325 module requirements. The project is divided into three parts: design and simulation of five core topologies and one hybrid topology (Part I), individual configuration of an IPv6 firewall (Part II), and a video demonstration (Part III).

---

## IP Addressing Scheme

### IPv4 Plan
| Topology         | Network Address    | Server IP      | DHCP Pool          |
|------------------|--------------------|----------------|--------------------|
| Bus              | 192.168.1.0/24     | 192.168.1.100  | 192.168.1.50 - .99 |
| Star             | 192.168.2.0/24     | 192.168.2.100  | 192.168.2.50 - .99 |
| Ring             | 192.168.3.0/24     | 192.168.3.100  | 192.168.3.50 - .99 |
| Mesh             | 192.168.4.0/24     | 192.168.4.100  | 192.168.4.50 - .99 |
| Extended Star    | 192.168.5.0/24     | 192.168.5.100  | 192.168.5.50 - .99 |
| Hybrid Core      | 192.168.10.0/24    | 192.168.10.100 | 192.168.10.50 - .99|

### IPv6 Plan
| Topology         | Network Address       | Server IP (::100)    |
|------------------|-----------------------|----------------------|
| Bus              | FD00:0001::/64        | FD00:0001::100       |
| Star             | FD00:0002::/64        | FD00:0002::100       |
| Ring             | FD00:0003::/64        | FD00:0003::100       |
| Mesh             | FD00:0004::/64        | FD00:0004::100       |
| Extended Star    | FD00:0005::/64        | FD00:0005::100       |
| Hybrid Core      | FD00:000A::/64        | FD00:000A::100       |

### VLAN Plan
-   **VLAN 10:** MANAGEMENT
-   **VLAN 20:** USERS
-   **VLAN 30:** SERVERS

---

## Topology Documentation

### 1. Bus Topology
*(This section is your first task. We will fill it in as you build.)*

-   **Objective:** To simulate a linear bus network where all devices share a single communication line.
-   **Devices Used:** 4 PCs, 1 Server, Coaxial cables, 2 Terminators.
-   **Screenshot:**
    *(You will add a screenshot of your topology here later)*
-   **IP Address Table:**
    | Device | IPv4 Address | IPv6 Address | VLAN |
    |--------|--------------|--------------|------|
    | PC0    | 192.168.1.1  | FD00:1::1    | 20   |
    | PC1    | 192.168.1.2  | FD00:1::2    | 20   |
    | PC2    | 192.168.1.3  | FD00:1::3    | 20   |
    | Server0| 192.168.1.100| FD00:1::100  | 30   |
-   **Configuration Notes:**
    *   Coaxial cable connects all devices in a single line.
    *   Terminators are placed at both ends of the bus.
    *   The server has DNS, DHCP, and HTTP services enabled.
-   **Testing & Verification:**
    *(You will add a screenshot of a successful ping from PC0 to Server0 here later)*
    > `ping 192.168.1.100` ... Successful!
    > `ping FD00:1::100` ... Successful!

---

### 2. Star Topology

- **Objective:** To simulate a star network where all devices connect to a central switch.
- **Devices Used:** 4 PCs, 1 Server, 1 Switch (2960), Copper Straight-Through cables.
- **Screenshot:**
  ![Star Topology](link-to-your-screenshot)
- **IP Address Table:**
  | Device  | IPv4 Address    | IPv6 Address | VLAN |
  |---------|-----------------|--------------|------|
  | PC0     | 192.168.2.1     | FD00:2::1    | 20   |
  | PC1     | 192.168.2.2     | FD00:2::2    | 20   |
  | PC2     | 192.168.2.3     | FD00:2::3    | 20   |
  | PC3     | 192.168.2.4     | FD00:2::4    | 20   |
  | PC4     | DHCP (192.168.2.50) | DHCP     | 20   |
  | Server0 | 192.168.2.100   | FD00:2::100  | 30   |
- **Configuration Notes:**
  * All devices connected to a central switch using Copper Straight-Through cables.
  * Server configured with DHCP, DNS, and HTTP services.
  * Four PCs with static IPs, one PC with DHCP.
- **Testing & Verification:**
  ![Star Ping Test](link-to-ping-screenshot)
  > Ping and web browsing tests successful from all PCs to server.

*(Sections for Star, Ring, Mesh, Extended Star, and Hybrid will be placed here following the same format)*

---

## Individual Feature: IPv6 Firewall Configuration
*(This section will be filled in during Part II)*

## Video Demonstration
*(This section will be filled in during Part III)*

## References & Tools
-   **Cisco Packet Tracer**
-   GitHub Guides
