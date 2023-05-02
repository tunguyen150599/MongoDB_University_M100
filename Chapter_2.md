# Lesson 2: Modeling for MongoDB
## Embedded Data
![Embedded Data](https://www.mongodb.com/docs/manual/images/data-model-denormalized.bakedsvg.svg)
## Refferences
![Refferces](https://www.mongodb.com/docs/manual/images/data-model-normalized.bakedsvg.svg)

## 1. Which of the following should you keep in mind when you design a data model with MongoDB? (Select all that apply.)
A. The document model encourages keeping related information together.
```
Deciding if you embed entities or keep the two entities in separate collections is the most critical decision you make while developing your data model with MongoDB. Information that is used together should be kept together in the same document.
```
B. MongoDB supports ACID with the document model and with transactions.
```
Because transactions exist in MongoDB, you can use them when you need to keep consistency between more than one document.
They are an alternative to the ACID property provided by the document model at the single document level.
```
C. MongoDB is a distributed database.
```
As seen in previous lessons, there are many ways you can read and write the data across many nodes.
You may need to choose different durability models for different types of operations.
```
~~D. None of the above.~~

## 2. Which are the three phases of our data modeling methodology? (Select all that apply.)
A. Apply Patterns.
```
This is the third phase of our methodology.
It is similar to denormalizing a schema for a traditional relational model once performance bottlenecks are observed.
Because MongoDB often deals with very large datasets and more demanding workload, it is part of the methodology. In other words, you should not wait after the code is written to apply these transformations.
```
~~B. Draw an Entity-Relationship Diagram.~~
```
Drawing an Entity-Relationship Diagram is an activity that is done when modeling for a traditional relational database.
Doing this activity will establish the relationships between the entities and can be compared to the second phase in our MongoDB methodology.
```
~~C. Write the Application Code.~~
```
Writing application code is not considered a modeling phase.
It will usually happen once you have defined your schema.
```
D. Model the Relationships.
```
This is the second phase of our methodology.
It is similar to the phase of drawing an Entity-Relationship Diagram for a traditional relational database. However, there is a decision between embedding and referencing to make for each relationship.
```
E. Describe the Workload.
```
This is the first phase of our methodology.
This is the phase in which we describe the read and write operations in order to understand which ones are the most important ones when constructing our model.
```

## 3. Which one of the following is the best reason to describe the workload as the first phase of the methodology? (Select one.)

~~A. A solution for a huge amount of data requires an entity relationship diagram.~~
```
Entity Relationship Diagrams are associated with traditional relational databases.
Using them to help you through the steps of modeling for MongoDB is fine, but they are not required.
```

~~B. There is only one solution to data normalization.~~
```
There is usually a single normalized solution with a traditional relational database.
However, with MongoDB, you can have different normalized solutions depending if you choose to embed or reference entities.
```
C. Different workloads could lead to different data model solutions.
```
Because each one-to-many relationship can be modeled by embedding or linking, there are many possible solutions to the problem.
These decisions about embedding or linking data can only be made if you know if the data is used together or not.
```
~~D. Because you want to apply schema design patterns.~~
```
Applying schema design patterns should not a goal by itself, but be a way to achieve an optimal model.
You can assess if you are getting the optimal model by understanding what type of operations the system should handle.
```

## 4. Which of the following would be a qualitative aspect of a write operation? (Select one.)
~~A. The operation happens 1000 times per second.~~
```
1000 is a quantification of the frequency of the operation.
```
~~B. The data written should be destroyed in 1 year.~~
```
1 year is the quantification for how long this data should live in the system.
```
C. The operation requires a durability of "majority." 
```
Here we want to qualify the durability as strong versus a weak durability. No number needs to be attached to this attribute to understand that it is an important write operation.
```
~~D. The operation must be acknowedged back to the client in 10 ms.~~
```
10 ms is the quantification on the maximum expected latency from the client side.
```

## 5. Which of the following criteria influence the choice of embedding instead of referencing a given relationship? (Select all that apply.)
A. The two entities have a one-to-many relationship and are always modified together.
```
An operation that always joins the data between 2 tables is a good sign that the data is used together and that it should be put together in one collection if possible.
```
B. The two entities are always read together.
```
Modifying a few tables in an update statement is a good sign that you want to keep this data together.
Also, by using a single collection to keep these 2 entities together, you can use the ACID property of the document model and avoid using transactions.
```
~~C. One entity can be related to 10 million entities in the second table.~~
```
When a one-to-many relationship has a high cardinality on the many side, it is usually not a good candidate to be embedded as an array into the parent entity.
Unbound arrays may exceed the maximum document size limit and they lead to less performant updates.
```

## 6. The queries on a application are mostly on users. In other words, it user-centric. Each user can have many addresses. The addresses and the user are always read or updated together. How should you model the relationship between the user and the addresses in MongoDB? (Select one.)

~~A. The user document should reference a collection holding the address documents.~~
```
When data is read and written together, prefer embedding to referencing.
```
~~B. The user should be a subdocument in the address document.~~
```
In a relationship between 2 entities, the parent one should be the one on which queries are made. In this case, the application is user-centric, so placing the user information in the addresses would be incorrect.
```
~~C. The address document should reference a collection holding the user document.~~
```
When data is read and written together, prefer embedding to referencing.
```
D. The addresses should be embedded as an array in the user document.
```
The application being user-centric tells us that we should have the user entity as the Primary one.
Next because the data is read and written together, it should be kept together.
There are possibly many addresses per user, so we will need to use an array to represent the addresses within the user entity.
```

## 7. Which of the following are true statements about schema design patterns? (Select all that apply.)
A. They are a common language to understand design intents.
```
Using the names of the common schema design patterns will help you and your team understand each other on how you intend to model some documents and relationships.
```
~~B. They help normalize the data model.~~
```
The main goal of the patterns is to make the model perform better or make it easier for the application to use.
It is likely that you have a normalized model before you start applying patterns on the model.
```
C. They often are denormalizations or transformations to improve performance.

## 8. How are schema design patterns used in modeling for MongoDB? (Select one.)
~~A. They are all applied to all use cases.~~
```
Refer to our matrix in this lesson to see the suggested patterns to potentially apply to a given use case.
```

~~B. They normalize the data model.~~
```
If you stop the modeling phase after the second phase, you will end up with a model that is pretty much normalized.
Applying schema design patterns is likely to denormalize the data, often to have better performance.
```
C. They are applied when needed for a given use case.Your Answer 

## 9. Which of the following can be validated through schema validation in MongoDB? (Select all that apply.)
A. Values are within a set of acceptable values for a given field.
```
This is supported by JSON Schema by using the keyword enum which allows you to list the acceptable values. There are also additional keywords to support ranges or other ways to list values.
```

~~B. Documents in different collections have referential integrity.~~
```
Schema validation is done per document. There is no syntax to link a document to another document that is related to the document under validation.
```
C. Values have the right type for a given field.
```
This is supported by JSON Schema and also easy to specify in a validator written in MongoDB Query Language (MQL).
```
D. A document has either one of two strict shapes.
```
There is a construct in JSON Schema called oneOf that let you specify two sub-schemas.
Use this technique for verifying different shapes of documents, including checking a specific shape for a document version.
```

## 10. Which one of the following actions permits to scale horizontally? (Select one.)
~~A. Move the cluster to Atlas in the Cloud.~~
```
This migration will likely help you reduce the operational costs of running your cluster. However, an Atlas cluster with the same topology as the one you currently use will provide basically the same capacity.
```
~~B. Add more memory to the servers.~~
```
Adding more memory to a server is considered scaling vertically, which is providing additional capacity by using more powerful servers.
```
~~C. Add more disk space.~~
```
Adding more memory to a server is considered scaling vertically, which is providing additional capacity by using more powerful servers.
```
D. Add a shard to the cluster.
```
The definition of scaling horizontally is to use more servers to do the same work.
With more servers and each having a lighter load, you can add load to the cluster. Once the servers are at capacity, you repeat the cycle by adding one or more additional shards.
```
~~E. Add a member in the replica set.~~
```
Adding a member to a replica set will improve the high availability of the cluster. It will not improve the capacity it provides.
```

## 11. Which of the following are ways MongoDB helps keep the integrity of the data? (Select all that apply.)
~~A. Cascading deletes are supported in the MongoDB database server.~~
```
MongoDB does not support cascading deletes for relationships across many documents. It will be up to the application to take care of this integrity concern.
```
B. Change streams can be used to create triggers to implement user-defined integrity checks.
```
Change streams are listeners on all writes to the database.
Use change streams to take action for given writes.
Atlas, the MongoDB database as a service, allows you to store such triggers to mimic stored procedures.
However, if you are not using Atlas, you will need to have an application apply the appropriate actions.
```
C. The document model guarantees referential integrity between parent and child entities.
```
Often data that is stored in many tables in a traditional relational database is kept together in documents in a single collection in MongoDB.
With a single document, deleting it also deletes the child entities that are embedded in it.
Referential integrity across documents must be handled by the application. The application can be notified of checks to perform by using change streams.
```
