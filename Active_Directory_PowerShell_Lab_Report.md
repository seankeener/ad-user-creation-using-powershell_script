# Active Directory PowerShell Lab Report
**Date:** December 09, 2025

## Objective
The objective of this lab was to create and manage Active Directory users using a PowerShell script on a virtual machine.

## Steps Performed

1. **Created Users in Active Directory using a PowerShell Script**
   - Opened a PowerShell session on the VM with administrative privileges.
   - Wrote a PowerShell script to create user accounts in Active Directory. Example snippet:

```powershell
# Sample script to create users
Import-Module ActiveDirectory

New-ADUser -Name "John Doe" -GivenName "John" -Surname "Doe" -SamAccountName "jdoe" -AccountPassword (ConvertTo-SecureString "P@ssw0rd123" -AsPlainText -Force) -Enabled $true
```

2. **How to Run the Script**
   - Saved the script with a `.ps1` extension.
   - In PowerShell, navigated to the folder containing the script.
   - Executed the script using: `.\CreateUsers.ps1`.
   - Ensured that PowerShell Execution Policy allowed script execution (`Set-ExecutionPolicy RemoteSigned` if needed).

3. **Verified the Script Worked**
   - Opened *Active Directory Users and Computers (ADUC)*.
   - Confirmed that the new users were created successfully.
   - Optionally used `Get-ADUser` in PowerShell to list and verify the created accounts.

## Outcome
The PowerShell script successfully created the desired Active Directory users. The process demonstrates automating user creation using scripts, which is efficient for managing multiple accounts.

## Notes
Using PowerShell scripts for Active Directory management reduces manual effort and errors when creating multiple user accounts.
