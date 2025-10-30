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

#### Brave 
- [https://brave.com/linux/]https://brave.com/linux/)

### Alacritty
```bash
sudo zypper in alacritty

# create alacritty config directory
mkdir -p ~/.config/alacritty/alacritty # -p will skip if directory exists
nano ~/.config/alacritty/alacritty/alacritty.toml
# add instructions for config config
```

### Nextcloud Desktop
- [https://nextcloud.com/install/#desktop-files](https://nextcloud.com/install/#desktop-files)

### Obsidian
- add obsidian sync using nextcloud how-to
```bash
# flathub
flatpak install flathub md.obsidian.Obsidian
```

### Visual Studio Code
- [https://code.visualstudio.com/download](https://code.visualstudio.com/download)   `I know.`

### Tor Browser
[https://www.torproject.org/download/](https://www.torproject.org/download/)

### Bambu Studio
```bash
# flathub
flatpak install flathub com.bambulab.BambuStudio
```

### OnlyOffice
- .

#### Tailscale
[https://tailscale.com/kb/1044/install-debian-sid](https://tailscale.com/kb/1044/install-debian-sid)

Two vital commands are missing. 
- to enable service
- to start service

```bash
# full tailscale sid instructions
https://grok.com/share/bGVnYWN5_7e342332-dcdc-431d-8053-214d82d0179b
curl -fsSL https://pkgs.tailscale.com/stable/debian/sid.noarmor.gpg | sudo tee /usr/share/keyrings/tailscale-archive-keyring.gpg >/dev/null
curl -fsSL https://pkgs.tailscale.com/stable/debian/sid.tailscale-keyring.list | sudo tee /etc/apt/sources.list.d/tailscale.list


sudo apt-get update
sudo apt-get install tailscale

sudo systemctl start tailscaled # web instructions DO NOT provide this as of 10/30/25

sudo tailscale up # no vlans
sudo tailscale up --accept-routes --operator=$USER # if wish to accept vlans

sudo tailscale status # provides tailscale IP

# If you're advertising routes, you should be able to ping a vlan subnet

ping -c 4 192.168.1.234 # -c : Limits to exactly X packets

# you should see:
PING 192.168.1.234 (192.168.1.234) 56(84) bytes of data.
64 bytes from 192.168.1.234: icmp_seq=1 ttl=64 time=28.5 ms
64 bytes from 192.168.1.234: icmp_seq=2 ttl=64 time=31.3 ms
64 bytes from 192.168.1.234: icmp_seq=3 ttl=64 time=37.8 ms
64 bytes from 192.168.1.234: icmp_seq=4 ttl=64 time=35.3 ms

--- 192.168.1.234 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3005ms
rtt min/avg/max/mdev = 28.485/33.211/37.839/3.594 ms
```

#### Signal Desktop
- [https://signal.org/download/linux/](https://signal.org/download/linux/)

#### Telegram Desktop
```bash
# flathub
flatpak install flathub org.telegram.desktop
```

 

### Apps #TODO
  
Wine

Winboat

distrobox




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
