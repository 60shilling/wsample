---
id: 4AAOkMLDzT5ix27M4M9sV
title: Iptables
desc: ''
updated: 1631313795419
created: 1631313795419
---


..a schema of commands for tweaking netfilter - the linux kernel packet filtering software.
## 5 Tables: 
- FILTER: the default, and primary table for end user packet filtering. If a rule does not specify a table then this one is assumed.
- NAT
- MANGLE: modifies IP headers
- RAW: connection tracking thru pkt sequence
- SECURITY: SELinux tagging.
asldkf

## 5 Chains 
- PRE-ROUTING: prior to any routing decision
- INPUT: pkt enters network stack
- FORWARD: pkts routed thru' server
- OUTPUT: pkts originated on this system
- POST-ROUTING: prior to going on wire

table |chain
------- | -------
 |  FILTER| input, forward, output
 |  MANGLE| pre, input, forward, output, post
 |  NAT| pre, output, post
 |  RAW| pre, output
 |  SECURITY| as filter
 

## traversal order 
- incoming pckts destined for local system: **prerouting** -> **input**
- incoming and destined for another host: **prerouting** -> **forward** -> **postrouting**
- locally generated pckts: **ouput** -> **postrouting**



 
 
