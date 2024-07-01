
- definition of the **domain model**
	- clearly defined domain dictionary (Pillar 1 : Ubiquitous Language)
	- simplified UML-class diagram
	- comments describing the behavior
- Implementation of the model
	- use a **clean architecture** (Pillar 2 : Strategic Design)
	- define domain level with entities, value objects and services
	- support with modules aggregates, factories and repositories (Pillar 3 : Tactic Design)
- Constantly refactor resulting implementation
	- overall preserve model **integrity**


### Pillar 1 : Ubiquitous Language
- identify the system's business domain
- create a domain model using the user's language
- discuss the model with the domain experts
- use the domain model as a basis of the system design
- identify subdomains and map them out to bounded contexts in the solution space

### Pillar 2 : Strategic Design
- Domain layer: Domain Model, Functions, Use Cases
	- Concepts of the business, business situation and business rules
- Application layer:
	- coordinates tasks and delegates work to domain objects
	- does not contain business rules or knowledge
	- state reflecting the task for users, but not on business situation
	- **can be omitted** if its tasks are accomplished in the domain layer
- Infrastructure: UI
	- Present information to the user
	- Receives input and interprets user commands
- Infrastructure: Technical Services
	- Comprises technical services (e.g. persistence, security or communications with other systems)

![[StrategicDesign.png]]

### Pillar 3 : Tactical Design

![[TacticalDesign.png]]