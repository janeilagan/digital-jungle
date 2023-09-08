---
alias:
tags:
- published
- index/25.04
---


Resources:
- [File policies - Microsoft Defender for Cloud Apps | Microsoft Learn](https://learn.microsoft.com/en-us/defender-cloud-apps/data-protection-policies)
- [[Onboard Office 365 to Defender for Cloud Apps]]

Prerequisites: 
- Defender for Cloud Apps appropriate license (see https://aka.ms/M365EnterprisePlans)
- Enable file monitoring from Defender portal under Cloud apps section

Procedure:
- From Defender portal, locate Settings > Cloud apps > Information Protection > Files
- Enable file monitoring
![bd20130f81b94876ada61a65dabaa012 MD5](https://i.imgur.com/KLREAB8.png)

- From Defender portal > Cloud Apps > Files
- Query the location and items you want to label
- Bulk select the files and "Apply sensitivity label" (Note: this option will only be available if you select files supported for labelling. Selecting any unsupported file will hide this option) See: [supported file types](https://learn.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels-sharepoint-onedrive-files?view=o365-worldwide#supported-file-types)

![a9ff686115be2077f5ae3f0e1ada3000 MD5](https://i.imgur.com/IlL64cH.png)

- This may take a couple of minutes to process, then the files should show up as labelled

![e2ff257ffac29af059d9fd21c6af61a7 MD5](https://i.imgur.com/Rpkx502.png)

![f17f4557a15db7b7e32ac8a1dc760de0 MD5](https://i.imgur.com/IKiBecP.png)

![4a5aed600b0deab5e82472731d349b6b MD5](https://i.imgur.com/DYQGY4q.png)
