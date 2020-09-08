class: center, middle
# Requirements for Software Security Engineering

???
We now start examining phases in the software development lifecycle where security engineering activities are most relevant. We start "early" in the lifecycle with Requirements. This is an important lifecycle phase to develop the problem context for the engineering activities. This phase also requires a lot of interactions with the system stakeholders to make sure that software meets operational intent.

---
# Customer Knows Best!\*

![business-analyst](https://s-media-cache-ak0.pinimg.com/564x/a6/c1/62/a6c162f649bd64050235f624b0972dce.jpg)

.footnote[
\*or do they?
]
???
So it is often said that customer knows best...or do they? I'll pause here to read this comic strip.
---
# Alice must surely know...

![dilbert-requirements](http://assets.amuniversal.com/3c9aa7b06d5101301d7a001dd8b71c47)

???
In interactions with real customers, you will quickly realize that requirements are not just out there for the taking. You have to elicit requirements. Which means that a good requirements engineer needs to draw them out from the customer by asking the right questions using a structured method.

---
class: middle
# [NIST SP 800-160 SSE](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-160v1.pdf)
## .green[Stakeholder Needs and Requirements] Definition Process\*
- **Purpose (Security Perspective):** _.red[Define the stakeholder security requirements] that include [protection capability](https://robinagandhi.github.io/swa/slides/lecture-1/systems-security-engineering.html#16), security characteristics, and security-driven constraints for the systems, so as to securely provide the capabilities needed by users and other stakeholders in a defined environment._

.footnote[
\*ISO/IEC/IEEE 15288-2015
]

???
NIST SP 800-160, the systems security engineering guide, identifies two technical processes in the requirements lifecycle phase where security can be integrated. The first process is the Stakeholder Needs and Requirements Definition Process.
The purpose of this process from a security perspective is to define the stakeholder security requirements] that include [protection capability](https://robinagandhi.github.io/swa/slides/lecture-1/systems-security-engineering.html#16), security characteristics, and security-driven constraints for the systems. The goal of this activity is to securely provide the capabilities needed by users and other stakeholders in a defined operational environment. Like the previous sentence in the definition, the we want to identify capabilities including general features and security features.

---
class: middle
# [NIST SP 800-160 SSE](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-160v1.pdf)
## .green[System Requirements] Definition Process\*
- **Purpose (Security Perspective):** _.red[transform the stakeholder security requirements into the system requirements] that reflect a .red[technical security view] of the system._

.footnote[
\*ISO/IEC/IEEE 15288-2015
]

???
The second technical process in the requirements lifecycle phase is to the System Requirements Definition Process. Now you might be a little surprised here. Did we not just talk about his? Actually, no! The goal of this process is to transform the stakeholder security requirements and needs into the system requirements]. The previous process resulted in requirements that reflect needs in the operational environment. This process results in requirements that reflect a .red[technical security view] of the system. More specifically, the outcomes of this process are a list of active protection capabilities needed in the software to support the stakeholder needs. Depending on the threats perceived in the operational environment we also determine what is the adequate assurance and strength of the protection capability that is needed. This analysis translates into passive protection capabilities for software construction and operation.

---
class: middle
## .red[Stakeholder Needs and   
Requirements] vs .blue[System Requirements]

> Litmus test for requirements:  
_Would the stakeholders still have the requirement even if we did not build the software?_
- **Yes:** It is a stakeholder requirement and need. These are located in the [environment of operation for the system-of-interest](https://robinagandhi.github.io/swa/slides/lecture-1/systems-security-engineering.html#13)
- **No:** It is a system/software requirements. These are located at the shared interface between the machine and the environment

.top-right[
![litmus-test](http://www.simplescience.info/_/rsrc/1469387124646/chemistry/acids-2/Litm%20test.jpg)
]

???
As it often turns out, the two processes and the resulting requirements are not distinguished in practice. This leads to a lot of issues, in particular with the early conceptualization of security needs and the corresponding balance of protection capabilities to be engineered for the system. These decisions get pushed until later in the software lifecycle. So how do we tell apart the among the two types of requirements? I have a quick litmus test for you. Here, the question to ask for each requirement is as follows: "Would the stakeholders still have the requirement even if we did not build the software?"

---
class: middle
## .red[Stakeholder Needs and   
Requirements] vs .blue[System Requirements]

![Requirements](images/requirements.png)

.footnote[
\* Michael Jackson, [The Meaning of Requirements, 1996](http://mcs.open.ac.uk/mj665/aserqts5.pdf)
]

???
In his seminal paper, the meaning of requirements, Jackson clearly depicted stakeholder requirements to exist in the environment, independent of the machine to be built. The system requirements or machine behavior are at the shared interface with the environment and the given conditions in the environment connect the two.  

---
class: middle
# Need 👉🏼 Fitness for Purpose
## Software is built for a purpose
- It will fail if either:  
1. Designer has inadequate understanding of the purpose  
1. Software is used for a purpose different than originally designed for  

## Inadequate understanding of the purpose leads to poor quality software

???
This understanding now helps us realize that stakeholder needs determine a given software's fitness for purpose. Software is built for a purpose. This software will fail if we inadequate understanding of the purpose or the software is used for a purpose different that it is originally designed for. Either one of these scenarios can be true for open-source software that you have selected for your semester projects.

Inadequate understanding of the purpose can occur due to several reasons.
1. The software is too complex i.e. designer does not know for sure if software will fulfill it purpose
1. The designer does not have the knowledge or experience
1. The the customer does not clearly know the purpose or express it or the purpose becomes apparent later in the system lifecycle
1. Or there could be a deliberate attempt to make the software not fulfill its purpose

To avoid these problems, software engineers often use structured methods to understand a systems purpose. Let's look at two popular methods.

---
class: middle
# .red[Use cases] -  OOP, UML
## .blue[Why] and .green[how] and would .orange[someone] use software?
- Goal-driven Scenarios
- User needs (goals) are fulfilled by descriptions of system behavior (Scenarios)
- Several [templates](http://www.cs.otago.ac.nz/coursework/cosc461/uctempla.htm) available for [use cases](http://www.cs.otago.ac.nz/coursework/cosc461/usecases.htm)  
  .red[Purpose] = build requirements  
  Contents = have consistent prose  
  Plurality = include multiple scenarios per use case  
  Structure = be semi-formal  

.top-right[
![case](http://www.it2051229.com/data_solutions/sysanaldesign/figure1.png)
]

???
Use cases were made popular by UML and its use of object-oriented programming to build complex software systems.

Use cases capture why and how would someone use software? The why question comes before the how. So they follow a goal-driven scenario elicitation technique.

User needs (goals) are fulfilled by descriptions of system behavior (Scenarios)

The purpose of use case is to build system requirements that fulfill user needs. They their structure promotes a consistent prose, motivates the identification of multiple scenarios per use case and the description is often tabular, a semi-formal way to express requirements.


---

class: middle
# .red[User stories] - Agile, XP, SCRUM
## .blue[How] and .green[why] would .orange[someone] use software?
- Scenarios about user needs
- [Informal](https://www.agilealliance.org/glossary/three-cs/), [Card, Conversation and Confirmation](http://ronjeffries.com/xprog/articles/expcardconversationconfirmation/)
.top-right[
![card](http://www.jamieclouting.co.uk/wp-content/uploads/2012/03/card-front-300x225.jpg)
]

???
User stories are more popular in agile processes. They first focus on the how and then the why. So they are scenarios about user needs.
Notice the reversed order of Why and How compared to User stories. Use cases are goal-driven for scenario elicitation. On the other hand User stories are scenario driven elicitation technique that link scenarios to goals.

Their specification is also informal compared to use cases, but often elaborated using test-driven methodology. i.e. for each scenario a series of tests are specified for the system. The three c's of user stories are cards, conversation and confirmation.

User stories are written on cards.
The conversation is typically verbal to discuss the expectations around the card.
Finally, the Confirmation is the acceptance test.

---

![userstories](http://1.bp.blogspot.com/_k29Vs3aHPNs/TVE4LXuamFI/AAAAAAAACSY/cpnxwiQx310/s1600/user+story+asteroids.jpg)


???
Here is an example of a user story card. They follow a restricted natural lanaguage pattern that start with the user role, then the wants of that user in terms of system interaction followed by the goal of the interaction.

With these structured techniques, you can start to realize that the problem context needs engineering know-how. This engineering know-how is pursued by the field of Requirements engineering. In the next video we will discuss more about requirement engineering and understand the primary theory of security requirements elicitation using a special notation called problem frames.

---
class: center, middle
# [What is Requirements Engineering?](http://www.cs.toronto.edu/~sme/RE01/)

.footnote[
See notes (hit `p`) for definition
]

???
Requirements engineering has a long standing professional international conference. Many prominent researchers in software engineering helped get it started. So it is worth while to read their description from the very first conference to see what requirements engineering is all about.

According to the website:
> Requirements Engineering (RE) lies at the heart of software development.  

> RE is concerned with identifying the purpose of a software system, and the contexts in which it will be used.  

> Hence, RE acts as the bridge between the real world needs of users, customers, and other constituencies affected by a software system, and the capabilities and opportunities afforded by software-intensive technologies.

Source: http://www.cs.toronto.edu/~sme/RE01/


---
class: middle
# Stakeholder Needs and Requirements

## These requirements are about .red[relationships] in the environment of operation
- They are not about the software system
- They are not about the shared interface at the environment of operation and the software system
- They are effects in the environment of operation that the customer wants the software system to guarantee

.top-right[
![Requirements](images/requirements.png)
]

???
Now we start to put structure around the requirements elicitation activity by identifying the ways in which we express them. We know from before that stakeholder needs and requirements are about relationships in the environment of operation. They are not about the software system and they are not about the shared interface at the environment of operation and the software system

---
class: middle
# Stakeholder Needs and Requirements

## Expressed in two moods
- .red[Optative]: expresses a wish (R)   
Desired condition over the phenomena of the environment
- .red[Indicative]: expresses things existing in the problem world (D)   
Given properties of the environment of operation

???
As a result these needs are requirements are typically expressed as wish over the phenomena of the operational environment. If you remember, the litmus test, then you know that stakeholder requirements exist whether we build the system or not. So this makes sense. In addition, to stakeholder wishes, we also have to collect information about the operational environment. These properties are generally expressed in an indicative mood, i.e. they express things that existing in the problem world.

Let's call the first set of requirements expressed in the optative mood as (R) and the indicative mood as (D)

---
class: middle
# System Requirements

## Expressed in a single mood
- .red[Optative]: expresses a wish, Specification (S)  
Desired condition over the shared phenomena at the interface between the system and the environment of operation

???
Now the system requirements are only expressed in an optative mood. They express a wish which reflects the desired condition over the shared phenomena at the interface between the system and the environment of operation. We call this requirement set (S). The letter S also comes from the fact that these system requirements are often referred to as the Specification.

While brainstorming stakeholder or system requirements, we have to aware of the tendency to start describing the solution context and lose focus of the problem context. So to stay focused on the problem context, and to really understand R, D and S, we need a better notation. One such notation is Problem frames.

---

class: middle
# Problem Frames
Allows focus on `problems` to be solved.

???
Problem frames is a notation specifically designed for requirements engineers to focus on the problems to be solved. While we will a different notation for our semester project security requirements, the study of problem frames will help us understand the foundational theory behind security requirements.

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
> Problem frames are described by frame diagrams, which basically consist of rectangles and links between these
> The task is to construct a machine that influences the behavior of the problem domain it is integrated in

The diagraming typically starts with the machine to be developed. This is a rectangle with two stripes. Next, you identify any designed, i.e. man-made artifacts that exist in environment of operation as well as any given things that exist, e.g. people. These are represented as designed domain and given domains. Both are things that exist in the environment of operation. Finally, dashed ovals represent requirements. They are dashed because they are conceptual and not tangible entities like the designed and given domains or the machine.

---
class: middle
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

???
The rectangles and ovals are connected with a solid or dashed line. Dashed lines can also have an arrow. The solid line represents shared phenomena between the domains and the machine. For example any input or output would represent shared phenomena. A requirement relates to a domain with a dashed line to indicate that the requirements pertains to that domain. When a requirements includes an arrow, this means that the requirement constraints the domain to behave in a certain way or its intrinsic properties. Hence it is called a constraining reference.

---
class: middle
# A Basic Problem Frame

![legend](images/problem-frame.svg)
???
So let's put this all together in the most basic form of a problem frame. Here we have a machine that solves a problem in the environment of operation. The machine and the environment of operation interact at an interface of shared phenomena and the requirement adds a constraint to the intrinsic properties or behavior of the environment of operation

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

???
What better way to learn problem frames, than to apply it to study a given problem.

Here we have a PC user who want to analyze messages in the mail client's mailbox. There seems to a certain structure to the mail files and they are all in a single directory. The report expected by the user also has some available guidance.

Pause the video here and try to construct a problem frame diagram based on this description. No really, I mean it.

---
class: middle
# Context Diagram
![example](images/example.svg)

.footnote[
Recap: Requirements are about .red[relationships] in the environment of operation
]

???
Here is how I would construct the problem frame diagram. The machine we want to build is the mailbox analyzer. The mailfiles are a given domain. They exist in the environment of operation. The analysis report is what we want to produce as an output artifact, so it is a designed domain. The format of the analysis report is constrained by the requirement of the analysis rules specified in the description. With this diagram it is now easy to see that requirements are about relationships in the environment of operation.

In this diagram you also see annotations for the relationships. Let's look at what they mean.

---
class: middle
# Relationships
.left-column[

.code[a: MF! {MsgDir, File, Char}]  

Domain .code[MF] initiates observable phenomena .code[MsgDir, File, Char] on interface .code[a]
]
.right-column[
![example](images/example.svg)
]

???
let's look at annotation a. This specification suggests that on shared interface a, the Mail File or the MF domain initiates an event. We know this because this domain name has an exclamation mark next to it. This event generated by the MF domain includes observable items such as the MsgDir, File name and Characters as input to the Machine.

Similarly, for b, the machine initiates an observable event that adds certain items to the Analysis Report domain.

c and d annotations represent the specific items that are part of the requirements reference with respect to the domains.  

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
???
In this diagram we now distinctly see the Stakeholder requirements, which includes the R and D. R is specified in the optative mood about what the customer wants to be true in terms of the references to the domains.
Capital D is what we know to be true in the domain. D is specified in the indicative mood. Both R and D combined together form the stakeholder requirements.

S specifies the system requirements. It conveys how we want the machine to behave in its interaction with the given and designed domains in the environment of operation. In other words, a and b are the shared phenomena at the interface between the system and the environment of operation.
---
class: middle
# Correctness argument
## S &#x2192; D, R  
- The argument to make:  
_(R)equirements_, _(S)pecifications_ and _(D)omain descriptions_ .red[fit] together

???
So to make sure that the machine will meet the operational intent, i.e. we build the right solution, we have to satisfy the following correctness argument. S entails D, R. i.e. They all fit together.

---
# Correctness argument
## Creating (R) is not enough !!
- Creating descriptions of the environment (D) and specification (S) helps our comprehension and provides basis for .red[validating] the requirements

???
Now we know that creating just R is not enough. To build a bridge from stakeholder needs (R) to the system specification (S), we also need to create descriptions of the environment (D).

--

## Claim: R is fulfilled
- Unless D or S is Insufficient
- Unless D or S is Incorrect
--

- Unless D or S is .red[Malicious]

???
So a claim that R is fulfilled can be defeated with a rebuttal that the given D or S is Insufficient, Incorrect or in the case of security engineering, D or S is Malicious. That is, Threat agents exist in the operational environment (D) or the machine specification (S) allows malicious behaviors.
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

???
Therefore to make an argument that a machine is fit for purpose, the engineering effort needs to show that machine or the domain descriptions are under specified which allow unwanted behaviors.
We also don't want to have the situation where S and D are over specified such that required behaviors cannot be achieved.

---
class: middle
# Problem Frames
![annotated](images/example-annotated.png)
???
With a frame diagram, we can now reason about missing domain descriptions or system specifications from a security engineering perspective. More importantly, we can pin point the source of issues with poor conceptualization of security requirements. For example missing a domain description of a malicious actor in the environment of operation OR perhaps a missing system specification that allows exploitable weaknesses in the developed system OR even missing security needs from the stakeholder!

---

class: middle
# How to systematically reason about these issues?
- Solution: Abuse frames

.footnote[
Technical Report No: 2003/10, [Analysing Security Threats and Vulnerabilities Using Abuse Frames](http://mcs.open.ac.uk/mj665/Abuse00.pdf), L.Lin, B.A.Nuseibeh, D.C.Ince, M.Jackson, J.D.Moffett, October 2003
]

???
Now that we are comfortable reading Frame diagrams, let's use them to understand the fundamental approach to identifying and refining security requirements. This approach leads to a systematic elicitation of security requirements initiated by domain descriptions of malicious (or in some cases clumsy) agents in the environment of operation.

This approach is described in a 2003 technical report, which calls these problem frame diagrams for security requirements elaboration as Abuse Frames.
---
class: middle
# Abuse Frame
![af](images/abuse-frame.png)

## Abuse argument
- For an attacker (AT), the specification of the Malicious Machine (MM) satisfies the anti-requirement (AR)


???
The fundamental pattern, useful for security requirements elicitation is show in this problem frame or aptly named Abuse frame. Here the problem world is analyzed from the perspective of an Attacker. The attacker exists as a given domain in the environment of operation. The attacker wants to fulfill an anti-requirement to harm a given Asset domain. Now take note that the anti-requirement is a negative requirement from the perspective of the attacker. The Malicious Machine or MM can be the machine that is being built, or could be another machine that is used specifically by the attacker (e.g. a virus or a scanner) that is not originally part of the problem world (D).

Given this frame, the Abuse argument makes the case that for an attacker (AT), the specification of the Malicious Machine (MM) allows observable effects on the asset domain (AS) to satisfy the anti-requirement (AR).

This fundamental pattern, known as the abuse frame is the genesis of security requirements engineering process. Let's apply it to the mailfile problem world.

Some examples and definitions:

> Example 1:
M/M: Wireshark
AS: Network messages
AT: Rouge ISP
AR: Targeted Advertising

>Example 2:
M/M: FBI Website with SQL injection vulnerability  
AS: Identity Database
AT: Lulzsec
AR: Threaten FBI Agents through identity theft


>Malicious Machine (M/M)
Can be assigned to an existing domain, or a domain that is introduced into the problem world in order to reflect that an attacker can utilize the existing domains or other tools (e.g., a virus) that are not originally in the problem world D.

>Vulnerability v(D)
Conditions in the problem world that combined with the Malicious Machine specification, will satisfy the anti-requirements  
An instance of the problem world that gives rise to an opportunity for attacks

---
class: middle
# Abuse Frame 1 (mailfile example)
![abuse](images/example-af-2.png)
## .center[MS &#x2192; v(D), AR]

???
Here we see that the malicious machine domain is assigned to existing domain of the mailfile analyzer machine, but with a weakness in its specification. The weakness is that of not having any authentication. Such a machine allows the analysis report asset to be read, leading to the satisfaction of the anti-requirement of the malicious user in the problem world.

---

class: middle
# Security Problem Frame
![spf](images/security-problem-frame.png)

## Correctness argument
- For an attacker (A), the specification of the Security Machine (SM) satisfies the security requirement (SR)  
SM &#x2192; A, SR

???
Stating the abuse argument, allows a security requirements engineer to specify a security frame. The security frame is also specified from the perspective of an attacker in the environment of operation. But in this frame, a "security machine" domain is specified that prevents harm to the asset by satisfying the security requirement (SR). The Security Machine or SM can be the machine that is being built, or could be another machine that is built specifically stop the attacker (e.g. an authentication module). The security machine represents active protection mechanisms. Which means that this kind of protection mechanism adds code to the software or system being built.

Given this frame, the correctness argument makes the case that for an attacker (AT), the specification of the Security Machine (SM) allows observable effects on the asset domain (AS) to satisfy the security requirement (SR).

---
class: middle
# Security Frame (mailfile example)
![sfmailfile](images/example-sf.png)

???
Applying the security frame pattern to counter the abuse frame for the mailfile example could result in a security frame as shown. Here we have introduced a Customer identifier security machine that satisfies the security requirement to identify and authorize the customer. We have also introduced a designed domain of an authentication database that allows the result domain to reflect the status of the identify of the Customer domain.

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

???
Examining the abuse frame and the corresponding security frame next to each other demonstrates a systematic reasoning method to identify protection mechanisms needed in response to the attacks perceived in the environment of operation.

This approach aligns well with our definition of software assurance, which took an attack based approach to undertake engineering activities in the system development lifecycle. That is exactly what we did here.

But we are not done. This is just the first step. As security professionals, we should anticipate that attackers will improvise in response to protection mechanisms. So a couple more rounds of analysis should be carried out.

---
class: middle
# Iterative Process
## Another Abuse Frame
![abuse](images/example-af-3.png)

???
For example, the attacker can use a malicious machine  SQL injection weakness

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
- Security functions  
  Security Functional Requirements - Active Protections
- No exploitable weaknesses  
  Assurance and Strength requirements - Passive Protections

---
# The Design Problem
## S &#x2192; D, R   
S is resilient to attacks, when D includes an Attacker (A) trying to implement (AR)

---
class: middle
# Active Protection Security Requirements

## Security functions in the specification (S)   
E.g. Encryption module, access control
## Security constraints on the problem world (D)  
E.g. Controlled physical access, access logs, cleared user base, authorization db

---
class: middle
# Passive Protection Security Requirements  

## Weaknesses avoided in security functions of the specification (S)     
E.g. Injection, memory issues, weak crypto algorithms or implementation  
E.g. _For openSSL_: Encryption module minimizes exploitable buffer overflow weaknesses to an acceptable level  
## Weaknesses avoided in the problem world (D)  
E.g. password sticky notes, guessable passwords, ad-hoc authorizations, poor clearance processes

---
# More Examples
.left-column[
## Active
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
## Passive
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
![bridge](https://www.history.com/.image/ar_1:1%2Cc_fill%2Ccs_srgb%2Cfl_progressive%2Cq_auto:good%2Cw_1200/MTY1MTc3MjE0MzExMDgxNTQ1/topic-golden-gate-bridge-gettyimages-177770941.jpg)
]

---
class: middle, center
# Questions?
![questions](https://media.giphy.com/media/ccRdPf8zWkivm/giphy.gif)
