---
alias:
tags:
- published
- index/25.20
---


## Setting up

- [x] create defender for identity instance ✅ 2022-10-28

UP NEXT: 
- [x] ⏫ fix internet connection of lab ✅ 2022-10-28
- [x] ⏫ migrate the server roles - remaining 15 days before server expires ✅ 2022-10-28
- [x] download sensor ✅ 2022-10-28

Setting up PGJILAB | [General How Tos](onenote:https://d.docs.live.net/b7d16696854446dc/Documents/Notebooks/Upskilling/JILAB/General%20How%20Tos.one#section-id={3445A6EF-9B2B-42B6-BC09-9E056EF03F95}&end)  ([Web view](https://onedrive.live.com/view.aspx?resid=B7D16696854446DC%213573&id=documents&wd=target%28JILAB%2FGeneral%20How%20Tos.one%7C3445A6EF-9B2B-42B6-BC09-9E056EF03F95%2F%29))

## Installing Sensor

- NPCAP is needed. already part of installer
- Need latest windows update install
- ensure prerequisites are met
- install on Domain Controller

### Simulation

- Account used: JSJohns
- Signed in to Windows 11 domain joined machine
- downloaded mimikatz

UP NEXT:
- [x] https://2vb732sensorapi.atp.azure.com/ ensure is reachable ✅ 2022-10-31

SEE: [desired result](https://learn.microsoft.com/en-us/defender-for-identity/configure-proxy#enable-access-to-defender-for-identity-service-urls-in-the-proxy-server:~:text=You%20should%20get%20an%20Error%20503%20The%20service%20is%20unavailable%2C%20which%20indicates%20you%20were%20successfully%20able%20to%20route%20to%20the%20Defender%20for%20Identity%20HTTPS%20endpoint.%20This%20is%20the%20desired%20result).

> **Result**: You should get an _Error 503 The service is unavailable_, which indicates you were successfully able to route to the Defender for Identity HTTPS endpoint. This is the desired result.


### Troubleshooting

![73fc29a586347772d7ebdc5d3231a5dd](https://i.imgur.com/foDRF9q.png)


Resource: [How to implement Defender for Identity and configure all prerequisites (jeffreyappel.nl)](https://jeffreyappel.nl/how-to-implement-defender-for-identity-and-configure-all-prerequisites/)

Note: Need to wait 10 hours before creating the gMSA account

Create: 
```powershell
New-ADServiceAccount -Name MDIGMSA -DNSHostName MDIGMSA.m365securitylab.local –Description "Microsoft Defender for Identity service account" –KerberosEncryptionType AES256 –ManagedPasswordIntervalInDays 30
```

Get gMSA details:

```powershell
Get-ADServiceAccount MDIGMSA -Properties * | fl DNSHostName, SamAccountName, KerberosEncryptionType, ManagedPasswordIntervalInDays, PrincipalsAllowedToRetrieveManagedPassword
```

Set Principals

```powershell
Set-ADServiceAccount -Identity MDIGMSA -PrincipalsAllowedToDelegateToAccount 'Domain Controllers'
```

Get gMSA details again, then test the service account

Test AD Service account

```powershell
Test-ADServiceAccount -Identity 'MDIGMSA'
```


### Onboard the sensor

Add Directory Service account 

![6f3e0963fcb3ae6e60435cbca3f075ea](https://i.imgur.com/xgbvril.png)



![25f8ec2cbe846fbf919e40c8ba4dfdc6](https://i.imgur.com/OjejhnM.png)

Add sensor

Install NPCAP, then Azure ATP Sensor Setup

![3cbd18b8ff09d9d47f3f4127bb8f0d07](https://i.imgur.com/lLtHEUv.png)


Setup honeytoken account 
(not to be used, used to trap malicious attacker)

![4fa6ec00c9967acd837d18d69131d7ad](https://i.imgur.com/zT3DYUC.png)


Tag from Defender for Identity portal

![4a74eac4d12a523462cd36740035d462](https://i.imgur.com/Q1xs5fP.png)

Add sensitive users 

![f2a264b6c64aa77aa8b607328fbb2864](https://i.imgur.com/heV2ror.png)

- Configure [[Remote Calls to SAM]]
- [[AHC Defender for Identity]]