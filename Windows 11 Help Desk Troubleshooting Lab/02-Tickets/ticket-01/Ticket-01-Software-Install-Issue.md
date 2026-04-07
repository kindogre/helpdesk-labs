# Ticket 01 — Standard User Cannot Install Software

## Ticket ID
HD-01

## Scenario
Standard user is unable to install an application on a Windows 11 system.

## User Impact
User cannot install required software, limiting ability to perform normal tasks.

## Symptoms Observed
- Installation fails or prompts for administrator credentials
- User does not have permission to complete installation

## Initial Checks
- Verified current logged-in user
- Checked account type (standard vs administrator)

## Troubleshooting Steps Performed
1. Attempted installation as TestUser1 and observed failure due to insufficient privileges
2. Verified account type using system settings and command line
3. Confirmed User Account Control prompt requiring administrative credentials
4. Logged into LocalAdmin account
5. Re-ran installer with administrative privileges

## Root Cause
Standard user account does not have sufficient privileges to install software.

## Resolution
Used administrator account to install the application.

## Verification
- Application installed successfully
- Standard user can now open and use the application

## Screenshots
- Before: Failed installation as standard user
- During: Account type verification and UAC prompt
- After: Successful installation using administrator account

## Commands Used
```powershell
whoami
net user TestUser1