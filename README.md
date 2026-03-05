# Homelab

My comprehensive **cybersecurity homelab** designed to simulate a small enterprise environment. This project integrates multiple security technologies to practice **network defense, vulnerability assessment, identity management, and incident investigation** in a controlled lab environment.

The lab replicates common enterprise infrastructure components such as **Active Directory, VPN access, firewall segmentation, centralized logging, and vulnerability scanning**.

The goal is to build practical experience with **defensive security operations and enterprise infrastructure security**.

---

# Lab Architecture

The environment is built using a combination of **VirtualBox, VMware Fusion, and a Raspberry Pi** to simulate internal infrastructure and external threat activity.

### Domain

```
SECURECORP.LOCAL
```

### Infrastructure Overview

| ID | Hostname | OS | Role | IP Address | Virtualization | OU | Host Machine |
|----|----------|----|------|------------|---------------|----|--------------|
| 1 | DC01 | Windows Server 2022 | Domain Controller | Static | VirtualBox | Domain | Huawei Matebook D15 |
| 2 | pfSense | pfSense CE (FreeBSD based) | Firewall / Gateway | Static | VirtualBox | Network | Huawei Matebook D15 |
| 3 | SPLUNK-SERVER | Ubuntu Server 24.04 LTS | SIEM / Log Management | DHCP | VirtualBox | Services OU | Huawei Matebook D15 |
| 4 | SEC-SCANNER | Ubuntu Server 22.04 LTS | Vulnerability Scanner | DHCP | VMware Fusion | Services OU | Mac M1 Pro |
| 5 | RDP-SERVER | Windows 11 Enterprise | Remote Access Server | DHCP | VMware Fusion | Services OU | Mac M1 Pro |
| 6 | VPN-SERVER | Ubuntu Server 22.04 LTS | OpenVPN Server | DHCP Reservation | VirtualBox | Remote OU | Huawei Matebook D15 |
| 7 | PC01 | Windows 11 Enterprise | User Workstation | DHCP | VMware Fusion | Operations OU | Mac M1 Pro |
| 8 | PC02 | Windows 11 Pro | User Workstation | DHCP | VMware Fusion | Operations OU | Mac M1 Pro |
| 9 | VULN-SERVER | Windows XP | Vulnerable Host | DHCP | VirtualBox | Operations OU | Huawei Matebook D15 |
| 10 | RASPBERRY | Ubuntu Server 22.04 LTS | Simulated External Threat Actor | Static | Raspberry Pi Zero 2 W | External | Physical Device |

---

# Network Diagram

```
                Internet
                    |
               [pfSense Firewall]
                    |
        -------------------------------
        |             |              |
    Domain        Services        Remote
    Network       Network         Access
        |             |              |
     [DC01]     [Splunk Server]   [VPN Server]
        |             |
    Workstations   Security Tools
   (PC01, PC02)    (Nessus Scanner)

External Attacker Simulation
      |
[Raspberry Pi Threat Actor]
```

---

# Technologies Used

## Infrastructure

- Active Directory (Windows Server 2022)
- DNS
- DHCP
- Group Policy

## Network Security

- pfSense Firewall
- OpenVPN with LDAP authentication
- Network segmentation

## Monitoring & Detection

- Splunk SIEM
- Centralized log aggregation
- Security event monitoring

## Vulnerability Management

- Nessus vulnerability scanning
- Vulnerability identification and analysis

## Attack Simulation

- Raspberry Pi external threat simulation
- Reconnaissance and attack emulation against lab hosts

## Virtualization

- VirtualBox
- VMware Fusion
- Raspberry Pi hardware

---

# Security Scenarios Tested

This lab enables testing and analysis of several real-world security situations:

- Authentication and authorization events in Active Directory
- Remote VPN access using LDAP authentication
- Firewall rule configuration and network segmentation
- Detection of suspicious activity through SIEM logs
- Vulnerability discovery using Nessus scans
- External attack simulation against internal hosts
- Incident investigation using centralized logs

---

# Skills Demonstrated

This project demonstrates hands-on experience in several key cybersecurity areas:

## Defensive Security

- Security monitoring
- Log analysis
- Incident investigation

## Infrastructure Security

- Active Directory administration
- DNS and DHCP configuration
- Identity and access management

## Network Security

- Firewall configuration
- VPN setup
- Network segmentation

## Vulnerability Management

- Vulnerability scanning
- Risk identification
- Security assessment

## Systems Administration

- Linux server administration
- Windows server management
- Multi-OS troubleshooting

---

# Project Goals

- Simulate a realistic enterprise network environment
- Gain practical experience with defensive cybersecurity tools
- Develop skills in incident detection and response
- Practice vulnerability assessment and remediation
- Understand how enterprise security infrastructure operates

---

# Future Improvements

Planned expansions for the lab include:

- Security orchestration and automation
- Endpoint detection and response (EDR)
- Threat intelligence integration
- Automated attack simulations
- Blue team detection exercises

---
