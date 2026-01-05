# Level 10

## Notes
This level connects four networks and requires proper subnetting to avoid conflicts. Hosts and routers use next hop and default routes to ensure full connectivity.

## Network 1
- Interfaces: R11, H11 and H21
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
- Given R11 IP: 143.191.77.1
- Subnet range: 0-127
- Valid IP range: 143.191.77.0 - 143.191.77.127 (excluding 143.191.77.1)
- Reserved IP 143.191.77.0 (network address) and 143.191.77.127 (broadcast address)

## Network 2
- Interfaces: R23 and H41
- Subnet Mask: 255.255.255.192
- CIDR: /26

A /26 subnet provides:
- 32 - 26 = 6
- 2^6 = 64
- 64 total IP addresses
- 62 usable host addresses
- Subnet ranges:
```
0–63, 64–127, 128–191, 192–255
```

Solution
- Given H41 IP: 143.191.77.131
- Subnet range: 128-191
- Valid IP range: 143.191.77.128 - 143.191.77.191 (excluding 143.191.77.131)
- Reserved IP 143.191.77.128 (network address) and 143.191.77.191 (broadcast address)

## Network 3
- Interfaces: R13 and R21
- Subnet Mask: 255.255.255.252
- CIDR: /30

A /30 subnet provides:
- 32 - 30 = 2
- 2^2 = 4
- 4 total IP addresses
- 2 usable host addresses
- Subnet ranges:
```
0-3, 4-7, 8-11, 12-15, ..., 248-251, 252-255
```

Solution
- Router R1
  - Destination: R22 interface IP + CIDR (143.191.77.222/28)

## Network 4
- Interfaces: R22 and H31
- Occupied subnet ranges: 0-127, 128-191 and 252-255
- Available subnet ranges: 192-151
- Choosing a small subnet mask is recommended because it minimizes IP address waste.
- Chosen subnet Mask: 255.255.255.240
- Chosen CIDR: /28

A /28 subnet provides:
- 32- 28 = 4
- 2^4 = 16
- 16 total IP addresses
- 14 usable host addresses
- Available subnet ranges:
```
192-207, 208-223, 224-239
```

Solution
- Chosen subnet range: 208-223
- Valid IP range: 143.191.77.208 - 143.191.77.223
- Reserved IP 143.191.77.208 (network address) and 143.191.77.223 (broadcast address)

Network 1 uses a /25 subnet (0–127), Network 2 uses a /26 subnet (128-191), Network 3 uses a /30 subnet (252-255) and Network 4 uses a /28 subnet (208-223).

<img width="667" height="763" alt="level10" src="https://github.com/user-attachments/assets/7393dc97-a342-4f1a-8861-2c607048e486" />

Summary
- Hosts forward traffic to the closest next hop
- Routers handle inter-network and Internet routing
- Small subnets are recommended for efficiency and IP conservation
