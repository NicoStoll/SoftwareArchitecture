- not a single entity - it is a composite of multiple attributes
- Quality attributes describe certain quality aspects (e.g. **performance, security, maintainability, usability**)
- quality attributes are often organized hierarchically
- top-level attributes (e.g. maintainability) are broken down into **sub-attributes** (e.g. modularity, testability)

### Quality Model - ==ISO25010==

![[ISO25010.png]]

### Quality Tree

Quality model instance for a specific system
- selects relevant attributes
- defines **scenarios** for attributes

**Scenario -** System Behavior in Response to Stimuli
- **Types** of behavior
	- **Usage**: Behavior during normal runtime
	- **Exploratory**: Behavior in extreme situations
	- **Growth**: Maintaining and evolving the system
- **Trigger** and the expected system response
- Affected quality attribute
- Priority
![[QualityScenario.png]]


### Evaluation with Prototyping
- (Strict) Prototype: Evaluation of different approaches
	- early feedback from stakeholders
	- Early quality analysis and assessment
- **Demonstration** prototype: Acquisition
- **Laboratory sample:** Design questions
- **Pilot system:** Product core

### Evaluation with Metrics
[[Martin Metrics]]


#### Software Metrics Examples
- Requirements
	- Rate of change
- Source Code
	- ==Coupling and cohesion==
	- Size in lines of code ==(LoC)==
	- Complexity (cyclomatic complexity)
	- Dependencies between building blocks
- Failure
	- Mean time between failures
- Software process
	- Number of implemented/tested features over time
	- Meeting time in relations to working time
	- Number of managers, developers, testers
- Test
	- Number of tests
	- ==Test coverage==
- Design
	- Dependencies
	- Abstraction
	- Stability
	- Distance