# Chapter 2 - Review Questions

**2.1** Define the following terms: data model, database schema, database state,
internal schema, conceptual schema, external schema, data independence,
DDL, DML, SDL, VDL, query language, host language, data sublanguage,
database utility, catalog, client/server architecture, three-tier architecture,
and n-tier architecture.

* **Data model**: Collection of concepts used to describe DB structure
* **Database schema**: Description of a database
* **Internal schema**: Catalog where the low-level details of the data storage resides.
* **Conceptual schema**: Catalog where the details of the structure of the database itself resides.
* **External schema**: Construct which presents the user with a view of the data they're interested in; usually this is linked to columns in the conceptual schema.
* **Data independence**: Ability to change schema at one level of a DB system without having to change schema at the next highest level.
* **DDL**: Data definition language, which is used to define schemas within a DBMS. Typically, DDL languages describe external and conceptual schemas.
* **DML**: Data manipulation language, which allows users / systems to make changes to the database itself. The most common DML is SQL.
* **SDL**: Storage definition language, which is used to describe the internal schema.
* **VDL**: View definition language, which if it exists, is separate from the main DDL to describe external schema, or views.
* **Query language**: A high-level DML used in a standalone, interative manner.
* **Host language**: DML language that is embedded within a general purpose programming language for usage with a DBMS.
* **Data sublanguage**: In the context of a host language, this refers to the underlying DML of the database.
* **Catalog**: General archive / repository of information.
* **Client / server architecture**: Architecture where the server offloads connectivity and query processing to the client's computer; in this sense, the server is offloading part of the computing burden to the user's computer.
* **Three-tier architecture**: In contrast to client/server, three-tier uses a middle layer, usually referred to as an application server, or web server, which lets the user interact with an application, and underneath is constructing the business logic, which then gets sent to the database server for processing.
* **N-tier architecture**: An extension of the three-tier architecture where more components are introduced in the middleware, such as separation between front-end, and back-end servers in an application architecture.

**2.2** Discuss the main categories of data models. What are the basic differences among the relational model, the object model, and the XML model?

The main categories of data models are: Conceptual data model, logical data model, and physical data model. 

Relational model: data is represented logically, and with relationtions. Columns must all be of the same type.

Object model: Handles the data like object-oriented programming, dealing with classes, methods, and properties of the classes.

XML model: a hierarchical model. Data types are defined based on their inheritance, and there is no ordering.

**2.3** What is the difference between a database schema and a database state?

A database schema is the description of a particular database, but by itself does not contain any data. A database state is a snapshot containing the current set of data at that particular time. The primary different is that while the schema remains relatively unchanged over time, the database state is constantly changing.

**2.4** Describe the three-schema architecture. Why do we need mappings among schema levels? How do different schema definition languages support this architecture?

The three schema architecture refers to the separate of: external schema, conceptual schema, and internal schema. Each level is essentially a separation of duties, and they handle specific aspects of the database. The internal schema handles the low-level details of how data is stored at the disk level. The conceptual schema contains the structure of the whole database. The external schema then provides an interface for users / applications to view data which are specific for their needs.

Mappings are needed to connect these three levels because, by themselves, they cannot exist without some dependence on another level. Thus, when looking at an external schema, ultimately the information is processed through the conceptual schema where the database structure it kept, and then the internal schema where the data is kept.

* DDL used to specify conceptual and internal schemas for the database.
* SDL used to specify the internal schema.
* VDL used to specify user view and their mapping to the conceptual schema.

**2.5** What is the difference between logical data independence and physical data independence? Which one is harder to achieve? Why?

Logical data independence is the ability to make changes to the conceptual schema without having to change the external schema. Physical data independence is the ability to change the internal schema without having to change the conceptual schema. Ultimtely, logical data independence is harder to achieve because external schemas are referenced by applications and / or users, and those parties often reference specific aspects (columns, usually) of the conceptual schema. 

**2.6** What is the difference between procedural and nonprocedural DMLs?

There are two main types of DMLs: procedural and non-procedural. The main difference between them is the way they deal with records; procedural DMLs are called "record-at-a-time" because they handle the functionality needed to process records as they come (looping, for example). Non-procedural DMLs, conversely, handle records in sets, and are called "set-at-a-time" DMLs. 

**2.8** With what other computer system software does a DBMS interact?
CASE tools for design of the DB, data dictionaries, and application development environments.

**2.9** What is the difference between the two-tier and three-tier client/server architectures?

The difference between these architectures is that three-tier architectures implement some kind of middleware between the client and the database server (an application server, for example), whereas two-tier architectures are direct client-to-server connections.

**2.11** What is the additional functionality incorporated in n-tier architecture (n > 3) ?

The additional functionality afforded by n-tier architectures is the ability to split duties of an application architecture into finer components. Instead of having a monolithic application server, these components can be split into front-end / back-end systems. Going further, back-end systems can be split into multiple horizontal or vertical tiers for data processing, or data transport to other systems.