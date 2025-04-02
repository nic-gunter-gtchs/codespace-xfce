# XFCE Desktop On Github Codespace
This configuration will install an XFCE desktop enviornment and automatically opens a VNC connection.

Using desktop enviornment on Codespace is generally allowed since Microsoft themself provided a documentation setting up a Fluxbox based desktop and installing a browser; https://github.com/devcontainers/features/tree/main/src/desktop-lite, but we will use XFCE instead.

# How to use
1. Create a new space: https://github.com/codespaces/new
2. Select this repo `nic-gunter-gtchs/codespace-xfce`
3. Select a machine type. To unlock better machine types, file a ticket to Github: https://support.github.com/contact?tags=rr-codespaces%2Ccat_codespace
4. Click "Create codespace". It will take a while to create
5. Once created, open PORTS tab, open forwarded address, click on `vnc.html` link and enter your VNC password

The default VNC password is just `password`. You can change it using `vncpasswd` in Terminal. You don't need to worry about weak password because the vnc ports are not public by default, accessing the ports requires your Github account to be logged in. This makes it a lot more secure

The default keyboard layout is English (US). You can change it in XFCE settings

To run Windows apps, install Wine: https://wiki.winehq.org/Ubuntu

# Limitations & bugs
- No hardware acceleration because Codespace does not have a GPU
- Terminal won't open. May work if you use Ubuntu 20.04, or use the XFCE Terminal
