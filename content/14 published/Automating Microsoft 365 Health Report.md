---
aliases: []
tags:
  - published
  - index/23.15
---

Automating M365 Health Report is one of the things I started that I am a bit proud of. Given it's not a level of *oh-I-am-a-developer!* type of automation, but it's pretty neat and helps a lot when generating reports that you would normally manually gather for your clients.

The report is built via PowerShell, utilising the `Microsoft.Office.Interop.Word` and `Excel.Application` Assemblies in order to build an all in one word file report like below:

![](https://i.imgur.com/NaMUq4h.gif)


Including the following exports:

![](https://i.imgur.com/l2UMITy.png)


## Usage

As part of the report still needs manual intervention (I know, I wish it's fully automated too), but I deemed some sections are important to be included even though there's no automated way to do it yet. 
 

Default way of running the report will be supervised mode, and will require authentication to **Exchange Online** using at least **Global Reader.**

```powershell
.\New-M365HealthReport.ps1 -CustomerName $CustomerName -TenantID $TenantID -AppID $AppID -AppSecret $AppSecret
``` 

All Report files will be stored in the `C:\Temp\M365 Health Reports\CustomerName` folder in this same location.
 

If it's prefer to use a different path, call the script with the `-ExportFolder` switch.

```powershell
.\New-M365HealthReport.ps1 -CustomerName $CustomerName -TenantID $TenantID -AppID $AppID -AppSecret $AppSecret -ExportFolder "C:\temp\Folder Name here"
```

This will prompt for authentication, then run the script.


### Use case: Automated part is done already and just need to run the manual sections

```powershell
.\New-M365HealthReport.ps1 -CustomerName $CustomerName -TenantID $TenantID -AppID $AppID -AppSecret $AppSecret -Supervised
```
#### Automated sections

The rest of the report is then automated. This can be called separately by using `-Unsupervised` switch

### Use case: Run the automated part as a scheduled task

```powershell
.\New-M365HealthReport.ps1 -CustomerName $CustomerName -TenantID $TenantID -AppID $AppID -AppSecret $AppSecret -Unsupervised
```

### Build the report
Once confirmed that all data has been gathered and all manual sections are updated, run the `-Build` switch 

**IMPORTANT**: This section calls for assemblies `Microsoft.Office.Interop.Word` and `Microsoft.Office.Interop.Excel` and will require Word/Excel to be working properly.

```powershell
.\New-M365HealthReport.ps1 -CustomerName $CustomerName -Build
```

## Generating an app registration

To generate a new app registration:

```powershell
.\Collectors\New-AppRegistration.ps1 -AppOwner "adm-jilagan@executivecats.com"         
```

Wherein `-AppOwner` is the Global Admin account giving the permissions.



## Source

I have the script hosted in a private repository as it's currently utilised for work and cannot be moved to open source:

![](https://i.imgur.com/4oq6YQB.png)


# Variations

I have made other reports in variation to this for different purposes and context:
- Intune Monthly Device Health Report
- Azure Health Report


---

I have also made another one via PowerBI (though in no means I am a PowerBI expert - just this one specifically)
- [[Automating Monthly Microsoft 365 Usage Report via PowerBI]]