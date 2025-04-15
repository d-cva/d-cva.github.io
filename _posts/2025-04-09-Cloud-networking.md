---
title: "Cloud Networking"
mathjax: true
layout: post
category: media
---

<h1>Cloud Gateways</h1>
- Each subnet within a VPC can either be private or public.
- To configure a public subnet, first an Internet gateway (virtual router) must be attached to the VPC configuration. 
- The internet gateway must be configured as the default route for each public subnet, if the default gateway is not configured the subnet remains private, even if the Internet gateway is attached with the VPC.
- Each instance in a subnet must also be configured with the public IP in it’s cloud profile. 
- The internet gateway perform 1:1 network address translation (NAT) to route internet communications to and from the instance.

There are other ways to provision external connectivity for a subnet if it is not appropriate to make it public:
- NAT gateway: This establish one way connection towards the public network. NAT allows the VPC to connect to other AWS instances, or to access the internet but it won’t allow the connections from public to the VPC.
- VPN- There are many options for establishing connections to and between the VPC using Virtual Private network at the software layer or using CSP-managed services.


<h2>Cloud Connectivity options</h2>

Cloud connectivity is the way to provide access to the services, application, infrastructure or any platform that is hosted on the cloud. When the software application or any services is hosted or is provided in the cloud the clients are required to access it or to make use of it, the cloud connectivity provides the clients ways of creating these connection and consuming these services.

There are several connectivity scenarios:
- Permitting secure access to the cloud for individual hosts or users.
- Connecting on-premises networks with cloud infrastructure
- Connecting cloud infrastructure established in different geographical regions.
- Creating multi-cloud infrastructure using different cloud providers.

<h2>Internet/virtual private Network</h2>

A virtual private network solution means that the tenatnt configures a VPN gateway for the VPC. Customers can establish a connection to this VPN gateway using either a client-to0-site model or a site-to-site model. A site-to-site model would be used to connect cloud instances to an on-premises network or to another provider’s cloud. Within the cloud, a virtual customer gateway is configured to represent the public IP address and security properties of the on-premises site.

VPNs-based methods have the advantages of being cost-effective and straight forward to setup wherever there is Internet connectivity, which is ideal for organizations that have a fragmented or distributed network structure. However, any connection over the public Internet can suffer from poor performance due to latency and bandwidth throttling, so this would not be normally be a solution for a mission-critical or high-volume application. 

<h2>Direct Connect/Colocation</h2>

Colocation within a datacenter offers a higher bandwidth solution by providing a direct connect or private link. The customer establishes infrastructure within a datacenter supported by the cloud provider or provisions a direct connect link from their enterprise network to the datacenter, possibly using private connections configured within a service provider’s network;. The data center installs a cross-connect cable or VLAN between the customer and the cloud provider, establishing a low-latency, high-bandwidth secure link. This solution is preferred for organizations which have a more centralized operation where the connection to the cloud can be from the main HQ and the company’s own enterprise network is used to allow branch locations access.

<h2>Transit Gateways</h2>

Connectivity can also be configured between VPCs in the same account or with VPCs belonging to different accounts, and between VPCs and on-premises networks. Configuring additional VPCs rather than subnets within a VPC allows for a greater degree of segmentation between instances. A complex network might split segments between different VPCs across different cloud accounts for performance or compliance reasons.

VPCs, can be interconnected using peering relationships and connected with on-premises networks using VPN gateways. These one-toone VPC peering relationships can quickly become difficult to manage, especially if each VPC must interconnect in a mesh-like structure. A transit gateway is a simpler means of managing these interconnections. Essentially, a transit gateway is a virtual router that handles routing between the subnets in each attached VPC and any attached VPN gateways.

<h1>Cloud Firewall Security</h1>

When traffic is routed between subnets, it can be subject to security rules that allow or block connections. These rules can be enforced by a cloud provider’s virtual firewall solution, or the traffic could be routed or switched through a virtual firewall instance, or other security appliance. 

segmentation may be needed for many different reasons, including separating workloads for performance and load balancing, keeping data processing within an isolated segment for compliance with laws and regulations, and compartmentalizing data access and processing for different departments or functional requirements.

Filtering decisions can be made based on packet headers and payload contents at various layers, 

- network layer (layer 3) - The firewall accepts or denies connections on the basis of the IP address, address range or the TCP/UDP port numbers.
- Transport layer (layer 4) - The firewall can store connection states and use rules to allow established or related traffic. 
- Application layer (layer 7) - The firewall can parse application protocol headers and payloads and make filtering decision based on their contents. This requires greater processing capacity.

A cloud firewall can be implemented in several ways to suit different purposes:

- As software running on an instance. This sort of host-based firewall is identical to ones that you would configure for an on-premises host. IT could be a stateful packet filtering firewall or a web application firewall (WAF) with a ruleset tuned to preventing malicious attacks. The drawback is that the software consumes instance resources and so is not very efficient. also, managing the rulesets across many instance can be challenging.
- As a service at the virtualization layer to filter traffic between VPC subnets and instances. This equates to the concept of an on-premise network firewall.

<h2>Security Groups and Security Lists</h2>

In AWS, basic packet filtering rules managing traffic that each instance will accept can be managed through security groups. A security group provides stateful inbound and outbound filtering at layer 4. The stateful filtering property means that it will allow established and related traffic if a new connection has been accepted.

The default security group allows any outbound traffic and any inbound traffic from instances also bound to the default security group. A custom security group sets the ports and endpoints that are allowed for inbound and outbound traffic. There are no deny rules for security groups: any traffic that does not match an allow rule is dropped. Consequently a custom group with no rules will drop all network traffic. Multiple instances can be assigned to the same security group, and instances within the same subnet can be assigned to different security groups. You can assign multiple security groups to the same instance. You can also assign security groups to VPC endpoint interfaces.

Oracle cloud Infrastructure a security list is a set of rules that applies to an entire subnet. An OCI security group is similar to the AWS concept, as it can be applied to selected network interfaces.

<br><br><br>
>Reference: Comptia network plus (certmaster)
