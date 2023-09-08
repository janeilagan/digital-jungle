---
alias: Intune Local Admin for LAPS
tags:
- published
- index/25.24
---

# Deploying the script via Intune

Replication time: 2 hours or more.

- Deploy a custom script that creates your custom local administrator account
- From Intune admin center > Devices > Scripts > Add > Windows 10 and later

![f3b4e91318f169e1c6aea1835cef6eab MD5](https://imgur.com/YPRuy5R.png)

- Upload your custom script that creates the local admin account. The below is just an example:

```powershell 
# New-LocalAdministrator.ps1

# Define the username and password for the new administrator account
$adminUsername = "LocalAdmin"
$adminPassword = ConvertTo-SecureString -String "GCdTKTOgv&eM!T5dw" -AsPlainText -Force

# Create a new local user account
$account = New-LocalUser -Name $adminUsername -Password $adminPassword -UserMayNotChangePassword

# Add the new account to the Administrators group
$group = "Administrators"
Add-LocalGroupMember -Group $group -Member $adminUsername

# Set the account as enabled and password never expires
$account | Enable-LocalUser
$account | Set-LocalUser -PasswordNeverExpires $true
```

- Deploy the script to all your Intune devices

![d459b90d5ada295394003916ac2922b3 MD5](https://i.imgur.com/jAdzpNF.png)




- The script creates a `LocalAdmin` account and adds it to the Administrators group.

![55c57997d2990cc125879efb2973c7b9 MD5](https://i.imgur.com/Puwo1wd.png)


See: [[Local Admin and LAPS on Intune Devices]] on how to configure this custom account with LAPS

For any failures, review `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs` 

---

Also, see: https://www.lieben.nu/liebensraum/?p=3605 for LeanLAPS (old way Lightweight LAPS solution for Intune MEM)