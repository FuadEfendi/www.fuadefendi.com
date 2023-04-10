---
date: 
title: Database Per Service
linkTitle: Database Per Service
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

## What is "Database Per Service" design pattern? 

- Each microservice uses its' own dedicated private persistence layer (database).
- This data can be accessed only via this dedicated microservice.
- A service’s (inernal) transactions only involve its own (internal, dedicated) database.

