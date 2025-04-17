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
<a href url="https://d-cva.github.io/assets/labs/simple-office-network.pkt">Simple network (lab1) packet tracer file</a>

<h2>Simple Office Network Design</h2>
<h3>Core Router Configuration</h3>
- change host name to R1<br>
- assign IP address to g 0/0/0 interface (internal)<br>
- enable the interface<br>

<code>
#enable   -- enter privilege mode
#configure terminal -- enter global configuration mode<br>
#hostname R1 -- change hostname to R1
#interface g 0/0/0 -- select the interface<br>
#ip address 192.168.10.1 255.255.255.0 -- assign IP address to the interface<br>
#no shutdown -- enable the interface<br>
#do show interface g 0/0/0 -- use do show command to view the interface configuration from the global configuraiton mode.<br>
</code>

<h3>Switch configuration</h3>
- change host name to SW1<br>
- assign VLAN 1 an IP address of 192.168.0.252/24<br>
- enable VLAN<br>
- Verify VLAN is enabled and the IP is assigned<br>

<code>
#enable   -- enter privilege mode
#configure terminal -- enter global configuration mode<br>
#hostname SW1 -- change hostname to SW1<br>
#interface vlan 1 -- select the VLAN interface<br>
#ip address 192.168.0.252 255.255.255.0 -- assign ip address to the vlan<br>
#no shut -- enable vlan <br>
#do sh ip int br -- verify VLAN is enabled and the IP is assigned
</code>

<h3>Wireless Router configuration</h3>
SSID: account_firm1(2g/5g)<br>
wep: 74c46b67d3<br>

guest SSID: account_firm_guest<br>
wep: 74c46c67d4<br>

- DHCP server enabled<br>
- DHCP pool (192.168.0.10 - 192.168.0.50) <br>

<h3>IP address table: </h3>

|  Host         | IP address           | Interface |
| ------------- | -------------------- | --------- |
|  R1           | 192.168.10.1/24      | G 0/0/0   |
| Office_router | 192.168.10.2/24      | Gig 01    |
| SW1           | 192.168.0.252/24     | VLAN 1    |
| Office Printer| 192.168.0.3/24       | ETH0      |
| File-server   | 192.168.0.2/24       | Eth0      |



<h2> Device location and Connection Map Room 1</h3>

| Host              | SW1 interface | 
| ----------------- | ------------- |
| office-printer    | fa 0/10       |
| office-printer    | fa 0/10       |
| fin-01            | fa 0/1        |
| fin-02            | fa 0/6        |
| support-02        | fa 0/2        |
| admin-01          | fa 0/3        |
| fin-02            | fa 0/6        |

<h2> Device location and Connection Map Room 2</h3>

| Host              | SW1 interface | 
| ----------------- | ------------- |
| accounts-04       | fa 0/4        |
| accounts-05       | fa 0/7        |
| accounts-06       | fa 0/8        |
| accounts-07       | fa 0/9        |



<h3>Design summary</h3>

- Assuming the core router is connected directly to the internet on g 0/0/1. <br>
- Internet line goes to the Office router internet port<br>
- Office_router LAN port is connected to SW1<br>
- Office_router functions as the DHCP server<br>
- SW1 is configured with one VLAN (VLAN 1) all the interfaces are in the same VLAN
- All the wired clients are directly connected to the Switch SW1<br>
- All the wireless clients are connected to Office_router<br>
- Wireless is configured with both 2g and 5g channel, with Auto Channel bandwidth wep security enabled<br>
- Guest network is also configured with both 2g and 5g channel, with Auto chaneel bandwidth, wep security enabled<br>
- Printer and File server are configured with static IP address<br>
- All the clients laptops, computers, tables and smartphone are configured to receive IP address from DHCP<br>




