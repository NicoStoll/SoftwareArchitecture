
**Definition:**
- general, reusable solution for common design problems
- described on high level
- programming language independent
- may be combined

**Classification:**
- Creational:
	- [[Simple Factory]]
	- [[Factory Method]]
	- Abstract Factory
	- Builder
	- Prototype
	- [[Dependency Injection]]
- Behavioral:
	- Command
	- Iterator
	- [[Observer]]
	- Visitor
	- [[Strategy]]
	- Template
- Structural:
	- [[Adapter Pattern]]
	- Bridge
	- [[Composite]]
	- Decorator
	- [[Facade]]
	- Proxy
**Patterns separate concerns and give structure to coupling.**


**Dependency Inversion Principle vs. Inversion of Control vs. Dependency Injection**

| Dependency Inversion Principle                                                                                                                             | Inversion of Control                                                                                                                                                                                                                        | Dependency Injection                                                                                                                                                                                                           |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| - High level module should not depend on low-level modules --> both should depend on abstractions<br>- details should depend on abstraction not vice versa | - component registers itself with the framework, later called by the framework<br>- Third-party libraries define the  control flow rather than application-specific components<br>- **Hollywood principle:** Don't call us, we'll call you. | - Creation and injection of instances for abstractions a client depends on<br>- special application of IoC (for the creation of component)<br>- other applications of IoC: callbacks, scheduler, event loops, observer pattern |

