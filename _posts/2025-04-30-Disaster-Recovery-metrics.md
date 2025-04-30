---
title : "Disaster Recovery metrics"
mathjax: true
layout: post
category: media
---

<h1>Disaster Recovery metrics:</h1>

Disaster recovery planning is governed by a variety of metrics that express how reliable services are and how long it takes to recover from critical events.

High availability is a characteristic of a system that can guarantee a certain level of availability.

Maximum tolerable Downtime(MTD) metric states the requirement for a business function. Downtime is calculated from the sum of scheduled service intervals (Agreed service Time) plus unplanned outages over the period. High availability might be implemented as 24X7 or 24 X 365. For critical system, availability will be described as two nines (99%) or up to five-or-six nines(99.9999%)

MTD sets the upper limit on the amount of recovery time that system should be recovered. The additional metrics can be used to govern recovery operations:

- Recovery time objective (RTO): This is the period following a disaster that an individual IT system may remain offline. This is the maximum time allowed to identify and perform recovery.
- Work recovery time (WRT): This is the time after the system recovery after the RTO, until the systems are fully recovered and started providing service. There can be multiple factors such as testing overall functionality, restore all backups.


Note: RTO+WRT must not exceed MTD

Recovery Point objective (RPO): Is the amount of data loss that a system can sustain, measure in time units. Example: if the database is destroyed and RPO of 24 hours means that the data can be recovered from a backup copy to a point not more than 24 hours before the database was destroyed.

