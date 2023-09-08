---
alias:
tags:
- published
- index/22.01
---


## Considerations
- Whenever you make any changes to the primary server, ensure you update the settings of the staging server as well.

## Pre-implementation plan
### Preparation
- If using custom setup, use the "Configuration Documenter" tool here: [microsoft/AADConnectConfigDocumenter: AAD Connect configuration documenter is a tool to generate documentation of an AAD Connect installation. (github.com)](https://github.com/Microsoft/AADConnectConfigDocumenter)
	- Extract the files and run `AzureADConnectSyncDocumenter.cmd` to test if the tool is working
	- This will generate a "Report" folder
	- Run the following command to export settings of current server installation
	```powershell
		Import-Module ADSync
		Get-ADSyncServerConfiguration -Path "C:\Temp\EC-DC01-Nov13-2022"
	```
	- Copy the folder generated to the "Data" folder of the tool
	- ![e68531c2fbb28070c37cdb2b6168f05c](https://i.imgur.com/voaIRsf.png)
	- This will generate a report under "Report" folder
	- Export the .json settings from original server
		- ![e582f498843dcdb910d67fe091ae27e8](https://i.imgur.com/19D1Tis.png)
		- ![833570967d7b83a84fa1ac1423f27764](https://i.imgur.com/riZH1uE.png)


## Implementation Plan
### From the new server

- Install Azure AD Connect and import settings from the exported one
- ![ad6a1ca1a25f3b38e13d204ae7872be9](https://i.imgur.com/WPG6ozo.png)
- click Install
- [locate the existing AD Connect account](https://www.alitajran.com/find-azure-ad-connect-accounts/#:~:text=Double%2Dclick%20the%20service%20name,shows%20the%20ADSync%20Service%20account.) used, or create a new account instead. This needs Enterprise admin account
	- ![23419918bdecd44086ffa5eda9651915](https://i.imgur.com/eXwRCvx.png)
- Uncheck the "Start the synchronisation process when configuration completes" option, and keep "Enable staging mode" checked. Click Install.
	- ![81ab8ecdb5b8c570d084ab6ec6d2faf9](https://i.imgur.com/pkAFAsd.png)

## Post-implementation plan
### Compare settings

- Copy the documenter tool to the staging server, including the exported folder during the pre-implementation plan
- Run the following on the new server:
	```powershell
		Import-Module ADSync
		Get-ADSyncServerConfiguration -Path "C:\Temp\EC-DC02-STAGING-Nov13-2022"
	```
- Copy the generated folder to the "Data" path of the documenter tool
	- ![835903ea0b45332b885b8d6ab0efa308](https://i.imgur.com/2dEf32a.png)
- Run the following command:
```cmd
AzureADConnectSyncDocumenterCmd.exe "EC-DC01-Nov13-2022" "EC-DC02-STAGING-Nov14-2022"
```
![a2953a35f3063fea765241b97ce14ef1](https://i.imgur.com/3XXZnIZ.png)

- This will generate a comparison report to which you should be able to see the difference in the setup. Ensure settings are almost identical. (Some like date, or aadsync account used if you generated a new account may be different)
- ![f1b5d9f83d81d9396f3bb28adf585492](https://i.imgur.com/da84rUI.png)

### Confirm staging mode
```powershell
$aadSyncSettings=Get-ADSyncGlobalSettings($aadSyncSettings.parameters | ?{$_.name -eq "Microsoft.Synchronize.StagingMode"}).value
# output "False" means Staging mode is disabled
# output "True" means Staging mode is enabled   
```

![1b7a9813614fad7396152958e66e80ac](https://i.imgur.com/YwWipEJ.png)

