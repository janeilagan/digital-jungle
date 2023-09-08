---
alias:
tags:
- published
- index/27.14
---

Resources: 
- [Network security group - how it works | Microsoft Learn](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-group-how-it-works)
- [The Guide to Azure Network Security Group | CloudBolt Software](https://www.cloudbolt.io/azure-costs/azure-nsg/)
- [[AZ-305]]

A network security group contains security rules that allow or deny inbound network traffic to, or outbound network traffic from, several types of Azure resources. For each rule, you can specify source and destination, port, and protocol.

Imagine you have a special box called Azure Network Security Group (NSG) that helps protect your computer or things you put in the box when they are connected to the internet.

The NSG acts like a guard or a filter that checks every message or request coming in or going out of your computer. It looks at the information in the messages and decides if they are safe or not.

For example, if someone tries to send a message to your computer that looks suspicious or harmful, the NSG will block it and not let it reach your computer. This helps keep your computer and the things inside it safe from bad things on the internet.

The NSG can also help you control what your computer can do on the internet. You can tell it which websites or services your computer can connect to and which ones it cannot. It's like setting rules or boundaries for your computer's internet access.

## Capabilities

- [Azure network security groups overview | Microsoft Learn](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-groups-overview)

![](https://i.imgur.com/3e9mYiX.png)


## Difference between NSG and firewall?

An NSG is more targeted and is deployed to particular subnets and/or network interfaces, whereas an Azure Firewall monitors traffic more broadly.

