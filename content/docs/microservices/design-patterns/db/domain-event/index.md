---
date:
weight: 7
title: Domain Events
linkTitle: Domain Events
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

## What is the "Domain Events" design pattern? 
- Use domain events to explicitly implement side effects of changes within your domain. 
- In DDD (Domain Driven Development) terminology, use domain events to explicitly implement side effects across multiple aggregates. 
- For better scalability and less impact in database locks, use eventual consistency between aggregates within the same domain.

An event is something that has happened in the past. A domain event is, something that happened in the domain that you want other parts of the same domain to be aware of. The notified services usually react to the events.

Domain events are similar to messaging-style events, with one important difference. With real messaging, a message is always sent asynchronously and communicated across processes and machines. This is useful for integrating multiple Bounded Contexts, microservices, or even different applications. However, with domain events, you want to raise an event from the domain operation you're currently running, but you want any side effects to occur within the same domain: for example, to implement eventual consistency.


## What are the benefits and drawbacks of the "Domain Events" microservices design pattern?

### The benefits of the "Domain Events" pattern
- Side effects can be expressed explicitly.
- we can implement eventual consistency.


### The drawbacks of the "Domain Events" pattern


### References

[Microsoft](https://learn.microsoft.com/en-us/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/domain-events-design-implementation)

