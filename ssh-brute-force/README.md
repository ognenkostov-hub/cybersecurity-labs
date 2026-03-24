# SSH Brute Force Detection (Hydra + Wazuh)

## Overview

This project simulates an SSH brute force attack using Hydra and demonstrates how repeated authentication failures are detected and analyzed using Wazuh SIEM.

The goal is to replicate a credential access attack and monitor how security tools identify and log malicious login attempts.

---

## Tools & Technologies

- Kali Linux (Attacker machine)
- Linux Mint (Target machine)
- Wazuh SIEM (Manager)
- Hydra (Brute force tool)
- SSH service (Target)

---

## Lab Architecture

- Wazuh Manager installed on Kali Linux  
- Wazuh Agent installed on Linux Mint  
- SSH service enabled on target machine  
- Both machines connected within the same local network  

---

## Attack Simulation

### Step 1: Execute brute force attack using Hydra
hydra -l ognen -P /usr/share/wordlists/rockyou.txt 192.168.1.127 ssh

### Step 2: Generate repeated login attempts
- Multiple failed SSH login attempts triggered  
- High-frequency authentication requests observed  

---

## Detection & Analysis

Wazuh detected:
- Multiple failed SSH login attempts  
- “authentication failed” events  
- “user missed password more than one time” alerts  

Key observations:
- Source IP: 192.168.1.198 (attacker)  
- Target IP: 192.168.1.127  
- Username targeted: ognen  
- High alert frequency (rule.firedtimes > 50)  

---

## MITRE ATT&CK Mapping

- T1110 – Brute Force  
- T1110.001 – Password Guessing  

  Tactic:
- Credential Access  

---

## Alerts Observed

- sshd: authentication failed  
- syslog: user missed password more than one time  
- High volume of login attempts within short timeframe  

---

## Key Learnings

- Understanding brute force attack behavior  
- Detecting credential access attempts using SIEM  
- Monitoring authentication logs (sshd + syslog)  
- Correlating multiple failed login events  
- Mapping attacks to MITRE ATT&CK framework  

---

## Screenshots

- Hydra attack execution  
- Wazuh alerts (authentication failed)  
- High rule.firedtimes values  
- MITRE ATT&CK mapping in Wazuh  

---

## Author
GitHub: https://github.com/ognenkostov-hub/cybersecurity-labs  
LinkedIn: https://www.linkedin.com/in/ognen-kostov-42921881
