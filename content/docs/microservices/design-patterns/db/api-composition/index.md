---
date:
weight: 4
title: API Composition
linkTitle: API Composition
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

## What is the "API Composition" design pattern? 
- "API Composer" queries multiple services and aggregates results.

Example: Elasticsearch has NRT (Near Real Time) search capabilities. Typical indexing (or optimmizing existing fragmented index) of large datasets will take hours; if we need to index latest tweets from Twitter in real-time, for past few hours only, we only need milliseconds, so that it is called NRT; and it supports near-real-time updates of the index and doesn't need any "optimization".

Now, what about Near-Real-Time Search for past week, month, year? Index optimization will take hours, and we have realtime data updates, it won't be optimized and we can't use NRT.

Solution: implement five services and aggregate results:
- index for all previous years
- index for all previous months in current year
- index for all days in current month, up to yesterday
- index for today, up to last hour
- NRT "in-memory" index




## What are the benefits and drawbacks of the "API Composition" microservices design pattern?

The benefits of the "API Composition" design pattern are:
- 


The drawbacks of the "API Composition" design pattern are:
- 
