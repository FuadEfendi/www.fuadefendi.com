---
title: The Twelve-Factor App
language: en
type: docs
series:
  - Design Patterns
categories:
  - Microservice Architecture
  - Methodology
  - SaaS
tags:
  - SaaS
---



## What is The Twelve Factor App?
> The Twelve Factor App a methodology for building modern, scalable, maintainable Software-as-a-Service (SaaS) apps.

## Why Do You Need The Twelve Factor App?
In the modern era, software is commonly provided as a service: so-called *Web Applications* or *Software as a Service*. The Twelve Factor App is a methodology for creating software as a service applications that:

- Use *declarative formats* to automate setup, and to minimize time and cost for new developers joining a project;
- Have a *clean contract* with the underlying operating system, allowing for maximum portability between runtimes;
- Suitable for deployment on modern *cloud* platforms, eliminating the need to administer servers and systems;
- Minimize discrepancies between development and production by enabling *continuous deployment* for maximum flexibility;
- And it can *scale* without significant changes in tooling, architecture, or development methods.

The twelve factor methodology can be applied to applications written in any programming language and using any combination of backing services (database, queue, cache, and etc.).



## The Twelve Factors Manifesto

### I. Codebase
One codebase tracked in revision control, many deploys

### II. Dependencies
Explicitly declare and isolate dependencies

### III. Config
Store config in the environment

### IV. Backing services
Treat backing services as attached resources

### V. Build, release, run
Strictly separate build and run stages

### VI. Processes
Execute the app as one or more stateless processes

### VII. Port binding
Export services via port binding

### VIII. Concurrency
Scale out via the process model

### IX. Disposability
Maximize robustness with fast startup and graceful shutdown

### X. Dev/prod parity
Keep development, staging, and production as similar as possible

### XI. Logs
Treat logs as event streams

### XII. Admin processes
Run admin/management tasks as one-off processes


## Credits

* [The Twelve-Factor App - 12factor.net](https://12factor.net/)
* [An illustrated guide to 12 Factor Apps - redhat.com](https://www.redhat.com/architect/12-factor-app)
