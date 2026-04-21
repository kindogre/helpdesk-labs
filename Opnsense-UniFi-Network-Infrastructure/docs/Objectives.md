# Objectives

## Project Purpose

The objective of this project was to design, deploy, secure, and document a small-business style network environment using real hardware and industry-relevant technologies.

The environment was built to develop practical experience in networking, firewall administration, wireless infrastructure, troubleshooting, and cybersecurity fundamentals.

---

# Primary Goals

## 1. Build a Segmented Network

Create multiple isolated network zones using VLANs to separate devices by trust level and function.

Targeted segments included:

- Secure Users
- Standard Users
- Restricted Devices
- Guest Access
- Dedicated Management Network

### Why This Matters

Segmentation reduces risk, limits lateral movement, and mirrors real business network design.

---

## 2. Deploy a Professional Firewall Platform

Use **OPNsense** on a **Protectli VP4650** appliance as the central routing and security platform.

Objectives included:

- Interface assignment
- Inter-VLAN routing
- Stateful firewall policy enforcement
- NAT configuration
- DNS / DHCP services

### Why This Matters

Hands-on firewall administration is directly relevant to IT support, networking, and security roles.

---

## 3. Implement Secure Access Control

Apply least-privilege firewall rules to control communication between networks.

Examples:

- Guest devices blocked from internal systems
- Restricted devices limited to internet-only access
- Firewall GUI protected from user networks
- WAN maintained deny-by-default posture

### Why This Matters

Access control is a core responsibility in modern IT environments.

---

## 4. Integrate Managed Switching and Wireless

Use UniFi infrastructure to extend segmented networks through switching and Wi-Fi.

Objectives:

- Configure VLAN transport across switch ports
- Map SSIDs to VLANs
- Manage infrastructure centrally

### Why This Matters

Most real environments require integration between routing, switching, and wireless systems.

---

## 5. Provide Core Network Services

Configure infrastructure services for each subnet:

- Kea DHCP
- Unbound DNS
- Gateway assignment
- Address management

### Why This Matters

Reliable network services are essential for users and devices to function correctly.

---

## 6. Deploy Security Monitoring

Enable Suricata IDS / IPS to inspect traffic and improve network visibility.

Objectives:

- Ruleset deployment
- Alert review
- Inspection validation

### Why This Matters

Detection capability adds operational security value beyond simple firewall filtering.

---

## 7. Practice Real Troubleshooting

Use the environment to investigate and solve practical issues such as:

- Email sync failures
- Blocked application traffic
- Rule ordering conflicts
- DNS vs connectivity issues
- Management access recovery

### Why This Matters

Troubleshooting skill is one of the most valuable competencies in Help Desk and IT Support roles.

---

## 8. Build a Professional Portfolio Project

Document the project clearly using screenshots, markdown documentation, and architecture summaries.

Deliverables included:

- README
- VLAN Design
- IP Addressing
- Troubleshooting Notes
- Key Learnings
- Skills Demonstrated

### Why This Matters

Strong documentation proves communication skills and helps translate technical work into hiring value.

---

# Hardware Objectives

Gain experience with real infrastructure:

- Protectli VP4650 firewall appliance
- UniFi Lite 8 PoE managed switch
- UniFi U7 Lite wireless access point

### Why This Matters

Real hardware experience provides stronger practical knowledge than theory-only labs.

---

# Career Alignment

This project was designed to strengthen readiness for roles such as:

- Help Desk Technician
- IT Support Specialist
- Junior Network Administrator
- NOC Technician
- SOC Analyst (Tier 1)

---

# Success Criteria

The project was considered successful when it achieved:

- Secure segmented connectivity
- Stable internet access across VLANs
- Controlled access between trust zones
- Working DNS / DHCP services
- Functional wireless integration
- Active monitoring capability
- Clear documentation of design and lessons learned

---

# Summary

The overall objective was to simulate and manage a real-world small business network using modern security principles, practical troubleshooting, and professional documentation.