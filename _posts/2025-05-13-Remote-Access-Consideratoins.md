---
title: "Remote Access Considerations"
mathjax: true
layout: post
category: media
---

<h1>Remote Access Considerations</h1>


Remote access means the client device is not directly connected to the host network, here the client network make use of the public WAN (internet) to create the connection to the remote network or host. The process of allowing the connection to particular remote hosts is Virtual Private Network or VPN. 

The remote access policy should implement the measures identified through compiling the documentation, the typical restriction policies can be:
- user or groups level access restriction
- access restriction as per times of day, and or days in a week.
- local network restriction, the remote users are only permitted access to only defined and required part of the network.
- Logging and auditing access logons and attempted logons.

note: The creation of Remote access Server (RAS) is necessary, accompanied by documentation describing the use of the service, security risks and countermeasures and authorized users of the service.

<h2>Tunnelling Protocols</h2>

Most of the remote network solutions use Internet to create a virtual private network (VPN). To establish a VPN connection it requires a protocol that can create a secure tunnel for the client device and the remote network over the public internet. Tunneling means the hosts are in the same logical network but are connected via multiple types of physical network or connection. The protocol used for the tunneling encrypts the data on one end, the packet is then decrypted upon receiving at the other end of the tunnel.

<h2>Type of Protocols:</h2>

<h2>Point-to-point protocol:</h2>

Point to point protocol is an encapsulation protocol that works at the Data Link layer. PPP has no security mechanisms and it must be used with other protocols to provide a secure tunnel.

<h2>Generic Routing Encapsulation:</h2>

Generic Routing Encapsulation (GRE) works at layer 3. This protocol is used to share data between the network nodes. GRE self encapsulate the IP packets the outer GRE packet is assigned protocol number 47. The GRE packet is then itself encapsulated in a layer 2 frame for transmission to the next hop router. GRE doesn’t support authenticating user hence uses or devices and so often VPN solutions are used in conjunction with other protocols.

<h2>IP Security:</h2>

IPSec is the collection of protocol operating at network layer. The IP Sec provides end to end encryption which means, the data is encrypted on one end and is decrypted at the other end where the data has been received. IPSec can used authentications for security.

<h2>Transport layer Security (TSL):</h2>

TLS over TCP or datagram TLS over UDP can be used to encapsulate frames or IP packets. The main drawback is that a TLS already operates at the Session layer.

