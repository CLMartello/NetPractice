# Level 8

## Notes
This level connects three networks. All networks can use the same subnet mask, but must have different, non-overlapping IP ranges.

Solution
- Subnet Mask: 255.255.255.240
- CIDR: /28
- 32 - 28 = 4
- 2^4 = 16
- 16 total IP addresses
- 14 usable host addresses
- Subnet ranges:
```
0-15, 16-31, 32-47, 48-63, 64-79, 80-95, 96-111, 112-127, 128-143, 144-159, 160-175, 176-191, 192-207, 208-223, 224-239, 240-255
```

- Internet:
  - Forwards traffic toward the next hop
  - Next hop: R12 interface IP (163.235.250.12)

## Network 1
- Interfaces: R13 and R21
- Router 2:
  - Given next hop: 147.235.143.62 (R13 interface IP)
  - Destination: default (to reach all external networks)
- R13 interface IP: 147.235.143.62
- Subnet range: 48-63
- Valid R21 interface IP range: 147.235.143.48 - 147.235.143.63 (excluding 147.235.143.62)
- Reserved IP 147.235.143.48 (network address) and 147.235.143.63 (broadcast address)
- Router R1:
  - Connects the Internet and forwards traffic toward next hop
  - Destination: Internet (147.235.143.0/26)
  - Next hop: R21 Interface IP (147.235.143.49)

## Network 2
- Interfaces: D2 and R23
- Chosen subnet range: 0-15
- Valid IP range: 147.235.143.0 - 147.235.143.15
- Reserved IP 147.235.143.0 (network address) and 147.235.143.15 (broadcast address)
- Host D:
 - Destination: default (to reach all external networks)
 - Next hop: R23 interface IP (147.235.143.1)

## Network 3
- Interfaces: C1 and R22
- Chosen subnet range: 16-31
- Valid IP range: 147.235.143.16 - 147.235.143.31
- Reserved IP 147.235.143.16 (network address) and 147.235.143.31 (broadcast address)
- Host C:
 - Destination: default (to reach all external networks)
 - Next hop: R22 interface IP (147.235.143.17)

All networks use the same /28 subnet mask. Network 1 uses IP range 48-63, Network 2 uses 0-15 and Network 3 uses 16-31.

<img width="912" height="842" alt="level8" src="https://github.com/user-attachments/assets/ae7694c6-b508-4eaa-aa58-0f4b67f12dbe" />

Summary
- All networks can use the same subnet mask, but IP ranges should not overlapping
- Hosts and routers use next hop and default routes to ensure connectivity
- Subnet planning prevents IP conflicts and ensures proper routing
