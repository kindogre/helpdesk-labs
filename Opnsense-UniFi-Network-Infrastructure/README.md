# Small Business Network Infrastructure Lab (OPNsense + UniFi)

## Overview

Designed and deployed a **small-business style segmented network** using real hardware:

- **Firewall Appliance:** Protectli VP4650 running OPNsense  
- **Managed Switch:** UniFi Lite 8 PoE  
- **Wireless Access Point:** UniFi U7 Lite  
- **Management Platform:** UniFi Network Application  

This project demonstrates practical hands-on experience with technologies and responsibilities commonly seen in real IT environments, including:

- VLAN segmentation
- Deny-by-default firewall design
- Dedicated management access
- DHCP and DNS infrastructure
- IDS / IPS monitoring with Suricata
- Managed switching and wireless VLAN mapping
- Structured troubleshooting
- Technical documentation

---

## Business Relevance

This lab was designed to simulate a small business environment where different users, guests, and devices require different trust levels, controlled access, reliable infrastructure services, and secure administration.

The design reflects practical responsibilities relevant to:

- Help Desk Technician
- IT Support Specialist
- Junior Network Administrator
- NOC Technician
- SOC Analyst (Tier 1)

---

## Network Topology

![Network Topology](assets/network-topology.png)

---

## Project Highlights

- Built a segmented production-style network using real hardware
- Separated management, guest, user, and restricted-device traffic
- Applied least-privilege firewall policies between trust zones
- Enforced internal DNS through Unbound
- Deployed Kea DHCP scopes per subnet
- Enabled Suricata IDS / IPS visibility
- Integrated OPNsense routing with UniFi switching and wireless infrastructure

---

# OPNsense Configuration

## 01. Dashboard

![OPNsense Dashboard](screenshots/opnsense/01-Lobby-Dashboard.png)

Main firewall overview showing platform health, running services, and system status.

---

## 02. Interface Assignments

![Interface Assignments](screenshots/opnsense/05-Interfaces-Assignments.png)

Physical and logical interfaces mapped to the correct networks and VLANs.

---

## 03. Interfaces Overview (View 1)

![Interfaces Overview 1](screenshots/opnsense/06-Interfaces-Overview-01.png)

Segmented interface layout with dedicated networks for different trust levels.

---

## 04. Interfaces Overview (View 2)

![Interfaces Overview 2](screenshots/opnsense/06-Interfaces-Overview-02.png)

Additional view of the multi-network design and addressing layout.

---

## 05. Admin Management Rules

![Admin Management Rules](screenshots/opnsense/09-Firewall-Rules-ADMIN_MGMT.png)

Dedicated management path used for secure firewall administration and recovery access.

---

## 06. Guest Access Rules

![Guest Access Rules](screenshots/opnsense/11-Firewall-Rules-VLAN_GuestAccess.png)

Guest devices isolated from internal resources while retaining internet access.

---

## 07. Restricted Devices Rules

![Restricted Devices Rules](screenshots/opnsense/12-Firewall-Rules-VLAN_RestrictedDevices.png)

Low-trust network with tighter outbound controls and blocked access to sensitive internal systems.

---

## 08. Secure Users Rules

![Secure Users Rules](screenshots/opnsense/13-Firewall-Rules-VLAN_SecureUsers.png)

Higher-trust network used for primary personal or administrative devices.

---

## 09. Standard Users Rules

![Standard Users Rules](screenshots/opnsense/14-Firewall-Rules-VLAN_StandartUsers.png)

Separate user zone for everyday devices with distinct access requirements.

---

## 10. WAN Rules

![WAN Rules](screenshots/opnsense/15-Firewall-Rules-WAN.png)

WAN-facing deny-by-default posture with no unnecessary inbound exposure.

---

## 11. Firewall Aliases

![Firewall Aliases](screenshots/opnsense/07-Firewall-Aliases.png)

Aliases used to simplify policy management and improve rule readability.

---

## 12. Outbound NAT

![Outbound NAT](screenshots/opnsense/08-Firewall-NAT-Outbound.png)

Automatic outbound NAT supporting internet access across multiple internal networks.

---

## 13. LAN Rules

![LAN Rules](screenshots/opnsense/10-Firewall-Rules-LAN.png)

Firewall policies applied to the LAN / backbone side of the network design.

---

## 14. Advanced Firewall Settings

![Advanced Firewall Settings](screenshots/opnsense/16-Firewall-Settigns-Advanced.png)

