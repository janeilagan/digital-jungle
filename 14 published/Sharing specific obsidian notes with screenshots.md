---
alias:
tags:
- published
- index/00.01
---

## Setting up screenshot uploads

By default, Obsidian stores the screenshots locally.

Configure Imgur to hold the screenshots for easy online sharing. (See [Privacy Settings](https://help.imgur.com/hc/en-us/articles/201746817-Post-Privacy-Settings))

### Option 1: Use plugin
Easiest option: https://github.com/gavvvr/obsidian-imgur-plugin

Enable the plugin, authenticate to your Imgur account and you're good to go! (If you don't have account, create one. If you can't because of mobile number issues, see [Phone Verification not available in some countries – Imgur](https://help.imgur.com/hc/en-us/articles/9025119832717-Phone-Verification-not-available-in-some-countries))


### Option 2: Using ShareX and Imgur

Change the Destinations settings for Image uploader to Imgur

![Fo2EukY](https://i.imgur.com/wUMwW8W.png)

Then select "Destinations" then choose "Destination Settings".

Under Image uploaders, select "Imgur", set the following settings:
- Account type: User
- User account: Connect (connect to the imgur account. If you don't have account, create one. If you can't because of mobile number issues, see [Phone Verification not available in some countries – Imgur](https://help.imgur.com/hc/en-us/articles/9025119832717-Phone-Verification-not-available-in-some-countries))
- Paste the verification code to complete authorization.
- Create an album and select it for upload
- Check "Use direct link"

Change the "After upload task" to:
- Shorten URL
- Copy URL to clipboard

Paste the URL to your notes as attachment.

### Option 3: Beta - Workflow in ShareX

This is currently in testing phase. 
The idea is all your images will be stored in a shared folder inside your personal OneDrive. ShareX will upload the pictures there, copy the sharing link and give the Obsidian/markdown friendly URL 

![Pasted image 20230523110630](https://i.imgur.com/m0vK48M.png)

TBD


## Sharing the notes

### Option 1: QuickShare
Install the plugin: https://github.com/mcndt/obsidian-quickshare

> Note: at the time of writing, it's in the roadmap to share the attachments as well, so this whole note would probably be useless by then lol

Pros:
- no setup needed
- encrypted notes
- you can unshare when you want to

Cons:
- hosted and dependent on the dev's hosting service (but see [funding](https://noteshare.space/funding) and read the docos should you want to host yourself)

### Option 2: Share as Gist
Install the plugin: https://github.com/timrogers/obsidian-share-as-gist

Pros: 
- your notes reside on your github gist account
- can share privately

Cons:
- requires Setup GitHub Personal Access Tokens
- manually unshare notes from gists


# Mobile Uploads and usage

Setup Shortcuts as follows:

![](https://i.imgur.com/F1MNU4C.png)

When working on images from mobile, just ‘copy’ and run shortcut to upload to imgur and update clipboard with the obsidian markdown/wikilink format 