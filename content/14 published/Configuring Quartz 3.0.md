---
alias:
tags:
- published
- index/00.01
---

Steps: 

- Fork repository from [GitHub]([jackyzha0/quartz: 🌱 host your own second brain and digital garden for free (github.com)](https://github.com/jackyzha0/quartz)). Note to 'fork' and not use the template. 
- Clone the forked repository on local machine
- Install [Go]([Download and install - The Go Programming Language](https://go.dev/doc/install)), relaunch all terminals, then run `go version` in command prompt to confirm it's installed.
- Installed  hugo-obsidian using the following command:
```go
# Install and link `hugo-obsidian` locally
go install github.com/jackyzha0/hugo-obsidian@latest
```

- Installed Hugo using chocolatey
```choco
choco install hugo-extended
```

- cd into quartz location then run below:
```hugo
hugo-obsidian -input=content -output=assets/indices -index -root=.
```

- then run `hugo server`


--- 

Using [[00.01 Configuring Quartz 4.0]] as of 2023-09-08