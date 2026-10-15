# CMPG325 — Leano Travel Agency Final Project Phase

This folder contains the final implementation and submission materials for the Leano Travel Agency network project.

## Required folder structure

- `packet-tracer/` — final Cisco Packet Tracer `.pkt` file
- `technical-report/` — final technical report PDF
- `screenshots/` — topology, VLAN/trunk, router subinterface, gateway, inter-VLAN, printer and ACL evidence

## Network summary

The design uses five VLANs and Router-on-a-Stick routing over the assigned `192.168.32.0/24` address block:

| VLAN | Name | Network | Gateway |
|---:|---|---|---|
| 10 | ADMINISTRATION | `192.168.32.0/28` | `192.168.32.1` |
| 20 | TRAVEL_OPERATIONS | `192.168.32.16/28` | `192.168.32.17` |
| 30 | FINANCE | `192.168.32.32/28` | `192.168.32.33` |
| 40 | IT_SERVER | `192.168.32.48/28` | `192.168.32.49` |
| 50 | SHARED_PRINTER | `192.168.32.64/28` | `192.168.32.65` |

## Final verification

Before submission, confirm that the final `.pkt` file opens correctly and that the recorded test results match the actual simulation. Include evidence of VLAN and trunk configuration, router subinterfaces, gateway and inter-VLAN tests, CR8 printer access from both required departments, and authorised/unauthorised server access.

Only report the ACL restriction as successful after verifying the ACL rules, interface assignment, and both access tests.
