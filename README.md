# Cybersecurity Labs Portfolio

This repository contains hands-on cybersecurity lab projects demonstrating SIEM monitoring, intrusion detection, endpoint telemetry, network scanning, attack simulation, Active Directory security hardening, and secure VPN deployment using industry-relevant tools.

---

## Lab Environment

Part of the labs were conducted on **physical machines** to better simulate real-world cybersecurity scenarios, including network traffic behavior, endpoint telemetry, and system-level interactions.


**Equipment used:**

- HP 255 G8 Notebook (Linux Mint)
- Lenovo G50-80 (Windows10)
- ASUS VivoBook X512D (Kali)
- Wireless Router TP-Link Archer C24


The Active Directory environment was deployed using **virtualization (ACI Lab)** to accurately replicate enterprise domain infrastructure, user management, and policy enforcement.

This setup allowed for more accurate detection, logging, and analysis compared to purely virtual environments.
## Tools & Technologies

---

- Wazuh (SIEM)
- Suricata (IDS)
- Sysmon (Endpoint Telemetry)
- Nmap (Network Scanning)
- PowerShell (Attack Simulation)
- Windows Server (Active Directory Domain Services, RRAS)
- Group Policy Management (GPO)
- Windows Defender Firewall
- Event Viewer (Logging & Monitoring)

---

## Projects Overview

### 1. Wazuh SIEM Monitoring
📂 [View Project](./wazuh-powershell-attack-detection)

- Configured Wazuh for log collection and analysis  
- Monitored system activity and generated alerts  
- Detected suspicious behavior through log correlation  

---

### 2. Suricata Intrusion Detection
📂 [View Project](./ssh-brute-force)

- Configured Suricata IDS for network monitoring  
- Analyzed network traffic for malicious patterns  
- Generated alerts for suspicious activity  

---

### 3. Nmap Network Scanning
📂 [View Project](./nmap-detection)

- Performed host discovery and port scanning  
- Identified open ports and running services  
- Conducted service enumeration and network mapping  

---

### 4. PowerShell Attack Detection
📂 [View Project](./wazuh-powershell-attack-detection)

- Simulated malicious PowerShell activity (encoded commands)  
- Generated process execution events  
- Collected endpoint telemetry using Sysmon  
- Detected suspicious behavior in Wazuh SIEM  

Focus:
- PowerShell execution monitoring  
- Endpoint telemetry analysis  
- SIEM detection rules  

---

### 5. Malware Behavior Simulation
📂 [View Project](./malware-simulation)

- Simulated malware-like activity on a Windows system  
- Created files in suspicious directories (Temp paths)  
- Modified registry keys (persistence techniques)  
- Generated detectable events for SIEM analysis  

Focus:
- Malware behavior patterns  
- File and registry monitoring  
- Detection through logs and alerts  

---

### 6. Active Directory Security Hardening
📂 [View Project](./active-directory-security-hardening)

- Configured domain-level security policies using GPO  
- Enforced strong password requirements and complexity rules  
- Implemented account lockout policies to prevent brute-force attacks  
- Disabled insecure default accounts (Guest account)  
- Verified configurations through command-line and policy validation  

Focus:
- Identity & Access Management (IAM)  
- Security hardening  
- Policy enforcement  
- Attack surface reduction  

---

### 7. Enterprise VPN Deployment & Secure Remote Access
📂 [View Project](./enterprise-vpn-deployment-rras-active-directory)

- Deployed VPN infrastructure using Routing and Remote Access Services (RRAS)  
- Configured Remote Access role and enabled VPN services  
- Implemented static IP address pool for VPN clients  
- Configured Windows Defender Firewall to allow VPN traffic (SSTP)  
- Enabled logging and monitoring using Event Viewer  
- Created and managed VPN users in Active Directory  
- Configured and tested VPN connection from client machine  

Focus:
- Secure remote access  
- VPN tunneling & encryption (SSTP)  
- Identity & access management (IAM)  
- Firewall configuration  
- Logging and monitoring  

---

## Objective

The goal of these labs is to build practical, hands-on experience in cybersecurity operations, focusing on:

- Threat detection & monitoring  
- Intrusion detection systems  
- Network analysis & scanning  
- Endpoint telemetry and log analysis (Sysmon)  
- Identity & access security (Active Directory)  
- Secure remote access (VPN)  
- Security hardening and policy enforcement  

These projects simulate real-world security scenarios and demonstrate the ability to detect, analyze, and secure enterprise environments.

---

## Author

**Ognen Kostov**  
Aspiring Cybersecurity Professional  

- GitHub: https://github.com/ognenkostov-hub/cybersecurity-labs  
- LinkedIn: https://www.linkedin.com/in/ognen-kostov-42921881  
