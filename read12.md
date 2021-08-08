# Read 12 - Mongo and Mongoose
### Five differences between SQL and NoSQL databases:
| SQL | NoSQL|
|---|---|---|
|called as Relational Databases|called as non-relational or distributed database|
 |have predefined schema| have dynamic schema for unstructured data|
  |uses structured query language ) for defining and manipulating the data, which is very powerful| queries are focused on collection of documents|
  |examples: MySql, Oracle, Sqlite, Postgres and MS-SQL|examples: MongoDB, BigTable, Redis, RavenDb, Cassandra, Hbase, Neo4j and CouchDb|
   |type of data to be stored: SQL databases are not best fit for hierarchical data storage|NoSQL database fits better for the hierarchical data storage as it follows the key-value pair way of storing data similar to JSON data|

## What kind of data is a good fit for an SQL database?
For the type of data to be stored: SQL databases are not best fit for hierarchical data storage.

### A real world example(SQL):
MySQL Community Edition A popular open-source database.

- MySQL benefits and strengths:
- Replication
Sharding
- Memcached as a NoSQL API to MySQL
- Maturity
- Wide range of Platforms and Languages
- Cost effectiveness
- What kind of data is a good fit a NoSQL database?
- NoSQL database fits better for the hierarchical data storage as it - follows the key-value pair way of storing data similar to JSON data. 
- NoSQL database are highly preferred for large data set.

### A real world example(NoSQL):
MongoDB A popular document based NoSQL database as it stores data in JSON like documents.

- MongoDB benefits and strengths:
- Speed
- Scalability
- Manageable
- Dynamic Schema

**Which type of database is best for hierarchical data storage?**
NoSQL database fits better for the hierarchical

**Which type of database is best for scalability?**
NoSQL

- SQL stand for:
Structured Query Language

Realational database:
A relational database is a type of database that stores and provides access to data points that are related to one another. The columns of the table hold attributes of the data, and each record usually has a value for each attribute, making it easy to establish the relationships among data points.

Type of structure that relational database work with:
The relational model means that the logical data structures—the data tables, views, and indexes—are separate from the physical storage structures. This separation means that database administrators can manage physical data storage without affecting access to that data as a logical structure.

schema:
an abstract design that represents the storage of your data in a database. It describes both the organization of data and the relationships between tables in a given database.

NoSQL database:
A NoSQL originally referring to "non-SQL" or "non-relational" database provides a mechanism for storage and retrieval of data that is modeled in means other than the tabular relations used in relational databases.

How does NoSQL work:
Each type of NoSQL database would be designed with a specific customer situation in mind, and there would be technical reasons for how each kind of database would be organized. The simplest type to describe is the document database, in which it would be natural to combine both the basic information and the customer information in one JSON document. In this case, each of the SQL column attributes would be fields and the details of a customer’s record would be the data values associated with each field.

The inside of a Mongo database:
MongoDB stores data records as documents (specifically BSON documents) which are gathered together in collections. A database stores one or more collections of documents

Which is more flexible - SQL or MongoDB? and why.
While MongoDB is more flexible because it’s ensures high and diverse data availability.

Disadvantage of a NoSQL database:
NoSQL databases don’t have the reliability functions which Relational Databases have.
NoSQL is not compatible.
NoSQL are very new compared to Relational Databases, which means that are far less stable and may have a lot less functionalities.