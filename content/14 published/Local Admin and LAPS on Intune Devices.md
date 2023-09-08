---
alias: LAPS AAD
tags:
- published
- index/25.24
---

# Setting up LAPS on Intune / AAD

Replication time: 15 minutes or more.

> Note: This assumes you have the '**Administrator**' account enabled on your devices. To use a custom local account, see [[Create a custom local administrator account via Intune]], and update the "**Administrator Account Name**" with the custom local administrator account you created. 


## License Requirements
- See [here](https://learn.microsoft.com/en-us/mem/intune/protect/windows-laps-overview#licensing-requirements) for the updated license requirements. At the time of writing, it needs basic Intune subscription and Azure AD Free.

## Enabling AAD LAPS 

- From Azure AD > Devices > Device Settings > Local administrator settings
- Enable Azure AD Local Administrator Password Solutions (LAPS)

![fc141f8ec8dbcca5a4e3f43adae2c576 MD5](https://i.imgur.com/BoGlDT8.png)

## Configure Account Protection

- From Endpoint security > Account protection > Create Policy
- Choose Windows 10 and later as the Platform
- Choose "Local admin password solution (Windows LAPS)" as the Profile

![30d812fc60c9714caa1a8912104cd355 MD5](https://i.imgur.com/Z6fTZFT.png)

- Set the settings as follows:

![7e4c2d7873350de86f03dcf6c3dabf41 MD5](https://i.imgur.com/bDrYtX2.png)

- If you have deployed a custom administrator account, update the "Administrator Account Name" with the admin account you created.

![8e1347337b95e8e8c94b8b0bf38845c6 MD5](https://i.imgur.com/W892YQv.png)


- Assign the profile to all devices

## Assigning Permissions

To allow viewing of local credentials, assign the following role: 

- Cloud Device Administrator
- Intune Administrator
- Global Administrator
- Custom roles with `microsoft.directory/deviceLocalCredentials/password/read` permission

## Retrieving local credentials

- From Devices > Local administrator password recovery > locate the device you need local administrator password for.

![b2ab5652a71960b054f10a53f29bb4f3 MD5](https://i.imgur.com/l0k9fcK.png)

- This is also the same credentials under Endpoint Admin Center > search for the device > Local admin password

![ae5fd833f5e464363d5243616ea82a1b MD5](https://i.imgur.com/sOioCli.png)


- Login or run any app on the device using the local admin credentials (if you created a custom one, use `.\CustomLocalAdminName `instead)

![0a4f195eafefecb55d91a321c44a55f6 MD5](https://i.imgur.com/oaJRk6c.png)

