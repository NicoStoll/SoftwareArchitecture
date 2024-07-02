
![[CleanArchitecture.png]]

- Core of the application --> **few changes, stable**
- Access/Dependencies always from outside to inside (layers may be skipped)
- Functions and data models may previously exist **independently of IT application**
- Technology only in outer layers --> technologies must be decided later
### Layers
1. **Layer 1:** Data model
2. **Layer 2:** Functions of the application, Tasks of the application according to the specification
3. **Layer 3:** Use Cases of the application
4. **Layer 4:** Infrastructure
5. **Layer 5:** Assembling the application


**To achieve the dependencies only pointing to inner layers it is often necessary to use [[Dependency Inversion]]**
