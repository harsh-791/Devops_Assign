# Introduction to Microservices and DevOps

## What are Microservices?
Microservices are an architectural style where an application is split into multiple small, independent services.  
Each service:
- Handles a specific business function  
- Is loosely coupled with others  
- Can be developed, deployed, and scaled independently  

This is different from a **monolithic architecture**, where the entire application is developed and deployed as a single unit.

---

## Monolithic vs Microservices Architecture

### Monolithic Architecture
- Single codebase and deployment unit  
- Difficult to scale specific components  
- One failure can affect the entire system  
- Technology stack is fixed  

### Microservices Architecture
- Multiple independent services  
- Each service can scale independently  
- Failures are isolated  
- Different services can use different tech stacks  

---

## Benefits of Microservices
- **Scalability:** Individual services can be scaled based on load  
- **Independent Deployment:** Faster releases and easier rollbacks  
- **Fault Isolation:** Failure of one service doesn’t crash the whole system  
- **Technology Flexibility:** Teams can choose the best tool for each service  

---

## Microservice Communication

### Synchronous Communication
- Direct request–response (usually REST APIs over HTTP/HTTPS)  
- Caller waits for a response  
- Simple but can cause tight coupling and cascading failures  

### Asynchronous Communication
- Services communicate via events or messages  
- Caller does not wait for a response  
- Improves resilience and scalability  

### Message Brokers
Examples:
- Kafka  
- RabbitMQ  
- ActiveMQ  

Used to decouple producers and consumers and manage message delivery.

### Communication Models
- **Publish–Subscribe:** One message → many consumers  
- **Queue Model:** One message → one consumer  

---

## API Gateway
- Acts as a single entry point for all client requests  
- Handles authentication, authorization, routing, and rate limiting  
- Reduces direct client interaction with microservices  

---

## Load Balancing and Routing

### Load Balancers
- Distribute traffic across multiple service instances  
- Improve availability and performance  

### Routing Types
- **Path-based routing:** Routing based on URL paths  
- **Instance routing:** Routing to specific service instances  

---

## DNS (Domain Name System)
- Translates human-readable domain names into IP addresses  
- Essential for service discovery and client access  
- Makes systems easier to manage and scale  

---

## Service Discovery
- Enables services to dynamically locate each other  
- Prevents hardcoding of IP addresses  
- Important in containerized and auto-scaled environments  

---

## Stateless Microservices
- No session or user data stored within the service  
- State is maintained in databases or caches  
- Makes scaling and service replacement easier  

---

## Databases in Microservices

### Single Database per Service Pattern
- Each microservice owns its own database  
- Avoids tight coupling at the data layer  
- Enables independent schema changes  

### SQL vs NoSQL
- **SQL:** Structured data, strong consistency  
- **NoSQL:** Flexible schema, high scalability  

### Caching
- Redis, Memcached used to reduce database load  
- Improves system performance and response time  

---

## Authentication and Authorization
- **Authentication:** Verifying user identity  
- **Authorization:** Ensuring access permissions  
- Commonly handled by API Gateway or auth services  

---

## Logging and Monitoring

### Externalized Logging
- Logs are stored outside the services  
- Helps in debugging and tracking failures  

### Common Tools
- Fluentd  
- ELK Stack (Elasticsearch, Logstash, Kibana)  
- Splunk  
- Dynatrace  

---

## 12-Factor App Methodology (Key Principles)
- Stateless services  
- Externalized configuration  
- Logs as event streams  
- Port binding  
- Disposability (fast startup and shutdown)  
- Dev/Prod parity  
- Separate admin processes  

---

## Configuration Management
- Configuration should be external to code  
- Avoid environment-specific hardcoding  
- Improves portability and consistency  

---

## Concurrency and Disposability
- Services should handle multiple requests simultaneously  
- Services must start and stop cleanly  
- Enables fault tolerance and auto-scaling  

---

## DevOps Overview

### What is DevOps?
DevOps is a set of practices that combines development and operations to enable faster and more reliable software delivery.

---

## CI/CD (Continuous Integration / Continuous Deployment)
- **Continuous Integration:** Frequent code merges with automated testing  
- **Continuous Deployment:** Automatic deployment to production  
- Reduces manual errors and speeds up delivery  

---

## Additional Concepts Mentioned
- **Richardson Maturity Model:** Defines levels of REST API maturity  
- **Component vs Service Dependencies:** Services should depend on interfaces, not implementations  
- **Admin Processes:** One-time tasks like migrations should be separate  
