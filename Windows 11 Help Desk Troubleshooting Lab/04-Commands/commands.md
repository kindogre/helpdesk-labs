# Commands Used – Windows 11 Help Desk Lab

This document lists the command-line and administrative tools used during troubleshooting simulations.

---

## 👤 User & Identity Verification

**whoami**  
- Verified the currently logged-in user context.

**net user**  
- Listed local user accounts.
- Verified account status and group membership.

---

## 🌐 Network Diagnostics

**ipconfig**  
- Reviewed IP address configuration.
- Verified gateway and DNS settings.

**ping 8.8.8.8**  
- Tested raw internet connectivity (bypassing DNS).

**ping google.com**  
**ping apple.com**  
- Tested DNS resolution and external reachability.

**nslookup google.com**  
- Verified DNS server response and name resolution functionality.

---

## ⚙️ Administrative Tools (Run Dialog – Win + R)

These tools were launched via `Win + R` to simulate real help desk workflow:

**control.exe**  
- Accessed Control Panel settings.

**compmgmt.msc**  
- Opened Computer Management console.
- Reviewed Event Viewer and system configuration.

**lusrmgr.msc**  
- Managed local users and groups.

**gpedit.msc**  
- Reviewed and modified Local Group Policy settings.

**services.msc**  
- Investigated and managed Windows services (e.g., Windows Update, BITS, Print Spooler).

---

## 🧠 Troubleshooting Approach

Commands were used to:
- Identify user context and permissions
- Diagnose network connectivity vs DNS issues
- Validate service status
- Investigate configuration and policy settings
- Apply structured troubleshooting methodology (identify → isolate → resolve → verify)