
# Question 1 - Patterns, Quality & Documentation (60 Points)

![[Pasted image 20240702192609.png]]

## The class instantiates the view. The view instantiates and sets the service. The service  accesses the repository. The repository uses mapper classes that convert the database-centric entity into the actual domain model classes. The domain model classes are the classes used by all layers.

## 1.1 Architecture Discussion

### The application described above is based on a layered architecture with a common data model used by all layers. What are the characteristics of such an architecture? (Name at least two characteristics)


### Please indicate the advantages and disadvantages of the above architecture (at least two pros and cons)


## 1.2 Architecture Evaluation (10 Points)

### Calculate the Martin-Metrics for the above application (please note, that the general dependencies have to be counted, too)

| Package        | Fan-in | Fan-out | Abstractness | Instability | Distance |
| -------------- | ------ | ------- | ------------ | ----------- | -------- |
| main           |        |         |              |             |          |
| gui            |        |         |              |             |          |
| domain.service |        |         |              |             |          |
| persistence    |        |         |              |             |          |
| common.model   |        |         |              |             |          |

### According to the metrics: Which is the most critical package, i.e. the one most resilient to change?


### What does this mean for the process of creating this package and its classes? I.e. what should you pay attention to when designing this package?



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

### Which design principle can be applied to solve this issue?


### Sketch a solution to this problem in Java code (only the  relationsship between Company )