- distribute computation, data and processing across multiple interconnected nodes to achieve ***scalability, fault tolerance and performance***
- Characteristics:
	- Scalability: handle varying load
	- Fault tolerance: operational despite failures
	- Communication protocols: inter-node communication and synchronization
- Actual patterns:
	- Broker
	- Microservices
	- Event-Driven Architecture (EDA)


***Broker***

![[Broker-pattern.png]]




***Microservices***

*Definition:* Microservices: A complex application software is built from
independent processes that communicate with each other using language independent programming interfaces . The services are largely decoupled and perform a small task . (Definition based on Eberhard Wolff, dpunkt, 2018)

![[Microservice-architecture.png]]

Microservices can be individually:
- developed
- deployed
- operated
- changed/replaces
- scaled

*Best practices:*
1. Decompose by domain: Design microservices around specific business domains or subdomains to ensure clear ownership and responsibility
2. Single Responsibility Principle (SRP): Each microservice should have a single responsibility, focusing on one aspect
3. Loose coupling: Minimize dependencies between microservices to allow for independent  development, deployment and scaling
4. API contracts: Define clear and stable APIs for communication between microservices, enabling interoperability and versioning

***Pros:***
- changeability and flexibility
- decouple technology decisions
- multiple versions of a service can coexist
- good scalability
- fast development

***Cons:***
- All cons of distributed computing (network latency, outages, bandwidth limitations)
- more sophisticated error handling
- more complex deployment
- dependency resolution at runtime may cause hard to find errors

