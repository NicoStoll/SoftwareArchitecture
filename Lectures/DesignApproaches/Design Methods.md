
![[iSAQB_ArchitectureViews.png]]


### Context View
- the system being designed is depicted as a black box
- **external actors** (e.g. systems, users)
- all interfaces to the outside world
	- Interface **Type**
	- Communication Protocol
	- Communication Pattern (sync/async, push/pull, ...)
- Relevance:
	- Entry point and overview for the system being designed
	- Overview of the most important use cases from an external perspective

![[ContextView.png]]
### Building-Block View
- explains the static decomposition of the system into building-blocks (**components, sub-systems, partitions, packages, classes, procedures, functions, ...**)
- describes building blocks and their relationships (**interfaces, dependencies, associations, relations, ...**)
- contains static aspects of the system
- Relevance:
	- Support PM with defining work packages
	- Helps stakeholders to understand the system
![[BuildingBlockView.png]]

### Deployment View
- Deployment of **run-time** elements to hardware components
- Logical channels + physical channels they are based upon
- Technical components and their run-time attributes such as availability
- Capacity of networks and memory
- Relevance:
	- Communicate with operations
	- Configure and administer the run-time environments
	- Recognize bottlenecks, calculate costs, identify risks
![[DeploymentView.png]]

### Run-time View
- Building blocks participating in execution of a use case
- How the system components interact at runtime
- which processes and threads there are, if applicable
- Relevance:
	- Help developers understand the system
	- Communicate with operations
