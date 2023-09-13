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

[[25.20 Creating gMSA Accounts for MDI]]
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
- [[25.20 Lessons learned from deployment]]