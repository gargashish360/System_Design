# System_Design

Important points:
* When designing the system take care about the availability, latency and throughput.
* Hard-core optimization is needed for transfer of data over the network.
* Availability is measured in terms of nines. 99.9% means 3 nines of system availability.
* Try to apply redundancy within the system, if the traffic need to be diverted try to have multiple load balancers and multiple servers to receive the request.
* Caching is important when we want to increase the speed within client-server model.
* Caches can become stale, if they haven't updated properly.
