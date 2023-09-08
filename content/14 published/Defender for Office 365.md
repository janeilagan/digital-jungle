---
alias: Defender for Office 365 - Baseline Config
tags:
- published
- index/25.09
- index/27.09
---


# Defender for Office 365 - Config

Permissions needed: Global Administrator or Security Administrator

-   Configure everything with 'anti' in the name.
    -   anti-malware
    -   anti-phishing
    -   anti-spam
-   Set up everything with 'safe' in the name.
    -   Safe Links
    -   Safe Attachments
-   Defend the workloads (ex. SharePoint Online, OneDrive, and Teams)
-   Protect with zero-hour auto purge (ZAP).

## Initial Setup options

Option 1 - Setup [preset security policies](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/preset-security-policies?view=o365-worldwide) 
- not configurable, you can't tune up or down as needed

Option 2 - Configure the [recommended policies](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365?view=o365-worldwide) manually
- best if you have need to tune it along the way

## Policies
- Standard protection
	- Good for most users
- Strict protection
	- aggressive profile for selected users (high value targets or priority users)
	- only couple of differences between standard and strict, so if it doesn't have huge impact on user experience, better to go with strict


### Anti-malware - (Standard and Strict)
[Protection settings](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365?view=o365-worldwide#eop-anti-malware-policy-settings)

- Enable the common attachments filter: selected
- When these file types are found: Reject the messages with a non-delivery receipt (NDR)
- Enable zero-hour auto purge[^1] for malware: Selected
- Quarantine policy: AdminOnlyAccessPolicy
- Notify an admin about undelivered messages from internal senders: Selected

### Anti-Phishing - Strict
[Protection settings](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365?view=o365-worldwide#eop-anti-phishing-policy-settings)

- Enable users to protect (impersonated user protection): Selected (Add the key users ie Executives, leaders etc)
- Enable domains to protect: Include domains I own, Include custom domains
- Enable mailbox intelligence[^2]: Selected
- Enable intelligence for impersonation protection: Selected
- Enable spoof intelligence: Selected

Actions:

- If message is detected as an impersonated user: Quarantine the message
- If message is detected as an impersonated domain: Quarantine the message
- If mailbox intelligence detects an impersonated user: Quarantine the message
- Apply quarantine policy: AdminOnlyAccessPolicy

If message is detected as spoof: Quarantine the message

- Show first contact safety tip: Selected
- Show user impersonation safety tip: Selected
- Show domain impersonation safety tip: Selected
- Show user impersonation unusual characters safety tip: Selected
- Show (?) for unauthenticated senders for spoof: Selected
- Show "via" tag: Selected

### Anti-Phishing -Standard
- Enable users to protect (impersonated user protection): Selected (Add the key users ie Executives, leaders etc)
- Enable domains to protect: Include domains I own, Include custom domains
- Enable mailbox intelligence: Selected
- Enable intelligence for impersonation protection: Selected
- Enable spoof intelligence: Selected

Actions:

- If message is detected as an impersonated user: Quarantine the message
- If message is detected as an impersonated domain: Quarantine the message
- If mailbox intelligence detects an impersonated user: Quarantine the message
- Apply quarantine policy: AdminOnlyAccessPolicy

If message is detected as spoof: Move the message to the recipients' Junk Email folders (Quarantine to change to Strict)

- Show first contact safety tip: Selected
- Show user impersonation safety tip: Selected
- Show domain impersonation safety tip: Selected
- Show user impersonation unusual characters safety tip: Selected
- Show (?) for unauthenticated senders for spoof: Selected
- Show "via" tag: Selected


### Anti-Spam - Strict
[Microsoft recommendations for EOP and Defender for Office 365 security settings - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365?view=o365-worldwide#eop-anti-spam-policy-settings)

Inbound:

- Bulk email threshold: 5
- Increase spam score settings: Off
- Mark as spam settings: Off

Actions:

- Spam detection action: Quarantine message
- High confidence spam: Quarantine message
- Phishing detection action: Quarantine message
- High confidence phishing detection action: Quarantine message
- Bulk detection action: Quarantine message
- Retain spam in quarantine for this many days: 30 days
- Enable spam safety tips: Selected
- Enable zero-hour auto purge (ZAP) for phishing messages: Selected
- Enable ZAP for spam messages: Selected

Allow & Block list: Not recommended to add any allowed senders or sender domains.



### Anti-Spam - Standard
Inbound:

- Bulk email threshold: 6 (5 for Strict)
- Increase spam score settings: Off
- Mark as spam settings: Off

Actions:

- Spam detection action: Move message to Junk Email folder (Quarantine for Strict)
- High confidence spam: Quarantine message
- Phishing detection action: Quarantine message
- High confidence phishing detection action: Quarantine message
- Bulk detection action: Move message to Junk Email folder (Quarantine for Strict)
- Retain spam in quarantine for this many days: 30 days
- Enable spam safety tips: Selected
- Enable zero-hour auto purge (ZAP) for phishing messages: Selected
- Enable ZAP for spam messages: Selected

Allow & Block list: Not recommended to add any allowed senders or sender domains.



### Safe Links (Standard and Strict)
Related: [Microsoft recommendations for EOP and Defender for Office 365 security settings - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365?view=o365-worldwide#safe-links-policy-settings)

URL & click protection settings

Email:

- On: Safe Links checks a list of known, malicious links when users click links in email: Selected
- Apply Safe Links to email messages sent within the organization: Selected
- Apply real-time URL scanning for suspicious links and links that point to files: Selected
- Wait for URL scanning to complete before delivering the message: Selected
- Do not rewrite URLs, do checks via Safe Links API only: Not Selected

Teams:

On: Safe Links checks a list of known, malicious links when users click links in Microsoft Teams: Selected

Office 365 Apps:

On: Safe Links checks a list of known, malicious links when users click links in Microsoft Office apps: Selected

Click protection settings:

- Track user clicks: Selected
- Let users click through to the original URL: Not selected
- Display the organization branding on notification and warning pages: Selected

How would you like to notify your users?: Use the default notification text


### Safe Attachments (Standard and Strict)

Related: [Microsoft recommendations for EOP and Defender for Office 365 security settings - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365?view=o365-worldwide#safe-attachments-policy-settings)

- Safe Attachments unknown malware response: Block
- Quarantine policy: AdminOnlyAccessPolicy
- Redirect attachment with detected attachments : Enable redirect: Selected, define a security admin email address for review, or support address if possible
- Apply the Safe Attachments detection response if scanning can't complete (timeout or errors): Selected

[^1]: ZAP is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.
[^2]: enables AI that determines user email patterns with frequent contacts

