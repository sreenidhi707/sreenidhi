---
layout: default
title: Add GUI to Linux
---

# Add GUI to Linux

## Install VNC Server:
```bash
sudo apt update
sudo apt install tightvncserver
```

## Install a Desktop Environment:
```bash
sudo apt install xfce4 xfce4-goodies
```

## Configure VNC Server
Start VNC server for the first time to set a password:
```bash
vncserver :1
```
You'll be prompted to set a VNC password (required) and a view-only password (optional).
Kill the VNC server to configure it:
```bash
vncserver -kill :1
```
Edit the VNC startup script:
```bash
vi ~/.vnc/xstartup
```
Replace the contents with:
```bash
#!/bin/bash
xrdb $HOME/.Xresources
startxfce4 &
```
Make it executable:
```bash
chmod +x ~/.vnc/xstartup
```

## Start VNC Server
```bash
vncserver :1 -geometry 1920x1080 -depth 24
```

## To make copy/paste work:
```bash
sudo apt install autocutsel xclip
```
Add this line: `autocutsel -fork` to `~/.vnc/xstartup`.
The final contents of `~/.vnc/xstartup` will look like this:
```bash
#!/bin/sh
xrdb "$HOME/.Xresources"
startxfce4 &

# Allow copy and paste to work
autocutsel -fork
# Fix to make GNOME work
export XKL_XMODMAP_DISABLE=1
/etc/X11/Xsession
```

[Back to home]({{ '/' | relative_url }})
