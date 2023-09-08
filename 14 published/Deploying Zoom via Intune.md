---
alias:
tags:
- published
- index/25.18
---

See: https://support.zoom.us/hc/en-us/articles/201362163-Mass-deployment-with-preconfigured-settings-for-Windows


Switch needed: 

```cmd
msiexec /i ZoomInstallerFull.msi /quiet /qn /norestart MSIRestartManagerControl=Disable /log zoommsi.log ZoomAutoUpdate=1 ZConfig="nogoogle=1" ZRecommend="AudioAutoAdjust=1"
```


![](https://i.imgur.com/cTFh4Bz.png)


![](https://i.imgur.com/125Xr7o.png)


For advanced packaging, use [[PS App Deploy Toolkit - PSADT]] 