# Project 01 LAN & DHCP Troubleshooting Lab

## Overview

A hands-on Cisco Packet Tracer lab demonstrating network configuration, troubleshooting, root cause analysis, and incident resolution.

This project includes **five intentionally introduced network failures**, each diagnosed and resolved using Cisco IOS commands and connectivity testing.

## Network Topology

- 1 Cisco 2911 router
- 2 Cisco 2960 switches
- 4 workstations
- LAN10: `192.168.10.0/24`
- LAN20: `192.168.20.0/24`
- Router-based DHCP for both LANs

## Troubleshooting Incidents

| Ticket | Problem | Status |
|---|---|---|
| INC-001 | Router interface administratively down | Resolved |
| INC-002 | Incorrect default gateway | Resolved |
| INC-003 | Incorrect subnet mask and Proxy ARP | Resolved |
| INC-004 | Incorrect DHCP default gateway | Resolved |
| INC-005 | Missing DHCP network statement | Resolved |

## Technical Skills Demonstrated

- Cisco IOS configuration and troubleshooting
- IPv4 addressing and subnetting
- DHCP configuration and lease renewal
- Routing between directly connected networks
- ARP and Proxy ARP analysis
- Network fault isolation
- Technical incident documentation

## Troubleshooting Methodology

1. Identify the reported connectivity issue.
2. Capture the failure using diagnostic commands.
3. Investigate the root cause.
4. Apply a targeted configuration fix.
5. Verify recovery using connectivity tests.
6. Document the results and lessons learned.

## Tools Used

- Cisco Packet Tracer
- Cisco IOS CLI
- `ping`
- `ipconfig`
- `arp`
- `show ip interface brief`
- `show ip route`
- `show running-config`

## Project Files

- **TROUBLESHOOTING.md** — Detailed reports for all five incidents
- **Packet Tracer (.pkt)** — Network simulation file
- **Screenshots** — Failure, diagnosis, and recovery evidence

## Key Takeaway

This project strengthened my ability to troubleshoot network connectivity problems systematically rather than relying on trial-and-error configuration changes.

**All five simulated incidents were successfully resolved and verified.**
