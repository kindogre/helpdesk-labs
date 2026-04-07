# Ticket 03 — No Internet Access Due to DNS Misconfiguration

## Ticket ID
HD-03

## Scenario
User reports inability to access websites despite being connected to the network.

## User Impact
User cannot access web-based services or browse the internet.

## Symptoms Observed
- Websites do not load
- Browser shows connection errors

## Initial Checks
- Verified network connection status
- Checked IP configuration
- Tested connectivity using command line tools

## Troubleshooting Steps Performed
1. Logged into system and reproduced issue
2. Verified system had an IP address using ipconfig
3. Tested connectivity to external IP (8.8.8.8)
4. Tested DNS resolution using ping and nslookup
5. Identified DNS resolution failure
6. Reviewed network adapter DNS settings
7. Corrected DNS configuration
8. Retested connectivity

## Root Cause
Incorrect DNS server configuration prevented domain name resolution.

## Resolution
Restored valid DNS settings to allow proper name resolution.

## Verification
- Successfully resolved domain names
- Websites loaded correctly
- Network functionality restored

## Commands Used
```cmd
ipconfig
ping 8.8.8.8
ping google.com
Ping apple.com
nslookup google.com