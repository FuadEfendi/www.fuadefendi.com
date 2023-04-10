---
date: 
title: Microservices vs. Monolithic Architecture
linkTitle: Microservices vs. Monolithic Architecture
series:
  - Microservices
categories:
  - Architecture
tags:
  - microservice
  - monolithic
  - architecture
images:
featured: false
authors:
  - Fuad Efendi
---

# Microservices vs. Monolithic Architecture

## Why would you neeused Microservices Architecture?

### Microservices Architecture

#### Pros
- although "additional complexity", it is alternative, different kind of "complexity"
- when something breaks, "monolith" breaks as a whole
- A service in a microservices architecture is small, responsibilities are minimal, the overall complexity is bounded (restricted)
- if service becomes overly complex and polluted over time, it is easy to refactor it into possibly few services, than to refactor huge monolith into another cleaner monolith
- The microservices architecture isolates complexity, allowing for smaller, more agile teams to create a service
- “two-pizza teams”, where the entire team — leaders and all — can be fed with only two pizza pies
- microservices architecture is flexible: individual services allow for a variety of platforms, languages, and tools to be used because these choices affect only a small team at one time
- You can rapidly make changes and build and release updates, and as long as Public APIs (or inputs and outputs) aren’t affected, developers can move fast without breaking things

#### Cons
- many moving parts (services) add extra complexity
- Compare smaller Public API of monolithic transactional "buy book" method with parameters "user" and "book", with three-service non-transactional Public APIs with 1st method "reserve funds", 2nd one "reserve book", and 3rd "commit transaction and notify user"

### Monolithic Architecture

- updates and releases become slow and painful
- over time, software tends to grow in complexity, it becomes "monster"
- monoliths are hard to scale: often one part of the monolith is particularly resource intensive
- no options to scale an individual part of the monolith
- most monoliths cannot be even replicated (Oracle Cluster vs. Master-Slave architecture)
