---
title: Service Mesh
language: en
type: docs
series:
  - Design Patterns
categories:
  - Microservice Architecture
  - Infrastructure
tags:
  - network
  - proxy
  - sidecar
---

## What is a Service Mesh?
> A service mesh is a mechanism for managing communications between the various individual services that make up modern applications in a microservice-based system.

## Why Do You Need a Service Mesh?
Once upon a time, programs were developed and deployed as a single application. This traditional approach, called a monolithic architecture, has worked great for simple applications, but becomes a burden as applications become complex and the codebase expands. 

This is why modern organizations typically move from a monolithic architecture to a microservices architecture. By allowing teams to work independently on an application in small pieces (called microservices), applications can be developed in a modular fashion as a set of services. But as the number of services grows, you need to provide a fast, smooth, and fault-tolerant connection between services.

Enter service mesh.

## How Does a Service Mesh Work?
Service Mesh implementations typically consist of two main components: the data plane and the control plane.

The data plane is a network proxy replicated along with each microservice (known as a "sidecar") that manages all incoming and outgoing network traffic on behalf of the microservice. As part of this, it can perform the functions of service discovery, load balancing, security and reliability. The service and the sidecar must be deployed on the same host and, if your deployment is containerized, in the same pod.

### The Data Plane
The data plane consists of services that work together with sidecar proxies. Services handle business logic, and proxies sit between them and other services. All traffic, incoming and outgoing, goes through proxy servers, which are responsible for routing (proxying) traffic to other services.

Many of the features provided by service mesh operate at the request layer, which makes sidecsars Layer 7 proxies. By operating at this layer, service meshes provide features such as intelligent load balancing based on observed latency, or provide reasonable and consistent timeouts for requests.
> Layer 7 is the Application layer, but it doesn't mean application in the typical sense. It refers to the underlying protocol that an application uses, such as how a web server uses HTTP to bundle a web page.

Sidecars also provide functionality at the connection level. For example, sidecars may provide features such as Mutual Transport Layer Security (mTLS) by allowing each side of a link to verify the other side's certificate.

### The Control Plane
Sidecars need to be configured. This is done through the control plane, which consists of several services that provide administrative functions on the service mesh and provide an interface for customizing the behavior of the data plane and for proxy servers to coordinate their actions.


Operators interact with the service mesh through the control plane using a command line interface or API. For example, operators work through the control plane to define routing rules, create circuit breakers, or provide access control.

Depending on the implementation, you can use the control plane to export observability data such as metrics, logs, and traces.

## Service Mesh vs. Microservice Architecture

### What’s the difference between service mesh and microservices?
* **Microservices** refer to an application that is made up of multiple interconnected and loosely coupled services that work together to provide the application's functionality (as opposed to a single monolithic system).
* **A service mesh** is a technology pattern that can be applied to a microservice-based system to manage network interactions between services. In a service mesh, the network functions are separated from the service application logic, which means that it can be controlled independently.

## Related patterns


## Credits

* [What is a Service Mesh? - konghq.com](https://konghq.com/learning-center/service-mesh/what-is-a-service-mesh)
* [Understanding Service Mesh Architecture - konghq.com](https://konghq.com/learning-center/service-mesh/what-is-service-mesh-architecture)
* [Service Mesh - techtarget.com](https://www.techtarget.com/searchitoperations/definition/service-mesh)