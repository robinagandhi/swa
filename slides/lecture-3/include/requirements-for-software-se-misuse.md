class: middle
# Abstractions for Security Requirements Elicitation
.top-right[
![business-analyst](https://s-media-cache-ak0.pinimg.com/564x/a6/c1/62/a6c162f649bd64050235f624b0972dce.jpg)
]

???
In this discussion I will demonstrate how suitable abstractions can be used to elicit and communicate security requirements in modern software development processes.

---
class: middle
# Security Requirement Sources
## Security Policy
- Stakeholder interviews
- Auditing needs
- [Certification needs](http://static1.1.sqspcdn.com/static/f/702523/26767149/1451886707923/201601-Gandhi.pdf?token=l4NhzGQJsXEqUX7CIOwzoK5au%2BM%3D)
- [Resiliency needs](https://csrc.nist.gov/publications/detail/sp/800-160/vol-2/final)

## Risk assessment
- Data, Software, Human or Organization, and Physical assets

???
There are many sources of security requirements. In particular, you want to pay attention to the security policies that stakeholders want to enforce on their information assets. These policy needs can be expressed in interviews, auditing needs, certification needs and resiliency needs.
I have a few links here to further elaborate on the last two. In 2016, I authored a paper that talks about the use of NIST recommended security controls for the identification of requirements for software security engineering. From a resiliency perspective, NIST has published a companion guide to NIST Special publication 800-160 Volume 2. It about about how to apply security principles to achieve resiliency outcomes.

Security requirements can also be sourced from risk assessment processes applied to various organizational assets.

Abstractions are used in requirements engineering to translate verbose natural language requirements sources into artifacts that facilitate engineering analysis. These artifacts also promote a shared understanding of the required engineering effort and what the system is designed to do and more importantly not do. These abstractions are called requirements elicitation techniques.

---
class: middle
# Primary abstractions

### 1. Attacker Goals
- Attacker goal is to violate security expectations
- [Anti-goals](https://www.info.ucl.ac.be/~avl/files/avl-Icse04-AntiGoals.pdf), [Attack Trees](https://www.schneier.com/academic/archives/1999/12/attack_trees.html), [N-SoftGoals](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.103.2997&rep=rep1&type=pdf)

???
There are three types of abstractions used primarily in requirements elicitation.

The first abstraction is that of attacker goals. Just like we start with abuse frames, here we start with attacker goals to elicit security requirements. Over the years, researchers have proposed and validated several methods using attacker goals. The attacker goal is to violate security expectations.
I have linked these methods with the research papers or blogs where they are discussed in more details if you want to explore further. For example, N-softgoals uses negative goals of an attacker to come up with ways to address them.

--

### 2. Attack Scenarios
- Negative scenarios (desired future experience of an attacker)
- [Misuse cases](http://www.scenarioplus.org.uk/papers/misuse_cases_ieee_jan_2003.pdf), [Abuse frames](http://mcs.open.ac.uk/mj665/Abuse00.pdf), [Keywords/checklists](https://msdn.microsoft.com/en-us/library/ee823878%28v=cs.20%29.aspx)

???
The next abstraction for requirements elicitation is attack scenarios or negative scenarios. These scenarios outline a story about a future desired experience of an attacker. We already saw and example of this technique with Abuse cases, where we depicted specific attack scenarios. We will look at misuse cases next and the keyword/checklists later during the design stage.

--

### 3. Viewpoints
- [Cross-cutting views](http://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=1048526), [conflicts](http://www.panda.sys.t.u-tokyo.ac.jp/kushiro/ReferencePaper/Requirements%20engineering/00487319.pdf)
- Attacker views, security properties, tradeoffs

???
The third primary abstraction is that of a viewpoint. Here the philosophy is to encapsulate different perspectives of the system and then reason about their conflicts and agreements explicitly. For security requirements, researchers have observed the use of attacker view and cross-cutting security properties that apply to a whole range of system components. With viewpoints, the tradeoff of security with other system properties such as safety can also be carried out.


Take note that all three abstractions focus on a future undesirable event to elicit security requirements. We often call this future undesirable event as Risk in Cybersecurity. So in a sense, we are using risk perception to drive the security engineering effort.

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
???
We talked about use cases before. It is a scenario based abstraction that is widely used for describing requirements and made popular by the Unified Modeling Language standard. The UML standard  introduced them to software developers using a visual notation that is quite intuitive and easy to understand.

Let's see how the Use case visual notation is used to depict system requirements.

---
class: middle
# Use Case Notation
- Actors (stick figures) and Use Cases (ovals)
- [Association](https://www.uml-diagrams.org/use-case-actor-association.html) relates actors to use cases (Solid line)
- Dependencies (include, extend) relate use cases (dotted arrow)  

![usecase](images/usecase-legend.svg)


???
The Use case notation that two basic entities. Actors and Use Cases. Actors are shown as a stick figure. The actor is also given a name. This has to be a noun-phrase. Best to give a name that personifies the Actor in the environment of operation. The Actor does not have to be a person, it can also be an external system, such as an "other system" from the systems engineering view.

Use cases are drawn as ovals. A use case is NOT an activity carried out by the Actor but it is a feature of the system of interest that the Actor will interact with. Use cases are best worded as a verb or a noun-verb pair. This grammatical guidance will ensure that the use case depicts an action supported by the system of interest.

The interaction between the Actor and use case is shown with an association relationship. It has to be a solid line with no arrows. Example: ![Association relationship](https://www.uml-diagrams.org/use-case-diagrams/use-case-association-actor.png). The association relationship depicts a shared interface between the Actor and the system for essential data-flows to take place.

Two use cases can be related with an includes or extends dependency. Includes represents a non optional inclusion of the referenced usecases in the base use case. So here transfer funds use case includes both deposit and withdraw funds use cases for money transfer to take place. In contrast, extends represents an optional extension of the referenced use case. Here the get help on registration use case is an optional extension of the register user use case.

---
class: middle
# Use Case Notation

.left-column[
![association](images/association.svg)
]
.right-column[
![specialization](images/specialization.svg)
]

???
In this example I illustrate the use of proper wording for actors and use cases. Here we also see that two actors can be related to each other using a generalization relationship. In the example, it means that the Actor librarian can do everything the Assistant librarian can do. This relationship can prevent duplication and reduce clutter in the diagram.

---
class: middle
# Use Case Diagram

![usecase](images/usecase.svg)

???
Using this simple notation, it is now time to look one particular use case diagram that describes a banking scenario where a customer can withdraw or deposit money.

Now you are probably wondering, how to use this notation to depict security requirements. Herein lies the biggest drawback of UML. In its base format, it has no support for conceptualizing and including security requirements. The fundamental philosophy of using an attackers perspective to refine security requirements remains the same regardless of the specific notation or method being used. As a result, this notation needed to be extended. This extended notation allows us to model a mis-use case diagram. Let's examine this extended notation.

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
### Step 1
- Introduce the major mis-actors. Name should give a clear understanding of motivation

![misusecase](images/misuse-1.svg)
---
class: middle
# Misuse Case Diagram
### Step 2
- Introduce misuse cases

![misusecase](images/misuse-2.svg)
---
class: middle
# Misuse Case Diagram
### Step 3
- Investigate potential relations between misuse and use cases

![misusecase](images/misuse-3.svg)

???
Investigate potential relations between misuse cases and use cases, especially in terms of potential `<<includes>>`-dependency. Many threats can realized by a system’s normal functionality. E.g. denial of service, covert channels, sql injection
---
class: middle
# Misuse Case Diagram
### Step 4
- Introduce new use cases with the purpose to detect or prevent misuse cases
![misusecase](images/misuse-4.svg)
---
class: middle
# Misuse Case Diagram
### Step 5 (1)
Iterate on steps 2 through 4 for recursive elicitation of security requirements
![misusecase](images/misuse-5.svg)
---
class: middle
# Misuse Case Diagram
### Step 5 (2)
Iterate on steps 2 through 4 for recursive elicitation of security requirements
![misusecase](images/misuse-6.svg)

---

class: middle
# Misuse Case Diagram
### Another example

![misusecase](images/misuse-8.svg)
---
class: middle
# Misuse Case Diagram
### Another example

![misusecase](images/misuse-9.svg)
---
class: middle
# Misuse Case Diagram
### Another example

![misusecase](images/misuse-10.svg)
---
class: middle
# Misuse Case Diagram
### Another example

![misusecase](images/misuse-11.svg)
---
class: middle
# Misuse Case Diagram
### Another example

![misusecase](images/misuse-12.svg)
---
class: middle
# Misuse Case Diagram
### Another example

![misusecase](images/misuse-13.svg)

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
# Risk and Security Requirements
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
.red[See Canvas]
- Submit a link to a markdown report on Canvas

---
# Generating shareable links on Lucidchart

![sharing](images/sharing.png)

---
class: middle
# Resources
1.	These slides!
1.	Readings on Canvas
1.	The [Common Attack Pattern Enumeration and Classification (CAPEC)](https://capec.mitre.org/data/definitions/1000.html) as another reference for common attacks

---
class: middle
# Guidance
## Strategy
1. Focus on how data enters the application from external sources. Examples: file, URL, form data, registry data, etc. .red.bold[*]
1. Once you have located external data sources, try to think of adversaries in the domain that can influence those inputs to their own advantage.  
1. Use misuse cases to analyze above scenarios

.footnote[.red.bold[*] Select diverse dataflows in your top 5]


---
class: middle
# Guidance
## Representation
* Use cases and misuse cases should be verb phrases  
  (verb + object)  
  The subject is the actor or misactor
* Use cases focus on .red[system behaviors] and .red[features]
* Recurse (abuse frame - security frame) until specific functional security requirements can be identified that are .red[implemented by the system].
* For misuse cases, prioritize mitigations that are implemented in the OSS project, instead of the environment
* Make sure all misuse cases are addressed by use cases
* Arrange the diagram to reduce clutter
