---
alias:
tags:
- published
- index/00.02
---


## configuring backup

Forked: [upleveled/notion-backup: Export Notion pages and subpages to a GitHub repo on a schedule (eg. to be used as a scheduled backup)](https://github.com/upleveled/notion-backup)

Use template and setup private repository. 

Created: [janeilagan/notion-backup](https://github.com/janeilagan/notion-backup)

Update index.js with folder ID and dirName for locations you want to backup:
![8ebb0986add42ca27b32ff6dd1fd3866](https://i.imgur.com/HD7m9L9.png)

Create new secret under Settings > called `NOTION_TOKEN`

![6ca2602523d614caf8c503440bf22417](https://i.imgur.com/KuSb3wX.png)

Open https://www.notion.so/janeilagan from web

`Ctrl + Shift + J` to open Dev Tools

![e228cad7c07214f6e8f7e23a1aef4de2](https://i.imgur.com/k2I4EFv.png)

Open Settings from Notion 

![fe9e88f40d0667bac85addc9e858c423](https://i.imgur.com/3PDTCJV.png)

Copy the tokenv2 value and update secret from GitHub Settings

Update secret:

![6ca2602523d614caf8c503440bf22417](https://i.imgur.com/KuSb3wX.png)

Rerun the job
![aff3fb50718829858b4dae3fffeb2f70](https://i.imgur.com/yiCpFTf.png)

Should be successful.
