# TP-Link Archer T2U Plus Linux Driver Installation Guide

The TP-Link Archer T2U Plus (AC600) is an affordable and powerful wireless adapter that supports dual-band, monitor mode, soft AP, packet injection, and more. It’s widely used by Kali Linux users for pentesting and network analysis. This guide provides step-by-step instructions to install, uninstall, and troubleshoot the driver on Linux.

## Table of Contents

1. [Driver Installation for Debian-Based Linux Distros](#driver-installation-for-debian-based-linux-distros)
2. [Uninstalling the Driver](#uninstalling-the-driver)
3. [Troubleshooting](#troubleshooting)

## Driver Installation for Debian-Based Linux Distros

### Step 1: Update Package Information

Make sure your package lists are up to date:

```bash
sudo apt update

Step 2: Install Required Dependencies
Install the required development tools and Linux headers:

sudo apt install dkms git build-essential libelf-dev linux-headers-$(uname -r)

Step 3: Clone the Driver Repository
Download the driver files from the GitHub repository:


git clone https://github.com/aircrack-ng/rtl8812au.git
cd rtl88*

Step 4: Install the Driver
Install the driver using dkms:

sudo make dkms_install

Step 5: Verify Wireless Interfaces
Check if your wireless interface is active:

iwconfig

Uninstalling the Driver
To uninstall the driver, check the currently installed dkms modules:

dkms status

Then, remove the driver:

sudo dkms remove 8812au/<version> --all

Delete the driver files:

sudo rm -rf /var/lib/dkms/8812au/

Extra Step (Reinstall after Git Checkout)
reinstall the driver, you can checkout a specific Git commit before proceeding with the installation:

git checkout 35308f4dd73e77fa572c48867cce737449dd8548
sudo make dkms_install

