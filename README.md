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

-   **Objective:** To simulate a linear bus network where all devices share a single communication line.
-   **Devices Used:** 4 PCs, 1 Server, Coaxial cables, 2 Terminators.
-   **Screenshot:**
    ![Bus Topology](BusTopology/setup.PNG)
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

>   `ping 192.168.1.100` ... Successful!
    ![Bus Topology Ping Test](BusTopology/pingSuccess.PNG)
>
>   **PC pings Server:**
    ![Bus Topology Ping Test](BusTopology/server1.PNG)
    ![Bus Topology Ping Test](BusTopology/server2.PNG)
    ![Bus Topology Ping Test](BusTopology/server3.PNG)
>
--     **Web page successful search:**
    ![Bus Topology Ping Test](BusTopology/webPageSuccess.PNG)

>
>   **PC pings PC:**
    ![Bus Topology Ping Test](BusTopology/step1.PNG)
    ![Bus Topology Ping Test](BusTopology/step2.PNG)
    ![Bus Topology Ping Test](BusTopology/step3.PNG)
    ![Bus Topology Ping Test](BusTopology/step4.PNG)
    ![Bus Topology Ping Test](BusTopology/step5.PNG)
    

    
    

---

### 2. Star Topology

- **Objective:** To simulate a star network where all devices connect to a central switch.
- **Devices Used:** 4 PCs, 1 Server, 1 Switch (2960), Copper Straight-Through cables.
- **Screenshot:**
  ![Star Topology](StarTopologyImagess/setup.PNG)
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
 
  * 
- **Testing & Verification:**

- 
  ![Star Ping Test](StarTopologyImagess/pingSuccess.PNG)

   **PC pings PC:**
  ![Star Ping Test](StarTopologyImagess/step1.PNG)
  ![Star Ping Test](StarTopologyImagess/step2.PNG)
  ![Star Ping Test](StarTopologyImagess/step3.PNG)
  ![Star Ping Test](StarTopologyImagess/step4.PNG)
  
  > Ping and web browsing tests successful from all PCs to server.
  

  ### 3. Ring Topology

- **Objective:** To simulate a ring network where switches are connected in a circular formation, creating a logical ring.
- **Devices Used:** 4 Switches (2960), 4 PCs, 1 Server, Copper Straight-Through cables.
- **Screenshot:**
  ![Ring Topology Diagram](RingTopologyImages/ringSetup.PNG)
- **IP Address Table:**
  | Device  | IPv4 Address    | IPv6 Address | VLAN | Connected To |
  |---------|-----------------|--------------|------|--------------|
  | PC1     | 192.168.3.1     | FD00:3::1    | 20   | Switch1      |
  | PC2     | 192.168.3.2     | FD00:3::2    | 20   | Switch2      |
  | PC3     | DHCP (192.168.3.50) | DHCP     | 20   | Switch3      |
  | PC4     | DHCP (192.168.3.51) | DHCP     | 20   | Switch3      |
  | Server0 | 192.168.3.100   | FD00:3::100  | 30   | Switch4      |
- **Switch Connections:**
  - Switch1: Port Fa0/1 → Switch2-Fa0/1, Port Fa0/2 → Switch4-Fa0/2
  - Switch2: Port Fa0/2 → Switch3-Fa0/1
  - Switch3: Port Fa0/2 → Switch4-Fa0/1
- **Configuration Notes:**
  * Four switches connected in a ring formation using Copper Straight-Through cables.
  * Spanning Tree Protocol (STP) automatically activated to prevent network loops.
  * Server configured with DHCP, DNS, and HTTP services for the 192.168.3.0/24 network.
  * Mixed static and DHCP IP assignment for end devices.
- **Testing & Verification:**


  ![Ring Ping Test](RingTopologyImages/pingSuccess.PNG)

   **Web Search:**
  ![Ring Web Test](RingTopologyImages/suceessWebPageSearch.PNG)

   **PC pings PC:**
  ![Ring Ping Test](RingTopologyImages/step1.PNG)
  ![Ring Ping Test](RingTopologyImages/step2.PNG)
  ![Ring Ping Test](RingTopologyImages/step3.PNG)
  ![Ring Ping Test](RingTopologyImages/step4.PNG)
  ![Ring Ping Test](RingTopologyImages/step5.PNG)
  > All devices successfully communicated across the ring. Ping tests and web browsing functional between all PCs and server.
  

  ### 4. Mesh Topology

- **Objective:** To simulate a mesh network where each switch connects to every other switch, providing multiple paths and redundancy.
- **Devices Used:** 4 Switches (2960), 4 PCs, 1 Server, Copper Straight-Through cables.
- **Screenshot:**

- 
  ![Mesh Topology Diagram](Mesh-Topology-Images/setup.PNG)
