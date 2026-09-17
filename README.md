#  CCNA Lab 07 – Standard & Extended ACLs
This lab introduces Cisco IOS Access Control Lists (ACLs) and demonstrates how to control network traffic using both Standard ACLs and Extended ACLs.


![Cisco](https://img.shields.io/badge/Cisco-IOS-blue)
![Packet Tracer](https://img.shields.io/badge/Cisco-Packet%20Tracer-orange)
![Networking](https://img.shields.io/badge/Topic-ACLs-green)
![Level](https://img.shields.io/badge/Level-Intermediate-red)

---

##  Description

This lab focuses on **Cisco Access Control Lists (ACLs)** and demonstrates how network traffic can be controlled using both **Standard ACLs** and **Extended ACLs**.

The lab covers ACL configuration, wildcard masks, interface application, traffic filtering, verification, and troubleshooting.

---

##  Objectives

By completing this lab, you will learn how to:

- Configure Standard ACLs
- Configure Extended ACLs
- Filter traffic using source IP addresses
- Filter traffic using destination IP addresses
- Filter traffic based on protocols
- Filter traffic based on TCP/UDP ports
- Apply ACLs to router interfaces
- Understand inbound and outbound ACLs
- Understand the implicit deny rule
- Verify ACL configuration
- Troubleshoot ACL problems

---

##  Network Topology

```text
                                       LAN 1                         WAN                         LAN 2

        ┌──── PC1 ────┐
        │ 192.168.10.10│
        │              │
        └──── PC2 ────┤
          192.168.10.20
                │
                │
             ┌──────┐
             │ SW1  │
             └──┬───┘
                │
                │ G0/0
                ▼
             ┌──────┐
             │  R1  │
             └──┬───┘
              G0/1
          10.0.0.1
                │
                │
          10.0.0.2
              G0/1
             ┌──┴───┐
             │  R2  │
             └──┬───┘
              G0/0
                │
             ┌──┴───┐
             │ SW2  │
             └──┬───┘
                │
          ┌─────┴─────┐
          │            │
         PC3          PC4
    192.168.20.10  192.168.20.20



## Key Concepts

### Standard ACL

Standard ACLs primarily filter traffic based on the source IP address.

Example:

```cisco
access-list 10 deny host 192.168.10.10
access-list 10 permit any


