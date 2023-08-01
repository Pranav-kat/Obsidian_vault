---
share: true
---

#meetup 
Challenges faced: 
Kubernetes node failure: 100% memory utilization
Services running out due to messages overload
Heavy updates like insert & delete caused spikes in IOPS and CPU

MQTT - Message Queuing Telemetric 

Solution:
fixed thread pool strategy to solve the spring boot app running inside the docker caused pool with very small threads.

Note:
