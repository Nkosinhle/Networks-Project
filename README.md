# 🌐 CMPG325 Networks Project

**👤 Student Name:** Nkosinhle  
**🆔 Student Number:** 44665032  
**📅 Due Date:** 13 October 2025  

---

## 📖 Overview
Final year project simulating and configuring multiple network topologies using **Cisco Packet Tracer**.  

## 🔒 Part 1: Network Topologies Design & Simulation using Cicso Packet Tracer
## 🌐 Topologies
- 🚌 **Bus:** Linear network  
- ⭐ **Star:** Centralized switch  
- 🔄 **Ring:** Circular switch formation with STP  
- 🕸️ **Mesh:** Full redundancy between switches  
- 🌟 **Extended Star:** Hierarchical core, distribution, access layers  
- ⚡ **Hybrid:** Combines features for scalability and redundancy 

✅ Features:  
- 🚌 Bus Topology
- **IP Address Table:**
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
 
    * 
- ⭐ Star Topology
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
- 🔄 Ring Topology
- **IP Address Table:**
  | Device  | IPv4 Address    | IPv6 Address | VLAN | Connected To |
  |---------|-----------------|--------------|------|--------------|
  | PC1     | 192.168.3.1     | FD00:3::1    | 20   | Switch1      |
  | PC2     | 192.168.3.2     | FD00:3::2    | 20   | Switch2      |
  | PC3     | DHCP (192.168.3.50) | DHCP     | 20   | Switch3      |
  | PC4     | DHCP (192.168.3.51) | DHCP     | 20   | Switch3      |
  | Server0 | 192.168.3.100   | FD00:3::100  | 30   | Switch4      |
  Configuration Notes:**
  * Four switches connected in a ring formation using Copper Straight-Through cables.
  * Spanning Tree Protocol (STP) automatically activated to prevent network loops.
  * Server configured with DHCP, DNS, and HTTP services for the 192.168.3.0/24 network.
  * Mixed static and DHCP IP assignment for end devices.
 
  * 
- 🕸️ Mesh Topology
- **IP Address Table:**
  | Device  | IPv4 Address    | IPv6 Address | VLAN | Connected To |
  |---------|-----------------|--------------|------|--------------|
  | PC1     | 192.168.4.1     | FD00:4::1    | 20   | Switch1-Port Fa0/4 |
  | PC2     | 192.168.4.2     | FD00:4::2    | 20   | Switch2-Port Fa0/4 |
  | PC3     | DHCP (192.168.4.50) | DHCP     | 20   | Switch3-Port Fa0/4 |
  | PC4     | DHCP (192.168.4.51) | DHCP     | 20   | Switch4-Port Fa0/4 |
  | Server0 | 192.168.4.100   | FD00:4::100  | 30   | Switch1-Port Fa0/5 |
  - **Configuration Notes:**
* Full mesh design with 4 switches, each connected to all other switches.
* Provides multiple paths for data transmission and high redundancy.
* Spanning Tree Protocol (STP) automatically manages potential loops.
* Server configured with DHCP, DNS, and HTTP services for 192.168.4.0/24 network.
* Mixed static and DHCP IP assignment demonstrating flexibility.

* 
- 🌟 Extended Star Topology
- **IP Address Table (Selected Devices):**
  | Device  | IPv4 Address    | IPv6 Address | VLAN | Hierarchical Path |
  |---------|-----------------|--------------|------|-------------------|
  | PC1     | 192.168.5.1     | FD00:5::1    | 20   | Acc-Switch1 → Dist-Switch1 → Core |
  | PC2     | DHCP (192.168.5.50) | DHCP     | 20   | Acc-Switch1 → Dist-Switch1 → Core |
  | PC12    | DHCP (192.168.5.55) | DHCP     | 20   | Acc-Switch6 → Dist-Switch3 → Core |
  | Server0 | 192.168.5.100   | FD00:5::100  | 30   | Core-Switch |
  - **Configuration Notes:**
