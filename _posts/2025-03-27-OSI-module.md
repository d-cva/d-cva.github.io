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


<h3>Addressing</h3>
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
