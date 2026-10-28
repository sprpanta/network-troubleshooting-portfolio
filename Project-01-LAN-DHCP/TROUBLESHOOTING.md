# Project 01 Network Troubleshooting Report

**Tools:** Cisco Packet Tracer, Cisco IOS CLI  
**Environment:** 1 Cisco 2911 router, 2 Cisco 2960 switches, 4 PCs  
**Networks:** 192.168.10.0/24 and 192.168.20.0/24

## INC-001 Router Interface Down

**Problem:** LAN20 connectivity was interrupted.

**Root cause:** Router interface GigabitEthernet0/1 was administratively disabled.

**Diagnosis:** `show ip interface brief` showed `administratively down/down`. Ping to `192.168.20.1` failed.

**Fix:** Re-enabled the interface using `no shutdown`.

**Verification:** Interface returned to `up/up`, and ping succeeded with 0% packet loss.

## INC-002 Incorrect Default Gateway

**Problem:** PC0 could communicate locally but not with another subnet.

**Root cause:** PC0 used `192.168.10.254` instead of `192.168.10.1` as its gateway.

**Diagnosis:** Local ping succeeded; remote ping failed.

**Fix:** Corrected the default gateway.

**Verification:** Remote ping succeeded with 4/4 replies.

## INC-003 Incorrect Subnet Mask and Proxy ARP

**Problem:** PC0 had an incorrect `/16` mask instead of `/24`.

**Diagnosis:** Ping initially succeeded because Proxy ARP was enabled. After disabling Proxy ARP and clearing the ARP cache, remote connectivity failed.

**Fix:** Corrected the subnet mask to `255.255.255.0`.

**Verification:** Remote ping succeeded with Proxy ARP disabled. The original Proxy ARP setting was restored afterward.

## INC-004 Incorrect DHCP Default Gateway

**Problem:** PC3 received an incorrect gateway through DHCP.

**Root cause:** LAN20 DHCP pool advertised `192.168.20.254`.

**Diagnosis:** `ipconfig /renew` confirmed the incorrect gateway, and remote ping failed.

**Fix:** Changed the DHCP pool's `default-router` to `192.168.20.1`.

**Verification:** Renewed the DHCP lease and confirmed successful remote connectivity.

## INC-005 Missing DHCP Network Statement

**Problem:** PC1 could not obtain a DHCP address.

**Root cause:** LAN10 DHCP pool had `network 0.0.0.0 0.0.0.0` instead of the intended subnet.

**Diagnosis:** PC1 repeatedly displayed `DHCP request failed`.

**Fix:** Restored `network 192.168.10.0 255.255.255.0`.

**Verification:** PC1 successfully received `192.168.10.10/24` with the correct gateway and DNS settings.

## Key Skills Demonstrated

- Cisco IOS configuration and verification
- IP addressing and subnet troubleshooting
- DHCP server and client troubleshooting
- ARP and Proxy ARP investigation
- Network connectivity testing
- Root cause analysis and technical documentation

All five incidents were intentionally reproduced, investigated, repaired, and verified in Cisco Packet Tracer.
