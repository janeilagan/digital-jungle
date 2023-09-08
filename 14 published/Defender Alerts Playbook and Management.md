---
alias:
tags:
- published
- index/25.27.05
---


- For official trainings and documentation, see [Become a Microsoft 365 Defender Ninja](https://techcommunity.microsoft.com/t5/microsoft-365-defender-blog/become-a-microsoft-365-defender-ninja/ba-p/1789376)
- Defender dashboard can be found at https://security.microsoft.com/

# Investigating incidents and alerts

When alerts come in, the links to their alert page and incident page will be indicated on the ticket. 

Incidents can have multiple alerts connected to it, especially if there are multiple assets affected. 

It is important to action alerts as timely as possible, especially for High and Critical alerts. 
## Data gathering

1. Open the alerts page, locate the following details (if available) and document in the ticket: 
	- User affected
	- Device affected
	- IP address (if available)
	- Sign in location (if available)
	- Current alert status

### Locating the user affected

-  Most of the time, the user affected is on the topmost part of the alert page. If it's not, scroll down to the right, lower part of the page and locate **"Impacted assets"**

![8949937006f4f5cd29968f80eaea123e](https://i.imgur.com/OA0tXVN.png)

- For any other instance that the user was no longer available or has been disabled, locate other evidence that may indicate who the user was.

![315c30956e06c800aadc937c87af3a06](https://i.imgur.com/2UpMw9B.png)

![d3729295fcb5631dc598390dc3a6fc7d](https://i.imgur.com/AOXgWxH.png)


![f392d2b7fc0ec978dd7c520ac7a2d7cd](https://i.imgur.com/qfEzAvW.png)


### Locating the device affected, IP and sign in location

For Defender for Endpoint alerts, there will always be a device impacted. If there isn't, confirm if the alert detection source was Defender for Endpoint, or potentially something else (ex: Defender for Office 365's impacted asset could be a mailbox, Defender for Cloud Apps' impacted asset could be an onboarded app)

If IP and sign in location is available, review the past 7 days sign in logs of the user and determine if there's suspicious behavior in terms of location.

### Current Alert Status

For tenants automated response and configured to automatically resolve alerts, there are instances that the alert you're reviewing has already been resolved. 

Confirm the status if it's already resolved, and review Comments & history section of the alert to see what Defender API did.

![263ae13773a74f0621391cb7aab09c90](https://i.imgur.com/RoALCb0.png)

For resolved Alerts, review the Incident linked to it and confirm all Alerts underneath are resolved as well. 


