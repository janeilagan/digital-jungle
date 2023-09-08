---
alias:
tags:
- published
- index/25.17
- index/25.23
---

Resources: 
- [Disable Macros in Microsoft Office using Group Policy – E-N Computers (encomputers.com)](https://www.encomputers.com/2018/05/disable-macros-in-microsoft-office-using-group-policy/)
- [Block Internet Macros For Office Applications Using Intune Group Policy HTMD Blog (anoopcnair.com)](https://www.anoopcnair.com/block-internet-macros-for-office-apps-intune/)
- Q/A: https://answers.microsoft.com/en-us/msoffice/forum/all/disable-office-365-macro-via-gpo/24c54ff3-7644-4972-864a-4f0c1b58e7b6
- Official docs: [Macros from the internet are blocked by default in Office - Deploy Office | Microsoft Learn](https://learn.microsoft.com/en-us/DeployOffice/security/internet-macros-blocked#block-macros-from-running-in-office-files-from-the-internet)

-   [Cloud Policy](https://learn.microsoft.com/en-us/DeployOffice/security/internet-macros-blocked#cloud-policy)
	- Requirements
		- Version should be [supported](https://learn.microsoft.com/en-us/officeupdates/update-history-microsoft365-apps-by-date#supported-versions)
		- Account is signed in to office apps
		- For Windows devices, policies are enforced based on the primary user that is signed into Microsoft 365 Apps for enterprise. If there are multiple accounts signed in, only policies for the primary account are applied.
		- If users are located in nested groups and the parent group is targeted for policies, the users in the nested groups will receive the policies. The nested groups and the users in those nested groups must be created in or synchronized to Azure AD.
-   [Microsoft Endpoint Manager admin center](https://learn.microsoft.com/en-us/DeployOffice/security/internet-macros-blocked#microsoft-endpoint-manager-admin-center)
-   [Group Policy Management Console](https://learn.microsoft.com/en-us/DeployOffice/security/internet-macros-blocked#group-policy-management-console)
	- Ensure you're using the [latest](https://www.microsoft.com/en-us/download/details.aspx?id=fa7662f5-4b7b-4e3e-8948-6c369d8195de) AMDX files 
	