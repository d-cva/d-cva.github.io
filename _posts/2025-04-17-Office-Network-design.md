---
title: "Office Network Design and Implementation"
mathjax: true
layout: page
category: media
---
<h1>Office Network Design and Implementation</h1>
<h2>Requirements</h2>
Scenario:
A small accounting firm has just moved into a new office space. The firm employs eight staff members, each requiring access to shared network resources such as a printer, file server, and the internet. The office space is divided into two rooms, and there is a requirement for both wired and wireless connectivity. As the network administrator, your task is to design and implement the network using appropriate Ethernet standards, configure the wireless access points, and ensure all devices are connected and can communicate effectively.

Lab Steps:

1. Identify and list all required network devices (e.g., switches, wireless access points, cables).
2. Draw a network topology diagram showing how devices will be connected.
3. Set up a switch to connect all wired devices using Cat5e or Cat6 Ethernet cables.
4. Install and configure wireless access points to provide wireless coverage throughout the office.
5. Configure DHCP on the router to assign IP addresses automatically to all connected devices.
6. Connect a printer and a file server to the network and ensure they are accessible by all employees.
7. Test network connectivity and ensure that all devices can access the shared resources and the internet.
8. Document the configuration settings for future reference.

Assessment: Verify connectivity by pinging the file server from each employee’s computer and accessing the printer. Ensure that wireless devices can connect to the network with appropriate security settings.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
<a href url="https://d-cva.github.io/assets/img/simple-network.png">Logical Design image</a>
<a href url="https://d-cva.github.io/assets/img/simple-network1.png">Physical Design image</a>

<h2>Simple Office Network Design</h2>
<h3>Core Router Configuration<h3>
- change host name to R1
- assign IP address to g 0/0/0 interface (internal)
- enable the interface
<code>

#enable   -- enter privilege mode
#configure terminal -- enter global configuration mode
#interface g 0/0/0 -- select the interface
#ip address 192.168.10.1 255.255.255.0 -- assign IP address to the interface
#no shutdown -- enable the interface
#do show interface g 0/0/0 -- use do show command to view the interface configuration from the global configuraiton mode.
</code>

