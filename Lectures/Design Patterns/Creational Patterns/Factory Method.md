#pattern #creationalPattern 

**Definition:** Define an interface for creating an object, but let the subclasses decide which class to instantiate. Factory method lets a class defer instantiation to subclasses.

![[Pasted image 20240525094338.png]]


```java
public enum FanType {
	TableFan, CeilingFan, ExhaustFan
}

public interface IFan {
	void switchOn();
	void switchOff();
}

public class TableFan implements IFan {}
public class CeilingFan implements IFan {}
public class ExhaustFan implements IFan {}

public interface IFanFactory {
	IFan createFan(FanType fanType);
}

public class TableFanFactory implements IFanFactory {}
public class CeilingFanFactory implements IFanFactory {}
public class ExhaustFanFactory implements IFanFactory {}

public class Main {
	public static void main(String[] args) {
		IFanFactory fanFactory = new CeilingFanFactory();
		IFan fan = fanFactory.createFan();
	}
}
```

**When to use:** If it is foreseeable that new ObjectTypes are added in the future. This approach allows to adhere to the Open-Closed-Principle. 

**Pros:** 
- Follows Open-Closed-Principle
- Easier to write UnitTests

**Cons:**
- Added complexity
