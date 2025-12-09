
# Watch me do it HERE

https://www.loom.com/share/d747df3df7484b9d98a665b05aa1bbc1

# Active Directory PowerShell Lab Report
The objective of this lab was to create and manage Active Directory users using a PowerShell script on a virtual machine.

## Steps Performed

1. **Created Users in Active Directory using a PowerShell Script**
   - Opened a PowerShell session on the VM with administrative privileges.
   - Wrote a PowerShell script to create user accounts in Active Directory. Example snippet:

```powershell
# Sample script to create users
PowerShell
# == User Details ==
# This is the only section you need to edit for each new user.
$firstname = "Jane"
$lastname = "Doe"
$username = "jdoe"
$password = "P@ssword1234!"
$domainName = "skool.local"

# == Create the Active Directory User ==
# This section takes the details above and creates the account.

# 1. Convert the password to a secure string required by Active Directory.
$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

# 2. Create the user with all the specified attributes.
# The command `New-ADUser` is the main instruction to create the account.
New-ADUser -Name "$firstname $lastname" `
           -GivenName $firstname `
           -Surname $lastname `
           -SamAccountName $username `
           -UserPrincipalName "$username@$domainName" `
           -AccountPassword $securePassword `
           -Enabled $true

# 3. Print a confirmation message to the screen.
Write-Host "User '$username' was created successfully."

```

2. **How to Run the Script**
   - Saved the script with a `.ps1` extension.
   - In PowerShell, navigated to the folder containing the script.
   - Executed the script using: `.\CreateUsers.ps1`.
   - Ensured that PowerShell Execution Policy allowed script execution (`Set-ExecutionPolicy RemoteSigned` if needed).
   - <img width="1130" height="405" alt="image" src="https://github.com/user-attachments/assets/7e1db39f-ef5c-43df-a53c-f56754f4df04" />
   <img width="1181" height="739" alt="image" src="https://github.com/user-attachments/assets/c459b713-fb11-493d-980f-9bac84e6fec1" />



3. **Verified the Script Worked**
   - Opened *Active Directory Users and Computers (ADUC)*.
   - Confirmed that the new users were created successfully.
   - Optionally used `Get-ADUser` in PowerShell to list and verify the created accounts.
   - <img width="751" height="528" alt="image" src="https://github.com/user-attachments/assets/4e922477-2dfa-4ee5-8810-0229152e91b9" />


## Outcome
The PowerShell script successfully created the desired Active Directory users. The process demonstrates automating user creation using scripts, which is efficient for managing multiple accounts.

## Notes
Using PowerShell scripts for Active Directory management reduces manual effort and errors when creating multiple user accounts.
