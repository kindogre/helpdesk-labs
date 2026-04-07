# Ticket 04 — User Unable to Access Folder Due to Permissions

## Ticket ID
HD-04

## Scenario
User reports "Access Denied" when attempting to open a shared folder.

## User Impact
User cannot access required files, preventing normal work tasks.

## Symptoms Observed
- "Access Denied" message when opening folder
- Folder visible but inaccessible

## Initial Checks
- Verified user account
- Confirmed folder exists
- Checked current permissions

## Troubleshooting Steps Performed
1. Logged in as affected user and reproduced "Access Denied" error
2. Verified user identity and group membership
3. Logged in as administrator
4. Reviewed folder Security settings (NTFS permissions)
5. Identified missing permissions for the user
6. Added appropriate access rights
7. Retested access using the affected user account

## Root Cause
User account did not have the required NTFS permissions to access the folder.

## Resolution
Updated folder permissions to grant appropriate access to the user.

## Verification
- User successfully accessed the folder
- Files could be opened without errors


## Skills Demonstrated
- NTFS permission troubleshooting
- User access control
- Windows file system security