
### How to start

- use an **iterative | incremental | view based** approach
- decide on a method
- Focus on four [[iSAQB-Views]]
- define a domain model
	- precise [[Domain Dictionary]]
	- simplified UML-class diagram
	- comments describing the behavior
- **Logical Design First**: Start with a logical design, do the technical mapping afterwards
- **Direct mapping**: the structure of the design should relate closely to the structures of the problem domain

### Design Methods - Overview
1. Hierarchical: Top-down/Bottom-up decomposition
2. **Stepwise refinement**: Decompose functions
3. **Structured Design:** Derive design from Information Flow
4. **Structured Analysis and Design Technique (SADT):** Design System like engineering blueprints
5. **Object Oriented Design (OOD):** Modeling the problem domain in terms of objects and operations performed upon them
6. [[Domain Driven Design]] (DDD)
7. **Service Oriented Architecture (SOA):** Construct the system by using many (small) services that can be obtained from one or more providers
8. **Event Driven Architecture (EDA):** Construct the system reacting on receiving one or more event notifications

### Top Down Design
- Start: Vision of the complete system
- Proceed: Decompose into smaller problems

| Advantages                                     | Disadvantages                                 |
| ---------------------------------------------- | --------------------------------------------- |
| General understanding of the problem           | (Possibly) difficult integration at the end   |
| Hardware/programming language **independence** | existing (partial) solutions might be ignored |
| Focus on abstract solution                     | Certain problems might be identified to late  |
| Consistent responsibilities and interfaces     | Late feedback if suitable                     |
| Design is visible in the product               |                                               |

 ### Bottom Up Design
- Start: Libraries, sub functions, domain classes
- Proceed: Assemble partial solutions | subsystems

| Advantages                           | Disadvantages                                              |
| ------------------------------------ | ---------------------------------------------------------- |
| Reuse of existing components         | Includes unneeded parts --> increases complexity           |
| Allows incremental testing           | Focuses on technical factors instead of users requirements |
| Stepwise integrations                | (possible) danger of premature optimization                |
| Starting point are real sub-problems | Danger of uncontrolled growth                              |
|                                      | Design is not visible in the product                       |

### Hierarchical Decomposition

- always achieve loose coupling and high cohesion
- Apply [[SOLID]]-Principles
- Design in iterations
- Reuse established and proven structures
- Check and evaluate alternatives

![[HierarchicalDecomposition.png]]
