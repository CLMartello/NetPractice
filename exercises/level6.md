# Level 6

## Notes
In this level, the Internet behaves like a router by using a routing table to forward packets from a destination IP to the closest next hop (router interface). The goal is to allow communication between Host A and external networks through the Internet.

## Network 1
- Interfaces: R1 and A1
- Subnet Mask: 255.255.255.128
- CIDR: /25

A /25 subnet provides:
- 32 - 25 = 7
- 2^7 = 128
- 128 total IP addresses
- 126 usable host addresses
- Subnet ranges:
```
0-127 and 128-255
```
Solution
- Given A1 IP = 75.231.206.227
- Subnet range: 128-255
- R1 interface IP:
  - Valid IP range: 75.231.206.128 - 75.231.206.255 (excluding 75.231.206.227)
  - Reserved IP 75.231.206.128 (network address) and 75.231.206.255 (broadcast address)
- Host A:
  - Destination: default (to reach all external networks)
  - Next hop: R1 interface IP (75.231.206.230)
  - Since Host A does not know the full network topology, the default route is sufficient.
- Router R:
  - Destination: default (to reach all external networks)
  - Next hop is the Internet interface
  - Router R connects to networks that are not explicitly shown in the exercise.
- Internet:
  - The Internet connects to Router R2 and must route traffic toward Host A.
  - Destination: A1 interface IP + CIDR (75.231.206.227/25)
  - Given next hop: Router R2 interface IP

<img width="928" height="850" alt="level6" src="https://github.com/user-attachments/assets/d4bea216-4680-4152-b13a-c7658a4e66bd" />

Summary
- Hosts use default routes to reach unknown networks
- Routers forward traffic using routing tables
- The Internet behaves like a router with network-based routing entries
