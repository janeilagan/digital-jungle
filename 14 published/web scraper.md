---
alias:
tags:
- published
- index/23.06
---

Link: https://www.webscraper.io/

How to use for MSDocs:

- Select F12 to open the Dev tool
- Create site map:
	- ![Pasted image 20230620084257](https://i.imgur.com/X81tAtI.png)
- Create selectors
	- ![Pasted image 20230620084326](https://i.imgur.com/mKGDrKp.png)
	
- **toggles** selector is for the navigation:
	- ![Pasted image 20230620084448](https://i.imgur.com/CwVR1L1.png)
	- `selector:` `div[data-test-id='primary-nav-bar']`
	- `click selector:` `span.tree-expander`
	
- **articles** selector for actual articles
	- ![Pasted image 20230620084526](https://i.imgur.com/7Aw5Le9.png)
	- `selector:` `li[tabindex='-1']:nth-of-type(n+2) a`
- Scrape then export
	- ![Pasted image 20230620084629](https://i.imgur.com/Uegq9T8.png)


# Exported sitemap sample

```sitemap
{"_id":"m365_spo_howtos","startUrl":["https://learn.microsoft.com/en-us/sharepoint/introduction"],"selectors":[{"id":"toggles","parentSelectors":["_root"],"type":"SelectorElementClick","clickElementSelector":"span.tree-expander","clickElementUniquenessType":"uniqueHTMLText","clickType":"clickMore","delay":2000,"discardInitialElements":"do-not-discard","multiple":true,"selector":"div[data-test-id='primary-nav-bar']"},{"id":"articles","parentSelectors":["_root"],"type":"SelectorLink","selector":"li[tabindex='-1']:nth-of-type(n+2) a","multiple":true}]}
```