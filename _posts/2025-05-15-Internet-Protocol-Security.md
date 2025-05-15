---
title: "Internet Protocol Security"
layout: post
mathjax: true
category: media
---
<h1>Internet Protocol Security</h1>

IPSec is a collection of communication rules or protocols used to establish secure network connections. IPSec enhances the protocol security by introducing encryption and authentication. The encryption happens at the source and then decryption happens at the destination. 

There are two core protocols in IPSec, depending on the policy:
- Authentication Header (AH): AH in IPSec is a protocol used for authentication and integrity for IP packets, The AH does not encrypt the data but protects the data agains attacks and data modification.
- Encapsulating Security Payload (ESP): Is a core IPsec protocol that provides confidentiality, integrity and origin authentication for IP packets. Can be used to encrypt the payload rather than simply calculating an ICV. ESP attaches three fields to the packet: a header, a trailer and an Integrity Check Value. 

<h2>IPSec can be used in two modes:</h2>

- Transport mode: In transport mode the data payload is encrypted but not the IP headers, encrypted traffic is sent between two nodes, which have pre-established communication. If AH is used in transport mode, it can provide authentication.
- Tunnel mode: This mode is used for communications between VPN gateways across an insecure network. With ESP, the whole IP packet is encrypted and encapsulated as a datagram with a new IP header. AH has no real used case in tunnel mode.

<h1>Internet key Exchange:</h1>

 Internet keys are the methods of validating the devices, data or services with in a network, in an organization keys are used in order to verify communications between two devices, or even to initiate the connections. Whereas IKE is the protocol used to establish the communication and provide to exchange key between two devices over any network. The key Exchange can be done in to ways:

1. Manual Key Exchange: Manual key exchange is a process which is conducted manually by the system administrator. This can be possible in a small organization. 
2. Automated key exchange: Unlike manual automated key exchange is an automated process, where the keys will be created or generated based on demand or requirement. This is mostly used in a larger organization 


There are two phases of Internet Key Exchange (IKE):

<strong>IKE Phase - 1:</strong>  In Phase 1 there will be two devices sender and receiver, at this phase the sender device initiate the communication with the security services such as encryption algorithm, authentication algorithm, hash function, etcs. Then the sender and receiver will form an association with each other and create a ISAKMP tunnel.

<strong>IKE Phase - 2:</strong> After the ISAKMP tunnel has been established in phase 1, the devices move to phase two. Which is very prompt and the devices exchange and negotiate the security associations and services between the devices. The devices will choose which protocol (AH and /or ESP) and which algorithm to use.
