# VLAN Design

## Overview

This project used Virtual LANs (VLANs) to separate devices into distinct security zones based on trust level and function.

Instead of placing every device on one flat network, traffic was segmented into multiple routed networks controlled by OPNsense firewall policies.

This mirrors common small-business network design where security, manageability, and troubleshooting efficiency are priorities.

---

# Why VLANs Were Used

## Security Benefits

- Reduces lateral movement between devices
- Isolates guest and untrusted systems
- Protects administrative services
- Allows separate firewall policies per group

## Operational Benefits

- Cleaner device organization
- Easier troubleshooting
- Predictable DHCP scopes
- Better Wi-Fi SSID mapping
- Simpler future growth

---

# VLAN Architecture

| VLAN ID | Name | Purpose | Trust Level |
|---|---|---|---|
| 10 | Secure Users | Personal / administrative devices | High |
| 20 | Standard Users | Everyday user devices | Medium |
| 30 | Restricted Devices | Low-trust / IoT style devices | Low |
| 40 | Guest Access | Temporary visitor internet access | Low |
| N/A | Admin Management | Firewall management path | High |

---

# VLAN 10 – Secure Users

## Purpose

Used for trusted devices such as:

- Admin laptop
- Admin phone
- Administrative systems

## Policy Goals

- Normal internet access
- Stronger trust than standard users
- Access to approved internal services when needed
- Blocked from firewall GUI unless intentionally allowed

## Why It Matters

Separates sensitive devices from less trusted users and devices.

---

# VLAN 20 – Standard Users

## Purpose

Used for employee-style devices such as:

- Standart users laptops
- Standart users phones
- Employee devices
- General productivity devices

## Policy Goals

- Stable internet access
- Reduced access to sensitive networks
- Separate from administrative systems

## Why It Matters

Not every trusted person uses trusted devices. This zone lowers risk without harming usability.

---

# VLAN 30 – Restricted Devices

## Purpose

Used for lower-trust devices that may need internet but should not interact with internal systems.

Examples:

- Smart TVs
- Streaming devices
- Printers
- IoT devices
- Test devices

## Policy Goals

- Internet access only as required
- DNS controlled through firewall
- Blocked from internal private networks

## Why It Matters

IoT and unmanaged devices often receive fewer updates and create unnecessary risk.

---

# VLAN 40 – Guest Access

## Purpose

Used for visitors or temporary devices.

## Policy Goals

- Internet access only
- No internal network access
- No access to management services

## Why It Matters

Guests should never share the same trust level as internal devices.

---

# Dedicated Admin Management Network

## Purpose

Separate interface/subnet used for firewall administration rather than standard user VLANs.

## Benefits

- Reduces GUI exposure
- Cleaner access control
- Safer recovery path
- Better security posture

## Why It Matters

Administrative access should be isolated from everyday client traffic whenever possible.

---

# Traffic Flow Design

All VLAN traffic was routed through OPNsense, allowing security inspection and policy enforcement between networks.

Example model:

```text
Client Device
   ↓
VLAN / Switch Port / SSID
   ↓
UniFi Switch / AP
   ↓
OPNsense Firewall
   ↓
Allowed Destination or Blocked by Policy