- **IP Address Table:**
  | Device  | IPv4 Address    | IPv6 Address | VLAN | Connected To |
  |---------|-----------------|--------------|------|--------------|
  | PC1     | 192.168.4.1     | FD00:4::1    | 20   | Switch1-Port Fa0/4 |
  | PC2     | 192.168.4.2     | FD00:4::2    | 20   | Switch2-Port Fa0/4 |
  | PC3     | DHCP (192.168.4.50) | DHCP     | 20   | Switch3-Port Fa0/4 |
  | PC4     | DHCP (192.168.4.51) | DHCP     | 20   | Switch4-Port Fa0/4 |
  | Server0 | 192.168.4.100   | FD00:4::100  | 30   | Switch1-Port Fa0/5 |

- **Switch Mesh Connections:**

- **Testing & Verification:**


  ![Mesh Ping Test](Mesh-Topology-Images/pingSuccess.PNG)
  ![Mesh Ping Test](Mesh-Topology-Imagess/webSuccess.PNG)
  ![Mesh Ping Test](Mesh-Topology-Images/toPCStep1.PNG)
  ![Mesh Ping Test](Mesh-Topology-Images/topcStep2.PNG)
  ![Mesh Ping Test](Mesh-Topology-Images/toPcStep3.PNG)
  ![Mesh Ping Test](Mesh-Topology-Images/topcStep4.PNG)


  
 
### 5. Extended Star Topology

- **Objective:** To simulate a hierarchical star network with core, distribution, and access layers, demonstrating enterprise-level network design.
- **Devices Used:** 10 Switches (1 Core, 3 Distribution, 6 Access), 12 PCs, 1 Server, Copper Straight-Through cables.
- **Screenshot:**
  ![Extended Star Topology Diagram](extendedStar-Images/setup.PNG)
- **IP Address Table (Selected Devices):**
  | Device  | IPv4 Address    | IPv6 Address | VLAN | Hierarchical Path |
  |---------|-----------------|--------------|------|-------------------|
  | PC1     | 192.168.5.1     | FD00:5::1    | 20   | Acc-Switch1 → Dist-Switch1 → Core |
  | PC2     | DHCP (192.168.5.50) | DHCP     | 20   | Acc-Switch1 → Dist-Switch1 → Core |
  | PC12    | DHCP (192.168.5.55) | DHCP     | 20   | Acc-Switch6 → Dist-Switch3 → Core |
  | Server0 | 192.168.5.100   | FD00:5::100  | 30   | Core-Switch |

- **Hierarchical Structure:**

- **Testing & Verification:**

![Extended Star Topology Diagram](extendedStar-Images/pingSuccess.PNG)
![Extended Star Topology Diagram](extendedStar-Images/webSuccess.PNG)
![Extended Star Topology Diagram](extendedStar-Images/ipConfigure.PNG)
![Extended Star Topology Diagram](extendedStar-Images/step1.PNG)
![Extended Star Topology Diagram](extendedStar-Images/step2.PNG)
![Extended Star Topology Diagram](extendedStar-Images/step3.PNG)
![Extended Star Topology Diagram](extendedStar-Images/step4.PNG)
![Extended Star Topology Diagram](extendedStar-Images/step5.PNG)
*(Sections for Star, Ring, Mesh, Extended Star, and Hybrid will be placed here following the same format)*

---

## Individual Feature: IPv6 Firewall Configuration

### Objective
Configure and test IPv6 firewall rules to secure network traffic while maintaining essential services.

## 🖥️ Implementation

- **Topology Used:** Simple network with one router and one PC (Modified Star Topology)
- **Firewall Device:** Cisco ISR 4321 Router (Packet Tracer)
- **Configuration Type:** IPv6 Access Control List (ACL)
- **Interface Used:** `GigabitEthernet0/1`

- ![IPv6 Firewall Setup](Part2Images/setup.png)

---
# IPv6 Firewall Rules
| Rule | Action | Protocol | Source | Destination | Port | Purpose |
|------|--------|----------|--------|-------------|------|---------|
| 1 | Permit | TCP | Any | Server | 80 | Allow HTTP web traffic |
| 2 | Permit | UDP | Any | Server | 53 | Allow DNS queries |
| 3 | Permit | ICMP | Any | Any | - | Allow network testing |
| 4 | Deny | TCP | Any | Any | 23 | Block Telnet |
| 5 | Deny | TCP | Any | Any | 21 | Block FTP |
| 6 | Deny | TCP | Any | Any | 22 | Block SSH |
| 7 | Permit | IPv6 | Any | Any | - | Allow all other traffic |


### Configuration Screenshots
![IPv6 Firewall ACL](ipv6-firewall-acl.png)
![Firewall Topology](firewall-topology.png)
![Firewall Test Results](firewall-tests.png)


## Video Demonstration
*(This section will be filled in during Part III)*

## References & Tools
-   **Cisco Packet Tracer**
-   GitHub Guides
