#metrics #important
### **Abstractness** of a package
= ratio of the number of **abstract classes** in the analyzed package **to the total number of classes** in the package

$$A=\frac{Classes_{abstract}}{Classes_{total}}$$



A = 0 --> completely concrete package
A = 1 --> completely abstract package

### **Fan-in & Fan-out** 

**Fan-in / Afferent Coupling** - the number of classes outside this package that depend on classes in this package, indicator for the **responsibility** of the package

**Fan-out / Efferent Coupling** - the number of ==classes within this package== that depend on classes outside the package. Indicator for the **independence** of the package
![[FanInFanOut.png]]

### **Instability** 
= indicator of the package's resilience to change
$$I=\frac{f{out}}{f_{out} + f_{in}}$$
I = 0 --> a completely stable package (i.e. many incoming / few outgoing dependencies)
I = 1 --> a completely instable package (i.e. many outgoing /few incoming dependencies, possibility of easy changes)


### **Distance from the Main Sequence

![[MartinMetrics.png]]
- the perpendicular **distance of a package** from the idealized line in the graph
- indicator of the packages balance between abstractness and stability
- A package squarely on the main sequence is **optimally balanced** with respect to its abstractness and stability

$$D=| A + I - 1 |$$
D = 0 --> a package that is coincident with the main sequence
D = 1 --> a package that is as far from the main sequence as possible