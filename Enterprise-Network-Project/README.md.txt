 Small Enterprise Network Simulation – Cisco Packet Tracer (THIS PROJECT IS NOT FULLY OPTIMIZED OR DONE , I AM STILL WORKING ON SOME THINGS BUT I THOUGHT IT WOULD BE NICE TO GET SOME ADVICE/THOUGHTS)

This project simulates a small business network using Cisco Packet Tracer. It includes complete VLAN segmentation, dynamic IP automation via DHCP, NAT for internet access, and inter-VLAN routing — reflecting key CCNA-level concepts and network engineering practices.

---

##  Overview

-  **VLANs**: HR, IT, Sales, and Guest networks
-  **DHCP**: Automated IP assignment for each department
-  **NAT**: Translation from private to public IP for internet access
-  **Inter-VLAN Routing**: Using router-on-a-stick via sub interfaces
-  **ACL Ready**: Guest VLAN isolated from internal subnets
-  **Tested and Verified**: Connectivity, routing, and translation tested with ping and `ipconfig`

---

##  Network Topology

![Network Topology](screenshots/topology.png)

---

## 🔧 Configured Features

### VLAN Assignment
- HR (VLAN 10) → PC0, PC1 (Switch2)
- IT (VLAN 20) → PC2, PC3 (Switch2, Switch1)
- Sales (VLAN 30) → PC4, PC5 (Switch1)
- Guest (VLAN 99) → PC6 (Cloud)

### DHCP Pools (Router or Server)
Each VLAN has its own pool with:
- Subnet: 192.168.X.0/24
- Gateway: 192.168.X.1
- DNS: 8.8.8.8
- Start IPs for client assignment

Example (Sales VLAN):
ip dhcp pool SALES
 network 192.168.30.0 255.255.255.0
 default-router 192.168.30.1
 dns-server 8.8.8.8