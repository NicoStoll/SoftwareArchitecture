Sometimes a use case is 'scattered' across several modules (e.g. **logging, security policies, monitoring**)
--> AOP tries to solve this by collecting this scattered code into **Aspects**

**Aspect** defines
- **Pointcuts:** regular expressions identifying method calls during the execution
- **Advices:** actions which are executed, when a pointcut is reached
	- **B