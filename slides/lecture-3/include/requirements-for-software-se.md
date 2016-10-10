class: center, middle
# Requirements for Software Security Engineering

---
# Customer Knows Best!\*

![business-analyst](https://s-media-cache-ak0.pinimg.com/564x/a6/c1/62/a6c162f649bd64050235f624b0972dce.jpg)

.footnote[
\*or do they?
]

---
# Alice must surely know...

![dilbert-requirements](http://assets.amuniversal.com/3c9aa7b06d5101301d7a001dd8b71c47)

---
class: middle
# [NIST SP 800-160 SSE](http://csrc.nist.gov/publications/drafts/800-160/sp800_160_final-draft.pdf)
## Stakeholder Needs and Requirements Definition Process\*
- _The purpose of the Stakeholder Needs and Requirements Definition process is to .red[define the stakeholder requirements] for a system that can provide the capabilities needed by users and other stakeholders in a defined environment._

.footnote[
\*ISO/IEC/IEEE 15288-2015
]

---
class: middle
# [NIST SP 800-160 SSE](http://csrc.nist.gov/publications/drafts/800-160/sp800_160_final-draft.pdf)
## System Requirements Definition Process\*
- _The purpose of the System Requirements Definition process is to .red[transform the stakeholder, user- oriented view of desired capabilities into a technical view of a solution] that meets the operational needs of the user._

.footnote[
\*ISO/IEC/IEEE 15288-2015
]

---
class: middle
# Stakeholder Needs and Requirements

## Litmus test
- Even if you did not build the software the stakeholder will still have this need!
- They are located in the [environment of operation for the system-of-interest\*](https://robinagandhi.github.io/swa/slides/lecture-1/systems-security-engineering.html#15)

.footnote[
\* Michael Jackson, [The Meaning of Requirements, 1996](http://mcs.open.ac.uk/mj665/aserqts5.pdf)
]
---
class: middle
# Fitness for Purpose
## Software is built for a purpose
- It will fail if either:  
1. Designer has inadequate understanding of the purpose  
1. Software is used for a purpose different than originally designed for  

## Inadequate understanding of the purpose leads to poor quality software

???
# When will a designer have inadequate understanding of the purpose?

1. Software is too complex, designer does not know for sure if software will fulfill it purpose
1. Designer does not have the knowledge or experience
1. Customer does not clearly know the purpose or express it
1. Purpose becomes apparent later.
1. Deliberate attempt to make the software not fulfill its purpose


---

class: middle
# .red[User stories] - Agile, XP, SCRUM
## .blue[How] and .green[why] and would .orange[someone] use software?
- Scenarios
- They are about user needs
- [Informal](https://www.agilealliance.org/glossary/three-cs/), [Card, Conversation and Confirmation](http://ronjeffries.com/xprog/articles/expcardconversationconfirmation/)
.top-right[
![card](http://www.jamieclouting.co.uk/wp-content/uploads/2012/03/card-front-300x225.jpg)
]

---

![userstories](http://butlerhouse.net/wp-content/uploads/2014/09/user-story-asteroids.jpg)

---
class: middle
# .red[Use cases] -  OOP, UML
## .green[Why] and .blue[how] would .orange[someone] use software?
- Goal-driven Scenarios
- They describe system behavior to fulfill user needs
- Several [templates](http://alistair.cockburn.us/Basic+use+case+template) available for [use cases](http://alistair.cockburn.us/Structuring+use+cases+with+goals)  
  .red[Purpose] = build requirements  
  Contents = have consistent prose  
  Plurality = include multiple scenarios per use case  
  Structure = be semi-formal  

.top-right[
![case](http://www.it2051229.com/data_solutions/sysanaldesign/figure1.png)
]
---
class: center, middle
# [What is Requirements Engineering?](http://www.cs.toronto.edu/~sme/RE01/)

.footnote[
See notes (hit `p`) for definition
]

???
# Requirements Engineering
- Requirements Engineering (RE) lies at the heart of software development.
- RE is concerned with identifying the purpose of a software system, and the contexts in which it will be used.
- Hence, RE acts as the bridge between the real world needs of users, customers, and other constituencies affected by a software system, and the capabilities and opportunities afforded by software-intensive technologies.
Source: http://www.cs.toronto.edu/~sme/RE01/

---
class: middle
# Stakeholder Requirements

## These requirements are about .red[relationships] in the application domain
- They are not about the software system or the shared interface with the software system
- They are effects in the application domain that the customer wants the machine to guarantee

---
class: middle
# Stakeholders Requirements

## Expressed in two moods
- .red[Optative]: expresses a wish (R)   
Desired condition over the phenomena of the environment
- .red[Indicative]: expresses things existing in the problem world (D)   
Given properties of the environment

---
class: middle
# System Requirements

## Expressed in a single mood
- .red[Optative]: expresses a wish, Specification (S)  
Desired condition over the shared phenomena at the interface between the system and the environment

---

class: middle
# Problem Frames
.footnote[
Allows focus on `problems` to be solved.
]
---
class: middle
# Problem Frames
## Frame Diagrams
.left-column[
- Plain rectangles denote given domains (things that already exist)
- A rectangle with a single vertical stripe denotes a designed domain
- A rectangle with a double vertical stripe denotes the machine to be developed
- Requirements are denoted with a dashed oval
]
.right-column[
![legend](images/legend.svg)
]

???
- Problem frames are described by frame diagrams, which basically consist of rectangles and links between these
- The task is to construct a machine that influences the behavior of the problem domain it is integrated in
---
# Problem Frames
## Frame Diagrams
.left-column[
- The connecting lines represent interfaces that consist of shared phenomena   
- A dashed line represents a requirements reference to a domain
- A dashed arrow shows that it is a constraining reference  
- Everything tangible is solid,intangible is dashed.
]
.right-column[
![legend](images/legend.svg)
]

---
class: middle
# Problem Frames

- The machine solves a problem in the application domain (part of the world)
- The machine and the application domain interact at an interface of shared phenomena (events, states)
- The requirement adds a constraint to the application domain’s intrinsic properties or behavior

![legend](images/problem-frame.svg)
---
class: middle
# Problem Frame Example

- A PC user wants to analyze the messages in the   
mail client’s mailbox.
- The messages for each correspondent are concatenated  
in one file. The mailfiles are all in one directory
- The analysis report has a specified format, with   
detail lines in order by correspondent name
- The analysis report will also show statistics on volume, size   
and frequency of incoming messages, time taken to reply

.footnote[
Source: Problem Frames, Addison Wesley, 2001
]

---
class: middle
# Context Diagram
![example](images/example.svg)

.footnote[
Recap: Requirements are about .red[relationships] in the application domain
]

---
# Problem frames
## Relationships
.left-column[
- Annotation .red[D!{E3}] means Domain D initiates the observable phenomena E3
- Example:   
```  
a: MF! {MsgDir, File, Char}
```
Domain `MF` initiates observable phenomena `MsgDir, File, Char` on interface `a`
]
.right-column[
![example](images/example.svg)
]
---
class: middle
# Frame Components
.left-column[
- .red[R: Requirements]  
What the customer wants to be true in terms of (c, d)
- .red[D: Domain Properties]   
What we know to be true in the domain
- .red[S: Specification]  
How we want the machine to behave at interface (a, b)  
]

.right-column[
![example](images/example.svg)
]
---
class: middle
# Correctness argument
## S &#x2192; D, R  
- The argument should adequately make _requirements_, _specifications_ and _domain descriptions_ fit together

---
# Correctness argument
## Creating (R) is not enough !!
- Creating descriptions of the environment (D) and specification (S) helps our comprehension and provides basis for validating the requirements

--

## R is fulfilled
- Unless D or S is Insufficient \*
- Unless D or S is Malicious \*
- Unless D or S is Incorrect \*

.footnote[
\* Eliminative Induction
]
---
class: middle
# Fitness for Purpose: S &#x2192; D, R

## Under constrained behavior
- (S, D) lacks constraints to fulfill (R)  
E.g.: Buffer overflows, Unauthorized physical/network access

--

## Over constrained behavior
- (S, D) includes constraints such that (R) CANNOT be fulfilled  
E.g: 8 char password only, No access allowed

---
class: middle
# Problem Frames
![annotated](images/example-annotated.png)

---

class: middle
# How to systematically reason about these issues?
- Solution: Abuse frames

.footnote[
Technical Report No: 2003/10, [Analysing Security Threats and Vulnerabilities Using Abuse Frames](http://mcs.open.ac.uk/mj665/Abuse00.pdf), L.Lin, B.A.Nuseibeh, D.C.Ince, M.Jackson, J.D.Moffett, October 2003
]


---
class: middle
# Abuse Frame
![af](images/abuse-frame.png)

## Abuse argument
- The malicious machine specification (MS), satisfies the vulnerability conditions (v(D)), to achieve the anti-requirement (AR). MS &#x2192; v(D), AR


???
# Example 1:
## M/M: Wireshark
## AS: Network messages
## AT: Rouge ISP
## AR: Targeted Advertising

# Example 2:
## M/M: FBI Website with SQL injection vulnerability  
## AS: Identity Database
## AT: Lulzsec
## AR: Threaten FBI Agents through identity theft


---
# Abuse Frame

## Malicious Machine (M/M)
- Can be assigned to an existing domain, or a domain that is introduced into the problem world in order to reflect that an attacker can utilize the existing domains or other tools (e.g., a virus) that are not originally in the problem world D.

## Vulnerability v(D)
- Conditions in the problem world that combined with the Malicious Machine specification, will satisfy the anti-requirements
- An instance of the problem world that gives rise to an opportunity for attacks

---
class: middle
# Abuse Frame 1 (mailfile example)
![abuse](images/example-af.png)
## .center[MS &#x2192; v(D), AR]

---
class: middle
# Abuse Frame 2 (mailfile example)
![abuse](images/example-af-2.png)
## .center[MS &#x2192; v(D), AR]

---

class: middle
# Security Problem Frame
![spf](images/security-problem-frame.png)

## Correctness argument
- For an attacker (A), the specification of the Security Machine (SM) satisfies the security requirement (SR)  
SM &#x2192; A, SR

---
class: middle
# Security Frame (mailfile example)
![sfmailfile](images/example-sf.png)

---
class: middle
# Comparison
.left-column[
## Abuse Frame

![abuse](images/example-af-2.png)
]
.right-column[
## Security Frame

![sfmailfile](images/example-sf.png)
]

---
class: middle
# Iterative Process
## Another Abuse Frame
![abuse](images/example-af-3.png)
---
class: middle
# Iterative Process
## Counter with another Security Frame
![secure](images/example-sf-2.png)

---
# The Design Problem

## What security functions/capabilities exist in the software, i.e. Specification (S), such that given (D), (R) is satisfiable?  
- Security functions (Security Functional Requirements)  
- No exploitable weaknesses (Assurance Requirements)  

## S &#x2192; D, R   
S is resilient to attacks, when D includes an Attacker (A) trying to implement (AR)

---
class: middle
# Functional Security Requirements

## Security related functions in the specification (S)   
E.g. Encryption module, access control
## Security related constraints in the problem world (D)  
E.g. Controlled physical access, access logs, cleared user base, authorization db

---
class: middle
# Assurance Security Requirements  

## Weaknesses avoided in security functions of the specification (S)     
E.g. Injection, memory issues, weak crypto algorithms or implementation  
E.g. _For openSSL_: Encryption module minimizes exploitable buffer overflow weaknesses to an acceptable level  
## Weaknesses avoided in in the problem world (D)  
E.g. password sticky notes, guessable passwords, ad-hoc authorizations, poor clearance processes

---
# More Examples
.left-column[
## Functional
- Access control
- Identification
- Authentication
- Authorization
- Cryptographic APIs
- Sandboxing
- Configuration mgmt.
- Patch and Vuln mgmt.
- Physical Access Control
]
.right-column[
## Assurance
- Input validation
- Exception handling
- TOUTOC
- Resistance to Common attack patterns
- Weak Crypto avoided
- Resistance to Memory issues
- Social Engineering thwarted
]

---
class: middle
# Reflection

## What did we just do?
- Using problem frames we built a bridge from stakeholder requirements to system requirements by identifying the necessary causal chains in the problem world.
- Using abuse and security frames we identify the causal chains and .green[security capabilities and assurances necessary in software] to satisfy the .blue[security requirements of the stakeholder.]

.top-right[
![bridge](http://nagasaki-jp.com/img/oshima_bridge1.jpg)
]

---
class: middle
# Abstractions for Security Requirements Elicitation
.top-right[
![business-analyst](https://s-media-cache-ak0.pinimg.com/564x/a6/c1/62/a6c162f649bd64050235f624b0972dce.jpg)
]
---
class: middle
# Security Requirement Sources
## Security Policies
- Stakeholder Security Needs
- Auditing Needs
- [Certification Needs](http://static1.1.sqspcdn.com/static/f/702523/26767149/1451886707923/201601-Gandhi.pdf?token=l4NhzGQJsXEqUX7CIOwzoK5au%2BM%3D)
- Survivability and Maintainability Needs

## Risk assessment
- Data, Software, Human or Organization, and Physical assets

## Assurance Needs
## Deception Needs
---
class: middle
# Primary elicitation techniques

## 1. Goal-driven approach
- Attacker goal is to violate security expectations
- [Anti-goals](https://www.info.ucl.ac.be/~avl/files/avl-Icse04-AntiGoals.pdf), [Attack Trees](https://www.schneier.com/academic/archives/1999/12/attack_trees.html), [N-SoftGoals](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.103.2997&rep=rep1&type=pdf)

--

## 2. Scenario-driven approach
- Negative scenarios (desired future experience, story grounded in real world, thread through a model)
- [Misuse cases](http://understandingrequirements.com/resources/MisuseCasesHostileIntent.pdf), [Abuse frames](http://mcs.open.ac.uk/mj665/Abuse00.pdf), [Keywords/checklists](https://msdn.microsoft.com/en-us/library/ee823878%28v=cs.20%29.aspx)

--

## 3. Viewpoint-oriented approach
- [Cross-cutting views](http://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=1048526), [conflicts](http://www.panda.sys.t.u-tokyo.ac.jp/kushiro/ReferencePaper/Requirements%20engineering/00487319.pdf)
- Attacker views, security properties, tradeoffs

---
class: middle
# .red[Use cases] -  OOP, UML
## .green[Why] and .blue[how] would .orange[someone] use software?
- Goal-driven Scenarios
- They describe system behavior to fulfill user needs
- Several [templates](http://alistair.cockburn.us/Basic+use+case+template) available for [use cases](http://alistair.cockburn.us/Structuring+use+cases+with+goals)  
  .red[Purpose] = build requirements  
  Contents = have consistent prose  
  Plurality = include multiple scenarios per use case  
  Structure = be semi-formal  

.top-right[
![case](http://www.it2051229.com/data_solutions/sysanaldesign/figure1.png)
]

---
class: middle
# Scenarios: UML Use Cases
## Examine concrete scenarios of system use
- Actors and Use Cases
- .red[Associate] actors/users to the use cases
- Relate actors using .red[generalization] and .red[realization]
- Relate use cases using .red[dependencies]
- Use cases have verbs or noun-verb pairs in it

---
class: middle
# Use Case Diagram
![usecase](images/usecase-legend.svg)
---
class: middle
# Use Case Diagram

## Relationships

.left-column[
![association](images/association.svg)
]
.right-column[
![specialization](images/specialization.svg)
]
---
class: middle
# Use Case Diagram

.left-column[
![usecase](images/usecase.svg)
]
---
class: middle
# Mis Use Case Diagram

## Misuser
An actor that initiates misuse cases, either intentionally or inadvertently.

--

## Misuse Case
A sequence of actions, including variants, that a system or other entity can perform, interacting with misusers of the entity and causing harm to some stakeholder if the sequence is allowed to complete

Extension to the UML use cases modeling language
---
class: middle
# Misuse Case Diagram
![misusecase](images/misuse-legend.svg)

---
class: middle
# Misuse Case Diagram
![misusecase](images/misuse-1.svg)
---
class: middle
# Misuse Case Diagram
![misusecase](images/misuse-2.svg)
---
class: middle
# Misuse Case Diagram
![misusecase](images/misuse-3.svg)
---
class: middle
# Misuse Case Diagram
![misusecase](images/misuse-5.svg)
---
class: middle
# Misuse Case
## Construction Steps
### Step 1
Include normal actors and the required use cases regardless of any security considerations
### Step 2
Introduce the major mis-actors and misuse cases, i.e., threats that are reasonably likely. Name should give a clear understanding of motivation

---
class: middle
# Misuse Case
## Construction Steps
### Step 3
Investigate the potential relations between misuse cases and use cases, especially in terms of potential “includes”-relations. Many threats can realized by a system’s normal functionality. E.g. denial of service, covert channels, sql injection
### Step 4
Introduce new use cases with the purpose to detect or prevent misuse cases

---
class: middle
# Misuse Case
## Construction Steps
### Step 5
Make a detailed requirements [documentation](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.9.8190&rep=rep1&type=pdf)

---

class: middle
# Requirements and Risk

---
class: middle
# Risk
![risk](images/risk.png)
???
This is the language of risk. Goals, Scenarios and viewpoints are the language of requirements. However our understanding always lacks an explicit traceability from the security requirements to the risk components. By building abuse and misuse models we make this relationship explicit.

---
class: middle
# The Design Activity
![risk](images/requirements-risk.png)

???
A model that helps to understanding security requirements in terms of related risk components is absolutely necessary. It can establish the necessity and sufficiency of security requirements in the given context.

---

class: middle, center
# Questions?
![questions](https://media.giphy.com/media/ccRdPf8zWkivm/giphy.gif)

---

class: center, middle
# Misuse Case Exercise

---
class: middle

### _Skip this step if you already have a Lucidchart account._

# Step 1
## Create a personal [education account](https://www.lucidchart.com/users/education/registerLevel?tP=1&t4=A&t10=A) on [Lucidchart](https://www.lucidchart.com/)

---

class: middle
# Step 2
## Recall the assurance case assignment
- You picked a claim related to your project and built an assurance case. You also did an in-class activity to identify 10-20 other claims related to your project.
- You prioritized the claims and selected 5 claims that you would like to further investigate.

---
class: middle
# Step 3
## Elaborate the top 5 claims using Misuse cases
## Click on this [template](https://www.lucidchart.com/invitations/accept/59a6e092-49bd-4af3-80be-a1f0862923e5) to start a new misuse case
- Misuse cases will allow you to systematically identify critical properties of interest related to the claims    
- Misuse cases focus attention to places where an external entity interacts with the system

---
class: middle
# Step 4
## Submit links to your misuse cases cases developed in Lucidchart
- Submission of the links on blackboard
- One submission per team
- Clearly indicate which claims are elaborated by which misuse case

---
# Grading criteria

## Use of proper notations
- Misuse case notation

## Argument Quality
- Misuse cases help elaborate critical properties of interest related to the top 5 claims
- Proper wording of the top 5 claims

## Due Date
.red[~~Wednesday, October 5th, 2016~~]  
Update: Friday, October 7th, 2016

---
# Generating shareable links on Lucidchart

![sharing](images/sharing.png)

---
class: middle
# Resources
1.	These slides!
1.	Reading on Mis-use case
1.	The [Common Attack Pattern Enumeration and Classification (CAPEC)](http://capec.mitre.org/data/graphs/1000.html) as a reference for common attacks
