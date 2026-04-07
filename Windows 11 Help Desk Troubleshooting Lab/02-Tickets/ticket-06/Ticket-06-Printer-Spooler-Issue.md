# Ticket 06 — Printer Not Working Due to Print Spooler Issue

## Ticket ID
HD-06

## Scenario
User reports that documents are not printing.

## User Impact
User cannot print documents required for work.

## Symptoms Observed
- Print jobs stuck or not processing
- Printer appears available but does not print

## Initial Checks
- Verified printer is installed
- Checked default printer
- Reviewed print queue

## Troubleshooting Steps Performed
1. Attempted to print document and observed failure
2. Opened print queue and verified job was stuck or not processed
3. Opened Services console (services.msc)
4. Located Print Spooler service
5. Found service stopped or not functioning properly
6. Restarted Print Spooler service
8. Retested printing
9. The issue was solved

## Root Cause
Print Spooler service was stopped or malfunctioning, preventing print jobs from processing.

## Resolution
Restarted Print Spooler service.

## Verification
- Print job completed successfully
- No further printing issues observed

## Skills Demonstrated
- Service troubleshooting
- Device troubleshooting
- Print queue management