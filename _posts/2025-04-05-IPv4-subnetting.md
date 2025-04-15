---
title: "IP Version 4 Subnetting"
mathjax: true
layout: post
category: media
---
<h1>Clasfull Addressing</h1>
- employed in the 1980s before the use of netmasks to identify the network ID portion of an address 

| Class           | 1<sup>st</sup> Octet                   |  Number of Host     |  Subnet Mask                 |
| --------------- | --------------------------  |  ------------------ | ---------------------------  |
| Class A         | 1- 126                      |  16.7 Million       |  255.0.0.0 (/8)              |
| Class B         | 128 - 191                   |  65 Thousand        |  255.255.0.0 (/16)           |
| Class C         | 192 - 223                   |  254                |  255.255.255.0 (/24)         |
| Class D         | 224.0.0.0 - 239.255.255.255 |                     |  Used for multicasting       |
| Class E         | 240.0.0.0 - 255.255.255.255 |                     | Reserved for experimental use|

<h1>Public vs Private Addressing</h1>

- Public IP address is one that establish a connection with other public IP networks and hosts over Internet
- Private IP IPs can be drawn from the pools of addresses defined in RFC 1918 as non-routable over the Internet:
    - 10.0.0.0 to 10.255.255.255 (Class A private address range)
    - 172.16.0.0 to 172.31.255.255 (Class B private address range)
    - 192.168.0.0 to 192.168.255.255 (Class C private address range)


Any organization use private addresses on its network, as the public Ip is limited and for the hundreds of the machine with in the network each machine cannot be allowed the public IPs. In Network a technology called NAT or network address translation is used.

NAT or network address translation allows to share the single public IP in a private network with multiple devices. Routers are able to perform NAT function. Routers are configured with the NAT function and these routers sit in between the private and public network to establish the connection between the public network for all the devices with in the private network.

Poxy servers fulfills requests for the Internet resources on behalf of clients. the server must be configured with the public IP address towards the external interface.


<h1>Other Reserved Address ranges</h1>

There are two additional classes of IP address (D and E that use the values above 223.255.255.255:
- class D address 224.0.0.0 through 239.255.255.255) are used for multicasting.
- class E address (240.0.0.0 through 255.255.255.255) are reserved for experimental use and testing.

<h2>Loopback Address:</h2>

loop back address are the special address that points to the local host. These address are usesful to test if the TCP/IP is installed on the machine. By default the class 4 network range 127.0.0.1 to 127.255.255.255 is a loopback address and is automatically assigned to the networking devices, which points to self. However, the routers or the networking devices can be assigned a valid IP address as a loopback address as well, these scenarios are used in real time environment to connect to the device for troubleshooting. When the loop back address is assigned a valid IP address the host will process the packet regardless of the physical interface on which it has been received.

<h2>Other:</h2>

There are few other IPv4 address ranges are reserved for special use and are not publicly routable:

- 0.0.0.0/8 This is used as a source address by a client seeking a DHCP lease.
- 255.255.255.255 - used to broadcast to the local network when the local network address is not known.
- 100.64.0.0/10, 192.0.0.0/24. 192.88.99.0/24. 198.18.0.0/15 set aside for a variety of special purpose
- 192.0.2.0/24. 198.51.100.0/24, 203.0.113.0/24 set aside for use in documentation and examples.

<h1>When planning an IPv4 network addressing scheme:</h1>

- The number of IP networks and subnetworks required must be considered.
- The number of hosts per subnet that must be considered.
- The network ID must be from a valid public or a private range (not from the loopback, link local reserved range, multicast range, or reserved/experimental range, for instance).
- The network and/or host IDs cannot be all 1s in binary -this is reserved for broadcasts
- The network and/or host ID cannot be all 0s, in binary; 0 means “this network”
- Each host ID must be unique on the IP network or subnet.
- The network ID must be unique on the Internet or on your internal system of internetwork

When you are performing subnet calculations, try to think in terms of the number of mask bits. IT helps to remember that each power of 2 is double the previous one:

| 2<sup>2</sup>  | 2<sup>3</sup>  |  2<sup>4</sup>  |  2<sup>5</sup>  |  2<sup>6</sup>  |  2<sup>7</sup>  |  2<sup>8</sup>  | 
| -------------- | -------------- |  -------------- |  -------------- |  -------------- |  -------------- |  -------------- |
|       4        |       8        |       16        |        32       |      64         |        128      |        256      |


Also memorize the decimal values for the numbers of bits set to 1 in an octet within a mask:

|       1        |      2         |       3         |        4        |      5          |        6        |        7        |       8         |
| -------------- | -------------- |  -------------- |  -------------- |  -------------- |  -------------- |  -------------- |  -------------- |
|       128      |     192        |       224       |        240      |      248        |        252      |        256      |      255        | 




