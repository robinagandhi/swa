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
# Requirements are about Needs

## Requirements "Litmus tests"
- Even if you did not build the system/software the user will still have this need!
- They are located in the [environment of operation for the system-of-interest\*](https://robinagandhi.github.io/swa/slides/lecture-1/systems-security-engineering.html#15)

.footnote[
\* Michael Jackson, [The Meaning of Requirements, 1996](http://mcs.open.ac.uk/mj665/aserqts5.pdf)
]
---
# Fitness for Purpose
## Software is built for a purpose
- It will fail if either:  
1. Software does not fulfill the purpose
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

???
# Requirements Engineering
- Requirements Engineering (RE) lies at the heart of software development.
- RE is concerned with identifying the purpose of a software system, and the contexts in which it will be used.
- Hence, RE acts as the bridge between the real world needs of users, customers, and other constituencies affected by a software system, and the capabilities and opportunities afforded by software-intensive technologies.
Source: http://www.cs.toronto.edu/~sme/RE01/

---
# If RE is about identifying Purpose then...

--

## Requirements are about .red[relationships] in the application domain
- They are not about the software system or the shared interface with the software system
- They are effects in the application domain that the customer wants the machine to guarantee

--

## Distance your analysis from the solution!

---
class: middle
# Requirements Expression

## Requirements are expressed in two moods
- .red[Optative]: expresses a wish (R). Desired condition over the phenomena of the environment.
- .red[Indicative]: asserts a fact (D). Given properties of the environment

---
# Solution Expression

## Specification (S)
- Optative description of a condition over the shared phenomena at the interface between the system and the environment

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
![legend](images/problem-frame-legend.png)
]

---

![legend](images/problem-frame-legend.png)
