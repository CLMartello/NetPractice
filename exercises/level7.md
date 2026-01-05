# Level 7

## Notes

This level connects three different networks. All networks must use different subnet masks if needed and have non-overlapping IP ranges.

## Network 1
- Interfaces: A1 and R11
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
- Subnet Mask: 255.255.255.240 or CIDR /28
- Given R11 IP = 119.198.14.1
- Subnet range: 0-15
- A1 interface IP:
  - Valid IP range: 119.198.14.0 - 119.198.14.15 (excluding 119.198.14.1)
  - Reserved IP 119.198.14.0 (network address) and 119.198.14.15 (broadcast address)
- Host A:
  - Destination: default (to reach all external networks)
  - Next hop: R11 interface IP (119.198.14.1)
 
## Network 2
- Interfaces: R12 and R21
- Communication between routers usually uses a /30 subnet mask to avoid wasting IP addresses.
- Chosen Subnet Mask: 255.255.255.252
- Chosen CIDR: /30

A /30 subnet provides:
- 32 - 30 = 2
- 2^2 = 4
- 4 total IP addresses
- 2 usable host addresses
Subnet ranges:
```
0-3, 4-7, 8-11, 12-15, ..., 248-251, 252-255
```

Solution
- Given R12 IP = 119.198.14.254
- Subnet range: 252-255
- Subnet mask: 119.198.14.252 or CIDR /30
- Valid R21 interface IP: 119.198.14.253
- Reserved IP 119.198.14.252 (network address), 119.198.14.255 (broadcast address) and 119.198.14.254 (occupied IP)
- Router R1:
  - Destination: default (to reach all external networks)
  - Next hop: R21 interface IP (119.198.14.253)
- Router R2:
  - Destination: default (to reach all external networks)
  - Next hop: R12 interface IP (119.198.14.254)

## Network 3
- Interfaces: R22 and C1
- Chosen Subnet Mask: 255.255.255.224
- Chosen CIDR: /27

A /27 subnet provides:
- 32 - 27 = 5
- 2^5 = 32
- 32 total IP addresses
- 30 usable host addresses
- Subnet ranges:
```
0-31, 32-63, 64-95, 96-127, 128-159, 160-191, 192-223, 224-255
```

Solution
- Occupied ranges: 0-15 (network 1) and 252-255 (network 2)
- Any available range can be used
- Chosen subnet range: 32-63
- C1 and R22 interfaces IP:
  - Valid IP range: 119.198.14.32 - 119.198.14.63
  - Reserved IP 119.198.14.32 (network address) and 119.198.14.63 (broadcast address)
- Host C:
  - Destination: default (to reach all external networks)
  - Next hop: R22 interface IP (119.198.14.33)

Network 1 uses a /28 subnet (0–15), Network 2 uses a /30 subnet (252–255), and Network 3 uses a /27 subnet (32–63).

<img width="1277" height="885" alt="level7" src="https://github.com/user-attachments/assets/7b423c50-789d-4e0c-bc43-ff4445c1fbad" />

Summary
- Each network uses a distinct, non-overlapping IP range
- CIDR /30 is ideal for router-to-router connections
- Hosts use default routes to reach external networks
- Proper subnet planning prevents IP conflicts
