# Milestone 2 – Client Implementation Review

## Overview

Milestone 2 implements the network designed in Milestone 1 for Leano Travel Agency (Mahikeng) in Cisco Packet Tracer.

Completed implementation:
- VLAN creation and departmental segmentation
- Access-port configuration
- 802.1Q trunk configuration
- Router-on-a-Stick inter-VLAN routing
- IPv4 addressing using /28 subnets
- Server configuration
- Shared printer configuration
- Connectivity testing
- Cisco IOS verification commands

## 1. VLAN Implementation

| VLAN | Department | Network | Default Gateway |
|---|---|---|---|
| 10 | Administration | 192.168.32.0/28 | 192.168.32.1 |
| 20 | Travel Operations | 192.168.32.16/28 | 192.168.32.17 |
| 30 | Finance | 192.168.32.32/28 | 192.168.32.33 |
| 40 | IT Server | 192.168.32.48/28 | 192.168.32.49 |
| 50 | Shared Printer | 192.168.32.64/28 | 192.168.32.65 |

Subnet mask: 255.255.255.240 (/28). Each /28 subnet provides 16 total addresses and 14 usable host addresses.

## 2. Switch Access Ports

| Switch Port | VLAN | Purpose |
|---|---:|---|
| Fa0/1 | Trunk | Connection to R1 |
| Fa0/2 | 10 | Administration |
| Fa0/3 | 10 | Administration |
| Fa0/4 | 20 | Travel Operations |
| Fa0/5 | 20 | Travel Operations |
| Fa0/6 | 30 | Finance |
| Fa0/7 | 30 | Finance |
| Fa0/8 | 40 | IT Server |
| Fa0/9 | 40 | IT Server |
| Fa0/10 | 50 | Shared Printer |

## 3. Trunk Configuration

SW1 Fa0/1 is the trunk connection between the switch and router.

Configuration:

    interface FastEthernet0/1
     switchport mode trunk

Verification was performed with:

    show interfaces trunk

The verification confirmed that Fa0/1 was trunking using 802.1Q and that VLANs 10, 20, 30, 40 and 50 were active and forwarding.

## 4. Router-on-a-Stick

R1 uses one physical interface with multiple subinterfaces to provide inter-VLAN routing.

| Subinterface | VLAN | Gateway |
|---|---:|---|
| G0/0.10 | 10 | 192.168.32.1 |
| G0/0.20 | 20 | 192.168.32.17 |
| G0/0.30 | 30 | 192.168.32.33 |
| G0/0.40 | 40 | 192.168.32.49 |
| G0/0.50 | 50 | 192.168.32.65 |

Each subinterface acts as the default gateway for its VLAN. Router-on-a-Stick allows traffic to be routed between the VLANs through R1.

## 5. Device IP Configuration

| Device | VLAN | IP Address | Subnet Mask | Default Gateway |
|---|---:|---|---|---|
| PC1 | 10 | 192.168.32.2 | 255.255.255.240 | 192.168.32.1 |
| PC2 | 10 | 192.168.32.3 | 255.255.255.240 | 192.168.32.1 |
| PC3 | 20 | 192.168.32.18 | 255.255.255.240 | 192.168.32.17 |
| PC4 | 20 | 192.168.32.19 | 255.255.255.240 | 192.168.32.17 |
| PC5 | 30 | 192.168.32.34 | 255.255.255.240 | 192.168.32.33 |
| PC6 | 30 | 192.168.32.35 | 255.255.255.240 | 192.168.32.33 |
| PC7 | 40 | 192.168.32.50 | 255.255.255.240 | 192.168.32.49 |
| Server0 | 40 | 192.168.32.51 | 255.255.255.240 | 192.168.32.49 |
| Printer0 | 50 | 192.168.32.66 | 255.255.255.240 | 192.168.32.65 |

## 6. Server Configuration

Server0 was placed in VLAN 40 (IT Server).
- IP address: 192.168.32.51
- Subnet mask: 255.255.255.240
- Default gateway: 192.168.32.49

## 7. Shared Printer Configuration

Printer0 was placed in VLAN 50 (Shared Printer).
- IP address: 192.168.32.66
- Subnet mask: 255.255.255.240
- Default gateway: 192.168.32.65

## 8. Switch Verification

The following commands were used:

    show vlan brief
    show interfaces trunk
    show interfaces status

show vlan brief confirmed that VLANs 10, 20, 30, 40 and 50 were active and that the correct ports were assigned.

show interfaces trunk confirmed that Fa0/1 was trunking with 802.1Q and that VLANs 10, 20, 30, 40 and 50 were active and forwarding.

show interfaces status confirmed the configured switch ports were connected and operating in their expected VLANs.

## 9. Connectivity Testing

Successful tests included:

| Source | Destination | Result |
|---|---|---|
| PC1 | 192.168.32.1 | Successful |
| PC1 | 192.168.32.18 | Successful |
| PC1 | 192.168.32.34 | Successful |
| PC1 | 192.168.32.50 | Successful |
| PC1 | 192.168.32.66 | Successful |
| PC7 | 192.168.32.51 | Successful |
| PC7 | 192.168.32.66 | Successful |

These tests demonstrate communication with the local VLAN gateway and communication between different VLANs through Router-on-a-Stick.

Some first packets in Packet Tracer initially timed out while address resolution took place; subsequent tests completed successfully.

## 10. Implementation Status

| Requirement | Status |
|---|---|
| VLAN 10 configured | Complete |
| VLAN 20 configured | Complete |
| VLAN 30 configured | Complete |
| VLAN 40 configured | Complete |
| VLAN 50 configured | Complete |
| Access ports configured | Complete |
| Trunk configured | Complete |
| Router-on-a-Stick configured | Complete |
| IP addressing configured | Complete |
| Server configured | Complete |
| Printer configured | Complete |
| Inter-VLAN connectivity tested | Complete |
| Switch verification performed | Complete |

## 11. Evidence

Evidence for the implementation consists of VLAN configuration, trunk verification, interface-status verification, PC IP configuration, server configuration, printer configuration, successful ping tests and the Packet Tracer topology.

The working Packet Tracer .pkt file and screenshots should be added to the repository alongside this documentation.

## 12. Milestone 2 Outcome

The Milestone 1 network design was implemented in Cisco Packet Tracer. The final implementation contains five departmental VLANs, an 802.1Q trunk between SW1 and R1, Router-on-a-Stick inter-VLAN routing, correctly addressed end devices, a dedicated IT server network and a shared printer network.

The network was verified using Cisco IOS commands and end-to-end ping tests.