---
date:
weight: 7
title: Event Sourcing
linkTitle: Event Sourcing
series:
  - Microservices
categories:
  - Design Patterns
tags:
  - microservice
  - design pattern
  - database
  - event
images:
featured: false
authors:
  - Fuad Efendi
---

## What is the "Event Sourcing" design pattern? 
- "Event Sourcing" persists the state of a business entity as a sequence of state-changing events. 
- Whenever the state of a business entity changes, a new event is appended to the list of events (to the log). 
- The application reconstructs current state of the entity by replaying the events.



## What are the benefits and drawbacks of the "Event Sourcing" microservices design pattern?

### The benefits of the "Event Sourcing" pattern



### The drawbacks of the "Event Sourcing" pattern

## When to use "Event Sourcing" design pattern?

Use this pattern in the following scenarios:

- When you want to capture intent, purpose, or reason of change in the data. For example, changes to a customer entity can be captured as a series of specific event types, such as Subscribed, Changed Address, Closed Account, Activated, or Deactivated.
- When it is important to minimize or completely avoid the occurrence of conflicting updates to data.
- When you need to audit data changes, including additional attributes such as "updateTimestamp", "ubdatedBy"
- When you need to to implement additional workflow such as "changeApprovedBy" and rollback if disapproved
- When you want to record events that occur, to replay them to restore the state of a system, to roll back changes, or to keep a history and audit log. 



## References

[Microsoft Azure](https://learn.microsoft.com/en-us/azure/architecture/patterns/event-sourcing)

