# Use the base image
FROM linuxmintd/mint22.3-amd64:latest

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
	# Installing stuff for vnc
    apt-get install -y dbus-x11 python3-websockify python3-numpy python3-pip pipx cabextract tightvncserver htop software-properties-common && \
