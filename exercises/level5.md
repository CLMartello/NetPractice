# Level 5

## Notes
In this level, Machine A must communicate with Machine B through routers. Unlike previous levels, this exercise introduces routing tables on hosts. A routing table entry contains:
- A destination (specific network or default)
- A next hop (the closest router interface)

## Network 1
- Interfaces: R2, B1 and Machine B
- Subnet Mask: 255.255.192.0
- CIDR: /18

A /18 subnet provides:
- 64 subnets in the third octet
- Host range from .1 to .254 per subnet

Solution
- Given R2 IP = 150.52.212.254
- Subnet range: 0-255
- B1 interface:
  - Valid B1 IP range: 150.52.212.0 - 150.52.212.255 (excluding 150.52.212.254)
  - Reserved IP 150.52.212.0 (network address) and 150.52.212.255 (broadcast address)
  - The third octet may also be modified, but it is not necessary in this case.
- Machine B:
  - Given destination: default (to reach all external networks)
  - Next hop: R2 interface IP (150.52.212.254)

## Network 2
- Interfaces: R1 and A1
- Subnet Mask: 255.255.255.128
- CIDR: /25

A /25 subnet provides:
- 32- 25 = 7
- 2^7 = 128
- 128 total IP addresses
- Subnet ranges:
```
0-127 and 128-255
```

Solution
- Given R1 IP = 73.138.77.126
- Subnet range: 0-127
- A1 interface:
  - Valid IP range: 73.138.77.0 - 73.138.77.127 (excluding 73.138.77.126)
  - Reserved IP 73.138.77.0 (network address) and 73.138.77.127 (broadcast address)
- Machine A:
  - Machine A needs to communicate with Machine B
  - Destination can be specific network of Machine B (B1 interface IP + CIDR) or default (all external networks)
  - Destination: B1 interface IP + CIDR (150.52.212.1/18) or default
  - Next hop: R1 interface IP (73.138.77.126)
- Machine A sends packets to R1, which then forwards them toward Machine B.

<img width="989" height="868" alt="level5" src="https://github.com/user-attachments/assets/f545e9a0-0ded-4fbe-82c5-7a4672b88a21" />

Summary
- Hosts require routing tables when communicating across networks
- default routes simplify host configuration
- The next hop is always the closest router interface
- Routers handle inter-network packet forwarding
