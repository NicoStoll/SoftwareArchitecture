#important #Design #principles

## Information Hiding Principle
- Encapsulating complexity in components improves **flexibility, stability, testability and understandability**
==Treat components as 'Black Boxes':==
- Hide internals from clients
- No direct access to internal data --> only through defined interfaces
- expose only what is needed

## Separation of Concerns
- **Objective: Manage different problems separately**
- Domain, sub-domains, sub-tasks, ...
- Persistence, logic, behavior, presentation, ...
==Split complex systems according to responsibilities==
**Separation of Concerns + Information Hiding --> Modularity**
### Modularity
Module:
- Encapsulate responsibilities
- Expose well defined interfaces only
- Can be **developed, maintained and tested independently**
- Objective: Can be **replaced without side-effects**

## Loose Coupling
- **Objective: Few, well-defined, well-structured, and explicit dependencies, between modules**
- Components interact with each other, each dependency increases complexity
- Aim: Keep number of dependencies low, keep dependencies simple
[[Coupling - Types]]

Pros:
- easier to comprehend
- easier to use
- easier to replace
- more flexible
- Changes are local, NOT global

![[LooseCoupling.png]]
### Tactics to Reduce Coupling

1. General
	- Temporal and data dependencies are mostly due to functional dependencies
	- Apply design principles and patterns
	- Define concrete dependencies only at runtime or installation time (defer building)
2. Structural Dependencies
	- Polymorphism, delegation
	- [[Facade]], Decorator Pattern
3. Instantiation dependencies
	- [[Simple Factory]], Proxy Pattern
	- [[Dependency Injection]]
4. Call dependencies
	- Messaging, with asynchronous
	- Avoid cyclical relationships
	- Restrict communication
	- Use abstraction [[Designing Interfaces]]
	- Use intermediaries e.g. adapters, brokers, proxies
5. Data or data type dependencies
	- Data replication, event sourcing
	- Standardized data structures
6. Time dependencies
	- Messaging, Events
	- [[Observer]]
7. Location dependencies
	- Registry, Repository
8. Dependencies on libraries and frameworks
	- [[Dependency Inversion]]
	- Inversion of Control

## High Cohesion
- **Objective: group components with related dependencies together within a module**
- determining cohesion depends on the **context and domain**
- A cohesive component:
	- ==solves a single problem==
	- contains strongly ==related functionalities==
	- accommodates interrelated sub-components
Separation of Concerns + Loose Coupling --> High cohesion

![[Cohesion.png]]
## KISS - Keep it simple, stupid!
- the architecture/solution should only ever be as complex as necessary, however not oversimplified
- the architecture should **adequately** address known requirements and incorporate appropriate foresight into the design

## YAGNI - You ain't gonna need it
- Only actual requirements are considered in the design
- even known, but unclear requirements should only be considered once they have been defined. This preserves the solution space

### DRY - Don't repeat yourself
**Goal:** Duplication only when wanted/required
**Downside:** DRY leads to increased coupling

## Robustness Principle - Postel's Law
**Goal: Tolerate errors**
Be precise and strict, when designing your components, BUT
- tolerate errors in other components
- be able to recover from errors
- degrade gracefully

## Abstraction
Identify useful generalizations
- Emphasize common properties or functionalities
- Omit/Hide unnecessary details
**Do not depend on implementations, depend on abstractions**
![[Abstraction.png]]
## Conceptual Integrity
**Goal:** Clear and recognizable concepts
E.g. Unix - Everything is a file, SQL - all data resides in a table

## Principle of least astonishment
System should behave in a way that minimizes confusion and surprise for its users. This is achieved with these key concepts:
- **Intuitive Design:** system should behave as users expect it to
- **Consistency:** consistent behavior across the whole system
- **Predictability:** Similar conventions and patterns make users quickly understand the system (e.g. standard icons, common terminology)