* Three-layer hierarchical design: Core, Distribution, and Access layers
* Scalable architecture allowing for easy expansion
* Mixed static and DHCP IP assignment across 12 end devices
* Server placed at core layer for centralized access
* VLAN segmentation configured for management, users, and servers

🌐 Hybrid Topology 
### IP Addressing Table

| Device | Interface | IPv4 Address | Subnet Mask | IPv6 Address | VLAN / Network | Description |
|--------|-----------|--------------|-------------|--------------|----------------|-------------|
| Router (2811) | Fa0/0.10 | 192.168.10.1 | 255.255.255.0 | 2001:DB8:10::1/64 | VLAN 10 | LAN_A Gateway |
| | Fa0/0.20 | 192.168.20.1 | 255.255.255.0 | 2001:DB8:20::1/64 | VLAN 20 | Wi-Fi Gateway |
| | Fa0/0.30 | 192.168.30.1 | 255.255.255.0 | 2001:DB8:30::1/64 | VLAN 30 | Server Gateway |
| | Fa0/1 | 10.0.0.1 | 255.255.255.252 | 2001:DB8:A::1/64 | WAN Link | Connection to ISP Router |
| ISP Router (1841) | Fa0/0 | 10.0.0.2 | 255.255.255.252 | 2001:DB8:A::2/64 | WAN Link | Simulated Cloud Connection |
| Switch – SW-Core | VLAN 1 | 192.168.10.2 | 255.255.255.0 | — | VLAN 10 | Core Switch for Inter-VLAN Routing |
| Switch – SW-A | — | — | — | — | VLAN 10 | LAN_A Access Switch |
| Switch – SW-B | — | — | — | — | VLAN 20 | Wi-Fi Access Switch |
| Server | NIC | 192.168.30.10 | 255.255.255.0 | 2001:DB8:30::10/64 | VLAN 30 | Web / DNS / FTP Server |
| PC1 | NIC | 192.168.10.10 | 255.255.255.0 | 2001:DB8:10::10/64 | VLAN 10 | LAN_A PC |
| PC2 | NIC | 192.168.10.11 | 255.255.255.0 | 2001:DB8:10::11/64 | VLAN 10 | LAN_A PC |
| Laptop (Wi-Fi) | Wireless NIC | 192.168.20.10 | 255.255.255.0 | 2001:DB8:20::10/64 | VLAN 20 | Wireless PC |
| WRT300N (Wi-Fi Router) | LAN | 192.168.20.254 | 255.255.255.0 | 2001:DB8:20::254/64 | VLAN 20 | Wireless Router |
| | WAN | DHCP / 192.168.20.1 | 255.255.255.0 | — | VLAN 20 | Connected to Main Router |
| Firewall (IPv6 ACL) | Applied on Router Fa0/1 | — | — | — | — | IPv6 Traffic Control |

### Network Segmentation
- **VLAN 10:** LAN_A (Wired Devices)
- **VLAN 20:** Wi-Fi Network (Wireless Devices)  
- **VLAN 30:** Server Network (Centralized Services)
- **WAN Link:** Internet Connection (10.0.0.0/30)

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
--- 

All topologies tested with **ping** and **web browsing** to verify connectivity. ✅ 

---

## 🔒 Part 2: Configure firewall rules to secure IPv6 traffic
- **Using the Star Topology**
- **Device:** Cisco 2881 Router  
- **Interface:** GigabitEthernet0/1  
- **Rules:**  
  - ✅ Permit HTTP (80), DNS (53), ICMP  
  - ❌ Deny Telnet (23), FTP (21), SSH (22)  
  - ✅ Permit all other IPv6 traffic  

---

## 🎥 Video Demonstration
Shows full functionality of all topologies, ping tests, and firewall verification.

▶️ Watch Project Demonstration (44665032_CMPG325_Project.mp4)

---

## 🛠️ Tools & References
- **Cisco Packet Tracer**  
- **GitHub guides** for network simulation and configuration  
