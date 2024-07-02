#pattern #behavioralPattern

The Observer pattern is a behavioral pattern, where the subject maintains a list of its dependents, known as observers. The observers are notified of any state changes, usually by calling one of their methods.

![[ObserverPattern.png]]


```java
public interface Observer { 
	void update(String message); 
}

public interface Subject { 
	void registerObserver(Observer observer); 
	void removeObserver(Observer observer); 
	void notifyObservers(); 
}

public class ConcreteSubject implements Subject { 
	private List<Observer> observers; 
	private String message; 
	
	public ConcreteSubject() { 
		this.observers = new ArrayList<>(); 
	} 
	
	@Override 
	public void registerObserver(Observer observer) { 
		observers.add(observer); 
	} 
	
	@Override public void removeObserver(Observer observer) 
		{observers.remove(observer); 
	} 
	
	@Override public void notifyObservers() { 
		for (Observer observer : observers) { 
			observer.update(message); 
		} 
	} 
	
	public void setMessage(String message) { 
		this.message = message; notifyObservers(); 
	} 
}

public class ConcreteObserver implements Observer { 
	private String name; 
	
	public ConcreteObserver(String name) { 
		this.name = name; 
	} 
	
	@Override public void update(String message) { 
		System.out.println(name + " received message: " + message); 
	} 
}
```