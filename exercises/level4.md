# Level 4

## Notes
A router connects multiple networks and forwards packets between them. Each network connected to a router must:
- Use its own subnet mask
- Have a non-overlapping IP range

In this level, only Network 1 (N1) needs to be configured. The other networks are already defined and are used to determine which IP ranges are still available.

## R2 Network
- Subnet mask: 255.255.255.128
- CIDR: /25
- 32 - 25 = 7
- 2^7 = 128
- Subnet ranges: 0-127 and 128-255
- Given IP: 107.150.117.1
- Occupied IP range: 0-127

## R3 Network
- Subnet mask: 255.255.255.192
- CIDR: /26
- 32 - 26 = 6
- 2^6 = 64
- Subnet ranges available: 128-191 and 192-255
- Given IP: 107.150.117.244
- Occupied IP range: 192-255

## Network 1
- Interfaces: R1, A1 and B1
- Occupied IP ranges: 0-127 and 192-255
To minimize IP usage, a smaller subnet mask is recommended.
- Chosen subnet mask: 255.255.255.240
- Chosen CIDR: /28
- 32 - 28 = 4
- 2^4 = 16
- 16 total IP addresses
- Subnet ranges available:
```
128-143, 144-159, 160-175 and 176-191
```

Solution
- Given A1 IP = 107.150.117.132
- Subnet range: 128-143
- Valid IP range: 107.150.117.128 - 107.150.117.143 (excluding 107.150.117.132)
- Reserved IP 107.150.117.128 (network address) and 107.150.117.143 (broadcast address)

<img width="859" height="868" alt="level4" src="https://github.com/user-attachments/assets/51357436-1de8-4048-903e-049e3b4cfddf" />

Summary
- Routers connect multiple networks, each requiring a unique subnet
- Existing networks restrict available IP ranges
- A smaller subnet mask helps avoid IP waste
