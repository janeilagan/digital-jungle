---
alias: Convert markdown file to pdf
tags:
- published
- index/23.14
---

- create a JSON file called `config.json`

```json
{
    "stylesheet" : "https://cdnjs.cloudflare.com/ajax/libs/github-markdown-css/2.10.0/github-markdown.min.css",
    "css": ".page-break { page-break-after: always; } .markdown-body { font-size: 14px; } .markdown-body table td, .markdown-body table th { word-break: break-all; width: 500px; } .markdown-body table td { table-layout: fixed; } .markdown-body table tr { page-break-inside: avoid; }",
    "body_class": "markdown-body",
    "marked_options": {
        "headerIds": false,
        "smartypants": false
    },
    "pdf_options": {
        "format": "A4",
        "margin": "10mm",
        "printBackground": false,
        "timeout": 0
    },
    "stylesheet_encoding": "utf-8"
}
```

- run md-to-pdf using below:

```powershell
cat file.md | md-to-pdf --config-file C:\temp\config.json > Output.pdf
```