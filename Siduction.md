# Siduction Post-Install

> [!Note]
> Apart from a few minor tweaks, Siduction Linux is nearly perfect OOB - at least in my opinion. 
> After distro-hopping I tend to return to Siduction as the palette cleanser. After a few weeks/months away, I'll forget how to optimize a fresh install. Some info exists but I've had difficulty pinning down a solid and **current** list of post-install actions for those using Siduction Linux. This is my attempt as of October in the year of our lord, 2025. 
> 
> Please refer to the [Siduction Manual](https://manual.siduction.org/index_en.html) before you follow random idiots to damnation. 
> 


## SUDO - doas
Siduction 7.3 `Doas` - Alternative to `sudo`
- Siduction devs prefer `doas` while I do not. 
```bash
# Add your user to SUDO
su - root
# enter root pw
/sbin/usermod -aG sudo -enterusername 
```
## Updates - `full-upgrade`
Siduction 7.6.7 through 7.6.9: Updating the System

The following procedure should be followed:
<BR>

0.  Check for [**Upgrade Warnings**](https://forum.siduction.org/) before proceeding. 
1. Log out of the desktop environment.
(This procedure is nowadays only recommended when updating X or the
desktop environment itself, but does not hurt in other cases.)

2. Switch to the text console with Ctrl+Alt+F3.
3. Log in as root.
Then execute the following commands:

```bash
systemctl isolate graphical.target
apt update
apt full-upgrade
apt clean
systemctl isolate multi-user.target && exit
```



## Fonts
```bash
sudo apt install ttf-mscorefonts-installer 
sudo apt install fonts-crosextra-carlito fonts-crosextra-caladea
```

## KDE
migrate dotfiles for settings, layout, etc
taskbar settings
krunner
dolphin
keyboard shortcuts
konsole 

### Kinda KDE
app shortcuts (tor browser)


## Applications

Brave 

Alacritty

Nextcloud Desktop

Obsidian

Visual Studio Code

Appimagelauncher

Tor Browser

Bambu Studio
 

### Apps #TODO
Tailscale

Signal Desktop

Telegram Desktop

Wine

Winboat

distrobox

OnlyOffice
- fuck you.


## Generic Obsidian Sync featuring nextcloud, dolphin and fstab

TBD



<BR><BR><BR><BR>
---
##### Sources of info
- When Chad says RTFM
  - https://manual.siduction.org/index_en.html
- Straight from the horses mouth
  - [https://forum.siduction.org/index.php?topic=9029.0](https://forum.siduction.org/index.php?topic=9029.0)
- Old post with a few suggestions
  - https://www.linuxquestions.org/questions/blog/beachboy2-315980/siduction-tips-for-beginners-36550/