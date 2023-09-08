---
alias:
tags:
- published
- index/28.09
- index/25.23
---

Resource: [Manage who can create Microsoft 365 Groups | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)

# Restrict tenant level settings

![c5ed8ea980ed1cb3436528d1534e443a](https://i.imgur.com/1882QNI.png)

## End user experience

![0f88da5f9b47d28d2429430c9daa203a](https://i.imgur.com/Orm833q.png)



# Create a group allowed to manage/create M365 groups

![b087c57b38c77fba55d3881853256140](https://i.imgur.com/dMi0ZFQ.png)


## Run the script to allow groups

```powershell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
    $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
  $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
} else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

## Confirm settings

![5b404b9bb0d858d53b6338031df3e550](https://i.imgur.com/IFT7X9T.png)

## End user experience

Non-member of group:
![0f88da5f9b47d28d2429430c9daa203a](https://i.imgur.com/Orm833q.png)


Member of the group:

![13d4d712819b8ac0b3b2852f7a1f3db3](https://i.imgur.com/96PWRur.png)