# Network Reconnaissance Detection (Nmap + Suricata + Wazuh)

## Overview
* This project simulates network reconnaissance activity using Nmap and demonstrates how port scanning behavior can be detected using Suricata    IDS and analyzed and prevented through Wazuh SIEM.

* The objective is to replicate the reconnaissance phase of an attack, where an attacker scans a target system to discover open ports and         services.

---

## Tools & Technologies

- Kali Linux (Attacker machine)
- Linux Mint (Target machine)
- Wazuh SIEM (Manager)
- Suricata (Network IDS/IPS)
- Nmap (Network scanning tool)

---

## Lab Architecture

- Wazuh Manager installed on Kali Linux  
- Wazuh Agent installed on Linux Mint  
- Suricata deployed on Linux Mint to monitor network traffic  
- All systems connected within the same local network  

---

## Attack Simulation

### Step 1: Perform SYN scan
nmap -sS -p- 192.168.1.127

### Step 2: Perform service/version detection scan
nmap -A 192.168.1.127

---

## Detection & Analysis

* Suricata detected:
- SYN scan behavior  
- Multiple connection attempts across ports  
- Suspicious network probing activity  

* Wazuh SIEM:
- Collected Suricata alerts  
- Correlated scan activity across events  
- Identified reconnaissance behavior  

---

## Active Response

* Wazuh active response was configured to automatically block the attacker IP after detecting suspicious scanning activity.
- Triggered firewall drop action on the target machine  
- Blocked further communication from the attacker  
- Demonstrated automated threat mitigation (IDS → IPS behavior)  

---

## Alerts Observed

- Network scan detection alerts triggered  
- High number of connection attempts within a short timeframe  
- Suspicious traffic patterns consistent with port scanning  

---

## MITRE ATT&CK Mapping
- T1046 – Network Service Discovery

---

## Key Learnings

- Understanding reconnaissance phase of cyber attacks  
- Detecting port scanning using IDS tools  
- Integrating Suricata alerts into Wazuh SIEM  
- Implementing active response for automated threat blocking  
- Analyzing network-based threats through log correlation  

---

## Screenshots

- Nmap scan execution (attacker side)  
- Suricata alerts  
- Wazuh detection dashboard/logs  
- Active response / blocked connection  

---

## 🔗 Author
GitHub: https://github.com/ognenkostov-hub  
LinkedIn: https://www.linkedin.com/in/ognen-kostov-42921881
