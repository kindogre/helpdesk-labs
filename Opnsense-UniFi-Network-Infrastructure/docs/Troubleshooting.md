# Troubleshooting

## Overview

This project included real-world troubleshooting scenarios commonly seen in IT Support, Help Desk, Network Administration, and Security operations.

Issues were approached using a structured method:

1. Identify symptoms  
2. Verify scope of impact  
3. Check physical connectivity  
4. Review addressing / DNS / gateway settings  
5. Inspect firewall behavior  
6. Test one change at a time  
7. Confirm resolution  
8. Document findings

---

# Scenario 1 – Apple Mail Inbox Not Updating

## Symptoms

- Apple Mail on macOS would not refresh inbox
- New messages delayed or missing
- Service often worked while connected to Proton VPN

## Investigation

Verified that:

- Basic internet connectivity was working
- HTTPS traffic was allowed
- Issue occurred only when traffic passed directly through firewall rules

Reviewed firewall logs and Live View.

## Root Cause

Outbound traffic for required mail services was blocked.

Observed blocked traffic included:

- **TCP 993** (IMAPS)
- **TCP 5223** (Apple Push Notification Service)

## Resolution

Created outbound allow rules for:

- TCP 993
- TCP 5223

## Result

Mail synchronization restored without weakening WAN security posture.

## Skills Demonstrated

- Log analysis
- Application traffic troubleshooting
- Port/service identification
- Firewall rule tuning

---

# Scenario 2 – Firewall Rule Order Causing Unexpected Behavior

## Symptoms

Traffic that should have been allowed did not always work as expected.

## Investigation

Reviewed interface rules and remembered that OPNsense processes rules top-to-bottom using first match logic.

## Root Cause

Specific allow rules were placed below broader or conflicting rules.

## Resolution

Reordered rules so that:

1. Required specific services appear first  
2. General rules appear later  
3. Block rules remain intentional and clear

## Result

Traffic behavior became predictable and easier to manage.

## Skills Demonstrated

- Rule precedence understanding
- Policy cleanup
- Structured testing

---

# Scenario 3 – Administrative Access Protection

## Symptoms

Need to secure firewall GUI while maintaining reliable recovery access.

## Investigation

Default management exposure on common user networks increases risk.

## Resolution

Built a dedicated management interface/subnet separate from user VLANs.

Administrative access was limited to that path rather than normal user networks.

## Result

Reduced attack surface while preserving a safe administration path.

## Skills Demonstrated

- Secure management design
- Least privilege access control
- Risk reduction planning

---

# Scenario 4 – DNS vs Internet Connectivity

## Symptoms

Some applications reported connectivity issues even when devices appeared online.

## Investigation

Validated separately:

- IP addressing
- Gateway reachability
- DNS resolution
- Web access

## Root Cause

Some failures were DNS-related rather than complete internet outages.

## Resolution

Used Unbound DNS on OPNsense as controlled resolver and validated client DNS settings.

## Result

More consistent name resolution and faster diagnosis.

## Skills Demonstrated

- Layered troubleshooting
- DNS fundamentals
- Client configuration review

---

# Scenario 5 – IDS / IPS Validation

## Symptoms

Needed to confirm that Suricata inspection was active and processing traffic.

## Investigation

Reviewed:

- Interface assignments
- Rulesets enabled
- Alert visibility
- Traffic generation tests

## Resolution

Adjusted monitored interfaces and confirmed ruleset operation.

## Result

Improved confidence that inspection controls were functioning.

## Skills Demonstrated

- Security tool validation
- Monitoring workflow
- Detection troubleshooting

---

# Scenario 6 – Wireless / VLAN Integration

## Symptoms

Need to ensure SSIDs mapped correctly to intended VLANs.

## Investigation

Reviewed UniFi configuration:

- SSID settings
- Port profiles
- VLAN tags
- Device addressing after connection

## Resolution

Validated wireless clients were receiving addresses from correct DHCP scopes.

## Result

Wireless segmentation aligned with firewall design.

## Skills Demonstrated

- Wireless troubleshooting
- VLAN tagging validation
- DHCP verification

---

# Troubleshooting Tools Used

## OPNsense

- Live View firewall logs
- Interface status pages
- DHCP lease review
- DNS resolver settings
- Suricata status / alerts

## UniFi

- Device topology
- Port configuration
- SSID / network settings

## Endpoint Testing

- Browser tests
- Mail client behavior
- Ping / connectivity checks
- DNS resolution tests

---

# Methodology Learned

Successful troubleshooting consistently depended on:

- isolating one variable at a time
- verifying assumptions
- checking logs before guessing
- understanding service ports
- documenting changes
- retesting after each fix

---

# Business Value of These Skills

These are directly relevant to real IT roles because they involve:

- user issue resolution
- network access troubleshooting
- secure change management
- root cause analysis
- communication under pressure

---

# Summary

This lab was not only a build project—it was also an active troubleshooting environment. Resolving realistic networking and application issues strengthened practical support skills that apply directly to Help Desk, IT Support, Network Operations, and Security teams.