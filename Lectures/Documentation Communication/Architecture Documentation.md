
### Why Architecture Documentation
--> document what can not be found in the source code
#### Documentation
- System overview
- Architectural/Technology decisions
- Rationale for decisions
- Cross-cutting concerns
- Error/Problem locating
- Adapt to change

### Basic / Additional Documentation
--> ==**high risk --> more extensive documentation**==

| Basic                                                                                   | Additional                                                |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| Structure and interaction of Building blocks \| Source code \| Technical infrastructure | Detailing above aspects                                   |
| Basic assumptions, decisions, technologies, and concepts                                | For developers \| administrators \| managers \| customers |

### Best Practices
- **Tailor content** to the ==reader's knowledge level and needs==
- be clear and concise: simple language, no jargon, short sentences, no repetition
- Clear structure and flow, headings, subheadings and bullet points
- prefer ==active== voice over passive
- use examples to illustrate complex concepts
- use **diagrams, tables and screenshots** to complement text
- Maintain **consistency** in terminology, formatting and style
- Keep documentation **current**
- use appropriate tools: **style guides, grammar checkers, templates ([[arc42]])**

 #### [[Cross-Cutting Concerns]] describe:
 - [[Requirements]] 
 - Solution outline
 - Constraints 
 - Rationale
 - Risks
 - Rejected Alternatives

#### Interfaces
- Specify early
- Plan for change/versioning
- Use tools like **Swagger**

![[Documentation_Interface.png]]
#### Design Decision
- understand architecture decisions and their implications
- user a ==[[ADR]]==

#### Documenting with Diagrams
- ==7 +- 2 Rule== (Information humans can hold in short-term memory)
- avoid too large or complex diagrams --> rather break down hierarchically
- **Exception: architectural wallpaper**
- use standards: UML/BPMN
- Provide descriptions
- Provide legend if no standard

#### Configuration Management of Documentation
- Establish ==**version control** for documentation==
- **Change Log Entry** (Data and version, Author of changes, sections that were changed)
- periodically validate/review/improve guidelines


### Common Document Types
1. **Central architectural description** - architectural goals (vision), quality  requirements, views, decisions, patterns and additional, necessary information
2. **Architectural overview** - summary, minimum substitution for the complete description
3. **Document summary** - a list of all architecture-related documents
4. **Overview presentation** - set of slides
5. **Architecture wallpaper** - many aspects of the architecture on a single, very large output (too big to fit a computer screen, hence wallpaper)
6. **Guide for documentation** - explains the function and the structure of the documentation
7. **Technical information** - information about development methodologies, code conventions, build and tests