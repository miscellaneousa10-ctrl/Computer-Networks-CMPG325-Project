# CMPG325 — Leano Travel Agency Final Project Phase

This folder contains the final implementation and submission materials for the Leano Travel Agency network project.

## Folder contents
- `packet-tracer/` — final Cisco Packet Tracer `.pkt` simulation
- `technical-report/` — final technical report
- `screenshots/` — implementation and connectivity test evidence

## VLAN design
| VLAN | Name | Network | Gateway |
|---:|---|---|---|
| 10 | ADMINISTRATION | `192.168.32.0/28` | `192.168.32.1` |
| 20 | TRAVEL_OPERATIONS | `192.168.32.16/28` | `192.168.32.17` |
| 30 | FINANCE | `192.168.32.32/28` | `192.168.32.33` |
| 40 | IT_SERVER | `192.168.32.48/28` | `192.168.32.49` |
| 50 | SHARED_PRINTER | `192.168.32.64/28` | `192.168.32.65` |

The actual simulation, report and evidence files still need to be uploaded to their respective folders.