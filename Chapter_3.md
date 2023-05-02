# Lesson 3: Code and Queries
## Let's compare MQL (MongoDB Query Language) to SQL (Structured Query Language)
#### Take a look at these documents
[SQL to MongoDB Mapping Chart](https://www.mongodb.com/docs/manual/reference/sql-comparison/?_ga=2.73561882.903372275.1683016034-1951862507.1680629634&_gac=1.52886874.1680954539.Cj0KCQjwocShBhCOARIsAFVYq0hFLe-H9Q50iQBJKZ3F-M7QNi208GHhVQsDNIsbrh-65A1I4q47QK8aAidVEALw_wcB)
[SQL to Aggregation Mapping Chart](https://www.mongodb.com/docs/manual/reference/sql-aggregation-comparison/?_ga=2.73561882.903372275.1683016034-1951862507.1680629634&_gac=1.52886874.1680954539.Cj0KCQjwocShBhCOARIsAFVYq0hFLe-H9Q50iQBJKZ3F-M7QNi208GHhVQsDNIsbrh-65A1I4q47QK8aAidVEALw_wcB#sql-to-aggregation-mapping-chart)
#### After that, let's save this valuable Cheet Sheet
[MongoDB Cheat Sheet](https://www.mongodb.com/developer/products/mongodb/cheat-sheet/)

## 1. How are nested SQL queries interpreted to understand the query logic? (Select one.)

~~A. bottom-to-top~~
```
A SQL SELECT statement is not processed from bottom-to-top. They are processed from innermost nested query to the outermost nested query, or more simply from inside-out.
```
~~B. outer-to-inner~~
```
A SQL SELECT statement is not processed from the outer-to-inner. They are processed from innermost nested query to the outermost nested query, or more simply from inside-out.
```
~~C. top-to-bottom~~
```
A SQL SELECT statement is not processed from top-to-bottom. They are processed from innermost nested query to the outermost nested query, or more simply from inside-out.
A MongoDB Aggregation Pipeline is interpreted from the top-to-bottom as each stage impacts the following stage.
```
D. inside-out
```
A SQL SELECT statement needs to be interpreted from the inside-out to understand the logic of the query.
This contrasts with MongoDB Aggregation Pipelines which are interpreted from the top-to-bottom as each stage impacts the following stage.
```
## 2. How are MongoDB Aggregation Pipelines interpreted to understand the query logic? (Select one.)
~~A. inside-out~~
```
MongoDB Aggregation Pipelines are not interpreted from the inside-out, rather they are interpreted top-to-bottom stage by stage.
```
~~B. bottom-to-top~~
```
MongoDB Aggregation Pipelines are not interpreted from the bottom-to-top, rather they are interpreted top-to-bottom stage by stage.
```
~~C. outer-to-inner~~
```
MongoDB Aggregation Pipelines are not interpreted from the outer-to-inner, rather they are interpreted top-to-bottom stage by stage.
```
D. top-to-bottom
```
As MongoDB Aggregation Pipelines need to be interpreted from the top-to-bottom as each stage impacts the following stage. You need to be aware of all of the stages to understand the complete logic of the query.
```
## 3. Which of the following are available query languages in MongoDB? (Select all that apply.)
A. MongoDB Query Language (MQL)
```
MongoDB provides the MongoDB Query Language (MQL) as a query language and it also provides the MongoDB Aggregation Framework as a query language.
```
B. MongoDB Aggregation Framework
```
MongoDB provides the MongoDB Aggregation Framework as a query language and it also provides the MongoDB Query Language (MQL) as a query language.
```
~~C. MongoDB MongoShell~~
```
The MongoDB shell is a tool you can use to write queries in either query languages it supports, the MongoDB Query Language (MQL) and the MongoDB Aggregation Framework.
```
~~D. Structure Query Language (SQL)~~
```
MongoDB provides two query languages, the MongoDB Query Language (MQL) and the MongoDB Aggregation Framework.
```

## 4. Which are valid statements for SQL queries and for Aggregation queries? (Select all that apply.)
A. MongoDB Aggregations uses sequential stages.
```
MongoDB Aggregations use sequential stages for queries.
```
~~B. SQL uses sequential statements without nesting.~~
```
SQL does not use sequential statements without nesting. Rather it uses nested statements for queries.
```
~~C. MongoDB Aggregations use nested stages.~~
```
MongoDB Aggregations queries do not use nested stages. They rather use sequential stages for queries.
```
D. SQL uses nested statements.
```
SQL uses nested statements for queries. 
```
## 5. Which function in MQL is equivalent to the SELECT statement in SQL? (Select one.)
~~A. count~~
```
The COUNT function in SQL and either the $count aggregation stage or the count() function in MongoDB are equivalent. They are not however equivalent to SQL's SELECT.
```
B. find
```
A traditional relational database uses the SELECT statement to query a table or groups of tables.
MongoDB uses the find method to query a collection, it's functionality equivalent to SQL's SELECT.
```
~~C. project~~
```
The $project aggregation stage is not equivalent to SQL's SELECT. SQL does not have an explicit projection function as it is entirely implicit within a SQL SELECT statement.
```
~~D. query~~
```
'query' is not a valid function in either MongoDB or in SQL.
```
~~E. limit~~
```
The LIMIT function in SQL and either the $limit aggregation stage or the limit() function in MongoDB are equivalent. They are not however equivalent to SQL's SELECT.
```

## 6. Which of the following functions exist both in SQL and MQL for queries? (Select all that apply.)
A. limit
```
Both query languages offer this function.
```
B. skip
```
Both query languages offer this function.
```
C. count
```
Both query languages offer this function.
```

## 7. Which function in MongoDB Query Language (MQL) is equivalent to the less than (<) operator in SQL? (Select one.)
~~A. <~~
```
< is not a valid function or operator in MongoDB. $lt is the MQL equivalent to the < (less than) operator in SQL.
```
B. $lt
```
$lt is the MQL equivalent to the < (less than) operator in SQL.
```
~~C. $lessthan~~
```
$lessthan is not a valid function or operator in MongoDB. $lt is the MQL equivalent to the < (less than) operator in SQL.
```

## 8. Which function in MongoDB Query Language (MQL) is equivalent to the ORDER BY operator in SQL? (Select one.)
~~A. order by~~
```
ORDER BY does not exist in MQL. The equivalent to this SQL operator is sort in MQL.
```
~~B. order~~
```
ORDER does not exist in MQL. The equivalent to this SQL operator is sort in MQL.
```
C. sort
```
sort() is the MQL equivalent to the ORDER BY operator in SQL.
```

## 9. Which stage in the MongoDB Aggregation Framework is equivalent to WHERE clause in SQL's SELECT statement? (Select one.)
A. match
```The $match stage of MongoDB's Aggregation Framework provides functionality that is equivalent to the WHERE clause in a SQL SELECT statement.
```
~~B. limit~~
```
The $limit stage of MongoDB's Aggregation Framework provides functionality that is equivalent to the LIMIT clause in a SQL SELECT statement.
```
~~C. count~~
```
The $count stage of MongoDB's Aggregation Framework provides functionality that is equivalent to the COUNT function in a SQL SELECT statement.
```

## 10. Which stage in the MongoDB Aggregation Framework is equivalent to the ORDER BY function in SQL's SELECT statement? (Select one.)

~~A. count~~
```
The $count stage of MongoDB's Aggregation Framework provides functionality that is equivalent to the COUNT function in a SQL SELECT statement.
```
B. sort
```
The $sort stage of MongoDB's Aggregation Framework provides functionality that is equivalent to the ORDER BY clause in a SQL SELECT statement.
```
~~C. limit~~
```
The $limit stage of MongoDB's Aggregation Framework provides functionality that is equivalent to the LIMIT clause in a SQL SELECT statement.
```
~~D. order by~~
```
order by is a keyword only available in SQL. MongoDB uses $sort to perform the same function in the aggregation framework.
```

## 11. Which stage in the MongoDB Aggregation Framework is equivalent to the LIMIT clause in SQL's SELECT statement? (Select one.)

A. limit
```
The $limit stage of MongoDB's Aggregation Framework provides functionality that is equivalent to the LIMIT clause in a SQL SELECT statement.
```
~~B. count~~
```
The $count stage of MongoDB's Aggregation Framework provides functionality that is equivalent to the COUNT function in a SQL SELECT statement.
```
~~C. where~~
```
MongoDB's Aggregation Framework combines SELECT and WHERE into the $match stage. The arguments to the WHERE clause are passed as a query operators in a JSON document to the $match stage.
```

## 12. Select the MongoDB Aggregation Framework pipeline that is equivalent to the following SQL statement:
## 'SELECT * FROM people WHERE status = "A" OR age = 50' (Select one.)

A. db.people.aggregate([ { $match: { $or: [ { status: { $eq: "A" } }, { age: { $eq: 50 } } ] } } ])
```
The $match stage of MongoDB's Aggregation Framework provides functionality that is equivalent to the WHERE clause in a SQL SELECT statement.
The $or operator provides the functionality of the OR operator in a SQL SELECT statement.
```
~~B. db.people.aggregate([ { $match: { $and: [ { status: { $eq: "A" } }, { age: { $eq: 50 } } ] } } ])~~
```
The $and operator of MongoDB's Aggregation Framework provides functionality that is not equivalent to the comparison operator (OR) operator in the a SQL SELECT statement.
```
~~C. db.people.aggregate([ { $where: { $or: [ { status: { $eq: "A" } }, { age: { $eq: 50 } } ] } } ])~~
```
The $where operator of MongoDB's Aggregation Framework matches documents that satisfy a JavaScript expression. The rest of the query is not a complete JavaScript expression.
```

## 13. Which are the following highlight the impact of an Object Mapper on a database? (Select all that apply.)

A. In a relational database, it gathers data from multiple tables by performing joins to create the object. 
```
An Object Mapper typically gathers data from multiple tables or collections to create the single object.
The joining and processing of data from various tables can be quite impactful in a relational database.
```
B. In MongoDB, the data already represents the object so it can be sent without processing.
```
The document in MongoDB often corresponds to the desired object so it can be sent directly without processing.
```
~~C. In a relational database, you must index the created object representation.~~
```
The Object Mapper object is stored in memory and not stored in the database. It does not need to be indexed.
```
~~D. In MongoDB, you must index the created object representation.~~
```
The Object Mapper object is stored in memory and not stored in the database. It does not need to be indexed
```

## 14. What typically maps directly to an object? (Select one.)
~~A. A record in a RDBMS~~
```
A record in a RDBMS typically only contains a portion of the information required by an object.
This means that to create the object, the operation requires joins or additional queries to gather the necessary information from multiple tables to create the object.
```
B. A document in MongoDB
```
A MongoDB document is typically modeled to represent the same information as required by an object.
As the information is in the desired shape, mapping is often unnecessary.
```

## 15. Which programming languages can use the exact same query syntax for the conditions than the MongoDB shell? (Select all that apply.)
A. Python
```
filter = { 'age': { '$lt': 30 } }
Python uses the same representation of the query as used by the MongoDB Query language. The query predicate is written as JSON like in the MongoDB shell.
```
B. Javascript (NodeJS)
```
const filter = {
    'age': {
        '$lt': 30
    }
    };
Javascript (NodeJS) uses the same representation of the query as used by the MongoDB Query language. The query predicate is written as JSON like in the MongoDB shell.
```
~~C. Java~~
```
Bson filter = lt("age", 30L);
The BSON class in Java is used to compose a query. The class uses builders that are specific to the class instead of having a JSON string to represent the query.
```
~~D. .NET (CSharp)~~
```
var filter = Builders<BsonDocument>.Filter.Lt("age", 30);
The Filter class in .NET is used to compose a query. The class uses builders that are specific to the class instead of having a JSON string to represent the query.
```

## 16. In translating a common MQL query to a coding language, our examples showed several common steps. Which of the following translation steps was done for all the coding languages? (Select all that apply.)
~~A. Used a variable to indicate an index to use when querying the collection~~
```
None of the examples indicated which index to use when querying. This can be done in MongoDB by using the driver-specific hint() function. This provides similar functionality to USE INDEX in a SQL SELECT statement.
```
B. Used a variable to hold the result of the query on the collection 
```
All of the examples used a variable that holds the results of the query.
```
C. Used a variable which referenced the collection we wanted to query
```
All of the examples used a variable referencing the collection that we queried.
```
D. Used a variable to hold the conditional / filter criteria for the query
```
All of the examples used a variable to represent the criteria we translated from our MQL query.
```
E. Used the MongoClient in the programming language to connect to the database

```
All of MongoDB's idiomatic drivers use a MongoClient, which you use to connect to the database.
```






