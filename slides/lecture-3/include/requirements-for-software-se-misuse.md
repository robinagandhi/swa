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
- [Certification needs](https://apps.dtic.mil/sti/tr/pdf/AD1056406.pdf)
- [Resiliency needs](https://csrc.nist.gov/pubs/sp/800/160/v2/r1/final)

## Risk assessment
- Data, Software, Human or Organization, and Physical assets

???
There are many sources of security requirements. In particular, you want to pay attention to the security policies that stakeholders want to enforce on their information assets. These policy needs can be expressed in interviews, auditing needs, certification needs and resiliency needs.
I have a few links here to further elaborate on the last two. In 2016, I authored a paper that talks about the use of NIST recommended security controls for the identification of requirements for software security engineering (See table of contents in the PDF linked from certification needs). From a resiliency perspective, NIST has published a companion guide to NIST Special publication 800-160 Volume 2. It about about how to apply security principles to achieve resiliency outcomes.

Security requirements can also be sourced from risk assessment processes applied to various organizational assets.

Abstractions are used in requirements engineering to translate verbose natural language requirements sources into artifacts that facilitate engineering analysis. These artifacts also promote a shared understanding of the required engineering effort and what the system is designed to do and more importantly not do. These abstractions are called requirements elicitation techniques.

---
class: middle
# Primary abstractions

### 1. Attacker Goals
- Attacker goal is to violate security expectations
- [Anti-goals](https://www.info.ucl.ac.be/~avl/files/avl-Icse04-AntiGoals.pdf), [Attack Trees](https://www.schneier.com/academic/archives/1999/12/attack_trees.html), [N-SoftGoals](https://dl.acm.org/doi/pdf/10.1145/291469.293165)

???
There are three types of abstractions used primarily in requirements elicitation.

The first abstraction is that of attacker goals. Just like we start with abuse frames, here we start with attacker goals to elicit security requirements. Over the years, researchers have proposed and validated several methods using attacker goals. The attacker goal is to violate security expectations.
I have linked these methods with the research papers or blogs where they are discussed in more details if you want to explore further. For example, N-softgoals uses negative goals of an attacker to come up with security measures to address them.

--

### 2. Attack Scenarios
- Negative scenarios (desired future experience of an attacker)
- [Misuse cases](http://www.scenarioplus.org.uk/papers/misuse_cases_ieee_jan_2003.pdf), [Abuse frames](https://ieeexplore.ieee.org/document/1232791/similar#similar), [Keywords/checklists](https://learn.microsoft.com/en-us/azure/security/develop/threat-modeling-tool-threats#stride-model)

???
The next abstraction for requirements elicitation is attack scenarios or negative scenarios. These scenarios outline a story about a future desired experience of an attacker. We already saw an example of this technique with Abuse cases, where we depicted specific attack scenarios. We will look at misuse cases next and the keyword/checklists based method later during the design stage.

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
- Several [templates available for use cases](https://www.cs.cmu.edu/~jhm/Readings/Cockburn%20Ch%201%20Scan.pdf)  
  .red[Purpose] = build requirements  
  Contents = have consistent prose  
  Plurality = include multiple scenarios per use case  
  Structure = be semi-formal  

.top-right[
![case](https://www.researchgate.net/profile/Jeremie-Guiochet/publication/290219988/figure/fig2/AS:634066718191623@1528184694868/Use-case-textual-description-template.png)
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
The Use case notation has two basic entities. Actors and Use Cases. Actors are shown as a stick figure. The actor is also given a name. This has to be a noun-phrase. Best to give a name that personifies the Actor in the environment of operation. The Actor does not have to be a person, it can also be an external system, such as an "other system" from the systems engineering view.

Use cases are drawn as ovals. A use case is NOT an activity carried out by the Actor but it is a feature of the system of interest that the Actor will interact with. Use cases are best worded as a verb or a noun phrase + verb phrase pair. This grammatical guidance will ensure that the use case depicts an action supported by the system of interest.

The interaction between the Actor and use case is shown with an association relationship. It has to be a solid line with no arrows. Example: ![Association relationship](https://www.uml-diagrams.org/use-case-diagrams/use-case-association-actor.png). The association relationship depicts a shared interface between the Actor and the system for essential data-flows to take place.

Two use cases can be related with an includes or extends dependency. Includes represents a non optional inclusion of the referenced usecases in the base use case. So, here transfer funds use case includes both deposit and withdraw funds use cases for money transfer to take place. In contrast, extends represents an optional extension of the referenced use case. Here the get help on registration use case is an optional extension of the register user use case.

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

???
For analyzing security requirements, we introduce the mis user and mis use case notations to a use case diagram. A mis user is an actor that initiates mis use cases, either intentionally or inadvertantly. This definition allows a mis user to be a threat agent or even a clumsy user that accidentally causes an issue.

--

## Misuse Case
A sequence of actions, including variants, that a system or other entity can perform, interacting with misusers of the entity and causing harm to some stakeholder if the sequence is allowed to complete

???
Mis use cases are features of the system or the a malicious machine that the mis user can use to cause harm to system assets. Just like use cases, also try to use verb or noun-verb pairs in their specification.

---
class: middle
# Misuse Case Diagram
![misusecase](images/misuse-legend.svg)

???
The mis use case notation is as shown here. Notice that the mis user is still a stick figure, but the head is completely filled. This can be any color of your choice. Similarly, mis use cases are also completely filled. This visual feature, clearly distinguishes them from regular users and use cases.

Mis use cases can have dependencies with each other as well as other use cases. The dependencies between mis use cases and use cases are more interesting.

First a misuse case can threaten a use case. This means that it can harm the fulfillment or the assets related to the use case.

Next, a misuse case can include a usecase for its fulfillment. A first this may appear to be strange, but if you think about a denial of service example then a DOS attack includes accessing the normal features of a system at an excessively high rate. This would be depicted with an includes relationship.

Additional use cases can be introduced in a system to prevent, detect or mitigate misuse cases. This would be similar to introducing a security frame to address an abuse frame.

With these extensions to the use case diagram, let's see the steps to construct a misuse case diagram.

---
class: middle
# Misuse Case Diagram
### Step 1
- Introduce the major mis-actors. Name should give a clear understanding of motivation

![misusecase](images/misuse-1.svg)

???
First we start with a usecase diagram and introduce major mis-actors.
Here you can see that we have a threat agent mr. robot introduced for the banking usecase.
---
class: middle
# Misuse Case Diagram
### Step 2
- Introduce misuse cases

![misusecase](images/misuse-2.svg)

???
In the second step we introduce a misuse case. Here we see that a "network evesdrop" misuse case is introduced.
---
class: middle
# Misuse Case Diagram
### Step 3
- Investigate potential relations between misuse and use cases

![misusecase](images/misuse-3.svg)

???
Investigate potential relations between misuse cases and use cases, especially in terms of potential `<<includes>>`-dependency. Many threats can realized by a system’s normal functionality. E.g. denial of service, covert channels, sql injection

In this case, the network evesdrop misuse case threatens the withdraw and transfer funds usecases.

---
class: middle
# Misuse Case Diagram
### Step 4
- Introduce new use cases with the purpose to detect or prevent misuse cases
![misusecase](images/misuse-4.svg)

???
With the misuse case established, a security engineer now introduces a usecase to address the misuse case. Here we see that encryp communication use case is introduced with a prevents dependency towards the network evesdrop misuse case.
---
class: middle
# Misuse Case Diagram
### Step 5 (1)
Iterate on steps 1 through 4 for recursive elicitation of security requirements
![misusecase](images/misuse-5.svg)

???
Now we continue to iterate between misuse and security usecases until adequate security is established.

---
class: middle
# Misuse Case Diagram
### Step 5 (2)
Iterate on steps 1 through 4 for recursive elicitation of security requirements
![misusecase](images/misuse-6.svg)

???
Now we continue to iterate between misuse and security usecases until adequate security is established. This approach is similar to the fundamental approach to security elaboration that we saw with abuse and security frames.

---

class: middle
# Misuse Case Diagram
### Another example

![misusecase](images/misuse-8.svg)

???
Let's look at another example. Here a teller actor can invoke the open and close account use cases.

---
class: middle
# Misuse Case Diagram
### Step 1

![misusecase](images/misuse-9.svg)

???
We introduce a mis-actor here who is an insider. Tyrell Wellic- who is a rouge teller.

---
class: middle
# Misuse Case Diagram
### Step 2 and Step 3

![misusecase](images/misuse-10.svg)

???
This actor initiates a money Laundering misuse case, which includes both open and close accounts. This is a good example of an includes relationship between misuse and usecases.

---
class: middle
# Misuse Case Diagram
### Step 4

![misusecase](images/misuse-11.svg)

???
Now we introduce a security usecase to address the misuse case. In this case, Scott the Admin can use a system feature of "Log review" to detect the misuse case.

---
class: middle
# Misuse Case Diagram
### Step 5

![misusecase](images/misuse-12.svg)
???
Now we iterate again and show improvisation by the attacker.

---
class: middle
# Misuse Case Diagram
### Step 5

![misusecase](images/misuse-13.svg)

???
And then introduce new security usecases to defeat the attacker. Here again we see how iterating over abuse and security frames elaborates security requirements.

---

class: middle
# Requirements and Risk

???
Using this method we have systematically used perceptions of risk to drive the elicitation of security requirements.

---
class: middle
# Risk
![risk](images/risk.png)
???

So conceptually, assets, threat, vulnerability and countermeasures concepts form the language of risk.

---
class: middle
# Risk and Security Requirements
![risk](images/requirements-risk.png)

???
With misuse cases, we build an explicit traceability from the security requirements to these risk components. This traceability is necessary to establish the adequacy of security requirements in a given environment of operation.


This is what you will be doing for your open source project in the security requirements assignment.

---

class: middle, center
# Questions?
![questions](https://media.giphy.com/media/ccRdPf8zWkivm/giphy.gif)

---
exclude: true
class: center, middle
# Misuse Case Exercise

---
class: middle
exclude: true

### _Skip this step if you already have a Lucidchart account._

# Step 1
## Create an educational account on Lucidchart
- Use your `.edu` email
- Link: https://www.lucidchart.com/pages/usecase/education-request

---
exclude: true
class: middle
# Step 2
## Data flows to identify Use-cases
- Identify five essential data flows through the software and describe them using use-cases diagrams.

---
exclude: true
class: middle
# Step 3
## Develop Mis-use cases
- Derive security requirements for use cases using misuse case diagrams.
- Iterate between use and misuse cases to elaborate additional security functions

## Click on this [template](https://www.lucidchart.com/invitations/accept/59a6e092-49bd-4af3-80be-a1f0862923e5) to start a new misuse case

---
exclude: true
class: middle
# Step 4
## Reflection
- Assess alignment of security requirements with advertised features.
- Review OSS project documentation and codebase to support your observations.

---
exclude: true
class: middle
# Step 5
## OSS Project Documentation Review
- Review OSS project documentation for security-related configuration and installation issues. Summarize your observations.

## Assignment Planning Activity
- Link to your team GitHub repository that shows your internal project task assignments and collaborations to finish this task.

---
exclude: true
# Misuse case grading criteria

## Use of proper notations
- Misuse case notation (as discussed in class)

## Reasoning Quality
- Misuse cases reflect reasoning that help derive security requirements

## Due Date
.red[See Canvas]
- Submit a link to a markdown report on Canvas

---
exclude: true
# Generating shareable links on Lucidchart

![sharing](images/sharing.png)

---
exclude: true
class: middle
# Resources
1.	These slides!
1.	Readings on Canvas
1.	The [Common Attack Pattern Enumeration and Classification (CAPEC)](https://capec.mitre.org/data/definitions/1000.html) as another reference for common attacks

---
exclude: true
class: middle
# Guidance
## Strategy
1. Focus on how data enters the application from external sources. Examples: file, URL, form data, registry data, etc. .red.bold[*]
1. Once you have located external data sources, try to think of adversaries in the domain that can influence those inputs to their own advantage.  
1. Use misuse cases to analyze above scenarios

.footnote[.red.bold[*] Select diverse dataflows in your top 5]


---
exclude: true
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