Advanced firewall behavior supporting hardened management access and custom policy design.

---

## 15. Suricata Netmap IPS Administration

![Suricata Netmap IPS Administration](screenshots/opnsense/17-Services-SuricataNetmapIPS-Administration.png)

Intrusion prevention configured on selected interfaces for active traffic inspection.

---

## 16. Suricata IDS Alert

![Suricata IDS Alert](screenshots/opnsense/18-Services-SuricataIDS-EXPLOIT_ALERT.png)

Example alert demonstrating visibility into inspected traffic.

---

## 17. Kea DHCPv4 Settings

![Kea DHCPv4 Settings](screenshots/opnsense/19-Services-KeaDHCPv4-Settings.png)

DHCP service configuration supporting segmented client addressing.

---

## 18. Kea DHCPv4 Subnets

![Kea DHCPv4 Subnets](screenshots/opnsense/20-Services-KeaDHCPv4-Subnets.png)

Separate DHCP scopes assigned per VLAN/subnet.

---

## 19. Unbound DNS General

![Unbound DNS General](screenshots/opnsense/21-Services-UnboundDNS-General.png)

Internal DNS resolver configuration used for controlled name resolution.

---

## 20. Unbound DNS Advanced

![Unbound DNS Advanced](screenshots/opnsense/22-Services-UnboundDNS-Advanced.png)

Advanced resolver behavior and security-related DNS settings.

---

## 21. Unbound DNS Access Lists

![Unbound DNS Access Lists](screenshots/opnsense/23-Services-UnboundDNS-AccessLists.png)

Resolver access restricted to approved internal networks only.

---

## 22. Backup Creation

![Backup Creation](screenshots/opnsense/02-Backup-creation.png)

Configuration backup process used before major changes or upgrades.

---

## 23. Firmware Audit

![Firmware Audit](screenshots/opnsense/03-System-Firmware-Audit-run-options.png)

Firmware audit and package validation workflow.

---

## 24. Administration Settings

![Administration Settings](screenshots/opnsense/04-System-Settings-Administration.png)

GUI management settings supporting secure administrative behavior.

---

# UniFi Network Integration

## 01. Topology

![UniFi Topology](screenshots/unifi/01-Topology.png)

Overview of the switch, access point, and connected infrastructure.

---

## 02. Wi-Fi Settings

![UniFi WiFi Settings](screenshots/unifi/02-Settings-WiFi.png)

Wireless configuration supporting segmented SSIDs and VLAN mapping.

---

## 03. Port Configuration

![UniFi Ports](screenshots/unifi/03-Ports.png)

Switch port profiles used for trunking and VLAN transport.

---

## 04. Client Devices

![UniFi Client Devices](screenshots/unifi/04-Client-Devices.png)

Managed visibility into connected endpoint devices.

---

## 05. Networks and Wi-Fi

![UniFi Networks and WiFi](screenshots/unifi/05-Network+WiFi.png)

Relationship between networks, VLANs, and wireless SSIDs.

---

# Security Highlights

- Dedicated management path for firewall administration
- WAN deny-by-default posture
- Guest and restricted devices isolated from trusted networks
- Internal DNS restricted through Unbound access lists
- VLAN-based separation by trust level
- IDS / IPS inspection using Suricata
- Real hardware deployment instead of simulation-only design

---

# Troubleshooting Experience

Examples of practical issues investigated and resolved during this project:

- Apple Mail sync failures caused by blocked **IMAPS (993)**
- Apple Push / iCloud traffic requiring **5223**
- Firewall rule order affecting traffic outcomes
- GUI access planning and management recovery design
- IDS / IPS visibility validation
- DNS resolution vs connectivity troubleshooting

---

# Documentation

Additional project documentation:

- [Objectives](docs/Objectives.md)
- [Skills Demonstrated](docs/Skills-Demonstrated.md)
- [IP Addressing](docs/IP-Addressing.md)
- [VLAN Design](docs/VLAN-Design.md)
- [Troubleshooting](docs/Troubleshooting.md)
- [Key Learnings](docs/KeyLearnings.md)

---

# Summary

This project documents the design and deployment of a segmented small-business style network using **OPNsense**, **UniFi switching**, and **UniFi wireless infrastructure** on real hardware. It demonstrates practical experience in firewall administration, network segmentation, infrastructure services, wireless integration, monitoring, and structured troubleshooting.