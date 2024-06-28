
![[DependencyInversion_Problem.png]]

**Problems with architecture above:**
1. Use Cases access the infrastructure (e.g. Database)
2. Controller accesses the Use Cases (**Possible, but introduces tight coupling**)

![[DependencyInversion_Solution.png]]

**Solution:**
1. Dependency Inversion: Sample Use Cases uses and interface. The interface acts as a so-called **outgoing port**
2. Controller uses an interface, that defines the possible Use Case calls. The interface acts as an **incoming port**

**Advantages:**
- Domain-Driven-Development
- Supports Testability: The Application **depends on interfaces instead of implementations** --> implementations can be mocked/exchanged
- Maps to SpringBoot-Architectures