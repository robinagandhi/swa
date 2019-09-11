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
# [NIST SP 800-160 SSE](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-160v1.pdf)
## .green[Stakeholder Needs and Requirements] Definition Process\*
- **Purpose (Security Perspective):** _.red[Define the stakeholder security requirements] that include [protection capability](https://robinagandhi.github.io/swa/slides/lecture-1/systems-security-engineering.html#16), security characteristics, and security-driven constraints for the systems, so as to securely provide the capabilities needed by users and other stakeholders in a defined environment._

.footnote[
\*ISO/IEC/IEEE 15288-2015
]

???
The purpose is from a security perspective.

---
class: middle
# [NIST SP 800-160 SSE](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-160v1.pdf)
## .green[System Requirements] Definition Process\*
- **Purpose (Security Perspective):** _.red[transform the stakeholder security requirements into the system requirements] that reflect a .red[technical security view] of the system._

.footnote[
\*ISO/IEC/IEEE 15288-2015
]

---
class: middle
# .red[Stakeholder Needs and Requirements] vs .blue[System Requirements]

## Litmus test
- Even if you did not build the _software_ the **stakeholder** will still have these needs and requirements!
- They are located in the [environment of operation for the system-of-interest\*](https://robinagandhi.github.io/swa/slides/lecture-1/systems-security-engineering.html#13)

.footnote[
\* Michael Jackson, [The Meaning of Requirements, 1996](http://mcs.open.ac.uk/mj665/aserqts5.pdf)
]

.top-right[
![litmus-test](http://www.simplescience.info/_/rsrc/1469387124646/chemistry/acids-2/Litm%20test.jpg)
]
---
class: middle
# Need 👉🏼 Fitness for Purpose
## Software is built for a purpose
- It will fail if either:  
1. Designer has inadequate understanding of the purpose  
1. Software is used for a purpose different than originally designed for  

## Inadequate understanding of the purpose leads to poor quality software

???
# When will a designer have inadequate understanding of the purpose?

## Claim: Designer has full understanding of the system purpose
1. Unless the software is too complex i.e. designer does not know for sure if software will fulfill it purpose
1. Unless designer does not have the knowledge or experience
1. Unless the customer does not clearly know the purpose or express it
1. Unless the purpose becomes apparent later.
1. Unless there is a deliberate attempt to make the software not fulfill its purpose
1. ...

---
class: middle
# .red[Use cases] -  OOP, UML
## .blue[Why] and .green[how] and would .orange[someone] use software?
- Goal-driven Scenarios
- They describe system behavior to fulfill user needs
- Several [templates](http://www.cs.otago.ac.nz/coursework/cosc461/uctempla.htm) available for [use cases](http://www.cs.otago.ac.nz/coursework/cosc461/usecases.htm)  
  .red[Purpose] = build requirements  
  Contents = have consistent prose  
  Plurality = include multiple scenarios per use case  
  Structure = be semi-formal  

.top-right[
![case](http://www.it2051229.com/data_solutions/sysanaldesign/figure1.png)
]


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

![userstories](http://1.bp.blogspot.com/_k29Vs3aHPNs/TVE4LXuamFI/AAAAAAAACSY/cpnxwiQx310/s1600/user+story+asteroids.jpg)


???
Notice the reversed order of Why and How compared to User stories. Use cases are goal-driven for scenario elicitation. On the other hand User stories are scenario driven elicitation technique that link scenarios to goals.
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
# Stakeholder Needs and Requirements

## These requirements are about .red[relationships] in the environment of operation
- They are not about the software system
- They are not about the shared interface at the environment of operation and the software system
- They are effects in the environment of operation that the customer wants the software system to guarantee

---
class: middle
# Stakeholder Needs and Requirements

## Expressed in two moods
- .red[Optative]: expresses a wish (R)   
Desired condition over the phenomena of the environment
- .red[Indicative]: expresses things existing in the problem world (D)   
Given properties of the environment of operation

---
class: middle
# System Requirements

## Expressed in a single mood
- .red[Optative]: expresses a wish, Specification (S)  
Desired condition over the shared phenomena at the interface between the system and the environment of operation

???
Based on this definition we are never really describing anything in the system beyond the shared phenomena at the interface of the system and the environment of operation.

---

class: middle
# Problem Frames
Allows focus on `problems` to be solved.

---
class: middle
# Problem Frames
## Frame Diagrams
.left-column[
#### .green[Rectangle with double vertical stripe]: Machine to be developed  
#### .green[Rectangle with single vertical stripe]: Designed domain  
#### .green[Plain rectangles]: Given domains (things that already exist)  
#### .green[Dashed oval]: Requirements  
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
#### .red[Solid line]: Interfaces that consist of shared phenomena   
#### .red[Dashed line]: A requirements reference to a domain
#### .red[Dashed arrow]: A constraining reference  
]
.right-column[
![legend](images/legend.svg)
]

---
class: middle
# Problem Frames

- The machine solves a problem in the environment of operation
- The machine and the environment of operation interact at an interface of shared phenomena (events, states)
- The requirement adds a constraint to the intrinsic properties or behavior of the environment of operation

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
Recap: Requirements are about .red[relationships] in the environment of operation
]

---
# Relationships
.left-column[
Annotation .code[c:D!{E3}] means Domain .code[D] initiates the observable phenomena .code[E3] on interface .code[c].

Example:   
.code[a: MF! {MsgDir, File, Char}]  

Domain .code[MF] initiates observable phenomena .code[MsgDir, File, Char] on interface .code[a]
]
.right-column[
![example](images/example.svg)
]
---
class: middle
# Frame Components

.left-column[
### .red[R: Requirements]  
What the customer wants to be true in terms of (c, d)

### .red[D: Domain Properties]   
What we know to be true in the domain

### .red[S: Specification]  
How we want the machine to behave at interface (a, b)  
]

.right-column[
![example](images/example.svg)
]
---
class: middle
# Correctness argument
## S &#x2192; D, R  
- The argument to make:  
_(R)equirements_, _(S)pecifications_ and _(D)omain descriptions_ .red[fit] together

---
# Correctness argument
## Creating (R) is not enough !!
- Creating descriptions of the environment (D) and specification (S) helps our comprehension and provides basis for .red[validating] the requirements

--

## Claim: R is fulfilled
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

class: middle
# Iterative Process
## Yet another Abuse Frame!
![abuse](images/example-af.png)

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

## Security functions in the specification (S)   
E.g. Encryption module, access control
## Security constraints on the problem world (D)  
E.g. Controlled physical access, access logs, cleared user base, authorization db

---
class: middle
# Assurance Security Requirements  

## Weaknesses avoided in security functions of the specification (S)     
E.g. Injection, memory issues, weak crypto algorithms or implementation  
E.g. _For openSSL_: Encryption module minimizes exploitable buffer overflow weaknesses to an acceptable level  
## Weaknesses avoided in the problem world (D)  
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
class: middle, center
# Questions?
![questions](https://media.giphy.com/media/ccRdPf8zWkivm/giphy.gif)
