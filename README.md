# System_Design Fundamentals:

** When designing the system take care about three dimensions:
  --> Availability.
  --> Latency.
  --> Throughput. **
  
"*" Hard-core optimization is needed to transfer data over network.
"*" Availability is measured in terms of nines. 99.9% states 3 nines of system availability.
"*" Redundancy is important in system design, if the traffic need to be diverted try to have multiple load balancers and multiple servers to receive the request.
"*" Caching is important when we want to increase the speed within client-server model.
"*" Cache can become stale, if they haven't updated properly. So make sure in a way to store them such that user dont see any outdated information.
"*" LRU policy: You get rid of least recently used data in the cache. We don't care much about this kind of data.
"*" Proxies: Mainly two types, forward proxy and reverse proxy:
    **Forward proxy:** It is a kind of server that sits between the clients or set of clients and another server. When the server responds it will give it response
     back to forward proxy which in turn will respond to the client. In this case the client identity is hidden from the server, for instance the VPN use-case.
    **Reverse proxy:** It hides the identity of server from client.
"*" There are multiple clients and servers, in order to use the functionality of hashing we can associate 1 client to 1 server, hence it can be acheived through    hashing.
"*" Relational Databases imposes tabular like structure over the data stored.
"*" There are some very powerful queries that can be performed over relational databases. That's why they are chosen many times over a non-relational database.
"*" Postgres is a popular relational database.
"*" SQL helps to perform querying directly into the database, without the need to load data in memory(This add the quickness).
"*" To select servers start with round robin order, starting from server A, B, C and then D.
"*" One should use caching strategy over the servers to store the information to process.
"*" Hash the client name/numbers to some respective server.
"*" Two reliable hashing strategies are consistent and rendezvous hashing.
"*" SQL uses ACID transactions:
  --> A: Atomiticity: If a transaction consist of multiple operations like deducting funds from 1 account and putting it into another, than make sure if one   
  suboperation fails they all fail.
  --> C: Consistency: Any transaction in database will abide by all rules in that database. Any future transaction in database will take into account any past  transaction.
  --> I: Isolation: Multiple transactions can occur at same time, but they will be executed as if they are put in a queue.
  --> D: Durability: The transaction if happened is quite permanent.
  "*" Creating indexes in a database, helps to make operations fast.
  "*" Key-value store database(A commonly used no-sql database):
    --> Flexible in a way, doesn't have any imposed structure.
    --> Simple.
    --> Ex: DynamoDb, Redis etc.
    --> There are the chances that when system goes down, such database will be removed automatically.
 "*" Specialized storage paradigms:
   --> Blob: Binary large objects. Blob in system design perspective means the arbitary piece of unstructured data. A video file, image file, a large text    file. Blob doesn't fit into a SQL database. GCS and S3 are blob storages.
   --> Time-Series Data: Influx, Prometheus.
   --> Graph Database.
   --> Spatial Database: quadtree.
   --> Quadtree: Every node has 0 children nodes or atleast 4 children nodes.
* Key-value stores database is good, as they help to access data very quickly.
* Replication and Sharding:
--> Main database is synced up with replica: Hence in this case the write operation will take fairly long time, as operations are need to be updated both on main database and replica.
--> For instance, if servers are placed in India(Original) and USA(Replica). An indian user, if updates anything will get its update instantaneously whereas replication can be done asynchronously with USA server let's say every 5 min or 10 min etc.
--> Horizontal Scaling: For Ex, having multiple database servers. 
--> Sharding: Split up the main data into multiple parts, and store each part on the different database server. For Ex, any payment coming from customer whose name start with A-B will store in database server 1, any customer whose name start with C-D will be stored in database server 2 etc. 
* We can use hashing to select which shard to use, based on the character no.
* Leader Election: Third-Party Service --> Database: If there are many services, doing the same task, then the leader is selected among them to not repeat the task. 
                   --> Zookeeper and Etcd are two tools, that can be used for leader election(They internally implement consensus algorithm).
                   --> Etcd is a key-value store. It is highly available and strongly consistent. Etcd implement Raft consistent algorithm. It follows the leader,                            follower algorithm to perform the election.
* Peer-To-Peer Networks: Helps to share files fast, like in torrent. Every node is a giver and each one of them is a taker. There is a distributed, which holds the info that what peer holds which information.
Polling and Streaming: This is a technique using which clients are always kept updated of the server values.
Polling: The client issues request for data that it want on recurring basis, following the set interval. For Ex: Every 2 sec etc. For Ex, if client want to get updated of outside temperature every 2 sec that is stored in server.
Streaming: For instance, if we are dealing with messages and want to see the message instantly, in such case polling will not help and we need to use streaming. The client here will open the long-lived connection. Here, the client is streaming data from the server.
Configuration: A configuration is a set of parameters or constants, that our system is going to use. It can be dynamic or static. Dynamic means that changes are reflected instantaneously.

                   
                   
