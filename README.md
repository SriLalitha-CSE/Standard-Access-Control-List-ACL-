# Standard Access Control List (ACL) using Cisco Packet Tracer

##  Overview

This project demonstrates the implementation of a **Standard Access Control List (ACL)** in Cisco Packet Tracer. Standard ACLs filter network traffic based only on the **source IP address**, allowing or denying packets before they reach their destination.

This lab helps understand how ACLs improve network security by controlling access between different networks.

---

##  Objectives

- Configure a Standard ACL on a Cisco router.
- Permit or deny traffic based on the source IP address.
- Apply the ACL to a router interface.
- Verify access restrictions using ping.
- Understand the importance of proper ACL placement.

---

## Software Used

- Cisco Packet Tracer

---

##  Network Topology

### Devices Used

- 1 Cisco Router
- 2 Switches
- Multiple PCs
- Copper Straight-Through Cables

The network consists of two LANs connected through a router. A Standard ACL is configured to control communication between the networks.

---

##  Network Addressing

| Network | Example Gateway |
|---------|-----------------|
| 192.168.1.0/24 | 192.168.1.1 |
| 192.168.2.0/24 | 192.168.2.1 |

---

##  Configuration Performed

- Assigned IP addresses to all PCs and router interfaces.
- Enabled router interfaces.
- Created a Standard ACL.
- Configured permit and deny rules based on source IP addresses.
- Applied the ACL to the appropriate router interface.
- Verified connectivity using ping.

---

## Key Commands Used

### Configure Router Interface

```bash
interface fastEthernet 0/0
ip address <IP_Address> <Subnet_Mask>
no shutdown
```

### Create a Numbered Standard ACL

```bash
access-list 10 permit 192.168.1.0 0.0.0.255
access-list 10 deny any
```

### Apply ACL to an Interface

```bash
interface fastEthernet 0/1
ip access-group 10 out
```

### Verify ACL

```bash
show access-lists
```

### Verify Interface Configuration

```bash
show running-config
```

---

##  Verification

After applying the ACL:

- Devices permitted by the ACL successfully communicated.
- Traffic from denied source networks was blocked.
- ACL counters increased as packets matched the configured rules.
- Network access behaved according to the configured policy.

---

## Concepts Learned

- Standard Access Control Lists
- Source IP Address Filtering
- Numbered ACLs
- Permit and Deny Rules
- Wildcard Masks
- Router Interface Configuration
- Inbound and Outbound ACLs
- Network Security Fundamentals

---

## Important Notes

- Standard ACLs filter traffic **only by source IP address**.
- They cannot filter based on destination IP, protocol, or port number.
- Standard ACLs are generally placed **close to the destination** network.

---

##  Repository Contents

- `Standard-ACL.pkt` – Cisco Packet Tracer simulation
- `README.md` – Project documentation

---

##  Future Improvements

- Implement Extended ACLs.
- Configure Named ACLs.
- Restrict Telnet and SSH access using ACLs.
- Combine ACLs with NAT and VLANs.

---
