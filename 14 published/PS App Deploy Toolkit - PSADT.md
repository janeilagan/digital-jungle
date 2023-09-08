---
alias:
tags:
- published
- index/25.18
---

- Source: [PSAppDeployToolkit](https://psappdeploytoolkit.com/)

- Download here: [Releases · PSAppDeployToolkit/PSAppDeployToolkit · GitHub](https://github.com/PSAppDeployToolkit/PSAppDeployToolkit/releases)
- Download ServiceUI for prompts
- References: [Using PSADT to bring system prompts to the user context (call4cloud.nl)](https://call4cloud.nl/2021/01/the-amazing-psadt/)

- The extract will contain
- ![](https://i.imgur.com/kz7Zzfh.png)


- Add the ServiceUI to the ToolKit location
- Paste your installer files inside "Files" folder
- Update the Deploy-Application.ps1 file
- ![](https://i.imgur.com/BW9q56I.png)
- Insert the Installation task script 
- Test the package on sandbox
- `.\[[ServiceUI]].exe -Process:explorer.exe Deploy-Application.exe`
- ![](https://i.imgur.com/JMCqNDB.png)
- Once working, package using IntuneWinAppUtil


## Download Service UI 

- Download the Microsoft Deployment Toolkit *MDT* to get the ServiceUI.exe file

- [Download Microsoft Deployment Toolkit (MDT) from Official Microsoft Download Center](https://www.microsoft.com/en-us/download/confirmation.aspx?id=54259)

- It will install first, then you can grab the ServiceUI.exe from `C:\Program Files\Microsoft Deployment Toolkit\Templates\Distribution\Tools\x86\`

