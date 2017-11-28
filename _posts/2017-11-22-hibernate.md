---
title:  "Hibernate"
last_modified_at: 2017-11-23
categories: 
  - Program
  - JAVA
  - Hibernate
tags:
  - Hibernate
  - DB
toc: true
toc_label: "Hibernate"
---

## Introduce
**[Hibernate ORM (Hibernate in short)][hibernate wiki]** is an object-relational mapping tool for the Java programming language. It provides a framework for mapping an object-oriented domain model to a relational database. Hibernate handles object-relational impedance mismatch problems by replacing direct, persistent database accesses with high-level object handling functions.

## Architecture
![Hibernate architecture](/assets/images/2017/hibernate-architecture.jpg)

| Unit                 | Description                                                                                                                                                                                                                                                   |
| -------------------- | :-------------------------------                                                                                                                                                                                                                              |
| Configuration        | The Configuration object provides two keys components: **Database Connection (hibernate.properties)** and **Class Mapping Setup (hibernate.cfg.xml)**                                                                                                         |
| Session Factory      | The SessionFactory is a heavyweight object; it is usually created during application start up and kept for later use.                                                                                                                                         |
| Session              | A Session is used to get a physical connection with a database. The Session object is lightweight and designed to be instantiated each time an interaction is needed with the database. Persistent objects are saved and retrieved through a Session object.  |
| Transaction          | A Transaction represents a unit of work with the database and most of the RDBMS supports transaction functionality. Transactions in Hibernate are handled by an underlying transaction manager and transaction (from JDBC or JTA).                            |
| Query                | Query objects use SQL or Hibernate Query Language (HQL) string to retrieve data from the database and create objects. A Query instance is used to bind query parameters, limit the number of results returned by the query, and finally to execute the query. |
| Criteria             | Criteria objects are used to create and execute object oriented criteria queries to retrieve objects.                                                                                                                                                         |

## Persistent Class
The entire concept of Hibernate is to take the values from Java class attributes and persist them to a database table. A mapping document helps Hibernate in determining how to pull the values from the classes and map them with table and associated fields.

Java classes whose objects or instances will be stored in database tables are called persistent classes in Hibernate. Hibernate works best if these classes follow some simple rules, also known as the Plain Old Java Object (POJO) programming model.

There are following main rules of persistent classes, however, none of these rules are hard requirements
- All Java classes that will be persisted need a default constructor.
- All classes should contain an ID in order to allow easy identification of your objects within Hibernate and the database. This property maps to the primary key column of a database table.
- All attributes that will be persisted should be declared private and have getXXX and setXXX methods defined in the JavaBean style.
- A central feature of Hibernate, proxies, depends upon the persistent class being either non-final, or the implementation of an interface that declares all public methods.
- All classes that do not extend or implement some specialized classes and interfaces required by the EJB framework.

The POJO name is used to emphasize that a given object is an ordinary Java Object, not a special object, and in particular not an Enterprise JavaBean.
## Session
A Session is used to get a physical connection with a database. The Session object is lightweight and designed to be instantiated each time an interaction is needed with the database. Persistent objects are saved and retrieved through a Session object.

Instances may exist in one of the following three states at a given point in time
- **transient** − A new instance of a persistent class, which is not associated with a Session and has no representation in the database and no identifier value is considered transient by Hibernate.
- **persistent** − You can make a transient instance persistent by associating it with a Session. A persistent instance has a representation in the database, an identifier value and is associated with a Session.
- **detached** − Once we close the Hibernate Session, the persistent instance will become a detached instance.

## Association Mappings
The mapping of associations between entity classes and the relationships between tables is the soul of ORM. Following are the four ways in which the cardinality of the relationship between the objects can be expressed. An association mapping can be unidirectional as well as bidirectional.
- ManyToOne
- OneToMany
- OneToOne
- ManyToMany

It is very much possible that an Entity class can have a reference to another class as a member variable. 
- Component Mappings

## Annotations
Hibernate Annotations is the powerful way to provide the metadata for the Object and Relational Table mapping. All the metadata is clubbed into the POJO java file along with the code, this helps the user to understand the table structure and POJO simultaneously during the development.
- @Entity
- @Table
- @Id and @GeneratedValue Annotations
- @Column

## Interceptors
As you have learnt that in Hibernate, an object will be created and persisted. Once the object has been changed, it must be saved back to the database. This process continues until the next time the object is needed, and it will be loaded from the persistent store.

Thus an object passes through different stages in its life cycle and Interceptor Interface provides methods, which can be called at different stages to perform some required tasks. These methods are callbacks from the session to the application, allowing the application to inspect and/or manipulate properties of a persistent object before it is saved, updated, deleted or loaded. Following is the list of all the methods available within the Interceptor interface.

## Cache
![Hibernate cache architecture](/assets/images/2017/hibernate-cache.jpg)
- *First-level Cache*
The first-level cache is the Session cache and is a mandatory cache through which all requests must pass. The Session object keeps an object under its own power before committing it to the database.
- *Second-level Cache*
Second level cache is an optional cache and first-level cache will always be consulted before any attempt is made to locate an object in the second-level cache. The second level cache can be configured on a per-class and per-collection basis and mainly responsible for caching objects across sessions.
- *Query-level Cache*
Hibernate also implements a cache for query resultsets that integrates closely with the second-level cache.

This is an optional feature and requires two additional physical cache regions that hold the cached query results and the timestamps when a table was last updated. This is only useful for queries that are run frequently with the same parameters.

1. First level cache is mandatory
2. The second level cache is optional

## Reference
- [https://www.tutorialspoint.com/hibernate/hibernate_architecture.htm](https://www.tutorialspoint.com/hibernate/hibernate_architecture.htm)

[hibernate wiki]:  https://en.wikipedia.org/wiki/Hibernate_(framework) "Hibernate wiki"
