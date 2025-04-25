---
title: "Virtual LANs"
mathjax: true
category: media
layout:post
---
<h1>Virtual LANs and Subnets</h1>
- VLANs operate at layer 2
- VLAN separates the Broadcast domains
- A broadcast domain is a network segment in which if a device broadcast a packet then all the devices in the same broadcast domain will receive it.
- As the routers block the broadcast traffic, if the broadcast traffic needs to be forwarded to another VLAN or a broadcast domain, interVLAN routing is needed.

<h2>Virtual LAN IDs and Membership</h2>

- <h3>Benefits of VLANS</h3>
    - reduce broadcast traffic
    - VLAN also adds to the security as it isolates the network segment
    - divides the network in more manageable segments
- A node can be assigned to a VLAN by configuring the port interface on the switch with the VLAN ID.
- VLAN ID can be in the range of 1 to 4094
- VLAN ID 1 is default and by default all the interface on the switch is assigned to this VLAN
- Once the VLAN is created and if the two host connected to the same switch are in a different VLAN, the connection to the two host are isolated.
- VLAN database is the list of VLANs configured on a switch


<h2>Types of VLAN tags or ports: </h2>

<h3>Access port:</h3>
- access port is a port connected towards the host
- it is also called as untagged port or host port
- Access port only accepts the traffic from and to single defined port

<h3>Trunk port:</h3>
In a large network or a network with multiple VLANs, where the communication between the VLANs are needed. The trunk port allows the communication between the access VLANS, as the access VLANS are isolated and are unable to communicate with other VLANs.
- Trunk port is also known as tagged port
- Tagged port is used to transport the traffic from one VLAN to another
- Tagged port or trunk port is configured to carry traffic from and to multiple VLANs
- Trunk port only allows the traffic from and to the VLANs allowed in the port

<h2>Types of VLAN:</h2>
<h3>Default VLAN:</h3>

VLAN ID 1 is used as a default VLAN. This cannot be changed. Default VLAN must not be used for the data communications, but can be used only for inter-switch protocol traffic, where necessary. For example, spanning tree traffice would be permitted to run over the default VLAN.

<h3>Native VLAN:</h3>

A native VLAN is a vlan which is used for any traffic that doesn’t have the VLAN tags. When a switch receives an untagged frame over a trunk, it assigns the frame to the native VLAN. 

<h3>Voice VLAN:</h3>
- Voice over Ip transmit voice traffic as data packets
- unlike data traffic the voice traffic is two way communication and requires an uninterrupted bandwidth and low latency
- To achieve an uninterrupted communication a dedicated VLAN can be used for the voice traffic.
- Voice vlan is also called as auxiliary VLAN
- Voice VLAN and the access VLAN can also be assigned to the same interface, this allows the data traffic to be tagged as access and the voice traffic to be tagged as voice VLAN while traversing through the network.

<h3>creating and assigning voice VLAN to interface gigabitEthernet 0/0:</h3>
<code>
#vlan 101 — create a vlan 101 for voice<br>
#name voice — name vlan 101 as voice vlan<br>
#interface gigabitEthernet 0/0<br>
#switchport mode access — switchport mode access<br>
#switchport access vlan 100 — access vlan for data <br>
#switchport voice vlan 101 — access vlan for voice <br>
</code>
note: The above command demonstrates both data and voice configured in the same interface.



<h2>VLAN encapsulation:</h2>

- VLAN encapsulation is a process of adding a VLAN tag to an Ethernet frame to indicate which VLAN the frame belongs to.
- The most common VLAN encapsulation protocol is IEEE 802.1Q also known as dot1q


note: To view the VLANs data base #show vlan 

<h3>VLAN is created from the global configuration mode by using the following command:</h3>

<code> 
#vlan 12 <br>
#name VLAN 2<br>
</code>

To assign the interface to the vlan:
- from the global configuration mode
- select the interface or the range of interface
- change the interface to access or trunk mode
- assign the vlan

<h3>Assign access mode VLAN 12 to interface range fastethernet 0/1 to fastethernet 0/13,  the command below are entered in the global configuration mode, and VLAN 12 is already created:</h3>
<code>
#interface range fastethernet 0/1-13 <br>
#switchport mode access<br>
#swtichport access VLAN 12<br>
</code>

<h3>Assign gigabitEthernet 0/1 trunk mode and allow VLAN 12(commands entered in global configuration mode):</h3>
<code>
#interface gigabitEthernet 0/1<br>
#swithport mode trunk<br>
#switchport trunk allowed vlan 12<br>
</code>

<h3>Assign IP address of 192.168.0.1/24 to VLAN 12 interface (commands entered in global configuration mode):</h3>
<code>
#interface VLAN 12<br>
#IP address 192.168.0.1 255.255.255.0<br>
</code>


>ref: certMaster Network plus