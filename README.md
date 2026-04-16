# 🏢 Startup Network Design – Cisco Packet Tracer

![Network](https://img.shields.io/badge/Cisco-Packet%20Tracer-blue?style=for-the-badge&logo=cisco)
![VLAN](https://img.shields.io/badge/VLANs-Configured-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)

---

## 📌 Overview
A fully functional small business network designed and implemented using Cisco Packet Tracer. This project simulates a real startup company environment with department segmentation, centralized server services, and secure remote management.

## 🗂️ Network Topology

        [Router R1 – Cisco 1941]
          GigabitEthernet 0/0
                  |
          GigabitEthernet 0/1
        [SW1-Core – Cisco 2960]
      /    /    |    |    |    \    \
  PC-HR1 IT1  IT2  IT3  IT4  SERVER  ADMIN-PC
  fa0/1  fa0/2 ...       fa0/6  fa0/7
---

## 🗃️ VLAN Structure

| VLAN | Name    | Network           | Gateway       | Purpose              |
|------|---------|-------------------|---------------|----------------------|
| 10   | HR      | 192.168.10.0/24   | 192.168.10.1  | HR Department PC     |
| 20   | IT      | 192.168.20.0/24   | 192.168.20.1  | IT Department PCs    |
| 40   | SERVER  | 192.168.40.0/24   | 192.168.40.1  | DHCP / DNS / Web     |
| 99   | MGMT    | 192.168.99.0/24   | 192.168.99.1  | Admin & Management   |

---

## 💻 Device IP Table

| Device   | VLAN | IP Address      | Method  |
|----------|------|-----------------|---------|
| PC-HR1   | 10   | 192.168.10.x    | DHCP    |
| PC-IT1   | 20   | 192.168.20.x    | DHCP    |
| PC-IT2   | 20   | 192.168.20.x    | DHCP    |
| PC-IT3   | 20   | 192.168.20.x    | DHCP    |
| PC-IT4   | 20   | 192.168.20.x    | DHCP    |
| Server   | 40   | 192.168.40.10   | Static  |
| Admin PC | 99   | 192.168.99.10   | Static  |

---

## ✅ Features Implemented

- ✅ VLAN Segmentation — HR, IT, Server, Management isolated
- ✅ Inter-VLAN Routing — Router-on-a-Stick (802.1Q sub-interfaces)
- ✅ DHCP Server — Auto IP assignment for HR and IT with relay agent
- ✅ DNS Server — Resolves www.startup.local
- ✅ HTTP Web Server — Internal company portal
- ✅ SSH Remote Management — Admin can securely manage the router
- ✅ Port Security — Unused switch ports disabled
- ✅ Spanning Tree (STP) — Portfast enabled on access ports

---

## 🔌 Cabling

| From       | Port        | To         | Port            |
|------------|-------------|------------|-----------------|
| R1         | G0/0        | SW1-Core   | G0/1            |
| SW1-Core   | fa0/1       | PC-HR1     | FastEthernet 0  |
| SW1-Core   | fa0/2       | PC-IT1     | FastEthernet 0  |
| SW1-Core   | fa0/3       | PC-IT2     | FastEthernet 0  |
| SW1-Core   | fa0/4       | PC-IT3     | FastEthernet 0  |
| SW1-Core   | fa0/5       | PC-IT4     | FastEthernet 0  |
| SW1-Core   | fa0/6       | Server     | FastEthernet 0  |
| SW1-Core   | fa0/7       | Admin PC   | FastEthernet 0  |

> All links use GigabitEthernet (1000 Mbps) for the uplink and FastEthernet (100 Mbps) for end devices.


## 🧪 Tests Performed

# From any PC — automatic IP via DHCP
ipconfig

# Ping across VLANs
ping 192.168.10.x    # HR to IT
ping 192.168.40.10   # Any PC to Server

# Web browser
http://www.startup.local   # Internal portal

# Admin remote management
ssh -l admin 192.168.99.1  # Secure router access

## 🧠 Features
- VLAN segmentation (IT, Admin, Server)
- Router-on-a-stick configuration
- Basic network security
- Structured IP addressing

## 🖥️ Technologies
- Cisco Packet Tracer
- Networking (CCNA basics)

## 🧪 Testing
- Successful communication within VLANs
- Inter-VLAN routing verified using ping

## 📷 Network Diagram
<img width="1366" height="619" alt="Capture" src="https://github.com/user-attachments/assets/cd9e6a21-5734-4493-81f1-84013171d41e" />


## 📁 Files

| File              | Description                    |
|-------------------|--------------------------------|
| Network.pkt | Cisco Packet Tracer project file |
| README.md       | This documentation              |

## 🚀 Author
Marouane akid
