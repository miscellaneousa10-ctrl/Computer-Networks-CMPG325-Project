# Computer-Networks-CMPG325-Project
Milestone 1 – Client Design Review
Project Overview

This project is a network design for Leano Travel Agency (Mahikeng). The purpose of Milestone 1 is to identify the client's requirements and design a network that provides departmental separation, appropriate IP addressing, and communication between the required departments.

1. Client Requirements

The network must:

Use the allocated 192.168.32.0/24 address block.
Separate departments using VLANs.
Provide connectivity for:
Administration
Travel Operations
Finance
IT/Server
Shared Printer
Support inter-VLAN communication.
Use Router-on-a-Stick for routing between VLANs.
Provide a shared printer that can be accessed by the required departments.
Keep the IT server network logically separated from the other departments.
2. Physical Topology

A star topology was selected because all end devices connect to a central switch. This makes the network easier to manage, troubleshoot and expand.

The main devices are:

R1 Router – Provides inter-VLAN routing using Router-on-a-Stick.
SW1 Switch – Connects the end devices and manages the VLANs.
PC1–PC7 – Represent departmental users.
Server – Located in the IT Server VLAN.
Printer – Located in the Shared Printer VLAN.

The connection between R1 and SW1 is configured as an 802.1Q trunk, allowing multiple VLANs to travel across one physical connection.

3. Logical Topology / VLAN Design

The network is divided into five VLANs:

VLAN	Department	Network	Gateway
10	Administration	192.168.32.0/28	192.168.32.1
20	Travel Operations	192.168.32.16/28	192.168.32.17
30	Finance	192.168.32.32/28	192.168.32.33
40	IT Server	192.168.32.48/28	192.168.32.49
50	Shared Printer	192.168.32.64/28	192.168.32.65

Router-on-a-Stick allows devices in different VLANs to communicate through R1.

Communication Rules
Administration can communicate with the required departmental resources.
Travel Operations can communicate with the required departments and the shared printer.
Finance can communicate with the required departments and the shared printer.
The IT Server network is separated into VLAN 40 and is intended for authorised IT access.
The Shared Printer is placed in VLAN 50 and can be reached by the departments that require printing.
4. IP Addressing

The original 192.168.32.0/24 network was divided into five /28 subnets.

Each /28 subnet provides:

16 total addresses
14 usable host addresses
1 network address
1 broadcast address

The subnet mask used throughout the network is:

255.255.255.240
Device Addressing
Device	VLAN	IP Address	Gateway

PC1	10	192.168.32.2	192.168.32.1
PC2	10	192.168.32.3	192.168.32.1

PC3	20	192.168.32.18	192.168.32.17
PC4	20	192.168.32.19	192.168.32.17

PC5	30	192.168.32.34	192.168.32.33
PC6	30	192.168.32.35	192.168.32.33

PC7	40	192.168.32.50	192.168.32.49
Server	40	192.168.32.51	192.168.32.49
Printer	50	192.168.32.66	192.168.32.65
