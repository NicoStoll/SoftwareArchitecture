
# Exercise 1 (10 Points)
## a) Give 5 examples, how software architecture impacts quality attributes

- **Performance** - A Client-Server-Architecture distributes tasks between client and server. This can lead to optimized resource usage and improved response times
- **Scalability** - Microservice Architectures allow individual services to scale independently based on demand.
- **Testability** - Clean Architecture allows easier isolation and therefore testing of the core business logic
- **Security** - Zero Trust Architecture ensures that all access requests are authenticated, authorized and encrypted, leading to higher security
- **Maintainability** - Layered Architecture organizes the system into layers which can be developed and maintained independently.

## b) Give 3 examples why design decisions need to be explained

- **Team collaboration and understanding** - team should have an understanding of the rationale behind decisions. This promotes coherent implementation.
- **Ensure future maintainability** - Helps to understand the rationale behind decisions, making it easier to grasp trade-offs and potential impact of decisions.
- **Justify trade-offs to stakeholders** - Explaining to the stakeholders the trade-offs of an architecture decision, helps stakeholders understand benefits and compromises

## c) Why is it important to provide the requirements and rationale behind a design decision?

- **Ensure alignment with stakeholders needs** - by outlining the requirements, the design decision is clearly linked to the specific needs of the stakeholders
- **Justifying and defending design choices** - clear documentation of requirements and rationale helps justify the design choice to stakeholders
- **Informed decision making** - rationale behind design decision

# Exercise 2 (12 Points)

## Name 4 different types of interfaces and their contract. Explain each type and five an example for each

- **Standard Interface** - JDBC (JDBC provides a standard interface for database access in Java. The interface is defined externally by the JDBC API, which both the caller and callee adhere to)
- **Independent Interface** - Microservice Architecture with API Gateway (In a microservice architecture, different services may have their own interfaces. An API Gateway can act as an adapter that connects these independent interfaces, providing a unified point of entry) 
- **Provided Interface** - TomTom Navigation API (TomTom provides a defined interface for embedding maps and interacting with map data. Developers use this provided interface to integrate it into their applications)
- **Required Interface** - Inversion of Control (IoC) Containers in Spring Framework (In Spring the caller defined the required interface or contract, which the framework then adheres to by injecting the appropriate dependencies)

# Exercise 3 (12 Points)

## Explain the topics 'Architecture Description', 'Concern', 'Architecture Viewpoint', 'Architecture View', 'Model Kind' and 'Architecture Model' and their relationships from the following picture (ISO/IEC/IEEE 42010:2011)


![[IEEE_42010_2011.png]]
**Architecture Description**: a collection of artifacts that document the architecture of a system. It includes architecture views, architecture viewpoints, ...
**Concern**: . Concerns arise throughout the life cycle from system needs and requirements, from design choices and from implementation and operating considerations. A concern could be manifest in many forms, such as in relation to one or more stakeholder needs, goals, expectations, responsibilities, requirements, design constraints, assumptions, dependencies, quality attributes, architecture decisions, risks or other issues pertaining to the system.
**Architecture Views**: Addresses one or more of the concerns held by the system's stakeholders. The architecture view expresses the architecture of the system-of-interest in accordance with an architecture viewpoint.
**Architecture Viewpoints**: A specification of a whole system from the perspective of a related set of concerns. It defines the stakeholders, concerns and model kinds.
**Architecture Model**: An architecture model consists of one or more architecture models. An architecture model uses modelling conventions appropriate to the concerns to be addressed. These conventions are specified by the model kind governing a model.
# Exercise 4 (12 Points)

## Name and briefly describe the most important 6 tasks of a Software Architect according to iSAQB

- **establish business case** - consider costs and benefits, and business value from client perspective, create and evaluate economically viable solutions
- **design/select architecture** - select potential architecture from existing solutions (compare costs and benefits, consider integration with existing systems), choose technologies (reuse proven frameworks, libraries, ...), design the system and thereby its architecture (define interfaces and dependencies)
- **evaluate architecture** - Analyze and evaluate software architecture and architectural decisions(quantitative and qualitative assessment, adherence to requirements, identify and mitigate risks)
- **document architecture** - document and communicate architecture based on views, architectural patterns and cross-cutting concerns
- **guide & help implementation** - ensure compliance of the implementation, lead and guide developers
- **clarify requirements** - Identify, gather, clarify, refine and scrutinize requirements, identify contradictions in requirements

# Exercise 5 (14 Points)

## a) What is the 'System Context' and what are the sources that contribute to the influencing factors?

![[SystemContext.png]]
### System Context
= the part of reality that is relevant for the requirements of a system

1. **People** - (groups of) stakeholders
2. **Systems in operation** - other technical systems/hardware
3. **Events** - technical/physical
4. **Processes** - technical/physical/business
5. **Documents** - laws, standards, system documentation
## b) What is Conway's Law? Also give an example for it.

**Conway's Law:** Organizations which design systems … are constrained to produce designs which are copies of the communication structures of these organizations. (E.g. a system built by 5 teams will consist of 5 large building blocks)
## c) Draw a sketch of the Quality model from ISO 25010 with at least 3 quality characteristics (first level) and quality attributes (second level)

![[Quality_ISO25010.png]]