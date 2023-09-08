---
alias:
tags:
- published
- index/23.02
---

[Install WSL | Microsoft Learn](https://learn.microsoft.com/en-us/windows/wsl/install)

- Enable "Windows Subsystem for Linux" from Windows Features (Turn Windows features on or off), restart PC
- Install "Debian" from Microsoft Store
- Setup UNIX username and PW
- Update using `sudo apt update && sudo apt upgrade`



# Install packages

**Git**
```bash
sudo apt-get install git

git config --global user.email "youremail@domain.com"
```

**NPM**
```bash
sudo apt-get install npm
```

**CURL**
```bash
sudo apt-get install curl
```

# Terminal

On Ubuntu-based distros, you can install zsh using: `sudo apt-get install zsh`. Once the installation completes, you can check the version using `zsh --version`, then make zsh your default shell using `chsh -s $(which zsh)`. You’ll need to log out, then log back in for the changes to take effect.

As with macOS, you can revert back to Bash using: `chsh -s $(which bash)`.

If you are running a non-Ubuntu based distro, then check out the instructions for other distros.

> From: [10 Zsh Tips & Tricks: Configuration, Customization & Usage — SitePoint](https://www.sitepoint.com/zsh-tips-tricks/)


--

# Switch from zsh to bash

From: [terminal - Switching from zsh to bash on OS X, and back again? - Stack Overflow](https://stackoverflow.com/questions/10341271/switching-from-zsh-to-bash-on-os-x-and-back-again)

You can just use `exec` to replace your current shell with a new shell:

Switch to `bash`:

```bash
exec bash
```

Switch to `zsh`:

```bash
exec zsh
```

This won't affect new terminal windows or anything, but it's convenient.

# Change root password in wsl

- Open cmd.exe
- Type wsl -u root
- Type passwd username and change the password
- Type exit
- Type wsl
- Type sudo echo hi to confirm the new password works.

> From: [Unable to change the root password in Windows 10 WSL - Ask Ubuntu](https://askubuntu.com/questions/931940/unable-to-change-the-root-password-in-windows-10-wsl)


# login as sudo

`sudo -s`