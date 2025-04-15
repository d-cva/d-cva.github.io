---
title: "IPv4 Troubleshooting Tools"
mathjax: true
layout: post
category: media
---

<h1>ipconfig</h1>
ipconfig is the command used in windows operating systems to view the ip configuration. ipconfig is also used to troubleshoot issues related to automatically assignedipconfiguration.
There are many use cases where ipconfig can be used to troubleshoot, which can also be views using ipconfig --help using a command prompt in windows operating systems. The following table
displays the few of them:

| Command                          | Description                                                                           |
| ---------------------------      | ------------------------------------------------------------------------------------- |
| ipconfig                         | Display the IP address, subnet mask, default gateway, for all network interfaces to which TCP/IP is bound|
| ipconfig /all                    | Displays complete TCP/IP configuraiton parameters for each interface, including DHCP information and MAC address |
| ipconfig /renew                  | Forces the DHCP client to renew the lease it has for the IP address                          |
| ipconfig /release                | Releases the IP address obtained from a DHCP server                                          |
| ipconfig /displaydns             | Displays dns resolver cache    |
| ipconfig /flushdns               |  Clears the DNS resolver cache  |
| ipconfig /registerdns            | 	Resisters the host with a DNS server |


<h1>ifconfig and ip</h1>


ifconfig is a part of legacy net-tools package and is deprecated on most of the linux systems. ifconfig can still be used to report the network interface configuration.

net-tools has been replace by the iproute2 package. 

<h2>basic ip commands</h2>

ip addr show (ip a s) -> displays the ip addresses for all the interface in the network
ip addr show dev eth0 (ip a s eth0) -> displays the ip configuration for the device eth0
ip link -> displays the status of the interface
ip -s link -> reports interface statistics
ip link set eth0 up|down -> can enable or disable the interface status
ip addr add|delete -> add ip address or delete IP address from the interface

all these commands are not presistent and apply only to the running configuration and will be removed after reboot.

ip r -> displays the ip routes
ip route add {network} via {ipaddress} -> add ip route

<h2>arp</h2>

The address resolution protocol is used by the host to determine which MAC address is associated with an IP address on the local network. 
- ARP queries are sent as broadcasts and can generate considerable traffic on a network, which can reduce performance.
- ARP broadcast are cached in an ARP table, the entry is used within the timeout period, the entry is held in the cache for a few minues before it is deleted.

- arp -a or arp -g shows the ARP cache contents
- arp -s IPAddress MACAddress adds an entry to the ARP cache. Under windows MACAddress needs to be entered with hyphens between each hex byte.
- arp -f * deletes all entry in the ARP cache; can also be used with IPAddress to delete a single entry.

in linux, the ip neigh command shows entries in the local ARP cache

<h2>ping</h2>
- Internet control message protocol (ICMP) is used to report errors and send messages about the delivery of a packet. 
- ICMP can also be used to test and troubleshoot the connectivity issues on IP network. 
- The ping command sends a configurable number of size of ICMP request packets to a destination host. 
- ping can be used to test basic connectivity test that is not dependent on the target host running higher level applications or services.
- ping IPAddress (IPv4, IPv6) displays basic connectivity

TTL or the time to live ip header field is reduced by one every time a packet is forwarded by a router (referred to as hop). The TTL output field in the ping command shows the value of the counter when the packet arrived at its destination.

If the ping are unseuccessful, 
- destination host unreacheable -> There is no routing information. This might be cause by some sort of configuraiton error on the local host, incorrect default gateway, loss of connectivity with a router, or by routing configuration error.
- No reply (Request Time out) - The host is unavailable or cannot route a reply to your computer. Request time out when the RRL is reduced to 0 because the packet is looping, when congestion causes delays, or when a host doesn’t respond.

<h3>Ping switches</h3>
- ping can be used with the ip address or the host name or fully qualified domain name
- ping can be used to force the ipv4 or IPv6 host record by using the switch -4 or -6
- ping can be used by -t switch to ping the host until interrupted


>reference: comptia network plus (certmaster)

