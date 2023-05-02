# Lesson 1: Concepts of RDBMS and MongoDB
![Diagram mapping common relational database terms to the corresponding MongoDB terms](https://university-courses.s3.amazonaws.com/M100/m100-database-terminology.png)

## 1. Which of the following are some of the main features of MongoDB? (Select all that apply.)

~~A. The MongoDB query language is optimized to pull data from many collections at once.~~
```
Pulling data from many collections, like Relational Databases Management Systems do, is inefficient.
MongoDB uses the power of the Document Model to keep information that needs to be retrieved together in the same location.
```

**B. Scalability allows to seamlessly scale across multiple servers to store and process data.**
```
As data volumes and performance requirements grow, you can add more servers instead of upgrading to million-dollar mainframes.
This feature is also great for cloud environments where spreading load across lots of machines is by far the best way to scale.
```

**C. Fault tolerance is natively built into MongoDB by keeping redundant copies of the same data on different servers.**
```
This feature allows the application to stay functional in the event of server or network failures.
It also allows for planning maintenance on any server in the cluster without incurring downtime of the applications.
MongoDB's replication and election processes make the task of maintaining a functional cluster completely automatic.
```

**D. MongoDB lets you move data where you need it, so you can keep data near users.**
```
MongoDB lets you move data to where you need it, so you keep data near users around the globe for fast access.
For example, you can keep data for European users in Europe and keep data for the Asian users on servers in Asia.
Creating and deploying such Global Cluster in Atlas can be done quickly in a matter of a few minutes.
```

## 2. Which are correct statements about NoSQL databases? (Select all that apply.)

~~A. NoSQL database scale better vertically than traditional relational databases.~~
```
Traditional relational databases have always scaled well vertically. 
As a matter of fact, you could often guess correctly that the largest server of an organization ran a database server.
```

**B. NoSQL databases were designed to scale large datasets horizontally.**
```
Scaling large datasets was the primary motivator to create NoSQL databases.
Datasets grew to humongous sizes with the advent of the Web. 
They did not fit anymore into traditional relational databases, so this drove the birth of all kinds of new database products within a few years.
```

**C. Most NoSQL databases have built-in modern features like data redundancy and tolerance to failures.**
```
When NoSQL databases were released, applications were commonly running 24 hours a day and serving customers all over the world.
These applications were built as distributed systems, so NoSQL databases embraced the same concepts in their designs.
```

## 3.Which statements are good descriptions of the Document Model used in MongoDB?

**A. It is similar to maps in Java and dictionaries in Python.**

~~B. It is identical to JSON.~~
```
In examples, documents are often represented in JSON, but under the hood, MongoDB uses BSON which offers more data types and better performance
```

**C. It allows us to model one-to-one and one-to-many relationships.**
```
Use a sub-object to model a one-to-one relationship.
Use an array to model a one-to-many or a many-to-many relationship.
```

## 4. Which of the following set of operations guarantee ACID data integrity? (Select all that apply.)

**A. Modify a field and array in a single document within a MongoDB transaction.**
```
Using a transaction in MongoDB will guarantee ACID of all the changes performed in the transaction.
```

~~B. Modify two documents without using a MongoDB transaction.~~
```
Each document will have its atomic write. However, there is no guarantee that both writes will succeed or fail together. Also, a reader may see one change and not the other one if the operation reads the database right in between the two writes operations.
```

**C. Modify two documents within a MongoDB transaction.**
```
Using a transaction in MongoDB will guarantee ACID of all the changes performed in the transaction.
```

**D. Modify a field and array in a single document without using a transaction.**
```
ACID is guaranteed at the document level.
If you change many fields in a document, regardless if they are scalar values, sub documents, or arrays, all changes will go together in an atomic write.
```

## 5.What are the main reasons distributed systems behave differently than single server systems? (Select all that apply.)

~~A. More servers equate to more downtime.~~
```
From a statistical point of view, the more components a system has, the more failures it will experience.
However, in a replicated distributed system, downtime is not directly correlated to failures.
Even if you have more servers, carefully designing the system allows for far less downtime than a single, non-replicated, server would experience by ensuring every component is replicated and not a single point of failure.
```

**B. Networks are a common point of failure.**
```
Networking connections between individual servers are very reliable these days, but they do fail once in a while, and when designing an application that uses many servers. You need to guard the application against potential failures.
```

**C. Network speed is usually fast, but not instantaneous.**
```
When an application depends on a piece of data being written or read from many servers, it will likely wait for the slowest link. When the latency of an operation is crucial, it is a good idea to locate dependant servers (for example database and application servers) close to each other.
```

## 6.Which one of the following are true about read/write preferences and concerns? (Select all that apply.)


**A. The read concern tells the required durability requested for the read operation.**

~~B. The write concern tells which server to write data to.~~
```
All write operations in MongoDB must be directed to the Primary.
```

**C. The write concern tells the required durability requested for the write operation.**

~~D. The read preference tells the required durability requested for the read operation.~~

**E. The read preference tells which server to read data from.**
```
By default read operations are done on the Primary, however, another common strategy is to use a nearest preference to have a shorter latency for the read operation.
```

## 7. Which of the following terms is used in MongoDB to map the concept of a row in RDBMS? (Select one.)

~~A. field~~
```
A field actually parallels a column in RDBMS.
```

~~B. collection~~
```
A collection actually parallels a table in RDBMS.
```

**C. document**
```
A traditional relational database row contains all the information (values) for a given entity. MongoDB uses a document to store all the values for a given entity as key/value pairs. Also, a document differs from a row as it is often a combination of rows from different tables in the traditional relational model.
```

~~D. row~~
```
A row is not a term used with MongoDB.
```
~~E. key~~
```
A key actually parallels a column name in RDBMS.
```


## 8. Which of the following terms is used in MongoDB to map the concept of a table in RDBMS? (Select one.)

~~A. field~~
```
A field actually parallels a column in RDBMS.
```

**B. collection**
```
A database table contains all the rows (objects) for a given type of entity. MongoDB uses a collection to store all the documents for a given entity. 
However, a collection differs from a table as it is often a combination of tables from the traditional relational model.
```

~~C. document~~
```
A document actually parallels a row in RDBMS.
```

~~D. row~~
```
A row is not a term used with MongoDB.
```

~~E. key~~
```
A key actually parallels a column name in RDBMS.
```
