#pattern
- easily accommodate changes in requirements, technologies or environment without extensive work
- *characteristics:*
	- Modularity: loose coupling --> easy replacement or modification
	- Configuration-driven: configuration --> system behavior
	- plug-and-play: new functionalities through interfaces and extensions
- Actual Patterns: Micro Kernel

***Micro Kernel:***
Consists of the core system and plug-in components. The core system contains the minimal functionality needed to run the system. The plug-in components contain additional functionalities and are isolated and independent from each other. The core system keeps track of the functionalities via a registry.

![[Micro-Kernel-Pattern.png]]***Pros:***
- can react to changes in plug-in components while minimizing changes to the core system
- easier to deploy than layers architectures
- easier testing of each component in isolation

***Cons:***
- not highly scalable



***Sources:***

- [[https://priyalwalpita.medium.com/software-architecture-patterns-microkernel-architecture-97cee200264e]]