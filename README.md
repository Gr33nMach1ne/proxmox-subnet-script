
## Overview
This script automates the creation and configuration of a subnet (`vmbr1`) in Proxmox VE, enabling NAT forwarding through the main network interface (`vmbr0`). It performs comprehensive checks and fixes common networking issues to ensure proper subnet functionality.

## Features
- Automatically creates and configures `vmbr1` network bridge
- Sets up NAT routing between `vmbr1` and `vmbr0`
- Enables IP forwarding for proper traffic flow
- Configures persistent `iptables` rules
- Performs extensive diagnostic checks
- Auto-fixes common networking issues
- Creates backups of network configurations before making changes
- Provides detailed logging of all actions

## Prerequisites
- Proxmox VE 6.x or later
- Root access to the Proxmox node
- Functioning `vmbr0` interface with internet connectivity

## Installation
Download the script to your Proxmox server:

```bash
wget -O /root/proxmox-subnet-script.sh https://raw.githubusercontent.com/yourusername/proxmox-subnet-script/main/proxmox-subnet-script.sh
