---
title: "Cable Troubleshooting"
mathjax: true
layout: post
categories: media
---
<h1>Cable Troubleshooting</h1>

<h2>Specification and Limitations</h2>

<h2>Speed Versus Throughput</h2>
- at physical layer, a signal transmitted over a communications channel consists of a series of events referred to as symbols. 
- A symbol could be something like a pulse of higher voltage in an electrical current or the transition between the peak and the trough in an electromagnetic wave. The number of symbols that can be transmitted per second is called baud rate and is measured in hertz or MHz or GHz
- At Data Link layer, the nominal bit rate of the link is the amount of information that can be transmitted, measured in bits per seconds(bps)
- In order to transmit information more efficiently, a signaling method might be capable of representing more than one bit per symbol. This also helps to overcome noise and detect errors.
- The use of these encoding methods means that the bit rate will be higher than the baud rate.

<h2>Distance Limitations, Attenuation and interference</h2>

Each type of media can consistently support a given bit rate only over a defined distance. Attenuation and interference enforce distance limitations on different media types.

Attenuation is the loss of signal strenght, expressed in decibels (dB) dB  expresses the ratio between two measurements; in this case, signal strength at origin and signal strength at destination.
Interference: or noise is anything that gets transmitted within or close to the channel that isn’t the intended signal. This serves to make the signal itself difficult to distinguish, causing errors in data and forcing retransmissions. This is expressed as the signal to noise ration(SNR)


<h2>Cable issues</h2>

Troubleshooting cable connectivity is at the physical layer or layer 1:
- network transceiver in the host (end system)
- Patch cable between the host and a wall port.
- Structured cable between the wall port and patch panel
- Patch cable between the patch panel port and a switch port
- Network transceiver in the switch port

While troubleshooting link failure, the first step is to check that the patch cords are properly terminated and connected to the network ports. If the cord is faulty replace the patch cord with a known good cable.

If the cable is not faulty test the transceivers using loopback tool to test for a bad port.

<h2>Cable Category issues</h2>

When troubleshooting a permanent link, the cable type also needs to be verified. 

- Cat 5e supports Gigabit Ethernet but most new installations and upgrades would now use Cat6 or better.
- Cat 6 can support 10 Gbps, but over a 55 m maximum distance
- Cat 6A is an imporved specification cable that can support 10 Gbps over 100m
- Cat 6A is used with Power Over Ethernet (PoE) 802.3bt installation and for horizontal connections to wireless access points.
- Cat7 cable is always of a screened/shielded type and rated for 10Gpbs applications up to 100m. it uses GG45 or TERA connectors rather than RJ45
- Cat 8 is mostly used in datacenters only for short patch cable runs. There are two variants of cat 8:
    - class I: uses RJ45 connectors
    - class II use outer shielding or screening and use GG45 or TERA connector

<h2>Cable Testers:</h2>

- A cable tester reports detailed information on physical and electrical properties of the cable. such as cable conditions, crosstalk, attenuation, noise, resistance.
- The devices classed as certifiers can be used to test and certify cable installation to a performance category.

<h2>Wire Map Testers and Tone Generators:</h2>
wire map tester device can be used to detect improper termination issues. Wire map testers can identify the following problems:
- continuity - a conductor does not form a circuit because of cable damage or because the connector is not properly wired.
- Short- Two conductors are joined at some point, usually because the insulating wire is damaged or a connector is poorly wired.
- Incorrect pin-out/incorrect termination/mismatched standards- The conductors are incorrectly wired into the terminals at one or both ends of the cable
- Reversed pair - The conductors in a pair have been wired to different terminals
- Crossed pair (Tx/Rx transposed)- The conductors from one pair have been connected to pins belonging to different pair 9eg pins 3 and 6 to pins 1 and 2)

Tone generator: are used to trace a cable from one end to the other. This is necessary when a cables are bundled and have not been labeled properly, This device is also known as a fox and Hound.

<h1>Attenuation and Interference Issues</h1>

If a cable link is too long, decible(dB) loss may mean that the link experiences signal degradation problems with high error rates and retransmission resulting in reduced speeds and possibly loss of connectivity. Insertion loss is measured in decibels (dB) and represents the ration of the received voltage to the original voltage.
- higher value represent more insertion loss.

* +3 dB means doubling, while -3 dB means halving.
* +6 dB means quadrupling, while -6 dB relates to a quarter.
* +10 dB means 10 times the ratio, while -10 dB is a tenth.

<h2>Cross talk Issues</h2>

- indicates a problem with bad wiring, a bad connector, or improper termination. 
- Check the cable for excessive untwisting at the ends and for kinks or crush points.
- it is also measured in dB, but unlike insertion loss higher values represent less noise.

<h2>Various types of crosstalk that can be measured:</h2>
- Near End(NEXT): This measures crosstalk on the receive pairs at the transmitter end and is usually caused by excessive untwisting of pairs or faulty bonding of shielded elements.
- Attenuation to Crosstalk Ratio, Near End (ACRN): This is the difference between insertion loss and NEXT. ACR is equivalent to a signal-to noise ration(SNR). A high value means that the signal is stronger than any noise present; a result closer to zero means the link is likely to be subject to high error rates.
- Attenuation-to-crosstalk Ration, Far End (ACRF): Far-end crosstalk (FEXT) is measured on the receive pairs at the recipient end. The difference between insertion loss and FEXT gives ACRF, which measures cable performance regardless of the actual link length.
- Power Sum: Gigabit and 10 GbE Ethernet uses all four pairs. Power sum crosstalk calculations confirm that a cable is suitable for this type of application. They are measured by energizing three of the four pairs in turn.
- Alien Crosstalk: This is signal traffic from cables in close proximity that causes interference to a disturbed or victim cable 


<h2>Fiber Optic Testing tools:</h2>

- Back-reflection or optical return loss: occurs when some light is reflected back down the cable towards the source.
- Ultra Physical Contact(UPC) and Angled Physical Contact(APC) polishing reduce ORL reflections, and reflectance loss values improve from UPC to APC.]
- APC connecters are always colored green and must be connected to APC connectors.

<h2>Visual Fault Locator:</h2>
- if a break is identified in an installed cable, the location of the break can be found using a visual fault locator. 
- They are different models for short and long distances, and they can be supplied with adapters for different types of connector types (ST, SC, or LC). 
- The tools shines visible light down the cable and glows brightly at the point where a cable is broken, excessively bent or improperly spliced.

<h2>Dirty optical cables:</h2>
- dirt, dust or grease in the transmission path will greatly reduce signal strength or block transmission completely.
- connectors must be covered with a dust cap when removed.

<h2>Cable Troubleshooting strategies</h2>

Sometimes a cable can fail. As a network technician’s duty is to troubleshoot the issue and find the root cause. Common issues to network connections include physical damage to the cable, loose connections, interference from other devices and issues with the network adapter or drivers. To identify the issues these strategies can be used:

1. Physical Inspection
    - Check the cable for any visible damage such as cut, kinks, or server bends.
    - Ensure that the connectors are not damaged and securely plugged into the network device and the computer.
2. Reseat the Cable:
    - Unplug the cable from both ends and then plug it back in. Also reseat the adapter if adapter is used. This helps with the loose connection issue.
3. Verify Drivers:
    - If the problem presists, the issues could be the drivers or a physical problem with the network adapter
    - On the clients end verify the required driver is installed for the network adapter.
    - It may also require to update the driver or install the correct driver package on the user computer.


  >Reference: Comptia Network plus (certmaster)

