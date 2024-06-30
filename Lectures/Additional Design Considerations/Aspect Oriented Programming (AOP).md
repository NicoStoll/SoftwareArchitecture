Sometimes a use case is 'scattered' across several modules (e.g. **logging, security policies, monitoring**)
--> AOP tries to solve this by collecting this scattered code into **Aspects**

**Aspect** defines
- **Pointcuts:** regular expressions identifying method calls during the execution
- **Advices:** actions which are executed, when a pointcut is reached
	- **Before/After** a method is executed
	- **Instead** of the original method --> bug fixing of libraries

![[AOP_1.png]]![[AOP_2.png]]
![[AOP_3.png]]