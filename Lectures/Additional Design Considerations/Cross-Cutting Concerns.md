![[CrossCuttingConcerns.png]]
- Impact the entire system
- result of fulfilling quality requirements
- cannot easily be separated into independent components

**Cross-Cutting Concerns**
1. **Authentication:** Determine the senders identity
2. **Authorization:** Grant rights based on identity
3. **Integrity:** Detect manipulation of data
4. **Confidentiality:** Restrict unauthorized data access
5. **Non-repudiation:** Authorship and validity of data
6. **Availability:** Precautions against accidental or deliberate system failure

### Reduce Complexity

Each problem has an intrinsic complexity that can not be reduced 
Approaches:
- **Abstraction:** A view of an object that focuses on the information relevant to a particular purpose and ignores the remainder of the information
- **Decomposition:** The process by which a complex problem or system is broken down into parts that are easier to conceive, understand, program and maintain

### Security

**Security Guidelines:**
- Use existing technologies -e.g. **JWT**
- Always use **HTTPS/TLS**
- Always **validate/filter** input to prevent SQL-Injections, XSS
- Always **validate** on the **server side**
- **Never store passwords** - always store the hashed + salted password

**Authorization:**
- JWT - encoded string that can be **decoded publicly** by everybody, represents a JSON-Map which contains at least
	- **Subject**
	- **Issue**
	- **Additional Payload**
- signed with a secret key --> server can check whether it has been untouched
- **expiration data** ensures that it cannot be misused for a long time

**Business Rules and Processes**
- Domain-specific: causal connections or conditional instructions (if X is finished, do Y)
- Business rules and processes are often implemented directly in the code (hard-coded)
	- may contain **complex knowledge**
	- distributed across many components --> low **maintainability**
	- simple changes become expensive to estimate
Better: **centralized, explicit declaration**
### Aspect Oriented Programming

[[Aspect Oriented Programming (AOP)]]

