The <span style="color:rgb(255, 0, 0)">fundamental organization</span> of a system embodied in its <span style="color:rgb(146, 208, 80)">components,</span> their <span style="color:rgb(0, 112, 192)">relationships to each other</span> and to the <span style="color:rgb(255, 192, 0)">environment</span>, and the <span style="color:rgb(255, 0, 0)">principles</span> guiding its design and evolution.

![[SoftwareArchitecture.png]]

### Software Architecture as Part of the Software Lifecycle
![[SoftwareLifecycle.png]]

### Principles of Good Architecture
1. **useful:** fulfill functional and quality requirements
2. **stable:** reliable, mature, maintainable
3. **graceful:** well-structured design, great UX

**Good Software Architecture**
- Creates a meaningful ==division of components== (Abstraction from complex details: [[Principles]], Isolate [[Cross-Cutting Concerns]] )
- Shows that functional and quality [[Requirements]] will or can be fulfilled over the entire system
- Helps the stakeholders understand the system
- Specifies necessary implementation measures
- Defined ==design guidelines== to ensure conceptual integrity
- ==Documents== and provides rationale for ==design decision==

### Objectives and Benefits of Software Architecture

**Objectives:**
- Determine high-level system structure
- Select the central design paradigms
- Map functionalities to system building blocks
- Achieve quality requirements
- Support the creation, maintenance, and implementation of the system
- Help stakeholders to understand the system

**Benefits:**
- Ensure that requirements and quality goals are met
- Ensure a ==consistent== solution: similar problems are solved similarly
- Ensure ==understandability== of the system and design decisions
- Focus on system ==longevity== and facilitate system maintenance
- Support of the ==entire life cycle== of a software system
- Enable reuse

### Key Terms

![[KeyTerms_SA.png]]

**Building Block/Component**
“entity with **discrete structure**, such as an assembly or software module, within a
system **considered at a particular level of analysis**” (ISO25010:2011)

**Interface**
“shared boundary between two functional units, defined by various characteristics
pertaining to the functions, physical signal exchanges, and other characteristics”

- 'Contract' that components must abide to
- Well-defined access point to a component/system

![[Interface_Types.png]]
**Standard Interface**:  Caller and called adhere to the interface contract that is defined externally
**Independent Interface**: Caller and called have their own interfaces that are connected using an adapter
**Provided interface**: The called party defines the interface. This type of contract is used very often
**Required interface**: The caller defines the contract. This type is often used with frameworks


**Black Box vs. White Box**
![[BlackBoxWhiteBox.png]]

**(De-)Composition and Refinement**
Components can be further decomposed into subcomponents according to, e.g.: Important data types, Layers, Customer journey, smallest piece of self-contained functionality

**Stakeholder Concern:** what interests or bothers someone about a system/component (e.g. goals, interests, required functionalities, expectations, fears, need for regulation, ...).

[[Cross-Cutting Concerns]]: Impact many components of the system, therefore difficult to isolate. Often related to technical constraints or functionality that is required in many places (e.g. logging, persistence, caching)

**(Elastic) Scalability**
Scalability: Potential to increase performance. Scalability does not automatically improve performance but will allow you to do so. **Horizontal scaling vs. vertical scaling**

**Complexity**
Amount of human effort required to understand something in order to change or extend it

