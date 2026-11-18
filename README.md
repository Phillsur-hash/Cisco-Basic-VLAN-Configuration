Cisco Basic VLAN Configuration

Project Overview

This project demonstrates how to configure Virtual Local Area Networks (VLANs) on a Cisco switch using the Cisco IOS Command-Line Interface (CLI).

Two VLANs are created to separate network traffic between the Sales and Finance departments. Switch ports are then assigned to their respective VLANs.
Objectives

    Configure a Cisco switch hostname.
    Create and name VLANs.
    Assign switch ports to specific VLANs.
    Configure access ports.
    Verify VLAN configuration using Cisco IOS commands.

Network Configuration:
Device	Interface	VLAN ID	VLAN Name	Department
S1	FastEthernet 0/1	2	Sales	Sales
S1	FastEthernet 0/2	3	Finance	Finance
VLAN Details
VLAN ID	VLAN Name	Status
1	Default	Active
2	Sales	Active
3	Finance	Active

Configuration Steps:

1. Access Global Configuration Mode

Switch> enable
Switch# configure terminal

2. Configure the Switch Hostname:
Switch(config)# hostname S1

3. Create VLANs and Assign Names:
S1(config)# vlan 2
S1(config-vlan)# name Sales

S1(config-vlan)# vlan 3
S1(config-vlan)# name Finance

4. Configure Access Ports:
Assign FastEthernet 0/1 to the Sales VLAN:

S1(config)# interface f0/1
S1(config-if)# switchport mode access
S1(config-if)# switchport access vlan 2

5. Assign FastEthernet 0/2 to the Finance VLAN:
S1(config)# interface f0/2
S1(config-if)# switchport mode access
S1(config-if)# switchport access vlan 3

6. Verify VLAN Configuration:

Use the following command to display the VLAN configuration:
S1(config)# do show vlan

The show vlan command should display the following VLAN assignments:
text

VLAN Name       Status    Ports
---- ---------- --------- ----------------
1    default    active    Fa0/3 - Fa0/24
2    Sales      active    Fa0/1
3    Finance    active    Fa0/2

Verification Results

    VLAN 2 (Sales) is active and assigned to FastEthernet 0/1.
    VLAN 3 (Finance) is active and assigned to FastEthernet 0/2.
    Both access ports are assigned to their respective VLANs.
    Remaining switch ports are assigned to the default VLAN 1.

Technologies Used

    Cisco IOS
    Cisco Catalyst Switch
    VLAN Configuration
    Cisco Command-Line Interface (CLI)
    Networking Fundamentals

Key Concepts Learned

    VLAN (Virtual Local Area Network): Logically separates a physical network into multiple broadcast domains.
    Access Port: A switch port assigned to a single VLAN.
    VLAN Segmentation: Separates departments to improve network organization and isolation.
    VLAN Verification: Uses Cisco IOS commands to confirm VLAN creation and port assignments.

Conclusion

This project demonstrates the basic configuration of VLANs on a Cisco switch. By creating separate VLANs for the Sales and Finance departments, network traffic can be logically segmented.

This is a fundamental networking skill used in enterprise network administration and Cisco networking environments.

Project: Cisco VLAN Configuration

Category: Networking / Cisco Switching

Author: Phillip Surrett
