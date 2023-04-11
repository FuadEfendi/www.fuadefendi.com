---
date:
nav_weight: 8
title: Database Sharding
linkTitle: Database Sharding
series:
  - Microservices
categories:
  - Design Patterns
tags:
  - microservice
  - design pattern
  - database
  - sharding
images:
featured: false
authors:
  - Fuad Efendi
---

## What is the "Database Sharding" design pattern? 
- Data sharding pattern separates datasets into different shards or partitions. 
- Each shard has the same schema but holds a distinct subset of the data.

Sharding patterns improve scalability, as you can add new shards when the storage needs or depand for higher throughput increase; you can improve performance by reducing the workload of each service. 




## What are the benefits and drawbacks of the "Database Sharding" microservices design pattern?

### The benefits of the "Database Sharding" pattern



### The drawbacks of the "Database Sharding" pattern

## When to use "Database Sharding" design pattern?

Use this pattern in the following scenarios:

- When you want to capture intent, purpose, or reason of change in the data. For example, changes to a customer entity can be captured as a series of specific event types, such as Subscribed, Changed Address, Closed Account, Activated, or Deactivated.
- When it is important to minimize or completely avoid the occurrence of conflicting updates to data.
- When you need to audit data changes, including additional attributes such as "updateTimestamp", "ubdatedBy"
- When you need to to implement additional workflow such as "changeApprovedBy" and rollback if disapproved
- When you want to record events that occur, to replay them to restore the state of a system, to roll back changes, or to keep a history and audit log. 



## References

[Microsoft Azure Architecture, Sharding Pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/sharding)

