# Computer-Networks-CMPG325-Project

## Milestone 1 – Client Design Review

### Project Overview

This project is a network design for Leano Travel Agency (Mahikeng). The purpose of Milestone 1 is to identify the client's requirements and design a network that provides departmental separation, appropriate IP addressing, and communication between the required departments.

### Client Requirements

- Use the allocated 192.168.32.0/24 address block.
- Separate departments using VLANs.
- Provide connectivity for Administration, Travel Operations, Finance, IT/Server and Shared Printer.
- Support inter-VLAN communication.
- Use Router-on-a-Stick for routing between VLANs.
- Provide a shared printer.
- Keep the IT server network logically separated.

### Physical Topology

A star topology was selected with end devices connected to a central switch. R1 provides inter-VLAN routing, SW1 manages VLANs, PC1–PC7 represent departmental users, Server is in the IT Server VLAN and Printer is in the Shared Printer VLAN.

### VLAN Design

| VLAN | Department | Network | Gateway |
|---|---|---|---|
| 10 | Administration | 192.168.32.0/28 | 192.168.32.1 |
| 20 | Travel Operations | 192.168.32.16/28 | 192.168.32.17 |
| 30 | Finance | 192.168.32.32/28 | 192.168.32.33 |
| 40 | IT Server | 192.168.32.48/28 | 192.168.32.49 |
| 50 | Shared Printer | 192.168.32.64/28 | 192.168.32.65 |

### IP Addressing

The original 192.168.32.0/24 network was divided into five /28 subnets. The subnet mask is 255.255.255.240.

| Device | VLAN | IP Address | Gateway |
|---|---:|---|---|
| PC1 | 10 | 192.168.32.2 | 192.168.32.1 |
| PC2 | 10 | 192.168.32.3 | 192.168.32.1 |
| PC3 | 20 | 192.168.32.18 | 192.168.32.17 |
| PC4 | 20 | 192.168.32.19 | 192.168.32.17 |
| PC5 | 30 | 192.168.32.34 | 192.168.32.33 |
| PC6 | 30 | 192.168.32.35 | 192.168.32.33 |
| PC7 | 40 | 192.168.32.50 | 192.168.32.49 |
| Server | 40 | 192.168.32.51 | 192.168.32.49 |
| Printer | 50 | 192.168.32.66 | 192.168.32.65 |

---

## Milestone 2 – Client Implementation Review

Milestone 2 implements the Milestone 1 design in Cisco Packet Tracer.

Completed:
- VLAN configuration
- Access-port configuration
- 802.1Q trunk configuration
- Router-on-a-Stick inter-VLAN routing
- IPv4 addressing
- Server configuration
- Shared printer configuration
- Connectivity testing
- Cisco IOS verification

### Milestone 2 Documentation

[Milestone 2 – Client Implementation Review](Milestone%202/README.md)

### Milestone 2 Status

- VLANs 10, 20, 30, 40 and 50: Complete
- Access ports: Complete
- Trunk: Complete
- Router-on-a-Stick: Complete
- IP addressing: Complete
- Server: Complete
- Shared printer: Complete
- Connectivity testing: Complete
- Switch verification: Complete