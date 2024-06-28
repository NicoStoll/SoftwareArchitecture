
**Requirement:** Condition or capability that must be met or possessed by a system to satisfy an agreement, standard, specification or other formally imposed documents.

**Types:**
- Functional Requirement
- Quality Requirement
- **Constraint:** Externally imposed limitation on system requirements, design or implementation or on the process used to develop or modify a system

![[SystemContext.png]]
### Architectural Uncertainty
- inherent uncertainty in requirements - vague/ambiguous, changing
- Architects can manage this by
	- Providing and regularly getting stakeholders feedbacbac

### System Context
= the part of reality that is relevant for the requirements of a system

1. **People** - (groups of) stakeholders
2. **Systems in operation** - other technical systems/hardware
3. **Events** - technical/physical
4. **Processes** - technical/physical/business
5. **Documents** - laws, standards, system documentation

### Influencing Factors
- are considered **holistically** --> mutual interdependencies, conflicts, ...
- viewed from **long-term perspective**
![[InfluencingFactors.png]]
#### Organizational Factors
- company structure
- project team structure
- decision makers
- Partnerships
- Internal vs. External Development
- Commercial product vs. Internal usage
- **Standards:** Process model, Quality standard, Test, Tools
- **Resources:** Contract (fixed-price), Time schedule and release plan, Budget
- **Legal:** Liability, Privacy Laws, data protection, ...
**Conway's Law:** Organizations which design systems … are constrained to produce designs which are copies of the communication structures of these organizations. (E.g. a system built by 5 teams will consist of 5 large building blocks)

#### Product Related Factors
- **Functional Requirements**: Describe desired functionalities
- **Quality Requirements:** describe quality attributes of the system
--> Quality requirements might contradict project goals or each other
--> architecture can not be designed without essential quality requirements

#### Technological Factors
- Software-Infrastructure
- Programming Guidelines
- Programming Language
- Hardware-Infrastructure
- Reference Architectures
- Libraries, Frameworks and Components

### Quality - ISO 25010
![[Quality_ISO25010.png]]

#### Correlation and Trade-Offs

![[Quality_CorrelationTradeoffs.png]]