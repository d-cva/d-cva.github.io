---
title: "Physical Installation Factors"
mathjax: true
layout: post
categories: media
---

<h1>Physical Installation Factors</h1>
<h2>Rack Systems</h2>
- Rack height is measured in “U” units of 1.75”/4.45cm
- Racks are sold in heights from 8U to 48U.
- There should be about 3 feet (1 meter) clearance aisle for service access and airflow.
- Multiple rows should be placed back-to-back not front to back to maximize cooling. This is referred to as a hot aisle/cold aisle layout
- Port-side exhaust, where hot air is expelled on the same side as the port interfaces, and port-side intake.
- Side panels and blanking plates should cover unused rack slots to improve airflow
- lockable doors rack can be installed to prevent unauthorized access to the equipment.

<h2>Humidity and Temperature<h2>

Environmental controls mitigate the loss of availability through mechanical issues with equipment, such as overheating.

The following environmental factors need monitoring:

1. Temperature: High temperature will make it difficult for device and rack cooling systems to dissipate heat effectively. This can increase the chance of overheating the components within the device and consequent faults.
2. Humidity: More water vapor in the air risks condensation forming within a device chassis, leading short circuit. Similarly very low humidity increases risks of static charges building up and damaging components.
3. Electrical: All the systems needs stable power supply, free from outage. In case of voltage dips or spikes the sensors built into power distribution systems and backup battery systems can report the changes.
4. Flooding: During flooding the electric systems needs to auto shutdown immediately.



<h2>Power Management</h2>

All types of networking appliance requires stable power supply to operate. The fluctuation in power supply can cause the devices to fail and also can cause major interruptions.power management means to deploy the systems to ensure the equipments are protected by providing stable power supply, also creating an alert incase of these types of events.

<h1>Power Load and Voltage:</h1>

- The circuits supplying grid power to a rack, network closet, or server room must meet the load capacity of all the installed equipment. 
- The alternating current (AC) circuits to a server room will typically be higher capacity than domestic or office circuits.
- The power supply for each appliance has a wattage rating
- Wattage is calculated as V*current(amps).
- To calculate the maximum load for a rack, add up the watts used by each appliance power supply and divide by the circuit voltage

<h2>Power Distribution Units (PDU)</h2>
- A PDU has circuitry to clean the power signal, provides protection against spikes, surges, and under-voltage events and can also integrate with an uninterruptible power supply (UPS)
- PDUs can also support remote power monitoring functions, such as reporting load and status, switching power to a socket on and off

<h2>Battery Backups and Uninterruptible Power supplies<h2>
- UPS will provide a temporary power source in the event of a power failure

<h2>Fire Suppression</h2>

<h2>Basic elements of fire safety:</h2>
1. wall-marked fire exits and an emergency evacuation procedure tested and practiced regularly.
2. Building design that does not allow fire to spread quickly, by separating different areas with fire resistant walls and doors.
3. Automatic smoke or fire detection systems, as well as fire alarm that can be operated manually.

Fire suppression systems works on the basis of the fire triangle. This works on the principle that a fire requires, heat, oxygen and fuel to ignite and burn Removing one of those elements provides fire suppression.

<h2>Alternative to wet-pip systems:</h2>
Dry-pipe: used in areas where freezing is possible and water only enter this part of the system if sprinklers are triggered somewhere else.
pre-action: this only fills with water when an alarm is triggered. it will spray when the heat rises.
Halon: This is a gas based system, it is useful as the gas doen’t create short circuit. As the gas used in Halon are depleting ozone layer this is banned in many countries.
Clean agent: Aletrnatives to Halon, the gas used in this are non toxic to humans, such as mixure of Co2, aragon and Nitrogen.


>Reference: Comptia Network plus (certmaster)
