---
title: "Fault Tolerance and Redundancy"
mathjax: true
layout: post
category: media
---

<h1>Fault Tolerance and Redundancy</h1>

Switching sites to a disaster recovery site is a very rare incident and only happens when there is a fault in the system. A fault can be defined as an occurrence when the service is interrupted and the service is unavailable for consumption.

<h3>Key Performance indicators (KPIs):</h3> KPI is the quantifiable measurement that determines the reliability of each assets and assess whether goal for MTD, RTO, and RP2025-05-01-O can be met. Main Kpis relating to component reliability are as follows:

- Mean Time between failure (MTBF)
- Mean Time to failure (MTTF)
- Mean time to repair (MTTR)

<h3>Mean time between failure (MTBF):</h3> defines the explicit lifetime of a product. The calculation of MTBF = Total Operational time / number of Failures.
Example:

If a hardware operates for 1000 hours and has 5 failures, the MTBF would be 200 hours (1000 hours / 5 failures).

<h3>Mean time to failure (MTTF) :</h3> MTTF helps an organization to estimate the life span of non-repairable assets. A harddrive or a fan belt in a datacenter can be defined as the non-reparible component. MTTF measures and generate the metric on the expected life span of these components. The formula to calculate MTTF is = Total number of operational time / number of devices.

Imagine you’re calculating MTTF for three desktop hard drives. The first failure occured after 62,000 hours. The second hard drive didn’t last as long, failing after 28,000 hours. Finally, the third hard drive failed after spending 42,000 hours in operation. 
In this instance, your calculations would look this: 
<code>
MTTF = (62,000 + 28,000 + 42,000) / 3 units<br>
MTTF = 132,000 / 3<br>
MTTF = 44,000 hours<br>
</code>
You can now reasonably assume that this particular make and model of hard drive will have a useful life of about 44,000 hours. 

<h3>Mean time to repair (MTTR): </h3> is a measure of the time taken to correct a fault so that the system is restored to full operation. It is a mean time to replace or recover. 

MTTR is calculated as the total number of hours of unplanned maintenance divided by the number of failure incidents. This average time helps to estimate whether a recovery time objective (RTO) is achievable.
