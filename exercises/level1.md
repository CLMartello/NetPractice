# Level 1

## Network 1
- Interfaces: A1 and B1
- Subnet Mask: 255.255.255.0
- CIDR: /24
- Given B1 IP = 104.96.23.12

A /24 subnet provides:
- 32 - 24 = 8
- 2^8 = 256
- Range of 0-255
- 256 total IP addresses
- 254 usable host addresses (from 0 - 255)
- .0 reserved for the network address and .255 reserved for the broadcast address

Solution
- Define both devices to the same network, the same mask: 255.255.255.0
- Valid IP range for A1: 104.96.23.1 – 104.96.23.254 (excluding 104.96.23.12)

## Network 2
- Interfaces: C1 and D1
- Subnet Mask: 255.255.0.0
- CIDR: /16
- Given C1 IP = 211.191.6.75

A /16 subnet defines the network using the first two octets.

Solution:
- Define both devices to the same network, the same mask: 255.255.0.0
- Valid IP range for D1 is define by the first two octets 211.191


<img width="994" height="799" alt="level1" src="https://github.com/user-attachments/assets/a57cb8d4-6b7e-485a-84be-d3aba28f2e5f" />


Summary

- Devices within the same network share the same subnet mask.
- IP addresses must belong to the same network range.
- Network and broadcast addresses cannot be assigned to hosts.
