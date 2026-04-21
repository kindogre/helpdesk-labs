# IP Addressing

## Overview

This project used a structured private IPv4 addressing plan to support network segmentation, simplify troubleshooting, and apply different security policies to different device groups.

Each VLAN was assigned its own subnet and default gateway through OPNsense. This design improves visibility, reduces broadcast scope, and allows firewall rules to be enforced between networks.

---

## Addressing Strategy

The environment used RFC1918 private addressing space:

- `192.168.x.x`
- Class C style subnets for clarity and easy administration
- `/24` networks for user VLANs
- Smaller dedicated subnet for management access

This approach is common in small business environments because it is simple, scalable, and easy to support.

---

## Network Segments

| Network Purpose | VLAN | Subnet | Gateway |
|---|---:|---|---|
| Secure Users | 10 | 192.168.10.0/24 | 192.168.10.1 |
| Standard Users | 20 | 192.168.20.0/24 | 192.168.20.1 |
| Restricted Devices | 30 | 192.168.30.0/24 | 192.168.30.1 |
| Guest Access | 40 | 192.168.40.0/24 | 192.168.40.1 |
| Admin Management | N/A | 192.168.x.0/28 | 192.168.x.x |

> Gateways were hosted on OPNsense interfaces and used as the default route for each VLAN.

---

## Why Separate Subnets Matter

Using different subnets for each network provides important operational and security benefits:

### Security

- Enables firewall filtering between VLANs
- Prevents unrestricted east-west movement between devices
- Allows guest and restricted devices to be isolated

### Stability

- Limits broadcast traffic to each VLAN
- Prevents one noisy network from affecting others

### Troubleshooting

IP addresses immediately identify device location:

- `192.168.10.x` = Secure Users
- `192.168.20.x` = Standard Users
- `192.168.30.x` = Restricted Devices
- `192.168.40.x` = Guest Access
- `192.168.x.x` = Admin Management

This speeds up support and log analysis.

---

## DHCP Design

Kea DHCP was used to issue addresses dynamically per subnet.

Each VLAN received:

- IP address
- Subnet mask
- Default gateway
- DNS server (OPNsense / Unbound)

Example:

```text
Secure Users device:
IP: 192.168.10.xx
Gateway: 192.168.1.1
DNS: 192.168.1.1