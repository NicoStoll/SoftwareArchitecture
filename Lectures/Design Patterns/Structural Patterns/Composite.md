#pattern #structuralPattern 

The composite pattern is a structural design pattern, that allows you to compose objects into tree structures to represent part-whole hierarchies. It lets clients treat individual objects and compositions of objects uniformly.

### Components of the Composite Pattern

**Component:** An interface that defines common operations for both simple and complex objects.
**Leaf:** A class that represents simple objects in the composition.
**Composite:** A class that represents complex objects that may contain children. It implements the component interface and manages child components.