# Level 9

## Notes
This level aggregates all previous concepts. The goal is to connect multiple networks through routers and the Internet, ensuring proper IP assignment, subnetting, and routing tables.

## Network 1
- Interfaces: A1, B1 and R11
- Subnet mask: 255.255.255.128
- CIDR: /25
- 32 - 25 = 7
- 2^7 = 128
- 128 total IP addresses
- 126 usable host addresses
- Subnet ranges:
```
0-127 and 128-255
```

Solution
- Chosen subnet range: 0-128
- The network IP addresses used in this exercise can be any valid public IPs, since private IP ranges are not required.
- Chosen network IP: 42.42.42
- Valid IP range: 42.42.42.0 - 42.42.42.128
- Reserved IP 42.42.42.0 (network address) and 42.42.42.128 (broadcast address)
- Host A:
  - Destination: default (to reach all external networks)
  - Next hop: R11 interface IP (42.42.42.1)
- Host B:
  - Destination: default (to reach all external networks)
  - Next hop: R11 interface IP (42.42.42.1)

## Network 2
- Interfaces: R13 and R21
- Router-to-router link
- Subnet mask: 255.255.255.252
- CIDR: /30
- 32 - 30 = 2
- 2^2 = 4
- 4 total IP addresses
- 2 usable host addresses
- Subnet ranges:
```
0-3, 4-7, 8-11, 12-15, ..., 248-251, 252-255
```

Solution
- Chosen subnet range: 252-255
- Valid host IP: .253 and .254
- The network IP addresses used in this exercise can be any valid public IPs, since private IP ranges are not required.
- Chosen network IP: 42.42.42
- Router R2:
  - Destination: default (to reach all external networks)
  - Next hop: R13 interface IP (42.42.42.254)
- Router R1:
  - R1 must route between networks and the Internet
  - Destination: R22 interface IP + CIDR (40.40.40.145/28) and R23 interface IP + CIDR (125.86.35.203/18)
  - Next hop: R21 interface IP (42.42.42.253)
  - This ensures all internal networks and Internet traffic are correctly forwarded

## Network 3
- Interface C1 and R22
- Choosing a small subnet mask is recommended because it minimizes IP address waste.
- Chosen subnet Mask: 255.255.255.240
- Chosen CIDR: /28

A /28 subnet provides:
- 32- 28 = 4
- 2^4 = 16
- 16 total IP addresses
- 14 usable host addresses
- Subnet ranges:
```
0-15, 16-31, 32-47, 48-63, 64-79, 80-95, 96-111, 112-127, 128-143, 144-159, 160-175, 176-191, 192-207, 208-223, 224-239, 240-255
```

Solution
- Chosen subnet range: 144-159
- Chosen network IP: 40.40.40
- Valid IP range: 40.40.40.144 - 40.40.40.159
- Reserved IP 40.40.40.144 (network address) and 40.40.40.159 (broadcast address)
- Host C:
 - Destination: default (to reach all external networks)
 - Next hop: R22 interface IP (40.40.40.145)

## Network 4
- Interfaces: D1 and R23
- Subnet mask: 255.255.192.0
- CIDR: /18
- Large network covering the required host range
- Host D:
  - Destination: default (to reach all external networks)
  - Given next hop: R23 interface IP (125.80.35.203)

Solution
- D1 interface IP = 64 subnets in the third octet and host IP range 0-255

## Internet
- Connects to the next hop and must reach Meson and Cation
- Given next hop: R12 interface IP (163.172.250.12)
- Meson destination: A1 interface IP + CIDR (42.42.42.3/25)
- Cation destination: C1 interface IP + CIDR (40.40.40.158/28)

<img width="725" height="766" alt="level9" src="https://github.com/user-attachments/assets/d9b54e5d-45af-4c1c-96c4-eeb7197c6885" />

Summary
- Routers forward traffic between networks and the Internet
- Proper subnetting prevents IP conflicts and ensures connectivity
