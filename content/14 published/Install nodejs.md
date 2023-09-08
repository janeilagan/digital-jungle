---
alias:
tags:
- published
- index/23.13
---

- Install nodejs LTS from https://nodejs.org/en/download
- Start > Search for **"Environment Variables"** 
- Click **"Edit system environment variables"**
- Click **"Environment Variables"** in the dialog.
- In the **"System Variables"** box, search for **Path** and edit it to include `C:\Program Files\nodejs` 

![](https://i.imgur.com/3jJdKMh.png)

- restart your Terminal
- Test by running the following:

```powershell
node -v
npm -v
```

![](https://i.imgur.com/BkAV5JW.png)
