# i3 Window Manager On Github Codespace
This setup installs an Ubuntu 24.04 container with the i3 tiling window manager and configures a VNC connection.

Running a GUI in Codespaces is generally permitted, as Microsoft themselves provide documentation for setting up a Fluxbox-based desktop with a browser: https://github.com/devcontainers/features/tree/main/src/desktop-lite. In this case, we’ll be using a tiling window manager instead. You don’t need to worry about account issues as long as you use the service responsibly and stay within GitHub’s Terms of Service.

# How to use
1. Create a new space: https://github.com/codespaces/new
2. Select this repo `nic-gunter-gtchs/codespace-xfce`
3. Select this branch: `i3wm`
4. Select a machine type. To unlock better machine types, file a ticket to Github: https://support.github.com/contact?tags=rr-codespaces%2Ccat_codespace
5. Click "Create codespace". It will take a while to create
6. Once created, open PORTS tab, open forwarded address, click on `vnc.html` link and enter your VNC password

The default VNC password is just `password`. You can change it using `vncpasswd` in Terminal. You don't need to worry about weak password because the vnc ports are not public by default, accessing the ports requires your Github account to be logged in. This makes it a lot secure

The default keyboard layout is English (US).

To run Windows app, install Wine: https://wiki.winehq.org/Ubuntu

# Limitations & bugs
- No hardware acceleration because Codespace does not have a GPU
- Terminal won't open. This is a work in progress

# Screenshots

![2024-05-31 20 36 02](https://github.com/AndnixSH/codespace-desktop/assets/40742924/efe23986-9024-457f-8e10-d04ac1898b18)

![2024-05-31 20 35 27](https://github.com/AndnixSH/codespace-desktop/assets/40742924/5ddd627e-d48f-413c-a153-dff1173e75de)
