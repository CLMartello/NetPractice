# Level 3

## Notes
A switch connects multiple devices within the same network, meaning all devices share the same subnet and all devices use the same subnet mask.

## Network 1
- Interfaces: A1, B1 and C1 (connected through a switch)
- Subnet Mask: 255.255.255.128
- CIDR: /25

A /25 subnet provides:
- 32- 25 = 7
- 2^7 = 128
- 128 total IP addresses
- 126 usable host addresses
- Subnet ranges:
```
0-127 and 128-255
```
Solution
- Given A2 IP = 104.198.9.125
- Subnet range: 0-127
- Valid IP range: 104.198.9.0 - 104.198.9.127 (excluding 104.198.9.125)
- Reserved IP 104.198.9.0 (network address) and 104.198.9.127 (broadcast address)

<img width="784" height="825" alt="level3" src="https://github.com/user-attachments/assets/590b68df-a971-4bb8-890f-fbd518b7e5aa" />

Summary
- A switch does not create multiple networks
- All connected devices remain in the same subnet
- Network and broadcast addresses cannot be assigned to hosts
