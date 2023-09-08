---
alias:
tags:
- published
- index/27.15
---

# Microsoft Learn notes


## Fundamentals
- Variables - store values and use as arguments
- Functions - list of statements or reusable commands
- Flow Control- If, ElseIf, Else
- Loops- ForEach, Do-While, Do
- Error handling - Try, Catch, Finally
- Expressions - operators and operands, computation - [Expressions - PowerShell | Microsoft Docs](https://docs.microsoft.com/en-us/powershell/scripting/lang-spec/chapter-07?view=powershell-7.2)

## Scope

- Global Scope - continues to exist after session ends
- Local scope - current scope, can be Global Scope or Script Scope

### Scope rules

- Scopes can nest
- Items are visible in the current and child scopes
- Items can be changed only in the created scope


## Parameters
Source: [Exercise - Parameters - Learn | Microsoft Docs](https://docs.microsoft.com/en-us/learn/modules/script-with-powershell/5-exercise-parameters)

- use to make scripts flexible
- allows options or inputs from users
- cmdlets, Functions, scripts can all accept parameters
- all are optional by default


### switch
```powershell
param(

  [switch]$IncludeUsage=$false

)

  

switch ($true)

{

  $IncludeUsage

  {

    Write-Host "Print this if switch is selected"

  }

}


#Usage
# ./switchtest.ps1 -IncludeUsage
```


#### dependent switch

```powershell
[CmdletBinding(DefaultParametersetName='None')] 
Param(
    [Parameter(ParameterSetName='Secrets',Mandatory=$false)][switch]$IncludeUsage,      
    [Parameter(ParameterSetName='Secrets',Mandatory=$true)][string]$TenantId,
    [Parameter(ParameterSetName='Secrets',Mandatory=$true)][string]$AppId,
    [Parameter(ParameterSetName='Secrets',Mandatory=$true)][string]$AppSecret
 )
$ParamSetName = $PsCmdLet.ParameterSetName

```


#### conditions

```powershell
function test-switch {
   param (
    [switch]$there = $true
   )
   if ($PSBoundParameters.ContainsKey('there')) {
       if ($there) {
          'was passed in'
       } else {
          'set to false'
       }
   } else {
       'Not passed in'
   }
}
```


### Declaration
`Param()`

```powershell
# Create-File.ps1

Param(
	$Path
)

New-Item $Path
Write-Host "File $Path was created"
```

### Usage

```powershell
./Create-File.ps1 -Path c:\temp

```

### Mandatory parameters

`  [Parameter(Mandatory=$true)]`

#### Usage
```powershell
 Param(

    [Parameter(Mandatory=$true)]

    [String] $AdminSiteURL,

    [String] $ReportOutput

 )
```

> [!NOTE] Summary
> Using parameters can be set as switches on the script
> 
> Param(
>	$**Path**
>)
>
>./Create-File.ps1 -**Path**


### Improving parameters
- setup optional or required parameters
- setup what allowed values can be
- can it accept more than one type of value? (string, boolean, int)
- use default when needed, but is it reliable?
- improve user experience by adding help message

```powershell
param(
	[String] $Param1
	[String] $Param2
	[Boolean] $Param3
)
```


## Command-based Help

(Apparently the comments on beginning of scripts aren't just to make them pretty lol)

- [What is Comment Based Help and Why Your Scripts Need It (inedo.com)](https://blog.inedo.com/powershell/what-is-comment-based-help)
- [Examples of Comment-Based Help - PowerShell | Microsoft Docs](https://docs.microsoft.com/en-us/powershell/scripting/developer/help/examples-of-comment-based-help?view=powershell-7.2)




## Flow Control
- how code runs in console or script

### Sanitize input
- Ensure parameters hold reasonable values

### Control Execution flow
- decide how to run code. Ensure you get reasonable and correct input data

### Iterate over data
- essentially looping (iteration is looping)
- Can use array, json dataset etc
	- [PowerShell For Loop, ForEach-Object Loop and Other Loops (business.com)](https://www.business.com/articles/powershell-for-loop/)
	- [PowerShell looping examples for the 4 key commands (techtarget.com)](https://www.techtarget.com/searchitoperations/answer/PowerShell-looping-examples-for-the-4-key-commands)

**for** loop

```powershell
for (<Initial iterator value>; <Condition>; <Code to repeat>)
{
    <Statement list>
}
```

```powershell
for ($num = 1 ; $num -le 10 ; $num++){ 
"I count $num"
}
```

![632b54793fa7a5c7529f135fb1f7d926](https://i.imgur.com/jaF4FFN.png)


**while** loop
- sometimes called pre-test loop
- instructions in the loop body will not be executed if the condition doesn't match
- condition only contains boolean
- to use a loop counter, you need to initialize it first
- LOGIC: unless condition is true, it will keep running the loop

---

# Action Items
[  ] Continue here: [Exercise - Parameters - Learn | Microsoft Docs](https://docs.microsoft.com/en-us/learn/modules/script-with-powershell/5-exercise-parameters)
