---
alias:
tags:
- published
- index/25.10
---


- Install python ([Download Python | Python.org](https://www.python.org/downloads/))
- [[Install nodejs]]
- Install `md-to-pdf` by running the command below:

```powershell
npm i -g md-to-pdf
```
- Install `IntuneCD` by running the command below:

 ```powershell
 pip install IntuneCD
```
- Create a folder called IntuneCD (or anything really)
- create a folder for client backup and create an **AUTH.json** file with this:


```json
{
    "params":{
        "TENANT_NAME": "tenant.onmicrosoft.com",
        "CLIENT_ID":  "",
        "CLIENT_SECRET": "" 
    }
}
```

- Run the following to start the backup:

```powershell
IntuneCD-startbackup -p .\ -m 1 -a .\AUTH.json
```
- Then once done, run this: 

 ```powershell
IntuneCD-startdocumentation -p .\ -o .\Report.md -t "Executive Cats" -c
```
 - [[md-to-pdf|Convert markdown file to pdf]] or use any other markdown to pdf converter like pandoc
 