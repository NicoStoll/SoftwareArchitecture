
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
3. **Structured Design:** Design systems like engineering blue

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
