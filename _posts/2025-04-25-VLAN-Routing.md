---
title : "VLAN Routing"
mathjax: true
layout: post
category: media
---
<h1>VLAN Routing</h1>

Many networks are segmented using the VLAN feature of managed switches. Traffic between VLANs must be routed. There are various ways to accomplishing this.


<h2>Methods of VLAN routing:</h2>

<h2>Subinterfaces:</h2>

- layer 2 switch is not able to do the packet routing and a router is required to perform inter vlan routing.
- subinterface method is also known as a one-armed router or router on a stick
- The trunk port carries all the VLAN to VLAN traffic that must be routed
- The routers physical interface is configured with the subinterfaces, each subinterface is configured with the specific VLAN and IP address associated with the VLAN
- The subinterface acts as a default gateway and the router forwards the traffic between the subinterface.

Switch Virtual interfaces:
- Routing the IP packets inbetween requires a router or the switch with the routing capabilities. 
- Switch virtual interfaces can be created in a layer 3 switch.


￼

<h2>Configuration:</h2>


VLAN 16
PC6 -> 192.168.0.2/24
PC7 -> 192.168.0.3/24
PC8 -> 192.168.0.4/24


VLAN 32
PC3 -> 192.168.1.2/24
PC4 -> 192.168.1.3/24
PC5 -> 192.168.1.4/24

Switch (SW1) configuration:
Access VLAN:
FastEthernet 0/1-0/3  VLAN 16
FastEthernet 0/4-0/6  VLAN 32

Trunk VLAN:
GigabitEthernet 0/1 —> VLAN 16, VLAN 32

Router (R1) configuration:

g0/0/0.16  VLAN 16 192.168.0.1
g0/0/0.32 VLAN 32 192.168.1.1

<figure><figurecaption><h3>Subinterface</h3></figurecaption>
<img src="https://d-cva.github.io/assets/img/Subinterface.png" alt="Subinterface">
</figure><br>

<h3>SW1 configuration:</h3<br>
<code>
#vlan 16 <br>
#name tech <br>
#interface range FastEthernet 0/0-3 <br>
#switchport mode access <br>
#swtichport access VLAN 16<br>

#vlan 32 <br>
#name office <br>
#interface range FastEthernet 0/4-6 <br>
#switchport mode access <br>
#switchport access VLAN 32 <br>

#interface GigabitEthernet 0/1 <br>
#switchport mode trunk <br>
#switchport trunk allowed VLAN 16,32<br>

R1 configuration: <br>
#interface g0/0/0.16 <br>
#encapsulation dot1q 16 <br>
#IP address 192.168.0.1 255.255.255.0<br>
#no shut<br>
#interface g 0/0/0.32<br>
#encapsulation dot1q 32 <br>
#IP address 192.168.1.1 255.255.255.0<br>
</code>
<br><br>download the packet tracert lab file: (https://github.com/d-cva/d-cva.github.io/blob/master/assets/labs/vlanrouting-subinterface.pkt)