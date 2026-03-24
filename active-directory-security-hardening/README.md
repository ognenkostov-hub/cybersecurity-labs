# Active Directory Security Hardening (GPO + AD DS)

## Overview
This project demonstrates the implementation of security hardening techniques in an Active Directory environment using Group Policy Objects (GPO). 

The goal is to reduce attack surface, enforce strong authentication policies, and protect against common threats such as brute-force attacks and unauthorized access.

The lab focuses on configuring password policies, account lockout mechanisms, and disabling insecure default accounts, following real-world enterprise security practices.

---

## Tools & Technologies
- Windows Server (Active Directory Domain Services)
- Group Policy Management Console (GPMC)
- Active Directory Users and Computers (ADUC)
- Windows Command Prompt
- Domain Environment (aciplab.com)

---

## Lab Architecture
- Windows Server configured as Domain Controller  
- Active Directory Domain: aciplab.com  
- Group Policy Objects applied at domain level  
- Domain users and groups created and managed  
- Security policies enforced via GPO  

---

## Security Configuration

### Step 1: Password Policy Hardening

Configured strong password requirements via GPO:

- Minimum password length: 10 characters  
- Password complexity: Enabled  
- Password history enforced  
- Maximum and minimum password age defined  

Purpose:
- Prevent weak passwords  
- Reduce risk of credential compromise  

---

### Step 2: Account Lockout Protection

Configured account lockout policies:

- Account lockout threshold: 5 invalid attempts  
- Account lockout duration: 10 minutes  
- Reset counter: 10 minutes  

Purpose:
- Protect against brute-force attacks  
- Limit unauthorized login attempts  

---

### Step 3: Disable Guest Account

Disabled built-in Guest account via GPO and verified using command line.

Verification command:
net user guest

Result:
- Guest account status: **Inactive**

Purpose:
- Reduce attack surface  
- Prevent unauthorized access through default accounts  

---

## Detection & Validation

Validation steps performed:

- Verified GPO settings applied successfully  
- Confirmed password policy enforcement  
- Tested account lockout behavior  
- Verified Guest account disabled via command line  

---

## Security Concepts Applied

- Identity & Access Management (IAM)  
- Principle of Least Privilege  
- Authentication Hardening  
- Brute Force Protection  
- Attack Surface Reduction  
- Security Policy Enforcement  

---

## Security Improvements Achieved
- Enforced strong password policies  
- Prevented unlimited login attempts  
- Disabled insecure default account  
- Strengthened overall domain security posture  

---

## Key Learnings
- Configuring and managing Group Policy Objects (GPO)  
- Applying domain-level security policies  
- Securing Active Directory environments  
- Understanding real-world enterprise hardening practices  
- Verifying security configurations through testing  

---

## Screenshots
Add screenshots showing:
- GPO (Default Domain Policy) configuration  
- Password policy settings  
- Account lockout policy  
- Guest account disabled (GPO view)  
- Command line verification (`net user guest`)  

---

## Lab Environment & Credits

This project was conducted using a virtual lab environment provided by ACI Learning (ACILab).

While the lab infrastructure was pre-configured, all security configurations, policy implementations, and validation steps were performed independently.

The project reflects hands-on practice in Active Directory security hardening, simulating real-world enterprise scenarios.

---

## Author
GitHub: https://github.com/ognenkostov-hub/cybersecurity-labs
LinkedIn: https://www.linkedin.com/in/ognen-kostov-42921881
