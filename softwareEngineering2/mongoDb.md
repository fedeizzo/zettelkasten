---
date: 2020-12-07T15:38
tags:
  - university/softwarengineering2
  - nosql
  - database
  - mongodb
---

# Mongo DB
Mongo DB is an open source document database and leading NoSQL database. Main features are:

* cross-platform
* document oriented
* high performance
* high availability
* easy scalability

## Components
A Mongo DB is composed by:

* ***Database*** → physical container for collections. Each database gets its own set of files on the file system;
* ***Collection*** → a group of documents, it is equivalent of an RDBMS table. The main difference with tables is that collection does not enforce a schema and fields inside it can have different shape;
* ***Document*** → a set of key-value pairs. Document have dynamic schema as explained above in collection.

Following is listed a table that shown main differences between RDBMS:

| RDBMS       | MongoDB            |
|:-----------:|:------------------:|
| Database    | Database           |
| Table       | Collection         |
| Tuple/Row   | Document           |
| Column      | Field              |
| Table join  | Embedded Documents |
| Primary Key | Primary Key (_id)  |

## Advantages over RDBMS

* schema less
* structure of a single object is clear
* no complex join
* deep query-ability
* tuning
* ease of scale-out
* conversion/mapping of application objects to database objects is automatic
* fast access to data

## Mongo DB in details
### Types
The main types are:

* string → UTF-8 valid
* integer → can be 32 bit or 64 bit depending on server
* boolean → 1 bit true or false
* double → used for floating point values
* min/max keys → used to compare a value against the lowest and highest *BSON* elements
* arrays
* timestamp → ctimestamp
* object
* Null
* symbol → equal to string but used with specific language types
* date → store date in UNIX time format
* Object ID → used to store document's ID
* binary data
* code → used to store javascript code into the document
* regular expression
