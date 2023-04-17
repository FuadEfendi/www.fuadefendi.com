---
title: Service Discovery
language: en
type: docs
series:
  - Design Patterns
categories:
  - Microservice Architecture
  - Infrastructure
tags:
  - network
  - discovery
  - autoscaling
---

## What is a Service Discovery?

The service discovery pattern uses a centralized server named "service registry" to maintain a global view of microservice network locations. Microservices update their location in the service registry at fixed intervals. Clients can connect to the service registry and get information about the location of the microservices.

There are 2 main service discovery patterns available to implement service discovery for microservices.

- Client-side service discovery
- Server-side service discovery

## Why Do You Need a Service Discovery?
In traditional monolithic applications, services run in specific, predefined locations. Thus, it is easy to track their location and clients can easily find and invoke services.

However, when it comes to microservices, their location on the network is assigned dynamically and often changes thanks to features like autoscaling. This behavior makes it difficult to track microservice locations ahead of time.

The service discovery pattern was introduced as a solution, which allows developers to find network locations for microservices without injecting or bundling services.

## How Does a Service Discovery Work?
The service registry stores records about the network locations of microservices. Microservice instances register themselves and indicate their location in the service registry. Clients can then find the location of the microservices using the service registry and invoke them directly to meet their needs.

## The Client‑side Discovery Pattern
In the client-side service discovery pattern, the client is responsible for finding the network locations of the microservices and load-balancing requests between them.

The client first queries the service's registry and retrieves the locations. The client then uses its dedicated load balancer to select a microservice and submits the request.

### Advantages of Client-side Service Discovery
- The service registry is the only moving part.
- The client knows the location of the microservices before sending the request.
- The client can implement intelligent load balancing (by introducing dedicated separate load balancer)

### Disadvantages of Client-side Service Discovery
- The client is responsible for implementing service discovery logic.
- The client is coupled with the service registry.
- Need to implement client-side components for each programming language

## The Server‑side Discovery Pattern
The server-side discovery pattern solves one of the important client-side discovery problems by decoupling the client from the service registry. With this approach, the client does not have a dedicated load balancer. Instead, **the load balancer acts as an intermediary and is responsible for communicating with the service's registry**.

First, the client requests the microservice through the load balancer. The load balancer then queries the service registry and finds the location of the appropriate microservice. Finally, the load balancer routes the request to the microservice.

This pattern is widely used in modern applications because both clients and microservices are independent of the service registry. Most importantly, you don't have to implement server-side discovery load balancers from scratch, as many deployment environments provide load balancers.

For example, you can use AWS Elastic Load Balancer or proxy servers in Kubernetes environments as server-side discovery load balancers.

### Advantages of Server-side Service Discovery
- The service registry is decoupled from the client.
- You don't have to implement service discovery client library for every programming language your clients use.
- Many deployment environments already provide this feature.

### Disadvantages of Server-side Service Discovery
- If the deployment environment does not provide this feature, developers need to create and manage load balancers.

## Related patterns


## Credits

* [Client-side service discovery - microservices.io](https://microservices.io/patterns/client-side-discovery.html)
* [Server-side service discovery - microservices.io](https://microservices.io/patterns/server-side-discovery.html)
* [Service Discovery in Microservices - baeldung.com](https://www.baeldung.com/cs/service-discovery-microservices)
* [Service Discovery in a Microservices Architecture - nginx.com](https://www.nginx.com/blog/service-discovery-in-a-microservices-architecture/)

