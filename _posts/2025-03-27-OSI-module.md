---
title:  "OSI Module"
mathjax: true
layout: post
categories: media
---
<h1>OSI Module introduction</h1>
- Open Systems Interconnection model <br>
- Breaks the data communication process into discrete layers<br>
- there are devices and protocols working at each layers<br>

<h1>OSI Layers</h1>

| Layers             | Numbers      |    PDU     |
| ---------------    | ------------ | ---------- |
| Physical layer     |  Layer 1     | Bits       |
| Data Link layer    |  Layer 2     | Frames     |
| Network layer      |  Layer 3     | Packets    |
| Transport layer    |  Layer 4     | Segments   |
| Session layer      |  Layer 5     | Data       |
| presentation layer | Layer 6      | Data       |
| Application layer  | Layer 7      | Data       |


<h1>Data Encapsulation and Decapsulation</h1>


<h2>Addressing</h2>
Is a uniques identifier for the network nodes, such as MAC address, IPv4 or IPv6 address. The addressing defines where the data should go. Each OSI model layer have different mechanisms for identifying nodes, and rules for how they can send and receive data.

<h2>Encapsulation</h2>
Encapsulation is the process of packaging the data. Data in the network is encapsulated in each layer, each layer in OSI model have its own method of encapsulating the data and each of these layer adds its own field in a header to whatever the payload data is received from an application or the protocol.


<h3>Same layer interaction:</h3>
In networking the communication is possible by the use of protocols. For one device to communicate with the other it requires the use of same protocols. As the protocols are the set of rules which defines the communication method, helping the network devices to establish how to communicate. 
The communication happening in the same layer by using the same protocol in both devices is known as same layer interaction. 

<h3>Adjacent layer interaction: </h3>
During the process of communication the layer above communicate with the layer just below it, this type of communication is known as adjacent layer interaction.
<h3>Protocol Data Unit (PDU):</h3>
When the data payload is transferred from the layer above to the layer below each layer adds it own information to the header field of the data. When this header information is added to the payload the chunk of the data as a whole including the header information is called Protocol data unit or PDU.

<h2>Decapsulation:</h2>

Once the data payload arrives at the receiving node, the receiving node opens the data packet, each layer checks for its header information confirms, extract the header information and passes it to the layer next layer above it. This process of opening the data is known as decapsulation. Just the opposite of Encapsulation, the decapsulation happens from the bottom layer to the top layer.

<h1>Physical Layer</h1>
<h2>Type of medium</h2>
<h3>cable:</h3>
When the bits of information travels over the cable in the form of electric signal over copper wire or in the form of light over fiber.
<h3>wireless:</h3>
When the information travels as radio signal.

Devices that operate at the physical layer include the following:
- Transceiver: The part of network interface that sends and receives signal over network
- Repeater: A device that amplifies the network signal.
- Hub: A multiport repeater deployed as the central point of connection.
- Media converter: A device that converts one media signal to another.

<h1>Data Link </h1>
Layer 2 in OSI model is also known as Data Link layer. This layer is responsible for transferring the data between the nodes using the same logical segment. Here a segment is one where all the nodes can send and receive traffic to one another using the local address or also called hardware address, the media used to connect the nodes is not required to be similar. The media that the nodes use to connect can be different or the combination of multiple media such as wired and wireless.

The data link layer uses Physical address which is also known as the MAC address or the media access control, which is unique to each devices. Before sending the data out Data Link layer also encapsulate the payload received from the upper layer (network layer). Network layer sends the packet to the data link layer. The data link layer add the control information to the payload in the form of header, the header field includes source and destination hardware address plus a basic error check to test if the frame was received fully. Once the payload has been encapsulated by data link layer the payload is known as frames and this will be passed to the next layer just below the data link, which is the physical layer where this information will be converted into the electrical signal or the wireless signal depending upon the physical media.

Devices that operates at this layer:
- network adapteors or Network interface card
- Bridges
- Switches
- Wireless accesspoint (AP)

<h1>Network layer</h1>  
NEtwork is Layer 3 in OSI model. This layer is responsible for moving data around multiple networks, known as internetwork. As data link uses the physical address to forward the data, this layer uses the network or the logical address and hostID to move the data with in the network. The networks are often different and can use different physical layer media to connect the network and also different protocols can be used. In general routers are the device which work at this layer.

In this layer each packet is given the destination network address. The routers are configured with the network address and how to reach these network which are called routing table. As per these information the routers forward the packet to the other routers, the process of forwarding the packets from one router to another router is called hops. Once the packet arrives at the destination network the packet is then forwarded to the target node.
The PDU at this layer is called packets. When the payload is received from the upper layer (transport layer) Network layer encapsulates the payload with the source and destination logical address at the header.

It is usually important for the traffic passing between the networks to be filtered. A basic firewall operates at layer 3 to enforce an access control list or ACL. The ACL is the list of address and types of filters that defines how the traffic will be addressed allowed, denied or discarded.

<h1>Transport layer</h1>
Transport layer is also known as the end-to-end or host-to-host layer. One function of the transport layer is to identify each type of network application by assigning it a port number. The network layer identifies the network ids and ensures the packets gets to the correct host, similarly one host might have multiple services or application running, such as the web server or web browsers, email servers. The transport layer assigns port numbers to each of these services and applications. For example the http request sent to the web server will have port 80 and the email server will have port 25.

At Transport layer the payload or the data received from the upper layer will be encapsulated with the port number information and once encapsulated the payload at this layer is called segment. The segment is then passed over to the network layer for delivery. The network and data link layer ignore the port information and encapsulate the payload with their relative header information send the PDU. 

Once the payload has arrived at the receiving host. The decapsulation starts where the data-link decapsulates, passes over to the network layer and finally to the transport layer. The transport layer checks for the destination port number and forwards the payload to the relevant handler at the application layer.

Transport layer can also implement reliable data delivery method, where if the data is lost or is corrupted the data will be resent.

Devices working at this layer include:

- multilayer switch
- IDS (intrusion detection systems)
- advance firewall devices
- security devices
- load balancer devices

<h1>Upper Layers</h1>
the upper layer session, presentation and application layers are associated with the distinct real-world protocols. These layers collect various information as required by the software applications and the provided by the lower layer. 

<h2>Layer 5 - session:</h2>

In real-world the applications require to exchange multiple messages between the hosts, or the server and the clients. The messages are exchanged in sequences, the sequence of exchanging the messages is called session or dialog. Session layer establish this dialog session maintaining the data transfer or exchange and upon completion session layer destroys this concurrent session with the hosts. 

<h1>Layer 6 - Presentation:</h1>

Presentation layer is the sixth layer in OSI model and mostly involves with the data. As the data to this point can be in different formats that are required as per multiple protocols. The main function of this layer is to assemble the payload data as per the requirement of the application layer. This layer translates the data that the application layer understands such as data unicode. Data encryption, data formatting, data compression are the functions of this layer.

<h1>layer 7 - Application:</h1>

Application layer doesn’t encapsulate or decapsulate the data or provide any service to the protocols. Application layer provides an interface to the software application on the network hosts that have established communication channels through lower-level protocols to exchange data.




