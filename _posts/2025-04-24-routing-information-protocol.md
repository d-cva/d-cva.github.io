---
title: "Routing Information Protocol (RIP)"
mathjax: true
layout: post
category: media
---
<h1>Routing Information Protocol (RIP)</h1>
- RIP is a routing protocol that uses hop count as a routing metric to find the best path between the source and the destination network.
- the maximum hop count allowed is 15 
- it is mostly used in small to medium sized network

What is Hop count?
- Hop count is the numbers of router in the path from the source to the destination network.
- The path with the lowest hop count is considered as the best route
- RIP prevents routing loops by limiting the hops allowed in a path
- RIP allows max is 15 hops when there is 16 hops the network is considered as unreachable 

How does RIP works?

- RIP uses distance vector routing to find the routing information. RIP maintains a routing table where the distance to each destination is mentioned. 
- RIP shares the routing tables to its neighbor in an interval of 30 seconds through broadcasting.
- Each router update its routing table accordingly once the routing information has been received.

RIPv1

- does not support authentication of the updated message
- only supports classful routing 

RIPv2 :
- supports authentication of the updated message
- supports classless routing


note: To check the route in cisco router:
	- show ip route

	To check the protocols used in router:
	- show ip protocols

note: To check the route in cisco router:
	- show ip route

	To check the protocols used in router:
	- show ip protocols

<code>
RIP configuration:<br>
Routing protocol configuration:<br>
#router rip<br>
#network 10.10.10.0<br>
#network 172.16.10.0<br>
#version 2<br>
#no auto-summary<br>
</code>

> reference "https://www.geeksforgeeks.org/routing-information-protocol-rip/"