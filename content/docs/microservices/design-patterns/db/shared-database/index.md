---
date:
nav_weight: 2
title: Shared Database
linkTitle: Shared Database
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

## What is "Shared Database" design pattern? 

- Few different services share the same persistence layer (database).
- The data is "shared" and different services need to implement for safe updates, cuncurrency, notifications, and so on.
- this pattern is primarily applicable for traditional "hard-to-scale" relational databases

For example, "Department" service can add Employee to the Department, and "Employee" service can move Employee from one Department to another, and both services share the same traditional relational database with two tables Employee and Department. To make it more sophisticated, we can have separate HR service and Payroll service with different Web UI installed in different network segments; all share the same database.

## What are the benefits of the "Shared Database" microservices architecture design pattern?

The benefits of the "Shared Database" pattern are:
- Developer uses straightforward ACID transactions to enforce data consistency
- Single database is simpler to operate: centralized audit, in-place (for decades) corporate standards, including centralized schema management
- We can have both legacy and newer microservices architecture accessing the same database which makes transition smoother
- Development time is faster: we can avoid worry about distributed non-ACID transactions

The drawbacks of the "Shared Database" pattern are:
- **Development time coupling** between different team members and even diffennt teams; additional coordination needed for each schema change which slows down development; huge corporations even have schema management procedures in place which can take weeks to get prroved
- **Runtime coupling**: different services can potentially interfere with each other. For example, long running annual transactions report may interfere with purchase transactions submitted by customers.

