---
title: 12 Factor App
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
The Twelve Factor App is a se of principles that describes a way of making software that, when followed, enables companies to create code that can be released reliably, scaled quickly, and maintained in a consistent and predictable manner.

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
> One codebase tracked in revision control, many deploys

The Codebase principle states that all assets related to an application, everything from source code, the provisioning script, and configuration settings, are stored in a source code repository that is accessible to development, testing, and system administration staff. The source code repository is also accessible to all automation scripts that are part of the Continuous Integration/Continuous Delivery (CI/CD) processes that are part of the enterprise's Software Development Lifecycle. (SDLC). 

The same codebase deploys to local woirkstation for developer local tests (without dependency on local OS), to DEV, QA, UAT STAGING, and PROD (production) environments.


### II. Dependencies
> Explicitly declare and isolate dependencies

The **Dependencies** principle states that only code that is unique and that matches the purpose of the application is kept in version control. External artifacts such as Node.js packages, Java .jars, or .NET DLLs should be referenced in a dependency manifest that is loaded into memory during development, testing, and production execution. You want to avoid storing artifacts along with the source code in a source code repository.

### III. Config
> Store config in the environment

The **Config** principle states that configuration information is injected into the runtime as environment variables or as options defined in an independent configuration file. While it is acceptable in some cases to store default settings that can be overridden directly in code, settings such as port number, dependency URLs, and state settings such as DEBUG must exist separately and be applied during deployment. Good examples of external configuration files are a Java properties file, a Kubernetes manifest file, or a docker-compose.yml file.

The advantage of keeping the configuration settings separate from the application logic is that you can apply the configuration settings according to the deployment path. For example, you might have one set of configuration settings for a deployment intended for a test environment and another set for a deployment intended for a production environment.

### IV. Backing Services
> Treat backing services as attached resources

The **Backing Services** principle encourages architects to consider external components such as databases, email servers, message brokers, and independent services that can be provided and maintained by system personnel as attached resources. Treating resources as support services contributes to the flexibility and efficiency of the Software Development Life Cycle (SDLC).

### V. Build, Release, Run
> Strictly separate build and run stages

The **Build, Release, Run** principle breaks down the deployment process into three reproducible steps that can be started at any time. During the **Build** phase, code is pulled from source control and built/compiled into artifacts stored in an artifact repository such as Docker Hub or a Maven repository. After the code is built, the configuration settings are applied during the **Release**** phase. Then, in the **Run** (execute) phase, the runtime is scripted using a tool like Ansible. The application and its dependencies are deployed to the newly provisioned runtime.

The key to **Build, Release, Run** is that the process is completely ephemeral. If something in the pipeline is destroyed, all artifacts and environments can be rebuilt from scratch using the assets stored in the source code repository.


### VI. Processes
> Execute the app as one or more stateless processes

The **Processes** principle, more accurately referred to as *stateless* processes, states that an application developed within the 12 Factor Application Framework will operate as a set of stateless processes. This means that no process keeps track of the state of another process, and no process keeps track of information such as session or workflow state. The stateless process makes it easy to scale. When a process is stateless, instances can be added and removed to address a particular load at a given time. Because each process runs independently, statelessness prevents unintended side effects.


### VII. Port Binding

> Export services via port binding

The **Port Binding** principle states that a service or application is identified on a network by a port number, not a domain name. The reason is that domain names and their associated IP addresses can be assigned on the fly through manual manipulation and automatic service discovery mechanisms. Thus, using them as a reference point is unreliable. However, providing access to a service or application on the network according to a port number is more reliable and easier to manage. At the very least, potential problems due to a collision between a network-private port number assignment and another process' public use of the same port number can be avoided by using port forwarding.

The basic idea behind the port binding principle is that uniform use of the port number is the best way to represent a process on the network. For example, patterns have emerged in which port 80 is common for HTTP web servers, port 443 is the default port number for HTTPS, port 22 is for SSH, port 3306 is the default port for MySQL, and port 27017 is default port number for MongoDB.

### VIII. Concurrency

> Scale out via the process model

The **Concurrency** principle recommends organizing processes according to their purpose, and then separating those processes so that they can be scaled up and down as needed. For example, let's consider an application on the network available through web servers running behind a load balancer. The group of web servers behind the load balancer in turn uses the business logic that resides in the business service processes running behind their own load balancer. If the load on the web servers increases, this group can be grown in isolation to meet current needs. However, if a bottleneck occurs due to the load on the business service, this tier can be scaled independently.

Concurrency support means that different parts of the application can scale to meet current needs. Otherwise, when parallelism is not supported, architectures have no choice but to fully scale the application.

### IX. Disposability

> Maximize robustness with fast startup and graceful shutdown

The **Disposability** principle states that applications must start and stop gracefully. This means doing all the necessary "housekeeping" before the application is made available to consumers. For example, soft start ensures that all database connections and access to other network resources are up and running. In addition, all other necessary configuration work has been completed.

Regarding shutdown, "disposability" stands for ensuring that all connections to the database and other network resources are properly terminated and all shutdown actions are logged.



### X. Dev/Prod Parity
> Keep development, staging, and production as similar as possible

The **Dev/Prod Parity** principle means that all deployment paths are similar but independent, and that a deployment does not "jump" to a different deployment target; we do NOT copy artifacts from DEV tyo PROD; instead, our CI/CD rebuilds everything and deploys using different targets (DEV, QA, PROD).

**Dev/Prod Parity** is very similar to **Build, Release, Run**. The important difference is that Dev/Prod Parity provides the same deployment process for production as it does for development.

### XI. Logs
> Treat logs as event streams

The **Logs** principle advocates sending log data in a stream that can be accessed by various interested consumers. The process of routing log data must be separate from the processing of log data. For example, one consumer may be interested only in error data, while another consumer may be interested in request/response data. Another consumer may be interested in keeping all log data for event archiving. An added benefit is that even if the application dies, the log data continues to live on after that.

### XII. Admin Processes
> Run admin/management tasks as one-off processes


The **Admin Processes** principle states that administration processes are first class citizens in the software development life cycle (SDLC) and should be treated as such. 

For example, consider application such as Amazon Shopping Website. "dataSeeder" non-web **Admin Process** may inject datafeed in specialized JSON format from manufacturer with exact product names, model numbers, and other specialized data; bypassing public Web API. "dataSeeder" is given Build, Release, and Run deployment path, it is released according to the principles of Codebase and Dev/Prod Parity. The admin process, dataSeeder, is not separate from the overall SDLC; it is part of it.


## Credits

* The [12 Factor App](https://12factor.net/), published in 2011 by Adam Wiggins
* [An illustrated guide to 12 Factor Apps - redhat.com](https://www.redhat.com/architect/12-factor-app)
