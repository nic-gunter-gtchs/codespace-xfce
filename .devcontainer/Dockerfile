# Use the base image
FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

# Enable privileged mode
USER root

# Set up environment variables to suppress interactive prompts
ENV DEBIAN_FRONTEND=noninteractive

# Preconfigure the keyboard layout
RUN echo 'keyboard-configuration keyboard-configuration/layoutcode string us' | debconf-set-selections && \
    echo 'keyboard-configuration keyboard-configuration/layout select English (US)' | debconf-set-selections

# add i3 provider
RUN /usr/lib/apt/apt-helper download-file https://debian.sur5r.net/i3/pool/main/s/sur5r-keyring/sur5r-keyring_2025.03.09_all.deb keyring.deb SHA256:2c2601e6053d5c68c2c60bcd088fa9797acec5f285151d46de9c830aaba6173c && \
	apt install ./keyring.deb && \
	echo "deb [signed-by=/usr/share/keyrings/sur5r-keyring.gpg] http://debian.sur5r.net/i3/ $(grep '^VERSION_CODENAME=' /etc/os-release | cut -f2 -d=) universe" | sudo tee /etc/apt/sources.list.d/sur5r-i3.list

# Install necessary packages
RUN apt-get update && \
    apt-get upgrade -y && \
	
	# Installing i3 and vnc. Installing xfce4 solves grey screen issue
    apt-get install -y tigervnc-standalone-server i3 dbus-x11 xfce4 novnc python3-websockify python3-numpy python3-pip pipx cabextract tightvncserver htop software-properties-common && \
	# Remove dummy Firefox
    apt-get remove -y firefox && \ 
	# Install Firefox without Snap
	echo 'Package: firefox*\nPin: release o=LP-PPA-mozillateam\nPin-Priority: 1001' | tee /etc/apt/preferences.d/Mozilla && \
	add-apt-repository ppa:mozillateam/ppa && \
	apt-get update && \
    apt-get install -y firefox
