---
title:  "SpringBoot -- JPA"
last_modified_at: 2017-11-22
categories: 
  - Program
  - JAVA
tags:
  - SpringBoot
toc: false
toc_label: ""
---

[The Java Persistence API (JPA)][JPA wiki] is a Java application programming interface specification that describes the management of relational data in applications using Java Platform, Standard Edition and Java Platform, Enterprise Edition.

Products support JPA: **Hibernate, Eclipselink, Toplink, Spring Data JPA**, etc.

## [The components in JPA][JPA architecture]

| Unit                 | Description                                                                                                                      |
| -------------------- | :-------------------------------                                                                                                |
| EntityManagerFactory | This is a factory class of EntityManager. It creates and manages multiple EntityManager instances.                               |
| EntityManager        | It is an Interface, it manages the persistence operations on objects. It works like factory for Query instance.                  |
| Entity               | Entities are the persistence objects, stores as records in the database.                                                         |
| EntityTransaction    | It has one-to-one relationship with EntityManager. For each EntityManager, operations are maintained by EntityTransaction class. |
| Persistence          | This class contain static methods to obtain EntityManagerFactory instance.                                                       |
| Query                | This interface is implemented by each JPA vendor to obtain relational objects that meet the criteria.                            |

## Three components
1. Entities
2. Object-relational metadata
3. Java Persistence Query Language - JPQL


[JPA wiki]: https://en.wikipedia.org/wiki/Java_Persistence_API "JPA wiki"
[JPA architecture]: https://www.tutorialspoint.com/jpa/jpa_architecture.htm
