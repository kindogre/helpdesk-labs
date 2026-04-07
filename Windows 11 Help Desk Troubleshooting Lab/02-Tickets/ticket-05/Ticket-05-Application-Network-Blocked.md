# Ticket 05 — Application Unable to Access Internet Due to Firewall Block

## Ticket ID
HD-05

## Scenario
User reports that a specific application cannot access the internet while the system is otherwise connected.

## User Impact
User cannot use application features that require internet connectivity.

## Symptoms Observed
- Application fails to connect to internet services
- Other applications (browser) work normally
- No system-wide network issues

## Initial Checks
- Verified system had internet connectivity
- Tested browser access
- Confirmed issue isolated to one application

## Troubleshooting Steps Performed
1. Reproduced issue by launching application and observing connection failure
2. Verified internet access using browser
3. Reviewed Windows Defender Firewall settings
4. Identified firewall rule blocking application
5. Deleted firewall rule to allow application
6. Retested application connectivity

## Root Cause
Firewall rule blocked the application from accessing the network.

## Resolution
Updated firewall settings to allow application network access.

## Verification
- Application successfully connected to internet
- No further connection errors observed

## Skills Demonstrated
- Firewall troubleshooting
- Application-level network diagnostics
- Security vs usability balancing