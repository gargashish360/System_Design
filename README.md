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
* There are multiple clients and servers, in order to use the functionality of hashing we can associate 1 client to 1 server, hence it can be acheived by doing hashing.
* Relational Databases imposes tabular like structure over the data stored.
* There are some very powerful queries that can be performed over relational databases. That's why they are chosen many times over a non-relational database.
* Postgres is a popular relational database.
* SQL helps to perform querying directly into the database, without the need to load data in memory.
* To select servers start with round robin order, starting from server A, B, C and then D.
* One should use caching strategy over the servers to store the information to process.
* Hash the client name/numbers to some respective server.
Two reliable hashing strategies are consistent hashing and rendezvous hashing.
--> Consistent Hashing: If we put servers and clients in a circle, if a server dies or a new server is added only few of them are affected.
* We can also perform multiple hashing in a way that, one server can be located on multiple locations on circle, after passing through multiple hashing functions(Maybe if the server is powerful, it can be placed over multiple locations).
--> Rendezvous hashing: 
* SQL uses ACID transactions:
  --> A: Atomiticity: If a transaction consist of multiple operations like deducting funds from 1 account and putting it into another, than make sure if one suboperation       fails they all fail.
  --> C: Consistency: Any transaction in database will abide by all rules in that database. Any future transaction in database will take into account any past  transaction.
  --> I: Isolation: Multiple transactions can occur at same time, but they will be executed as if they are put in a queue.
  --> D: Durability: The transaction if happened is quite permanent.
  * Creating indexes in a database, helps to make operations fast.
  
