# Level 2

## Network 1
- Interfaces: A1 and B1
- Subnet Mask: 255.255.255.224
- CIDR: /27

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
- Given B1 IP = 192.168.27.222
- Subnet range: 192-223
- Valid IP range: 192.168.27.192 - 192.168.27.223 (excluding 192.168.27.222)
- Reserved IP 192.168.27.192 (network address) and 192.168.27.223 (broadcast address)

## Network 2
- Interfaces: C1 and D1
- Subnet Mask: 255.255.255.252
- CIDR: /30

A /30 subnet provides:
- 32 - 30 = 2
- 2^2 = 4
- 4 total IP addresses
- 2 usable host addresses
- Subnet ranges:
```
0-3, 4-7, 8-11, 12-15, 16-19, ..., 248-251, 252-255
```
- For each range the first (network address) and the last (broadcast address) IPs are reserved
- The two middle IPs are usable

Solution
- Any valid /30 subnet may be used, as long as reserved addresses are avoided.

## Notes 
- The IP block 127.0.0.0/8 is reserved for loopback and cannot be used in network configurations.

<img width="864" height="799" alt="level2" src="https://github.com/user-attachments/assets/74042a12-0711-42e0-a96e-efc23003d369" />


Summary
- /27 subnets divide networks into blocks of 32 IPs
- /30 subnets are ideal for point-to-point connections
- Network and broadcast addresses must never be assigned to hosts
