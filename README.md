# XFCE Desktop On Github Codespace
This repo will set up the XFCE desktop environment on a Github Codespace and open a noVNC web interface.

Using a desktop enviornment on a Codespace is allowed since Microsoft provided a documentation setting up a Fluxbox based desktop and installing a browser `https://github.com/devcontainers/features/tree/main/src/desktop-lite`, but this repo uses XFCE instead.

# How to use
1. Create a new codespace: https://github.com/codespaces/new
2. Select this repo `nic-gunter-gtchs/codespace-xfce`
3. Click "Create codespace". It will take a while to build
4. Once created, open PORTS tab, open forwarded address, click on `vnc.html` and enter your VNC password once noVNC shows up

The default VNC password is `password`. You can change it using `vncpasswd` in VSCode. The VNC ports are not public.

The default keyboard layout is English (US).

To run Windows apps, install wine: https://wiki.winehq.org/Ubuntu << the default package is outdated from apt!! use this guide

# Limitations & bugs
- No hardware acceleration because Codespaces are not equipped with GPUs
- Terminal Emulator crashes. XFCE Terminal opens and works, use that instead
