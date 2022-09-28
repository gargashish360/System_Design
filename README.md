# System_Design

Important points:
* When designing the system take care about the availability, latency and throughput.
* Hard-core optimization is needed for transfer of data over the network.
* Availability is measured in terms of nines. 99.9% means 3 nines of system availability.
* Try to apply redundancy within the system, if the traffic need to be diverted try to have multiple load balancers and multiple servers to receive the request.
* Caching is important when we want to increase the speed within client-server model.
* Caches can become stale, if they haven't updated properly. So make sure in a way to store them such that user dont see any outdated information.
* LRU policy: You get rid of least recently used data in the cache. This type of data we dont care about much.
* Proxies: Mainly two types, forward proxy and reverse proxy.
* Forward proxy is a kind of server that sits between the clients or set of clients and another server. When the server responds it will give it response back to forward proxy which in turn will respond to the client. In this case the client identity is hidden from the server, for instance the VPN use-case.
* Reverse proxy hides the identity of server from client.
