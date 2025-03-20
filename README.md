Overview
This script automates the creation and configuration of a subnet (vmbr1) in Proxmox VE, enabling NAT forwarding through the main network interface (vmbr0). It performs comprehensive checks and fixes common networking issues to ensure proper subnet functionality.

Features
Automatically creates and configures vmbr1 network bridge

Sets up NAT routing between vmbr1 and vmbr0

Enables IP forwarding for proper traffic flow

Configures persistent iptables rules

Performs extensive diagnostic checks

Auto-fixes common networking issues

Creates backups of network configurations before making changes

Provides detailed logging of all actions

Prerequisites
Proxmox VE 6.x or later

Root access to the Proxmox node

Functioning vmbr0 interface with internet connectivity

Installation
Download the script to your Proxmox server:

bash
wget -O /root/proxmox-subnet-script.sh https://raw.githubusercontent.com/yourusername/proxmox-subnet-script/main/proxmox-subnet-script.sh
Make the script executable:

bash
chmod +x /root/proxmox-subnet-script.sh
Usage
Run the script as root:

bash
./proxmox-subnet-script.sh
The script will automatically:

Check your current network configuration

Create backups of existing network settings

Configure vmbr1 with subnet 192.168.1.0/24

Set up NAT forwarding through vmbr0

Apply all necessary fixes for proper routing

Provide detailed output of all operations

Customization
You can modify the following variables at the top of the script to customize your subnet:

bash
MAIN_BRIDGE="vmbr0"     # Your main bridge interface
NAT_BRIDGE="vmbr1"      # The subnet bridge to create
NAT_IP="192.168.1.1"    # IP address for the subnet bridge
NAT_SUBNET="192.168.1.0/24"  # Subnet range
Troubleshooting
The script includes comprehensive diagnostics that will identify and fix common issues:

IP forwarding not enabled

Missing NAT rules

Bridge configuration problems

MAC address conflicts

Missing iptables persistence

If you encounter issues after running the script, check the logs in /root/network_backups/ directory.

Contributing
Contributions are welcome! Please feel free to submit a Pull Request.
