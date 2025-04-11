# Use the base image
FROM mcr.microsoft.com/devcontainers/base:ubuntu-22.04

# Enable privileged mode
USER root

# Set up environment variables to suppress interactive prompts
ENV DEBIAN_FRONTEND=noninteractive

# Preconfigure the keyboard layout
RUN echo 'keyboard-configuration keyboard-configuration/layoutcode string us' | debconf-set-selections && \
    echo 'keyboard-configuration keyboard-configuration/layout select English (US)' | debconf-set-selections

# Install necessary packages
RUN apt-get update && \
    apt-get upgrade -y && \
	# Installing xfce, vnc and Wine.
    apt-get install -y tigervnc-standalone-server xfce4 xfce4-goodies novnc python3-websockify python3-numpy cabextract tightvncserver htop python3-pip software-properties-common && \
	# Remove dummy Firefox
    apt-get remove -y firefox && \ 
	# Install Firefox without Snap
	echo 'Package: firefox*\nPin: release o=LP-PPA-mozillateam\nPin-Priority: 1001' | tee /etc/apt/preferences.d/Mozilla && \
	add-apt-repository ppa:mozillateam/ppa && \
	apt-get update && \
    apt-get install -y firefox
