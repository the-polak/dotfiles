# OpenSUSE Post Install

## The basics:
[https://en.opensuse.org/Portal:Tumbleweed](https://en.opensuse.org/Portal:Tumbleweed)
- run w/ `sudo`
- adds repos

### Update Hostname
```bash
sudo hostnamectl set-hostname new-hostname

#display hostname
hostnamectl
```


### Web Services
Sign in to a few services to make later portions of the setup quicker:
- Twitter
- Grok
- Github
- Nextcloud
- gmail
- Discord

### Update
```bash
sudo zypper ref && sudo zypper dup
```

### Create `Applications` directory for AppImages
```bash
mkdir ~./Applications
```
[Download latest Nextcloud Desktop](https://github.com/nextcloud-releases/desktop/releases)



## Tools
---

### Install Alacritty
```bash
# install
sudo zypper in alacritty

# create config directory
mkdir ~/.config/alacritty/alacritty.toml

# create alacritty.toml
nano ~/.config/alacritty/alacritty.toml

# paste backup config
```

### Brave Browser
```bash
# https://brave.com/linux/
curl -fsS https://dl.brave.com/install.sh | sh
```

### Tailscale
```bash
# https://tailscale.com/kb/1031/install-linux
curl -fsSL https://tailscale.com/install.sh | sh

# accept routes
sudo tailscale up --accept-routes --operator=$USER
```

### Install MS VS Code
[https://linuxiac.com/how-to-install-vs-code-on-opensuse-leap-tumbleweed/](https://linuxiac.com/how-to-install-vs-code-on-opensuse-leap-tumbleweed/)

```bash
# non oss version
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo zypper addrepo https://packages.microsoft.com/yumrepos/vscode vscode

sudo zypper ref

sudo zypper install code
```


## Social / IRC


### Install Halloy
```bash
# IRC client
sudo zypper in halloy

# edit config.toml
cp ~/.config/halloy/config.toml ~/.config/halloy/config.toml.bak && nano ~/.config/halloy/config.toml

####################################

# Halloy config.
# 10-17-25
# For a complete list of available options,
# please visit https://halloy.chat/configuration/

[servers.rogueserver]
nickname = "kielbasa"
alt_nicks = ["kielbastard", "spoko"]
server = "irc.rogueserver.com"
channels = ["#dragonmere","wasted","whuppy"]
use_tls = false
port = 6667
on_connect = ["/list","/join #wasted", "/join #dragonmere"]

####################################

```

### Konversation
- Should be preinstalled
- #TODO - copy configs



### Rogueserver MP3 Stream
Listen to Wasted & Dragonmere via VLC stream rather than in browser

VLC `=>` Media `=>` Open Network Stream
- or `Control + N`

direct mp3 link https://listen.rogueserver.com/wastedmemory.mp3 
<br>
chat interface link https://www.rogueserver.com/wastedmemory
<br>
mumble : mumble.rogueserver.com


## Virtualization and Containers

### Install Docker and Docker Compose
[https://en.opensuse.org/Docker](https://en.opensuse.org/Docker)
- see official OpenSUSE howto

### Install Podman
[https://www.opensuse.org/](https://www.opensuse.org/)
