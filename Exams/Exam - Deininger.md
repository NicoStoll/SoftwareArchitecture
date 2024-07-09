
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
package domain.service.ports.out;
public interface Repository { 
	
}


package domain.service;
public class CompanyService { 

	private final Repository repository;

	public CompanyService(final Repository repository) {
		this.repository = repsority;
	}
}

package persistence;

import domain.service.ports.out.Repository;
public class SQLRepository implements Repository { 

	
}

package main;
import domain.service.ports.out.Repository;
import domain.service.ComparnyService;
import persistence;

public class Main { 
	public static void main(String[] args){ 

		Repository repo = new 
			SQLRepository("jdbc:sqlite:database/company.db");
		CompanyService service = new CompanyService(repo);
	} 	
}
```


## What are the main elements of Domain Driven Design and how does the newly refactored architecture fit in?

### Main ideas

- **Ubiquitous Language** - identify the Business Domain, comprise a Domain Dictionary and Build the Domain model from that, use the Domain Model as the basis for your design
- **Strategic Design** - The high-level organization of the system, which includes identifying the main components and their interactions. This often involves dividing the system into Bounded Contexts and mapping their relationships
- **Tactical Design** - The detailed design within a Bounded Context, including entities, value objects, aggregates, repositories, factories and services.

### Architecture compliance

- **Ubiquitous Language** - the refactored architecture uses domain-specific terminology in class names and methods, promoting a clear and consistent language
- **Strategic Design** - The separation of concerns in the architecture aligns with the concept of Bounded Context
- **Tactical Design** - The use of interfaces and dependency injection promotes flexibility and adheres to DDD principles.

## 1.5 Cross-cutting concerns (5 points)

### What are cross-cutting concerns in general and what are the challenges?

Cross-cutting concerns are functionalities that affect multiple parts of a system and are typically needed in many places within an application. These concerns cannot be neatly encapsulated in a single module or layer, because they cut across the system's primary decomposition.

Examples
- **Persistence**
- **Logging**
- **Authentication**
- **Authorization**
- **Error Handling**

Challenges:
- **Code Duplication:** The same functionality needs to be implemented in multiple places
- **Maintainability**: Changes to cross-cutting concerns require updating all places where to code is used
- **Consistency**
- **Tight Coupling**: Business logic can become tightly coupled with these concerns, making the system harder to understand and modify
### State a possible use case for a cross-cutting concern in the previous application.

Persistence, Logging

### Name one programmatic way in which cross-cutting concerns are being implemented.

Aspect Oriented Programming (AOP) (with AspectJ in Java)

# 1.6 Architecture Quality (8 Points)

A quality tree is a visual representation of the quality attributes of a system, helping to organize and prioritize the various quality requirements. It breaks down high-level quality attributes into more detailed and specific aspects, facilitating a clear understanding and assessment of the systems behavior.

Key Component:
- Root/Intermedia Nodes: attributes or sub-categories (Performance, Security, Response Time, Throughput, ...)
- Lead Nodes: Concrete Scenarios or requirements related to the upper nodes
	- Usage: Behavior under normal runtime
	- Exploratory: Behavior under extreme situations
	- Growth: Maintaining and evolving the system

### Give an example of a 'Growth Scenario' for the previous application

Type: Growth

Trigger: Implementing Multi-Factor Authentication (MFA) due to security concerns. Because of data breaches implementation of additional security measures is prompted.

Expected System Response: Introduce MFA for user logins, ensuring that sensitive operations require verification via email or SMS code, enhancing user account security.

Priority: High

### What is the advantage of using a quality tree to build such a scenario?

- **Clarity and structure:** Clear and structured way to identify and document quality attributes, breaking them down into detailed and actionable scenarios.
- **Prioritization:** It helps in prioritizing quality attributes based on their importance and impact on the system, ensuring that critical aspects are addressed first.
- **Comprehensive Coverage:** By systematically categorizing attributes and scenarios, it ensures comprehensive coverage of all relevant quality concerns.
- **Communication:** Better communication among stakeholders, including developers, business analysist, and domain experts.
- **Consistency:** Attributes implemented across the whole system

### How could the Martin-Metrics help in designing such a scenario?

**Stability:** Ensuring low instability means the modules are less likely to break, when changes are made. For the growth scenario, ensuring that Services have a low stability would help in safely adding new features like MFA without affecting existing functionalities.

**Abstractness:** Designing the system with a higher level of abstractness in key modules allows for easier extension. For the growth scenario, having a well-defined interface for Authentication that can be implemented for MFA or other form can facilitate growth

**Distance from Main Sequence:** Measures the balance between abstractness and stability. For the growth scenario, ensuring the Services are well balanced between abstractness and stability ensures ease of extension and integration.

### What quality aspect(s) does your scenario cover?

Security
- Authenticity

