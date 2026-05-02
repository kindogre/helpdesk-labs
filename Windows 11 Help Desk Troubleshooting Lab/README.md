# Windows 11 Help Desk Troubleshooting Lab

## Overview
This project simulates real-world help desk troubleshooting scenarios using a Windows 11 virtual machine.  
The goal was to practice diagnosing, isolating, and resolving common desktop support issues in a controlled lab environment.

---

## Lab Environment

- Host System: macOS (VMware Fusion)
- Guest OS: Windows 11
- Network: Segmented via OPNsense firewall (VLAN-based lab environment)
- Tools Used: Command Prompt, PowerShell, Event Viewer, Services Manager, Windows Defender Firewall
 
---

## Tickets Simulated

### Ticket 1 – User Login Issue
Diagnosed local account access problems and verified group membership.
[Ticket1](https://github.com/kindogre/it-support-portfolio/tree/main/Windows%2011%20Help%20Desk%20Troubleshooting%20Lab/03-Screenshots/Ticket%201)

### Ticket 2 – Network Connectivity Failure
Used command-line tools to isolate DNS vs connectivity issues.
[Ticket2](https://github.com/kindogre/it-support-portfolio/tree/main/Windows%2011%20Help%20Desk%20Troubleshooting%20Lab/03-Screenshots/Ticket%202)

### Ticket 3 – Application Blocked by Firewall
Identified and corrected Windows Defender Firewall rule misconfiguration.
[Ticket3](https://github.com/kindogre/it-support-portfolio/tree/main/Windows%2011%20Help%20Desk%20Troubleshooting%20Lab/03-Screenshots/Ticket%203)

### Ticket 4 – Windows Service Failure
Investigated and managed Windows services (Windows Update, BITS).
[Ticket4](https://github.com/kindogre/it-support-portfolio/tree/main/Windows%2011%20Help%20Desk%20Troubleshooting%20Lab/03-Screenshots/Ticket%204)

### Ticket 5 – Application Network Access Issue
Analyzed firewall behavior and verified outbound connectivity.
[Ticket5](https://github.com/kindogre/it-support-portfolio/tree/main/Windows%2011%20Help%20Desk%20Troubleshooting%20Lab/03-Screenshots/Ticket%205)

### Ticket 6 – Printer Troubleshooting
Configured and tested virtual printer setup to simulate real-world support case.
[Ticket6](https://github.com/kindogre/it-support-portfolio/tree/main/Windows%2011%20Help%20Desk%20Troubleshooting%20Lab/03-Screenshots/Ticket%206)

---

## Skills Demonstrated

- Windows 11 troubleshooting
- Network diagnostics (ipconfig, ping, tracert, netstat)
- Windows service management
- Firewall rule analysis
- Event Viewer log investigation
- Structured troubleshooting methodology

---

## Key Takeaways

- Applied systematic troubleshooting process (identify → isolate → resolve → verify)
- Gained hands-on experience diagnosing OS-level and network-related issues
- Reinforced real-world help desk workflow in a segmented network environment

---

## Repository Structure

01-Setup – Lab configuration documentation  
02-Tickets – Written troubleshooting scenarios  
03-Screenshots – Visual evidence of issues and fixes  
04-Commands – Command-line tools used  
05-Resume_Bullets – Resume-ready experience statements  

---

## Purpose

This lab was built to simulate entry-level Help Desk responsibilities and demonstrate hands-on troubleshooting ability for IT support roles.
