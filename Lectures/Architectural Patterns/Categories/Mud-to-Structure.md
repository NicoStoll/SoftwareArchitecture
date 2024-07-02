#pattern 

- transform complex, unstructured set of requirements  into a well-organized and modular system architecture
- ***Characteristics:***
	- Separation of concerns: Break down the system into components with distinct responsibilities
	- Design patterns adoption: introduce established design patterns to address recuring design problems
- Actual patterns:
	- Layered Architecture
	- [[Clean Architecture]] (Onion, Hexagonal, Ports and Adapters)
	- Pipes and Filters
	- Micro Kernel


***Layered Architecture***
- Each layer 
	- encapsulates details, may provide abstraction
	- provides services to layer above
	- never depends on a layer above
- dependencies ==only between adjacent layers (for strict layering)==
	- usage directed from upper to lower layer
	- communication in both ways

***Pros:***
- layers are independent (development - distribution of tasks and production - installation and maintenance)
- implementations are ==interchangeable==
- unidirectional dependencies (no circular dependencies)
- easy to understand

***Cons:***
- additional overhead
- loose layering: allow skipping of layers, BUT increases dependency
- some changes may require changes to ALL layers
![[Layered_Architecture.png]]

Separation of concerns:
- Manage different problems separately (persistence, logic, behavior, presentation)
- Divide the code into components that can perform a specific task independently
→ interface segregation
→ single responsibility

Example: ISO OSI model

![[ISO-OSI-model.png]]

***Pipes and Filters***

***Pipes:*** transport data/messages between filters and can buffer data
***Filters:*** processing unit, unaware of other filters. Transform, aggregate and manipulate data

![[Pipes-and-Filters.png]]

***Pros:***
- simple dependencies
- flexible
- easily scalable
- filters can be developed independently

***Cons:***
- difficult error tracking and handling
- buffers might overflow
- sharing global data might be difficult



==***Ports and Adapters (Hexagonal Architecture)***==

**Core Domain/Domain Logic:** Contains the business logic and application rules. This core should be independent of external technologies

**Ports:** Ports are interfaces that define, how the core domain interacts with the outside world. They serve as an entry point for requests (**incoming ports**) and exit points for sending data (**outgoing ports**)

**Adapters:** Adapters are ==implementations of the ports== that facilitate communication between the core domain and external systems or interfaces


![[PortsAndAdapters.png]]

