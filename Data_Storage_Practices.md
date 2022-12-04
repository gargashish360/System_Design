# Database Practices.

* Relational Databases imposes tabular like structure over the data stored.
* There are some very powerful queries that can be performed over relational databases. That's why they are chosen many times over a non-relational database.
* Postgres is a popular relational database.
* SQL helps to perform querying directly into the database, without the need to load data in memory(This add the quickness).
* To select servers start with round robin order, starting from server A, B, C and then D.
* One should use caching strategy over the servers to store the information to process.
* Hash the client name/numbers to some respective server.
* Two reliable hashing strategies are consistent and rendezvous hashing.
* SQL uses ACID transactions:
  --> A: Atomiticity: If a transaction consist of multiple operations like deducting funds from 1 account and putting it into another, than make sure if one   
  suboperation fails they all fail.
  --> C: Consistency: Any transaction in database will abide by all rules in that database. Any future transaction in database will take into account any past transaction.
  --> I: Isolation: Multiple transactions can occur at same time, but they will be executed as if they are put in a queue.
  --> D: Durability: The transaction if happened is quite permanent.
* Creating indexes in a database, helps to make operations fast.
* Key-value store database(A commonly used no-sql database):
    --> Flexible in a way, doesn't have any imposed structure.
    --> Simple.
    --> Ex: DynamoDb, Redis etc.
    --> There are the chances that when system goes down, such database will be removed automatically.
* Specialized storage paradigms:
   --> Blob: Binary large objects. Blob in system design perspective means the arbitary piece of unstructured data. A video file, image file, a large text file. Blob doesn't fit into a SQL database. GCS and S3 are blob storages.
   --> Time-Series Data: Influx, Prometheus.
   --> Graph Database.
   --> Spatial Database: quadtree.
   --> Quadtree: Every node has 0 children nodes or atleast 4 children nodes.
* Key-value stores database is good, as they help to access data very quickly.
* Replication and Sharding:
--> Main database is synced up with replica: Hence in this case the write operation will take fairly long time, as operations are need to be updated both on main database and replica.
--> For instance, if servers are placed in India(Original) and USA(Replica). An Indian user, if updates anything will get its update instantaneously whereas\ replication can be done asynchronously with USA server let's say every 5 min or 10 min etc.
--> Horizontal Scaling: For Ex, having multiple database servers
--> Sharding: Split up the main data into multiple parts, and store each part on the different database server. For Ex, any payment coming from customer whose name start with A-B will store in database server 1, any customer whose name start with C-D will be stored in database server 2 etc.
* We can use hashing to select which shard to use, based on the character no.
