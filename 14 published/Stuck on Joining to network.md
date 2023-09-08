---
alias: rokon stuck on joining
tags:
- published
- index/25.12
---

The device is initially joined to Active Directory, but not yet registered with Azure AD. That registration process (tied to AAD Connect) could take some time, maybe 30 minutes. Until that happens, the user can’t get an Azure AD token, and without that Azure AD token it can’t authenticate to Intune so it can’t get any user-targeted policies. So the ESP could time out, or just sit there for a very long time waiting for that stuff to happen in the background.

From: [[SOLVED] Windows AutoPilot - Hybrid Domain Join not fully working - Microsoft Intune (spiceworks.com)](https://community.spiceworks.com/topic/2196102-windows-autopilot-hybrid-domain-join-not-fully-working)

Changes to happen:


SkipUserStatusPage Profile

Name: SkipUserStatusPage (or  
OMA-URI: ./Vendor/MSFT/DMClient/Provider/MS DM Server/FirstSyncStatus/SkipUserStatusPage  
Data type: Boolean  
Value: True

![](https://i.imgur.com/dlNV6RH.png)


Create a separate ESP Page

![](https://i.imgur.com/DnYO1HG.png)



[[Why you need to AAJ instead of HAADJ]]


If you need to use Dynamic group: `(device.devicePhysicalIds -any (_ -eq "[OrderID]:179887111881"))`.
