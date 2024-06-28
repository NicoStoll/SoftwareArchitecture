#SOLID #Design 

### Single Responsibility Principle (SRP)
= Each component is responsible for only one clearly defined task
- contains only functions directly contributing to this task
- encapsulates this functionality
- **Gather together the things that change  for the same reasons. Separate those things that change for different reasons.**

### Open-Closed Principle (OCP)
= Components should be open for extension but closed for modification
- extend behavior/features without changes to source code
- no 'side effects' from future extensions
- changes do not require modifications to existing users of this component
![[OpenClosedPrinciple.png]]

### Liskov's Substitution Principle (LSP)
= an object of a superclass shall be replaceable with objects of its subclasses
- derived classes can be used instead of superclass **'as is'**
- classes violating the LSP might use inheritance incorrectly or change the semantics of the call
![[Liskov_Violation.png]]
### Interface Segregation Principle (ISP)
= Clients should not be forced to depend on method they do not use. Multiple small and specific interfaces are better than a single, large one

### Dependency Inversion Principle (DIP)