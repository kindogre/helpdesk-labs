# Key Learnings

## Overview

Building this network lab provided hands-on experience that goes beyond theory and basic simulations. It demonstrated how real infrastructure behaves, how security controls affect usability, and how careful planning is required to balance protection with reliability.

This project reinforced technical skills in networking, security, troubleshooting, and documentation.

---

# 1. Security Must Be Balanced With Usability

One of the biggest lessons learned was that a secure configuration can still create operational problems if it is too restrictive.

Examples encountered during the project:

- Apple Mail sync issues caused by blocked **IMAPS (993)**
- Apple Push / notification traffic requiring **5223**
- Applications failing even when basic web access worked

### Takeaway

Effective security is not simply blocking everything. It means allowing legitimate traffic while restricting unnecessary or risky access.

---

# 2. Firewall Rule Order Matters

OPNsense evaluates rules top-to-bottom using first match logic.

Incorrect rule placement can cause:

- valid traffic to be blocked
- troubleshooting confusion
- policies behaving differently than expected

### Takeaway

Specific rules should be placed above broader rules, and every change should be validated with logs or testing.

---

# 3. Segmentation Reduces Risk

Separating users and devices into dedicated VLANs created meaningful security boundaries:

- Guest devices isolated from internal systems
- Restricted devices separated from trusted devices
- Management traffic separated from user traffic

### Takeaway

Segmentation is one of the most effective security controls for small business environments because it limits lateral movement after compromise.

---

# 4. Dedicated Management Access Is Valuable

Using a separate administrative management path for the firewall created a safer and more reliable way to manage infrastructure.

Benefits included:

- reduced exposure of the GUI
- cleaner access control
- recovery path during rule mistakes

### Takeaway

Administrative access should be separated from normal user traffic whenever possible.

---

# 5. Real Hardware Teaches Real Lessons

Working with:

- Protectli VP4650
- UniFi Lite 8 PoE
- UniFi U7 Lite

provided experience that virtual labs alone do not teach.

Examples:

- physical interfaces
- port/VLAN behavior
- switch uplinks
- wireless VLAN mapping
- controller/device management

### Takeaway

Hands-on hardware builds stronger troubleshooting instincts than theory-only labs.

---

# 6. DNS Is Critical Infrastructure

Many connectivity issues are actually DNS issues, not internet outages.

Using Unbound DNS showed how DNS affects:

- application performance
- name resolution
- security filtering
- troubleshooting speed

### Takeaway

Always test whether a problem is DNS, routing, firewall policy, or application-specific.

---

# 7. Monitoring Is Necessary

Deploying Suricata reinforced that visibility matters.

Without logs and alerts, it is difficult to know:

- what is blocked
- what is allowed
- whether inspection is active
- whether devices are behaving normally

### Takeaway

Security tools are most valuable when paired with monitoring and review.

---

# 8. Documentation Saves Time

Creating organized screenshots and markdown files highlighted the importance of documentation.

Benefits:

- easier change tracking
- faster troubleshooting
- clearer communication
- professional presentation

### Takeaway

Strong documentation is a technical skill, not just an administrative task.

---

# 9. Troubleshooting Requires Methodology

Successful troubleshooting came from structured testing:

- identify symptoms
- isolate variables
- test one change at a time
- verify results
- document findings

### Takeaway

Methodical troubleshooting is often more valuable than memorized fixes.

---

# 10. Small Networks Still Need Enterprise Thinking

Even a compact environment benefits from:

- least privilege
- segmentation
- patching
- monitoring
- controlled administration
- backup planning

### Takeaway

Good practices scale down just as well as they scale up.

---

# Professional Growth From This Project

This lab improved readiness for real-world IT roles by strengthening:

- network fundamentals
- firewall administration
- endpoint connectivity troubleshooting
- wireless/network integration
- security mindset
- communication and documentation

---

# Summary

The biggest lesson from this project was that technology alone is not enough. Successful infrastructure requires balancing security, usability, and maintainability while using a structured troubleshooting mindset.