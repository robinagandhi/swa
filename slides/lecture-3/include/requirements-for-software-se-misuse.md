class: center, middle
# Requirements for Software Security Engineering (Part - 2)

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
- [Misuse cases](http://www.scenarioplus.org.uk/papers/misuse_cases_ieee_jan_2003.pdf), [Abuse frames](http://mcs.open.ac.uk/mj665/Abuse00.pdf), [Keywords/checklists](https://msdn.microsoft.com/en-us/library/ee823878%28v=cs.20%29.aspx)

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
- [Associate](https://www.uml-diagrams.org/use-case-actor-association.html) actors/users to the use cases
- Relate actors using .red[generalization] and .red[realization]
- Relate use cases using .red[dependencies]
- Use cases have verbs or noun-verb pairs in it
- Focus on essential data-flows from actors

---
class: middle
# Use Case Diagram
![usecase](images/usecase-legend.svg)
---
class: middle
# Use Case Diagram

#  


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
### [Optional] Step 5
[Document requirements](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.9.8190&rep=rep1&type=pdf)

???
We will not do this step to keep the process lightweight. But you know how to do it if required.

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
## Create an educational account on Lucidchart
- Use your `.edu` email
- Link: https://www.lucidchart.com/pages/usecase/education-request

---

class: middle
# Step 2
## Data flows to identify Use-cases
- Identify five essential data flows through the software and describe them using use-cases diagrams.

---
class: middle
# Step 3
## Develop Mis-use cases
- Derive security requirements for use cases using misuse case diagrams.
- Iterate between use and misuse cases to elaborate additional security functions

## Click on this [template](https://www.lucidchart.com/invitations/accept/59a6e092-49bd-4af3-80be-a1f0862923e5) to start a new misuse case

---
class: middle
# Step 4
## Reflection
- Assess alignment of security requirements with advertised features.
- Review OSS project documentation and codebase to support your observations.

---
class: middle
# Step 5
## OSS Project Documentation Review
- Review OSS project documentation for security-related configuration and installation issues. Summarize your observations.

## Assignment Planning Activity
- Link to your team GitHub repository that shows your internal project task assignments and collaborations to finish this task.

---
# Misuse case grading criteria

## Use of proper notations
- Misuse case notation (as discussed in class)

## Reasoning Quality
- Misuse cases reflect reasoning that help derive security requirements

## Due Date
.red[[See Project Page](https://robinagandhi.github.io/swa/pages/project.html)]
- Submit a link to a markdown report on Canvas

---
# Generating shareable links on Lucidchart

![sharing](images/sharing.png)

---
class: middle
# Resources
1.	These slides!
1.	Readings on Canvas
1.	The [Common Attack Pattern Enumeration and Classification (CAPEC)](http://capec.mitre.org/data/graphs/1000.html) as another reference for common attacks
