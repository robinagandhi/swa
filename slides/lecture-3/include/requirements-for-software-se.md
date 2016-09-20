class: center, middle
# Requirements for Software Security Engineering

---
# Customer Knows Best!\*

![business-analyst](https://s-media-cache-ak0.pinimg.com/564x/a6/c1/62/a6c162f649bd64050235f624b0972dce.jpg)

.footnote[
\*or do they?
]

---
# Dilbert must surely know...

![dilbert-requirements](http://assets.amuniversal.com/3c9aa7b06d5101301d7a001dd8b71c47)

---
class: middle
# NIST SP 800-160 SSE
## Stakeholder Needs and Requirements Definition Process\*
- _The purpose of the .red[Stakeholder] .green[Needs and Requirements Definition] process is to define the stakeholder requirements for a system that can provide the capabilities needed by users and other stakeholders in a defined environment._

.footnote[
\*ISO/IEC/IEEE 15288-2015
]

---
class: middle
# NIST SP 800-160 SSE
## System Requirements Definition Process\*
- _The purpose of the .red[System] .green[Requirements Definition] process is to transform the stakeholder, user- oriented view of desired capabilities into a technical view of a solution that meets the operational needs of the user._

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

# Fitness for Purpose
## Software is built for a user purpose
- It will fail if either:  
1. Designer has inadequate understanding of the purpose  
1. Software is used for a purpose different than originally designed for  
--

- Inadequate understanding of the purpose leads to poor quality software
???
# When will a designer have inadequate understanding of the purpose?

1. Software is too complex, designer does not know for sure if software will fulfill it purpose
1. Customer does not clearly know the purpose or express it
1. Purpose becomes apparent later.
1. Deliberate attempt to make the software not fulfill its purpose


---

class: middle
# .red[User stories] - Agile, XP, SCRUM
## .green[Why] and .blue[how] would .orange[someone] use it?
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
## .green[Why] and .blue[how] would .orange[someone] use it?
- Goal-driven Scenarios
- They describe system behavior to fulfill user needs
- Several [templates](http://alistair.cockburn.us/Basic+use+case+template) available for [use cases](http://alistair.cockburn.us/Structuring+use+cases+with+goals)  
  .red[Purpose] = requirements  
  Contents = consistent prose  
  Plurality = multiple scenarios per use case  
  Structure = semi-formal  

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
- .red[Optative]: expresses a wish (R).   
Desired condition over the phenomena of the environment
- .red[Indicative]: asserts a fact (D).   
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
Allows focus on problems!
]
---
# Problem Frames
## Frame Diagrams
- Plain rectangles denote given domains      
(that already exist)
- A rectangle with a single vertical stripe   
denotes a designed domain
- A rectangle with a double vertical stripe   
denotes the machine to be developed
- Requirements are denoted with a dashed oval
- Everything tangible is solid,  
intangible is dashed.
.top-right[
![legend](images/problem-frame-legend.png)
]

???
- Problem frames are described by frame diagrams, which basically consist of rectangles and links between these
- The task is to construct a machine that influences the behavior of the problem domain it is integrated in
---
# Problem Frames

- The machine solves a problem in a given domain   
(part of the world)
- The machine and the given domain interact at an   
interface of shared phenomena (events, states)
- The requirement adds a constraint to the   
domain’s intrinsic properties or behavior

![machine](images/problem-frame.svg)

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

---
class: middle
# Problem Frame Example
![example](images/example.svg)

---
# Problem frames
## Relationships

- The connecting lines represent interfaces   
that consist of shared phenomena.   
- The annotation .red[D!{E3}] means   
Domain D initiates the observable  
phenomena E3
- A dashed line represents a   
requirements reference to a domain,
- A dashed arrow shows that it is  
a constraining reference.
.top-right[
![example](images/example.svg)
]


---
