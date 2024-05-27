#pattern #creationalPattern

**Definition:** A simple factory is a factory class which has a method that returns different types of an object based on a given input.

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

public class FanFactory implements IFanFactory {

	public IFan createFan(FanType fanType) {

		switch(fanType) {
			case FanType.TableFan:
				return new TableFan();
			case FanType.CeilingFan:
				return new CeilingFan();
			case FanType.ExhaustFan:
				return new ExhaustFan();
			default:
				throw new Exception('Type not recognized');
		}
	}
}
```


**Pros:**
- Abstraction of the fan creation
- Information hiding from the client

**Cons:**
- Addition of the Open-Closed-Principle if a new Fan is added since we need to change the 'createFan'-Method.