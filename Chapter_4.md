# Lesson 4: The Life Cycle of An Application and Additional Resources

## 1. What happens automatically in MongoDB that allows for server maintenance without downtime? (Select all that apply.)

A. Failed write operations are retried automatically once by the MongoDB drivers.
```
Retryable writes are one of the great features of MongoDB.
Retryable writes can overcome most temporary hiccups in the cluster and the network.
From a maintenance point of view, they help do a smooth transition from one Primary node to a new Primary node.
```
~~B. MongoDB automatically upgrades itself to the latest available version.~~
```
It is debatable if this would be desirable.
Some users would like it, while other users want to be in control of deciding when minor or major upgrades should be performed.
However, the concept of having redundant nodes gives you much more control on how and when you upgrade the version of MongoDB in your cluster.
```
C. A faulty Primary will be replaced by a new Primary by an automatic election.
```
Elections of a new Primary node are automatic in MongoDB.
There is no need for any administrative action.
```

## 2. What are the recommended steps to do maintenance on a Primary node without downtime? (Select one.)

A. Step down the Primary node and wait for a Secondary node to take over as the new Primary.
```
This is the first step to perform.
```
~~B. Stop the application from interacting with the MongoDB cluster.~~
```
The purpose of having redundant copies of our data and servers is to avoid this in the first place.
```
~~C. Stop all the nodes in the replica set at the same time.~~
```
You only need to stop the node on which you want to do maintenance on.
If the node is the Primary, another member of the replica set will be elected as the new Primary by the remaining majority of nodes.
Bringing down all nodes, or just a majority of them, would prevent the election of a new Primary node that can service the write operations.
```

## 3. Which of the following help achieve a no-downtime schema migration with MongoDB? (Select all that apply.)
A. The polymorphism aspect of having documents with different shapes within a collection.
```
Because documents in the same collection can have different shapes, we can have documents with the original schema and documents with the new schema.
Instead of seeing the migration as an atomic operation, it becomes a continuous process throughout the migration.
```
~~B. Database replication allows us to update one node at the time.~~
```
Database replication allows data synchronization across the different replica members.
Database replication is not used for changing the schema of the documents.
```
C. Each document can carry its schema version number.=
```
Using a schema version to identify the shape of the document is optional. The alternative is to deduce the version of the schema by the differences in the fields.
Both approaches highlight the fact that each document must respect one of the schema versions for our collection.
```

## 4. Which of the following are tools within MongoDB's data platform ecosystem? (Select all that apply.)
A. MongoDB Charts
```
MongoDB Charts is a tool to construct rich visualization with your datasets in MongoDB.
```
~~B. RDMBS server~~
```
Traditional relational database servers are not part of the MongoDB platform. However, you can use their command shell to connect to MongoDB instead of the RDBMS server.
```
C. MongoDB BI Connector
```
MongoDB BI Connector permits you to connect tools using an ODBC connector to connect to MongoDB as the data source.
```
D. MongoDB Compass
```
MongoDB Compass is the native data visualizer and data explorer for MongoDB.
```

## 5. Which of the following is the best definition of High Availability (HA)? (Select one.)
~~A. The replication of the data to other servers~~
```
Replication is one option to achieve high availability. However, it is not high availability itself.
```
B. The capacity to serve operations, even in the event of failures or planned downtime
```
High availability is usually provided by having redundant copies of the data, multiple instances of the software, or additional hardware. This permits a system to operate even if not all components are active.
```
~~C. The ability to scale a cluster~~
```
The ability to scale a cluster is independent of being able to maintain its availability. Sharding a database or adding resources to a server is what permits a cluster to scale.
```

