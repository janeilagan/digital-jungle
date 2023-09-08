---
alias:
tags:
- published
- index/25.15
---


[Enable per-user Multi-Factor Authentication - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/authentication/howto-mfa-userstates)

Enabling Azure AD Multi-Factor Authentication through a Conditional Access policy **doesn't change the state** of the user. Don't be alarmed if users appear disabled. Conditional Access doesn't change the state.

**Don't enable or enforce per-user Azure AD Multi-Factor Authentication if you use Conditional Access policies.**

Use: [gists/Set-MFAState.ps1 at main · executivecats/gists (github.com)](https://github.com/executivecats/gists/blob/main/Set-MFAState.ps1)

Changing user states isn't recommended unless your Azure AD licenses don't include Conditional Access and you don't want to use security defaults.

All users start out Disabled. When you enroll users in per-user Azure AD Multi-Factor Authentication, their state changes to Enabled. When enabled users sign in and complete the registration process, their state changes to Enforced. Administrators may move users between states, including from Enforced to Enabled or Disabled.
