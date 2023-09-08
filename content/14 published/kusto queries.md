---
alias:
tags:
- published
- index/27.09
---


Reference Guides:
- [KQL quick reference | Microsoft Learn](https://learn.microsoft.com/en-us/azure/data-explorer/kql-quick-reference)
- [Query best practices - Azure Data Explorer | Microsoft Learn](https://learn.microsoft.com/en-us/azure/data-explorer/kusto/query/best-practices)

Notes:
- almost like SQL 
- where = filters columns based on rules (like typical SQL) 
- pipe is used as the same like SQL or when running Powershell
- Read only request
- parameters are case sensitive

Log Analytics Demo: https://aka.ms/lademo

![da99ad523bbfa9012fe41753f75666ca](https://i.imgur.com/zrZenex.png)

## variables

- let - declares a variable
![8d6d086c93693d6ea291b1ed9c3f5170](https://i.imgur.com/sfT7kFs.png)

## search and where operators
![924a087e8fa2f20de629131c221335b6](https://i.imgur.com/sXBnvs6.png)


![60e6247235cb3efd55654c2aa6b5c4ab](https://i.imgur.com/qGFKJNa.png)

## extend operator
- adding a new column that you specify and what you want to see
![3576d85f806a1d9a7304b8b856194da7](https://i.imgur.com/2bhVw48.png)

## order by
- ASC, DESC or nulls

## project operator
### project
- like Select-Object
- will only choose the columns you project
- ![82565844124f0e145434e437f9177977](https://i.imgur.com/om5qzLg.png)

### project-away
- like exclusion
### project-rename
- renames the column
### project-reorder
- changes order/sequence of columns
### project-keep 
- will only keep defined columns

## Summarize, Count and dCount Functions

- summarize or counts per item (kinda like group by)
- ![67e6a505a7653b627e002b740f81d3fa](https://i.imgur.com/wMIfnHw.png)

- dCount is distinctCount (kinda like group by unique values)

## Arg_Max and Arg_Min Functions
- used in conjunction with summarize operator
- latest events and oldest events

### arg_max
![2f344501f173e8c67b5153c859a262ec](https://i.imgur.com/KBPtxbr.png)

### arg_min
![14443157dc7615005ae27bd51a404c6f](https://i.imgur.com/5xvyCKj.png)

## Make_List and Make_Set Functions
- for outputs / json format
- return json arrays

#### make_list
- return json as defined in expression
- will contain duplicate accounts

#### make_set
- results are unique accounts

## Render Operator
- generates visualization (area, bar, column, etc)
![b14e8f4d516282faa8824caa506ac63c](https://i.imgur.com/0Hc6Zjc.png)

## Bin Function
- place results in smaller brackets
- like group by (but used with summarize)

Difference:

not using bin:
![6e22fca84ff2141800c9ec3c839390a4](https://i.imgur.com/N1GDXcm.png)

using bin:
![68ed6b5e25f7eb1f60d651aa6b840dea](https://i.imgur.com/p2m96G8.png)

## Union Operator
- combine data from two tables
- like SQL join

