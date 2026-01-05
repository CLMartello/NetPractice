*This project has been created as part of the 42 curriculum by clumertz.*

# NetPractice

## Description

NetPractice is a networking training project from 42 School designed to teach and validate core networking concepts through interactive, level-based exercises. The project progressively introduces IPv4 addressing, subnetting, routing, and packet forwarding using visual network topologies.

The main goal is to correctly configure IP addresses, subnet masks, default gateways, and routing tables so that all required hosts can communicate successfully across multiple networks.

The training is divided into 10 levels, each increasing in complexity and combining previously learned concepts.

## Core Concepts
1. TCP/IP Addressing

TCP/IP is a suite of protocols that allows computers to communicate over networks. Within this model, IP (Internet Protocol) is responsible for addressing and routing packets.

There are two versions of IP used today:
- IPv4
- IPv6

2. IPv4 Addressing

An IPv4 address is composed of 4 octets, split into a network part and a host part. IPv4 addresses range from:
```css
0.0.0.0 to 255.255.255.255
```
Each IP address has two parts:
- Network part → identifies the network
- Host part → identifies the device inside that network

Devices can only communicate directly if they are in the same network.

3. Subnet Masks & CIDR

A subnet mask defines which part of the IP address is the network and which part is the host.

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
4. Networks

A network is a group of interfaces that can communicate directly without a router.
- One physical link means one network
- Each network has one subnet mask
- Different networks must not overlap

5. Default Gateway

The default gateway is the IP address of the router interface that connects a local network to other networks. If a device wants to reach an IP outside its network, it sends the packet to Default Gateway or Router Interface IP.

6. Routers & point-to-point links

A router connects different networks together. Point-to-point links are direct connections between routers. Routers forwards packets between networks, uses a routing table to decide where packets go, and each router interface belongs to one network.
- They usually are CIDR /30 or subnet mask 255.255.255.252
- This provides 4 total IP addresses and 2 usable IP addresses (.253 and .254)
- This is ideal for router-to-router links because it avoids wasting IP addresses

7. Routing Tables

A routing table is the map a router uses to direct traffic across networks.
- Each routing entry contains:
  - A destination network (network address)
  - A subnet mask
  - A next hop (the IP address of the closest router)
- Routers use this information to determine where packets should be forwarded

8. Private IP Addresses

A private IP address is used for internal networks and cannot be accessed directly from the public Internet. Private IP addresses cannot be used for direct Internet routing.

- Common private IP ranges are:
```
10.0.0.0 – 10.255.255.255
172.16.0.0 – 172.31.255.255
192.168.0.0 – 192.168.255.255
```

9. OSI Layers

The OSI model explains how data moves through a network, from hardware to applications. For NetPractice, the most important are:
- Layer 3 (Network): IP addresses, routing
- Layer 2 (Data Link): switches, same network logic

## Instructions

How to Run NetPractice

1. Open the NetPractice training interface provided by 42 (usually via a web interface or index.html).
2. Select a level and analyze the given network topology.
3. Configure:
   - IP addresses
   - Subnet masks (CIDR)
   - Default gateways (for hosts)
   - Routing tables (for routers)
4. Validate the level by checking connectivity between the required hosts.

Exporting Configurations

- Once a level is successfully completed, export its configuration using the interface’s export feature.
- The export generates a configuration file representing the solved level.

## Resources

During this project, the following networking concepts are studied and applied:

- IPv4 addressing
- Subnet masks and CIDR notation
- Network address and broadcast address
- Default gateway
- Routing tables
- Longest prefix match
- Point-to-point links
- Routers and switches
- Private vs public IP addresses
- TCP/IP model
- OSI layers (focus on Layers 2 and 3)

References
- The playlist You Suck at Subnetting by NetworkChuck.
- Computer Networking: A Top-Down Approach — Kurose & Ross

Use of Artificial Intelligence

AI tools were used as a learning assistant to:

- Clarify networking concepts (subnetting, routing, CIDR)
- Review explanations and correct technical inaccuracies
- Improve English clarity and README structure

All configurations, calculations, and final solutions were understood and produced by me.

## Submission details

- 10 configuration files are submitted at the root of the repository, one for each level (Level 1 to Level 10).
- 10 directories are also included, each corresponding to a level and containing a README that explains the solution for that exercise.
