---
date: 
title: REST vs GraphQL
linkTitle: REST vs GraphQL
series:
  - Microservices
categories:
  - Design Patterns
tags:
  - REST
  - GraphQL
images:
featured: true
authors:
  - fuadefendi
---

## What is REST?

- REST: Representational State Transfer
- Server responds with the representation of a resource
- there is no "official" standard for RESTful web APIs
- REST is an architectural style, while SOAP is a protocol
- REST is not a standard in itself, but RESTful implementations make use of standards, such as HTTP, URI, JSON, and XML


References
[Codecademy](https://www.codecademy.com/article/what-is-rest)


## REST vs GraphQL

- RESTful services allow application to change state (modify data) without being state aware. For example, a RESTful user management service will always return the entire user record tree not just a few attributes specific to the requested state change.
- RESTful services always have specific endpoint to fetch specific data, to change specific state
  
### REST cons
- over-fetching: fetching whole object graph instead of just few attributes
- under-fetching: multiple round trips to DB, multiple endpoints for different data types
- data binding via endpoints causes multiple iterations to build final "representation"

## GraphQL pros
- GraphQL introduces a schema definition layer 
- schema definition is built using JSON and it is state-aware
- you can chose specific data elements (instead of whole record) and you can have multiple domains of data with just one endpoint