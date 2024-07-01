
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
