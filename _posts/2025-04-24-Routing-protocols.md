---
title: "Open Shortest Path First (OSPF)"
mathjax: true
layout: post
category: media
---

- OSPF is a link state protocol, it make use of the neighbor table, topology table, and routing table.
- works on network layer
- It is suited for large organization with multiple redundant paths between networks
- OSPF is hierarchical, Networks and their connected hosts and routers within an autonomous system are grouped into OSPF areas. 
- Routers within a given area share the same topological database of the networks they serve.
- Routers that can connect to multiple areas are called area border routers
- A backbone (always called Area 0) is created by the collection of border routers.
- Backbone router is only visible to the border routers 
- OSPF routers exchange hello messages, both as a form of a keep-alive packet and in order to acquire neighbors with which to exchange routing information. 
- Neighbors share Link State Advertisement (LSA) updates to build a consistent link state database (LSDB) that represents the network topology of the area
- The router applies an algorithm called shortest path first (SPF) to analyze the LSDB and add least-cost, loop free routes to its routing table.
- OSPF does adjacent layer interaction, meaning each neighbor routers share all the routing information they have.

<h1>Border Gateway Protocol(BGP)</h1>
- BGP is used to route between domains in a mesh internetwork
- BGP is primarily used for routing between autonomous systems.
- An ASN or autonomous system number are allocated by IANA via the various regional registries.
- An AS hides the private networks from the public Internet. 
- BGP works with classless network prefixes called Network Layer Reachability Information (NLRI)
- Path selection is based on multiple metrics, including hop count, weight, local preference, origin, and community. 
- BGP works over TCP on port 179

<h2>Route Selection:</h2>

- Routers use the longest prefix match or the more specific prefix to perform route