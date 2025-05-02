---
title: "Load Balancers"
mathjax: true
layout: post
category: media
---

<h1>Load balancers</h1>

The application, service, or the data is hosted or available in a server. The server is connected to a network which then is accessed by the clients in order to consume the service that has been provided by the server. If the server has a very less use case or the amount of the users accessing the service is limited one server is enough to provide the service and the server is able to handle all the request. However when the use of the service increases then one single server may not be able to handle all the incoming request. 

When there is a high volume of the clients accessing the service the server resource starts depleting, resulting slow service or even the hardware itself can crash when the server is unable to handle all the requests. These issues of slow service or the server crash can be resolved by the use of load balancers. 

Load balancers can be a software or a hardware, the load balancer sits in between the clients and the servers network. Load balancer uses the virtual service address, which allows the load balancer to distribute the network loads in multiple servers either manually or the most common way is by using the algorithms. In general load balancer are the network component which allows to distribute the load in multiple server. The load balancer can be used for any type of services that is available in the network.

For instance, let’s take an example of a web site that is hosted on a server. When users starts accessing the web site and using the applications hosted in the site the servers starts to slow down. Now to avoid this there will be multiple server with the same application and a load balancer is added in the network with the virtual address which points tot he web site server. The load balancer will include all of the servers address, and the resource uses in a server as well. When the client request for the site the request initially lands at the load balancer, the load balancer then with its algorithm decides which server with in the network of server should handle this request and start distributing the load to the servers. 

The client is directly not aware of presence of the load balancer.

The benefits of load balancers are but not limited to:

- Service efficiency or fast service
- Facilitate maintenance without disruption of service
- Provides a level of security
- Expansion of the service with out disruption

Types of load balancers:

<h2>Layer 4 switch:</h2> Basic load balancers function as per the IP address, TCP/UDP headers, port numbers, these load balancer function at layer 4 which is the transport layer of the OSI model.

<h2>Layer 7 switch:</h2> also known as the content switch, now as the load balancing needs to be done on the content basis such as video streaming or the data in the applications, the modern load balancing requires application level load balancing. These modern load balancers supports complex logic to make the forwarding decisions. 

On a high level load balancers can be virtual software or a hardware as well.

