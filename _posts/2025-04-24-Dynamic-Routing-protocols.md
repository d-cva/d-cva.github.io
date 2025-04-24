---
title: "Dynamic Routing Protocols"
mathjax: true
layout: post
category: media
---

-uses algorithm and metrics to build and maintain a routing information 

<h2>Topology and metrics</h2>
- category of algorithm
    - distance vector or link state or hybrid of different methods to perform path selection more efficiently
- When the routing database contains more than one route 
    - a metric is calculated to determine which path will be selected for use in the IP routing table.
        - The path with the lowest cost metric is preferred.
    - The type of algorithm determines which factors are used to calculate the metric. 
        - Distance vector protocols use the number of hops to the destination as the metric. 
        - The route with the fewest hops is the least-cost path and will be selected for use.
- Convergence
    - it is the process whereby routers running dynamic routing algorithms agree on the network topology
    - A sinkhole means that a packet is discarded without notification to the source; a loop causes the packet to be forwarded around the network until its TTL expires.

- A network where all the routers share the same topology is described as steady state.

<h2>Autonomous Systems (AS)</h2>

- A network under the administrative control of a single owner is referred to as an autonomous system (AS).
- Interior Gateway Protocol (IGP) is one that identifies routes within as AS.
- An Exterior Gateway Protocol (EGP) is one that can advertise routes between autonomous systems.
- An EGP includes a field to communicate the network’s autonomous system ID and allows network owners to determine whether they can use paths through another organization’s network.

