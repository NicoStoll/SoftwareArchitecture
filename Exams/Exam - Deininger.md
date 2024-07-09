
# Question 1 - Patterns, Quality & Documentation (60 Points)

![[Pasted image 20240702192609.png]]

## The class instantiates the view. The view instantiates and sets the service. The service  accesses the repository. The repository uses mapper classes that convert the database-centric entity into the actual domain model classes. The domain model classes are the classes used by all layers.

## 1.1 Architecture Discussion

### The application described above is based on a layered architecture with a common data model used by all layers. What are the characteristics of such an architecture? (Name at least two characteristics)

- each layer encapsulates detail, and may provide an abstraction
- provides a service to the layer above
- never depends on a layer above
- **strict layering**: dependencies only between adjacent layers

### Please indicate the advantages and disadvantages of the above architecture (at least two pros and cons)

Pros:
- layers are independent (development - distribution of tasks)
- implementations are interchangeable
- no circular dependencies

Cons:
- additional overhead
- some changes may require changes in all layers

## 1.2 Architecture Evaluation (10 Points)

### Calculate the Martin-Metrics for the above application (please note, that the general dependencies have to be counted, too)

| Package        | Fan-in | Fan-out | Abstractness | Instability | Distance |
| -------------- | ------ | ------- | ------------ | ----------- | -------- |
| main           | 0      | 1       | 0            | 1           | 0        |
| gui            | 1      | 1       | 0            | 1/2         | -1/2     |
| domain.service | 1      | 1       | 0            | 1/2         | -1/2     |
| persistence    | 1      | 3       | 1/6          | 1/4         | -14/24   |
| common.model   | 5      | 0       | 0            | 0           | -1       |

### According to the metrics: Which is the most critical package, i.e. the one most resilient to change?

The common model has a Distance of -1, indicating it is the least balanced and most critical package. It is the most resilient to change, which is to be expected from the model.
### What does this mean for the process of creating this package and its classes? I.e. what should you pay attention to when designing this package?

- **Minimize change frequency** - Ensure classes are well thought out
- **Encapsulation and Modularity** - Ensure internals are well encapsulated, expose only what is necessary
- **Extensive Testing** - Implement comprehensive unit tests as well as integration tests ensuring every works as it should
- **Clear documentation** - Since this package is used in many different places it is important to provide clear documentation of public API and the intent behind design decisions
- **Design for extensibility**

## 1.3 Revision towards a 'Clean Architecture' (20 Points)

### The above application is to be redesigned into a “clean (onion| ports & adapters) architecture” as discussed in the lecture. First, in the (onion) diagram below, enter which of the previous packages should be in which (onion) layer (note that a layer can contain more than one package).


### Currently the CompanyService instantiates the SQLRepository like this:

```java
public class CompanyService { 
	private final SQLRepository repository; 
	
	public CompanyService() { 
		this.repository = new 
			SQLRepository("jdbc:sqlite:database/company.db"); 
	} 
	… 
}
```

### This contradicts the idea of a clean architecture. Why?

Dependency Inversion Principle (DIP): High level modules should not depend on low-level implementations

### Which design principle can be applied to solve this issue?

Dependency Injection (DI)


### Sketch a solution to this problem in Java code (only the  relationsship between CompanyService and SQLRepository has to be refactored and only the relevant code is required).


```java
package domain.service.ports.out
public interface Repository { 
	
}


package domain.service 
public class CompanyService { 

}

package persistence 
import 
public class SQLRepository { 

	
}

package main 
import 
import 
import 

public class Main { 
	public static void main(String[] args){ 
	
	} 	
}
```


## What are the main elements of Domain Driven Design and how does the newly refactored architecture fit in?

### Main ideas


### Architecture compliance


## 1.5 Cross-cutting concerns (5 points)

### What are cross-cutting concerns in general and what are the challenges?


### State a possible use case for a cross-cutting concern in the previous application.


### Name one programmatic way in which cross-cutting concerns are being implemented.

# 1.6 Architecture Quality (8 Points)

### Give an example of a 'Growth Scenario' for the previous application


### What is the advantage of using a quality tree to build such a scenario?


### How could the Martin-Metrics help in designing such a scenario?


### What quality aspect(s) does your scenario cover?

