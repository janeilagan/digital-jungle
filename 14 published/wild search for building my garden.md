---
alias: Obsidian customisation
tags:
- published
- index/00.01
---

# Workflow
- All notes should be independent
- Create MOPs instead and link the individual notes there together instead
- use jd in frontmatter 

## Hotkeys
- Ctrl 2 - Open Daily Note
- Ctrl Shift X - Open Workspaces
- Ctrl U - Create Unique Note
- Ctrl Shift Delete - Delete current file
~~- Ctrl S - Start Sync~~ 2023-06-29 no longer using remotely-save
- `Ctrl + -` - Toggle Task

## Taking notes
- [[best way to take notes]]
- [[Obsidian Clipper|clipping notes]]

## Heatmaps
- Enabled Dataveiw
- Enabled heatmap-calendar-obsidian


# Sharing
- Use local attachments for sensitive contents
- For sharing, ensure screenshots info are blurred out, then use share as gist
- [[Sharing specific obsidian notes with screenshots]]
- If necessary, download all shared attachments locally using local images plus. 


# Syncing

## What I'm looking for
- not costly (I really want to try Obsidian Sync but I'm not sure if it's worth it)
- can sync with iPhone and iPad
- can sync with other Windows devices
- sync plugins as well 
- make use of my OneDrive Personal storage/subscription
- encryption

### Options

#### [Syncthing](https://syncthing.net/)
- usage is only free up to 20MB

#### [Remotely-save](https://github.com/remotely-save/remotely-save)
- open source and free
- can be used with iPhone and iPad
	- caveat: will be using the phone/iPad's storage
	- plugins are not synced (not sure if this is possible since sync with _ is available, but since I'm using git too I didn't want to sync that as well)
- makes use of OneDrive Personal 
- encrypted, but I personally used another OneDrive account rather than granting the plugin access to my personal one.
- easy to configure.
~~- went with this!~~ **2023-06-29 too many bugs - deletes my files so i had to leave this solution, went with iCloud instead.**

20221124 - Update on settings "Skip Large Files = 5MB" to avoid crashing. [Issue](https://github.com/remotely-save/remotely-save/issues/247)


# Publishing


## What I want
- little to no cost (Obsidian Publish is great but costly 😥)
- with graph view
- easy to deploy
- using GitHub Pages
- 20230110 - share private pages including attachments

### how much should you publish online
- [The only way to learn in public is to build in public • Mental Nodes](https://www.mentalnodes.com/the-only-way-to-learn-in-public-is-to-build-in-public)
- For inspiration: [About • Mental Nodes](https://www.mentalnodes.com/about)
	- This is using this [kmcgillivray/obsidian-lettersmith: Transform any Obsidian vault (or any folder of markdown files) into a backlink-powered static website using Lettersmith. (github.com)](https://github.com/kmcgillivray/obsidian-lettersmith)

## Options

[Obsidian Publish alternatives - Share & showcase - Obsidian Forum](https://forum.obsidian.md/t/obsidian-publish-alternatives/22886)

### [obsidian-userland/publish](https://obsidian-userland.github.io/)
- looks simple and nice, but long way to go and too many limitations

### [Pubsidian](https://forum.obsidian.md/t/pubsidian-free-and-elegant-obsidian-publish-alternative/21825)
- needs to be installed (it's essentially a converter)
- great view, would consider using because of interface
- using Netlify (for some reason my ISP blocks Netlify here)
- Attempts:
	- not working yet (cant get it to show the actual pages!) 
	- Update: got it working but links are not working T_T
	- Pause. Trying something else.

### [Obsidian mkdocs](https://github.com/jobindjohn/obsidian-publish-mkdocs)
- should be easy to use and deploy as I have used mkdocs before 
- however no graph view

### [Perlite](https://github.com/secure-77/Perlite)
- too many dependencies
- too many tweaking required
- I need to read through further to know, long learning curve

### [Mindstone](https://github.com/TuanManhCao/digital-garden)
- UI looks great
- plain graph (in comparison to Pubsidian and obsidian-zola )
- can be tested locally
- known issues with graph view

### [Obsidian Zola](https://github.com/ppeetteerrs/obsidian-zola)

^d41417

- really pretty interface based from Adidoks
- Using Netlify (still can't get it to work with my ISP)
- [[Cant get to work locally for testing]]
- was able to partially make it work, but links aren't working, and having hard time testing it because of ISP limitation (I had to use VPN)
- giving this another go 20230428
	- This is now working! 2023-05-06

### [Quartz](https://github.com/jackyzha0/quartz)
- pretty interface, sitting on top of Hugo
- can use GitHub pages
- can test locally
- has graph interface (and pretty one too!)
- cons:
	- linking files from private folders / See [Issue #77](https://github.com/jackyzha0/quartz/issues/77)  > had to move to obsidian-zola because of this
- can use [[gitalk as comment section]]
- [[Configuring Quartz 3.0]]
- 2023-09-05 giving this another go because [Issue #77](https://github.com/jackyzha0/quartz/issues/77)  was fixed on Quartz 4.0 --> plus they update regularly!
	- [[00.01 Configuring Quartz 4.0]]

### [Obsidian Share](https://file.obsidianshare.com/572e1ae4a0aeadf5943862d1deaf8fe6.html)
- for sharing one pagers
- no option to delete the shared notes 
- not encrypted
- includes images
- can modify(?) css if you host personally

