# NetPractice

NetPractice is a networking exercise from 42 School designed to teach and validate core networking concepts through interactive problem-solving. The project progressively introduces IP addressing, subnetting, routing, and packet forwarding using visual network topologies. The goal is to correctly configure IP addresses, subnet masks, and routing tables so that all required hosts can communicate successfully.

## Goal

The goal of this project is to study networking through practical exercises, complete all 10 levels, and understand the core concepts of computer networks. Each exercise is described by level in this repository.

## Core Concepts

1. IPv4 Addressing

An IPv4 address is composed of 4 octets, split into a network part and a host part. IPv4 addresses range from:
```css
0.0.0.0 to 255.255.255.255
```
2. Subnet Masks & CIDR

CIDR (Classless Inter-Domain Routing) defines how many bits belong to the network and how many bits are available for hosts.

Example:
```
255.255.255.192
```
- The value 192 in binary is 11000000
- This means 2 bits are used for the network and 6 bits are available for hosts
```
32 - 6 = 26
```
- CIDR is /26 and subnet mask is 255.255.255.192
- Number of addresses is:
```
2⁶ = 64
```
- Subnet ranges are:
```
0-63, 61-127, 128-191, 192-255
```
- For each subnet range, the first adress is the network address and the last address is the broadcast address, these two addresses cannot be assigned to hosts.
```
0 and 63, 61 and 127, 128 and 191, and 192 and 255
```
3. Networks

A network is a group of interfaces that can communicate directly without a router.
- One physical link means one network
- Each network has one subnet mask
- Different networks must not overlap

4. Point-to-point links

Point-to-point links are direct connections between routers.
- They usually are CIDR /30 or subnet mask 255.255.255.252
- This provides 4 total IP addresses and 2 usable IP addresses (.253 and .254)
- This is ideal for router-to-router links because it avoids wasting IP addresses

5. Routing Tables

A routing table is used to direct traffic across networks.
- Each routing entry contains:
  - A destination network (network address)
  - A subnet mask
  - A next hop (the IP address of the closest router)
- Routers use this information to determine where packets should be forwarded

6. Private IP Addresses

A private IP address is used for internal networks and cannot be accessed directly from the public Internet. Private IP addresses cannot be used for direct Internet routing.

- Common private IP ranges are:
```
10.0.0.0 – 10.255.255.255
172.16.0.0 – 172.31.255.255
192.168.0.0 – 192.168.255.255
```
