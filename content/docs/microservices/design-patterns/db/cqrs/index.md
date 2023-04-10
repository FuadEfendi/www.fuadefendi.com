---
date:
weight: 7
title: CQRS
linkTitle: CQRS
series:
  - Microservices
categories:
  - Design Patterns
tags:
  - microservice
  - design pattern
  - database
images:
featured: false
authors:
  - Fuad Efendi
---

## What is the "CQRS" design pattern? 
- CQRS stands for Command and Query Responsibility Segregation, a pattern that separates read and update operations for a datastore.
- CQRS separates reads and writes into different models, using **commands** to update data, and **queries** to read data.
- Commands should be business method oriented, such as "reserve funds", "buy book", "register user"
- Queries should never modify database
- Queries can use "materialized views" specifically optimized for reads; queries can be routed to "replica" as a performance optimmization
- "Command" can update First Name, Last Name, and DOB, and Query can return concatenated string "full name" and pre-calculated "age"



## What are the benefits and drawbacks of the "CQRS" microservices design pattern?

The benefits of the "CQRS" design pattern are:
- Implementing "CQRS" in your application can maximize its performance, scalability, and security.
- The flexibility created by migrating to "CQRS" allows a system to better evolve over time and prevents update commands from causing merge conflicts at the domain level.


The drawbacks of the "CQRS" design pattern are:
- 
