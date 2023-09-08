---
alias:
tags:
- published
- index/27.14
---

from: https://k21academy.com/microsoft-azure/admin/recap-day-3-3/



Virtual network peering enables us to connect two VNet in the same or across regions. If both of the virtual networks are in Azure and also within the same region, then you can use **peering.** Due to this, the workload in those virtual machines can communicate with each other.

![](https://i.imgur.com/wuDh4tN.png)

- **Regional Vnet peering** connects Azure virtual networks in the same region.
- **Global Vnet peering** connects Azure virtual networks in different regions.

---

**Q1: Can we peer the VNet with a VNet in a different subscription?**

Ans. Yes. You can peer virtual networks (VNets) across subscriptions and across regions.

**Q2: Can we peer two VNets with matching or overlapping address ranges?**

Ans. No. Address spaces must not overlap to enable VNet Peering.

**Q3:** **Can we create a peering connection to a VNet in a different region?**

Ans. Yes. **Global VNet peering** enables you to peer VNet in different regions. Global VNet peering is available in all Azure public regions, China cloud regions, and Government cloud regions. You cannot globally peer from Azure public regions to national cloud regions.

![](https://i.imgur.com/MetGdWd.png)

**Q4: Does peering will be a good option for end-users?**

Ans. Peering typically produces a more **direct path** between two networks, thereby reducing the distance that data have to travel. The result is **lower latency** and improved user experience.

**Q5: If we peer VNetA to VNetB and I peer VNetB to VNetC, does that mean VNetA and VNetC are peered?**

Ans. No. **Transitive** peering is not supported. You must peer VNetA and VNetC for this to take place.

If we have 3 VNets peered with each other; example A <> B <> C. We want Azure VM in A Vnet to talk to Azure VM in C Vnet then it won’t work; because A and C VNet have not peered directly to each other; but through B Vnet.

Fact that VM in A VNet not able to reach VM in C Vnet is called as **“Transitive Routing Problem”.**

For a Solution: [Read this documentation](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-network-peering-overview#service-chaining)

**Q6: Are there any bandwidth limitations for peering connections?**

Ans. No. VNet peering, whether local or global, does not impose any bandwidth restrictions. Bandwidth is **only** limited by the VM or the compute resource.