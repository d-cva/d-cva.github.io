---
title: "High Availability (HA) Clusters"
mathjax: true
layout: post
category: media
---

High Availability (HA) Clusters

<h1>What is a High Availability cluster?</h1>

A cluster is simply a group of servers providing some kind of services. When these servers are grouped in a single group to then these group as a single is known as a cluster. These clusters share the same database, or storage network address. Depending upon the application or the service provided all the computers in the cluster can function same or the same task is assigned to all of the nodes with in the function.

High Availability clusters are the clusters with the function of high availability or less down time. These clusters are designed to share work load between the nodes with in the cluster, when a single node fails or is unable to process the request, the task is automatically assigned to another  node with in the cluster, hence the service is always available.

The High availability clusters also uses the load balancers to ensure the availability of the services and distribute the load to the cluster nodes. In a real environment a virtual IP is used facing external where all the request lands, where the virtual server with the public IP or the virtual IP performs the load balancing, deciding where the traffic should go. 

There can be multiple types and multiple layers of load balancers used in an organization depending upon the application uses, and requirements. These load balancers use Redundancy protocol, such as Common <strong>Address Redundancy protocol (CARP)</strong>, that enables the active node to respond to the requests.  These protocol also uses heartbeat mechanism to allow failover to the passive node if the active one should fail.

Types of High Availability Clusters:

- <h3>Active-Active clustering</h3>: in an active-active cluster all of the nodes are active and function concurrently. When a request comes in depending upon the load any of the cluster or the node will respond to the request connection. In this topology when one node fails the remaining nodes will pick up the task. Active-active cluster provides greater flexibility towards the expansion, as the nodes can be added without interruptions. This is also beneficial as the user would experience faster service all of the nodes are actively function which also provides better through put aiding towards the faster application or service access and distributing the load to all the nodes in the cluster. However, when a node fails and if the auto scaling of the nodes during failure is not an option these cluster can suffer the slowness in through put due to decrease in the nodes, where users can experience slow service.

- <h3>Active-passive clustering:</h3> Unlike active-active architecture where all nodes participate actively, in active-passive topology only a cluster of nodes will be active and a cluster of node remains passive. The nodes with in the active cluster do share the work load and load balancing still remains with in the cluster depending upon the numbers of nodes available in the cluster, however the passive cluster and the nodes with in them remains in active and do not share the tasks of the active nodes. 
	
The nodes in active passive clustering remains in active towards the external request or providing service but that doesn’t mean they remain completely passive as powered off nodes. Nodes in the passive cluster are as a backup resource or a backup cluster hence they will be actively participating internally to backup the resources and should have the data that the active nodes have, and if requires they can provide full functionality as active cluster if the active cluster failed. The backup of the resource depends upon the requirement of the application and the organization. The passive clusters are mostly used as Disaster recover cluster and reside in different geographical regions.


