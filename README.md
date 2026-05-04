# 🌐 DHCP Server Configuration with VLAN Segmentation (Cisco Packet Tracer)

## 📌 Overview
This project demonstrates the configuration of a DHCP infrastructure in a segmented network using VLANs.  
The goal was to simulate how IP address assignment works across different departments within an organization.

---

## 🎯 Objective
- Configure a DHCP server for automatic IP allocation  
- Implement VLAN segmentation (HR and IT)  
- Validate network connectivity within and across VLANs  
- Understand DHCP limitations in multi-VLAN environments  

---

## 🧱 Network Topology
- 1 Server (DHCP)
- 1 Switch
- 3 PCs:
  - 2 in **HR VLAN (VLAN 10)**
  - 1 in **IT VLAN (VLAN 20)**

---

## 🛠️ Technologies Used
- Cisco Packet Tracer  
- VLAN configuration  
- DHCP protocol  
- Basic network troubleshooting (ping tests)  

---

## 🔧 Configuration Steps

### 1. Server Setup
- Assigned static IP: `192.168.1.1`  
- Enabled DHCP service  
- Configured IP pool:
  - Start: `192.168.1.2`
  - Max users: 253  

---

### 2. VLAN Configuration
- VLAN 10 → HR department  
- VLAN 20 → IT department  

Switch ports:
- fa0/2 → HR PC1  
- fa0/3 → HR PC2  
- fa0/4 → IT PC  
- fa0/1 → DHCP Server  

---

### 3. DHCP Assignment
- HR VLAN successfully received IPs automatically  
- IT VLAN required a separate DHCP configuration  

---

## ⚠️ Limitation Identified

- Devices in different VLANs could not communicate  
- DHCP server did not assign IPs across VLANs  

### Root Cause:
- No inter-VLAN routing configured  
- Each VLAN behaves as a separate network  

---

## 🔍 Testing & Validation

### ✅ Successful Tests
- Ping between HR PCs → Success  
- Ping from HR PCs to server → Success  
- DHCP IP assignment confirmed  

### ❌ Failed Tests
- Ping between HR and IT VLAN → Failed  
- IT PC did not receive IP from initial DHCP server  

---

## 🧠 Solution Implemented

- Added second DHCP server for VLAN 20  
- Configured new network:
  - IP: `192.168.10.1`  
- IT PC successfully received IP  

---

## 💥 Key Learnings
- VLANs isolate network traffic  
- DHCP does not cross VLANs without relay  
- Inter-VLAN communication requires routing  
- Network segmentation improves security but adds complexity  

---

## 🚀 Possible Improvements
- Implement router for inter-VLAN routing  
- Configure DHCP Relay (IP Helper)  
- Centralize DHCP instead of multiple servers  

---

## 📎 Full Report
👉 See full detailed report: `dhcp-lab-report.pdf`
