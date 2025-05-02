---
title: First Hop Redundancy"
mathjax: true
layout: post
category: media
---
<h1>First Hop Redundancy</h1>

In any type of network, alternative network can be established to bypass a failed router or a faulty connection. Most of the end user systems accept single default user gateway, however some of the systems do accept multiple or alternative route to be configured. While it is possible to configure multiple default gateway it may not be the best alternative to resolve the route issue. 

The issue of alternative route if a router device fails can be resolved by the First Hop Redundancy protocol (FHRP). 

There are many first hop redundancy protocols, such as:

- Hot Standby Router Protocol
- Virtual Router Redundancy Protocol
- Gateway Load Balancing Protocol

Hot Standby Router Protocol: This is the protocol developed by Cisco. Hot Standby Router Protocol is a group of router sharing the common virtual IP and common Mac address for one interface. These routers are known as standby routers. Here, one interface of each router is configured with unique IP address in the same subnet with its own mac address, and one interface of each router is configured with same virtual IP address and same mac address. Using Hot Standby Router Protocol, when the active router fails the stand by router automatically becomes active. The stand by routers are set by the priority configured by the administrator.

The routes with in the group using HSRP use multicast address to create internal communication and the passive routers in this group monitors the status of the active router and when the active router becomes unavailable the passive router becomes active.

Virtual Router Redundancy Protocol: The Virtual Router Redundancy Protocol and Hot Standby Router Protocol are very similar how they function, the difference would be the terminology and the packet formats. As in HSRP there will be a stand by router, but in VRRP there won’t be a stand by router but these routers are called backup routers. 

In VRRP there will be a master router as a main router and a group of backup router, they all share the same virtual address. Unlink HSRP there is not a presence of the stand by router but all the backup router will monitor the master router and when the master router fails the backup router becomes an active router. In these backup routers priorities can be defined to set which router to become an active router if the master to fail.

One advantage of VRRP over HSRP is VRRP doesn’t require each of the interface to assign unique IP address. It is possible to configure VRRP routers to use only the virtual IP address. 