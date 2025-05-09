---
title: "Enterprise Wireless Network"
mathjax: true
layout: post
category: media
---
<h1>Enterprise Wireless Network</h1>

<h2>Infrastructure network Type</h2>

<strong>Service Set Identifier (SSID):</strong> An SSID can be up to 32 bytes in length and for maximum compatibility should only use ASCII letters and digigts plus the hyphen and underscore characters. 

Most sites use the infrastructure network type. An infrastructure topology means that each station is configured to connect to the WLAN via an access point (AP) or the logical star topology. Each client station requires a wireless adapter compativle with the standard supported by the AP. 

<strong>Basic Service Set identifier(BSSID):  </strong> SSID is the wireless identifier that is used by the clients devices and is visible from the client devices. Where as BSSID is the unique identifier for a access point. The BSSID is the Media access number of the Access point.

<strong>Extended Service Set (ESS):</strong> ESS is a group of AP connected together to broadcast the same SSID and security information. 
<strong>Extended SSID (ESSID): </strong>Is the name which is broadcasted by the ESS APs.


<h2>Range and Signal Strength:</h2>

<h3>Received Signal Strength Indicator (RSSI):</h3> IS the strength of the signal from the transmitter as measured at the client end. When measuring RSSI, dBm will be a negative value with values closer to zero representing better performance. -30 dBm is the perfect signal, whereas -65 dBm is good signal, while anything above -80dBm is worst and likely to suffer packet loss or dropped.

<h3>Signal-to-noise ration (SNR):</h3>
SNR calculates the difference between the signal and the background noise. The opposite of the RSSI, the higher the SNR it denotes the higher speed and the better connection. The SNR of 25 or higher is usually recommended. If signal is ‑65 dBm and noise is ‑90 dBm, the SNR is the difference between the two values, expressed in dB (25 dB). If noise is -80 dBm, the SNR is 15 dB and the connection will be much, much worse.

<h2>Wireless surveys and Heat Maps</h2>

Wireless survey is a planning tool to ensure the WLAN delivers acceptable data rates to the supported number of devices in all the physical locations.
Basic service area (BSA): is the area where a single AP is used to provide the Wireless network.
Extended service area (ESA): is the area with the use of multiple APs where the device is able to roam around, and the use of Extended SSID is implemented.

To perform the wireless survey the first step would be to examine the blueprint or the floor plan of the premises, and also identify the devices that can produce radio frequency interference (RFI). And also verify where the network port and power jack is as the APs require these connections. 

The next step would be to create a plan where you will mark the basic service areas and associated APs and booster antennae, the APs and the antenna should cover the dead zones. Dead zones are the physical area where the signal are very low or not reachable, where the packet loss is maximum.

<h2>Wireless Roaming</h2>

An ESA is created by installing multiple APs with the same ESSID. This allows the clients to roam, while the clients are roaming the wireless adapter automatically connects to the closest AP or the AP with the strongest wireless signal. The access points are configured with different channels so that where BSAs overlap there is no interference. 

When the signal start degrading the client checks for another signal with the same ESSID but on the different channels or on a different frequency band, if the signal is strong, it disassociates from the current AP and connects to the new AP. The authentication might be required or can be done automatically depending upon the used security measures. 

<h3>SSID Broadcast and Beacon Frame</h3>

SSID in a WLAN is the name that the wireless connection is given, which is shown in the clients wireless connection list. Clients can select the SSID to connect to the particular wireless network. The SSID can be hidden, if the SSID is hidden the connection in the clients end needs to be done manually.

A beacon Frame is a management frame broadcast by the AP to advertise the WLAN, which contains the SSID/ESSID, the BSSID, supported data rates and signaling, plus encryption/authentication requirements.

<h3>Wireless Distribution System/Repeater</h3>

WDS or the repeater mode is the way to extend the wireless signal where the LAN or the wired connection is not available. While using WDS the APs acts as the receiver and transmitter both. Here the base station can be connected with the cables but the remote stations are not connected to a cabled segments. Remote APs are used as the wireless booster and forwards the traffic from and to the base station.

<h3>Wireless controller:</h3>
Wireless controller is the device used in the enterprise network to control, administer, and monitor multiple APs. In an enterprise network there can be hundreds of APs and managing these individually can be difficult hence the wireless controller allows to manage all these APs from the single console. 


<h3>Other Wireless Network Types:</h3>

Ad hoc Topology: This topology allows the wireless adapter to connect directly with each other. Ad Hoc topology doesn’t require any other medium such as routers or APs to establish the connection, for example two laptops or the computer device can connect to each other only by using the wireless adapter to share the information.

Mesh Topology: wireless mesh network (WMN) is the topology where the devices are able to discover one another and peers forming a Mesh Basic Service Set (MBSS). The stations are able to perform path discover and forwarding between peers using a routing protocols.

Point to Point: Point to point link means the physical and logical connection between two devices.
