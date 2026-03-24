# Enterprise VPN Deployment & Secure Remote Access (RRAS + Active Directory)

## Overview
This project demonstrates the deployment and configuration of a secure VPN infrastructure using Routing and Remote Access Services (RRAS) in a Windows Server environment.

The goal is to enable secure remote connectivity for domain users while enforcing authentication, access control, and firewall configurations aligned with enterprise security practices.

The lab includes VPN server setup, Active Directory user provisioning, firewall configuration, logging, and validation of remote client connectivity.

---

## Tools & Technologies
- Windows Server (Routing and Remote Access Services - RRAS)
- Active Directory Domain Services (AD DS)
- Group Policy & Security Configuration
- Windows Defender Firewall
- Event Viewer (Logging & Monitoring)
- Windows Client (VPN Testing)
- Domain Environment (aciplab.com)

---

## Lab Architecture
- Windows Server configured as VPN Server (RRAS)  
- Active Directory Domain: aciplab.com  
- Remote Access role installed and configured  
- VPN access enabled for domain users  
- Firewall rules configured for secure communication  
- Client machine connected via VPN  

---

## VPN Deployment & Configuration

### Step 1: Install Remote Access Role

Installed Remote Access role via Server Manager:

- Selected DirectAccess and VPN (RAS)  
- Enabled required role services  

Purpose:
- Provide secure remote connectivity  
- Enable VPN tunneling services  

---

### Step 2: Configure RRAS (VPN Server)

Configured Routing and Remote Access:

- Selected Custom Configuration  
- Enabled VPN access  
- Started RRAS service  

Purpose:
- Allow remote clients to connect securely  
- Establish VPN gateway functionality  

---

### Step 3: Configure IP Address Assignment

Configured IPv4 address allocation:

- Used Static IP address pool  

Purpose:
- Assign IP addresses to VPN clients  
- Ensure proper network segmentation  

---

### Step 4: Configure Firewall Rules

Configured Windows Defender Firewall:

- Allowed Routing and Remote Access  
- Enabled Secure Socket Tunneling Protocol (SSTP)  
- Verified HTTPS-related services  

Purpose:
- Allow VPN traffic through firewall  
- Maintain secure encrypted communication  

---

### Step 5: Logging & Monitoring

Configured logging settings:

- Enabled RRAS event logging  
- Created custom Event Viewer filters for VPN activity  

Purpose:
- Monitor connection attempts  
- Detect anomalies and troubleshoot issues  

---

### Step 6: Active Directory User Configuration

Configured VPN users:

- Created Organizational Unit (Users VPN)  
- Created test user account  
- Added user to Remote Desktop Users group  

Purpose:
- Control VPN access through Active Directory  
- Implement identity-based access management  

---

### Step 7: VPN Client Configuration & Testing

Configured VPN connection on client machine:

- Created VPN profile (MyVPN)  
- Connected using domain credentials  

Validation:

- Successful VPN connection established  
- Verified secure remote access  

---

## Detection & Validation

Validation steps performed:

- Verified RRAS service is running  
- Confirmed VPN connectivity from client machine  
- Tested authentication using AD credentials  
- Verified firewall rules allow VPN traffic  
- Checked logs in Event Viewer for VPN activity  

---

## Security Concepts Applied

- Remote Access Security  
- VPN Tunneling & Encryption (SSTP)  
- Identity & Access Management (IAM)  
- Network Segmentation  
- Firewall Configuration  
- Secure Remote Connectivity  
- Logging & Monitoring  

---

## Security Improvements Achieved

- Enabled secure remote access for domain users  
- Enforced authentication via Active Directory  
- Restricted access through firewall rules  
- Implemented logging for monitoring and visibility  
- Reduced exposure of internal network resources  

---

## Key Learnings

- Deploying VPN infrastructure using RRAS  
- Configuring secure remote access in enterprise environments  
- Integrating Active Directory with VPN authentication  
- Managing firewall rules for secure connectivity  
- Monitoring VPN activity through logs and event filtering  
- Troubleshooting remote access issues  

---

## Screenshots

Add screenshots showing:

- Remote Access role installation  
- RRAS configuration (VPN enabled)  
- IP address pool configuration  
- Firewall allowed apps/services  
- Event Viewer (VPN logs)  
- Active Directory user creation  
- VPN connection from client machine  

---

## Lab Environment & Credits

This project was conducted using a virtual lab environment provided by ACI Learning (ACILab).

While the lab infrastructure was pre-configured, all security configurations, policy implementations, and validation steps were performed independently.

The project reflects hands-on practice in Active Directory security hardening, simulating real-world enterprise scenarios.

---

## Author

GitHub: https://github.com/ognenkostov-hub/cybersecurity-labs  
LinkedIn: https://www.linkedin.com/in/ognen-kostov-42921881  
