# System_Design Fundamentals:

When designing the system take care about three dimensions:
  --> Availability.
  --> Latency.
  --> Throughput.
  
* Hard-core optimization is needed to transfer data over network.
* Availability is measured in terms of nines. 99.9% states 3 nines of system availability.
* Redundancy is important in system design, if the traffic need to be diverted try to have multiple load balancers and multiple servers to receive the request.
* Caching is important when we want to increase the speed within client-server model.
* Cache can become stale, if they haven't updated properly. So make sure in a way to store them such that user dont see any outdated information.
* LRU policy: You get rid of least recently used data in the cache. We don't care much about this kind of data.
* Proxies: Mainly two types, forward proxy and reverse proxy:
    **Forward proxy:** It is a kind of server that sits between the clients or set of clients and another server. When the server responds it will give it response
     back to forward proxy which in turn will respond to the client. In this case the client identity is hidden from the server, for instance the VPN use-case.
    **Reverse proxy:** It hides the identity of server from client.
* There are multiple clients and servers, in order to use the functionality of hashing we can associate 1 client to 1 server, hence it can be acheived through    hashing.
* Leader Election: Third-Party Service
                   --> Database: If there are many services, doing the same task, then the leader is selected among them to not repeat the task.
                   --> Zookeeper and Etcd are two tools, that can be used for leader election(They internally implement consensus algorithm).
                   --> Etcd is a key-value store. It is highly available and strongly consistent. Etcd implement Raft consistent algorithm. It follows the leader,                        follower algorithm to perform the election.
* Peer-To-Peer Networks: Helps to share files fast, like in torrent. Every node is a giver and each one of them is a taker. There is a distributed, which holds the                          info that what peer holds which information.
* Polling and Streaming: This is a technique using which clients are always kept updated of the server values.
* Polling: The client issues request for data that it want on recurring basis, following the set interval. For Ex: Every 2 sec etc. For Ex, if client want to get               updated of outside temperature every 2 sec that is stored in server.
* Streaming: For instance, if we are dealing with messages and want to see the message instantly, in such case polling will not help and we need to use streaming.
             The client here will open the long-lived connection. Here, the client is streaming data from the server.
* Configuration: A configuration is a set of parameters or constants, that our system is going to use. It can be dynamic or static. Dynamic means that changes are                    reflected instantaneously.
* Logging and Monitoring shoule be incprporated to manage the system.

* Publish/Subscribe pattern: Publisher(Server) and subscriber(Client) they communicate with each other via a topic. Server pushes a data to a topic and client
                 access the data from a topic. 
                 * Whenever the publisher publishes the message, it is guarranteed that subscriber will receive it atleast once.
                 * Subscriber send ack to the topic regarding that particular message is received.
                 * Suppose if subscriber looses connection while sending ack. Then same messgase will be delivered again. Hence the concept of Idempotency is very
                   crucial here i.e even if multiple transactions happen values at server side doesn't change.
                 * Google Cloud offers different topics and their storage solution, that have the capability to scale automatically.


                   
