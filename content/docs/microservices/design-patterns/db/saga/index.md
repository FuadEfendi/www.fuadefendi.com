---
date:
weight: 3
title: Saga Distributed Transactions
linkTitle: Saga
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

## What is the "Saga Distributed Transactions" design pattern? 

- A saga is a sequence of transactions that spans many services. 
- Each transaction updates the database and publishes a message (emits an event) to trigger the next transaction in the saga. 
- If a transaction fails then the saga executes a series of compensating transactions that undo the changes that were made by the preceding transactions.

## What are the benefits and drawbacks of the "Saga Distributed Transactions"?

The benefits of the "Saga Distributed Transactions" design pattern are:
- Good for simple workflows that require few participants and don't need a coordination logic.
- Doesn't require additional service implementation and maintenance.
- Doesn't introduce a single point of failure, since the responsibilities are distributed across the saga participants.


The drawbacks of the "Saga Distributed Transactions" design pattern are:
- Workflow can become confusing when adding new steps, as it's difficult to track which saga participants listen to which commands.
- There's a risk of cyclic dependency between saga participants because they have to consume each other's commands.
- Integration testing is difficult because all services must be running to simulate a transaction.

