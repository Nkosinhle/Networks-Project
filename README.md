# 🌐 CMPG325 Networks Project

**👤 Student Name:** Nkosinhle  
**🆔 Student Number:** 44665032  
**📅 Due Date:** 13 October 2025  

---

## 📖 Overview
Final year project simulating and configuring multiple network topologies using **Cisco Packet Tracer**.  

✅ Features:  
- 🚌 Bus Topology  
- ⭐ Star Topology  
- 🔄 Ring Topology  
- 🕸️ Mesh Topology  
- 🌟 Extended Star Topology  
- ⚡ Hybrid Topology combining multiple designs  
- 🔒 IPv6 Firewall configuration  
- 🎥 Video demonstration of network functionality  

---

## 💻 IP Addressing & VLANs

**IPv4 Example:**  
- Bus: 192.168.1.0/24, Server: 192.168.1.100, DHCP: 192.168.1.50–99  
- Star: 192.168.2.0/24, Server: 192.168.2.100, DHCP: 192.168.2.50–99  

**VLANs:**  
- VLAN 10 = 🛠️ MANAGEMENT  
- VLAN 20 = 👥 USERS  
- VLAN 30 = 💻 SERVERS  

**IPv6 Example:**  
- Bus: FD00:0001::/64, Server: FD00:0001::100  
- Star: FD00:0002::/64, Server: FD00:0002::100  

*(Other topologies follow the same addressing scheme.)*  

---

## 🌐 Topologies
- 🚌 **Bus:** Linear network  
- ⭐ **Star:** Centralized switch  
- 🔄 **Ring:** Circular switch formation with STP  
- 🕸️ **Mesh:** Full redundancy between switches  
- 🌟 **Extended Star:** Hierarchical core, distribution, access layers  
- ⚡ **Hybrid:** Combines features for scalability and redundancy  

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

---

## 🛠️ Tools & References
- **Cisco Packet Tracer**  
- **GitHub guides** for network simulation and configuration  
