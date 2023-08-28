class: center, middle
# Systems Security Engineering*

.footnote[
\*Based on Chapter 2 through 4 of [NIST SP 800-160v1r1](https://doi.org/10.6028/NIST.SP.800-160v1r1) which enhances
[ISO/IEC/IEEE 15288:2023
Systems and software engineering](https://www.iso.org/standard/81702.html) with security engineering activities

]

???
In our introduction to software assurance, we brought up the need to make trust decisions. We also discussed that the kind of software that we are concerned with is inherently complex and continually operates in threat environments. To provide an engineering-perspective to this problem, The National Institute of Standards and Technology (NIST) has developed the Systems Security Engineering publication. It is also referred to as NIST SP 800-160.

This publication enhances an existing internationally recognized ISO standard for systems and software engineering. The NIST special publication enhances this standard by identifying several security relevant actions in each step of the system or software lifecycle.

[Appendices to NIST SP 800-160](https://csrc.nist.gov/Projects/Systems-Security-Engineering-Project/publications)  
[ISO/IEC/IEEE 15288:2023
Systems and software engineering](https://www.iso.org/standard/81702.html)

---

class: center, middle
![Dilbert](http://assets.amuniversal.com/b7797c402f4901348be4005056a9545d)
???
Make no mistake, security engineering is hard but necessary. Particularly, when you have a well-resourced and capable adversary.

---
class: center, middle
# Agenda

### Need for Security Engineering  
### Terminology  
### Security Engineering Perspective  
### Security Engineering Framework

???
Here is are the primary topics for our discussion in this module. First, executive buy-in is necessary to institutionalize engineering processes. As a result, any attempts to gather evidence for assurance must be rationalized. So in the first part of the discussion, I will motivate the need for security engineering, because it represents a cost to be borne by system stakeholders. Next, I will introduce terminology that helps us develop a shared understanding of an engineering-driven perspective which leads to a framework to organize our activities during the system lifecycle. Finally, I will also discuss how our course topics fit within this security engineering framework.

Let's start by establishing a business case for security engineering.

---

![Tiers](images/dsb-taxonomy.png)
.footnote[
\*[Defense Science Board 2013 Report](https://dsb.cto.mil/reports/2010s/ResilientMilitarySystemsCyberThreat.pdf)
]

???
The [Defense Science Board](https://dsb.cto.mil) is a well respected DoD organization. The Ware Report, the first comprehensive discussion of the computer security problem, was developed by a task force from the Defense Science Board. More recently, they published a report on Resilient Military Systems and the Advanced Cyber Threat.

To motivate the recommendations in this report, the task force uses a threat hierarchy. This hierarchy describes capabilities of potential attackers, organized by level of skills and breadth of available resources

> Tiers I and II attackers primarily exploit known vulnerabilities. No significant resources required.

> Tiers III and IV attackers are better funded and have a level of expertise and sophistication sufficient to discover new vulnerabilities in systems and to exploit them

> Tiers V and VI attackers can invest large amounts of money (billions) and time (years) to actually create new vulnerabilities in systems, including systems that are otherwise strongly protected. Think about this one. Most businesses are woefully underprepared to handle such attacks. Also, it would be extremely costly to defend against such well-resourced adversaries.

Higher-tier attackers will use all capabilities available to them to attack a system but will usually try lower-tier exploits first before exposing their most advanced capabilities. Thankfully, Tier V and VI level capabilities are today limited to just a few countries such as the *United States, China and Russia*. Knowing this, the dominance of any one country in developing mass-market consumer electronic devices and network devices is perceived as a huge threat to the national security of other nations.

Some Terms on the Graph...

.red[Cyber]
> broadly used to address the components and systems that provide all digital information, including weapons/battle management systems, IT systems, hardware, processors, and software operating systems and applications, both standalone and embedded.

This definition helps us understand the kinds of software to this threat taxonomy.

Next, the attacks by these threats range from just plain nuisances to existential.  

.red[Existential]
> defined as an attack that is capable of causing sufficient wide scale
damage for the government potentially to lose control of the country, including loss or damage to significant portions of military and critical infrastructure: power generation, communications, fuel and transportation, emergency services, financial services, etc.

---

# Need for Security Engineering
## Vulnerabilities within organizations
- Tier 1: Known vulnerabilities (Lowest)
- Tier 2: .red[Unknown] vulnerabilities
- Tier 3: .red[Adversary-created] vulnerabilities (Highest)

--

## Visible Vulnerabilities
- Discovery and patching

--

## Invisible Vulnerabilities
- Sound security engineering



???

The DSB report also goes on to describe several tiers of vulnerabilities within organizations. The tiers include known vulnerabilities, unknown vulnerabilities, and adversary-created vulnerabilities. The important and sobering message conveyed by the Defense Science Board is that the top two tiers of vulnerabilities (i.e., the unknown vulnerabilities and adversary-created vulnerabilities) are, for the most part, totally invisible to most organizations!

Tier 1 vulnerabilities can be addressed by Discovery and patching. This is what most security teams in organizations are engaged in.

Tier 2 and Tier 3 vulnerabilities have to be addressed by sound systems security engineering.

Without such an effort, our systems and software that support critical missions and business operations, lack the trustworthiness to survive well-resourced, sophisticated cyber-attacks.

---
class: center, middle

![iceberg](http://www.titanicuniverse.com/wp-content/uploads/2014/12/iceberg.jpg)

.footnote[
\*.red[above the waterline] and .red[below the waterline] problems
]

???

If we think of an iceberg, the Tier 1 visible vulnerabilities are above the waterline and the invisible ones from Tier 2 and 3 are the ones below. They pose an existential risk! They are difficult to address and can potentially sink the entire ship!

In the security community these are often referred to as "above the waterline" and "below the waterline" problems

I hope this discussion provides a strong motivation to pursue security engineering activities throughout the system lifecycle. But engineering activities tend to be time and resource intensive. So we need a systems engineering perspective that identifies the cyber components that are relevant for the engineering effort. They help us scope the required engineering effort.

---
class: center, middle
# Systems Engineering View
.top-right[
    ![Abstractions](http://www.espen.com/graphics/math-answer-findx.gif)
]

???
Now we start to create a shared understanding of the cyber components that will be central to the systems engineering effort.

---
# Terminology

## System
Combination of interacting system .red[elements] organized to achieve stated purposes

## System Element
Recursively defined as a .red[system]  
Member of a set of elements that constitute a system  

> _Examples: hardware; .red[software]; firmware; data; facilities; materials; humans; processes; and procedures_

???
To create such an understanding, a shared vocabulary is needed for the systems engineering view. In this vocabulary, the first two terms are interesting in the sense that they are have a cyclical dependency. The term System means a
combination of interacting system .red[elements] organized to achieve stated purposes. The term System
element, means it is a system itself, but it is also a member of a set of elements that constitute a larger system.

Why such cyclical definitions?
> It allows us to support the notion of a system of systems.  
> The term **system** may apply to a collection of elements or a single element
> One observer's system may be another observer’s system element. This flexibility permits different stakeholder views to co-exist.

---
# Terminology

## System-of-Interest
System that is the focus of the .red[engineering] effort

## Enabling System
System that supports a .red[system‐of‐interest] during its life cycle stages but does not necessarily contribute directly to its function during operation  

> _Examples: code compilers, assemblers, prototypes, test harness, unit tests_

???
The systems engineering view allows us to make scoping decisions. By designating a system-of-interest, we identify the system that is the focus of the engineering effort. It is used to define the set of system elements, system element interconnections, and the environment that it operates in.

For appropriate scoping, it is also necessary to identify enabling-systems that are separate from the system-of-interest. Enabling systems are systems that supports a .red[system‐of‐interest] during its life cycle stages but does not necessarily contribute directly to its function during operation. For example, compilers and IDEs are enabling systems but don't directly contribute to the the software's function during operation.

---
# Terminology

## Other Systems
System that interacts with the .red[system‐of‐interest] in its operational environment

> _Examples: a global positioning system space vehicle being an “other system” interacting with a GPS receiver as the “system‐of‐interest.”_

???
Finally, systems-of-interest have to interact with other systems in its operational environment. Naturally, we will call them "other systems"! For example, if the system of interest is a GPS receiver, then the GPS satellite is an "other system" in its operational environment.

It helps to visualize this systems engineering view

---
class: center, middle
![NIST SP 800-160v1](images/view.png)  
Systems Engineering View

???
Things to note:
> The system-of-interest identification scopes the set of system elements, system element interconnections, and the operational environment where security engineering efforts are needed.
> _Other systems_ that interact with the system-of-interest are included in the operational environment.
> Finally, some enabling systems may exist outside the environment of operation, for example, the compiler used at the developer site, open source developer

In the context of your semester project, you will thinking about these concepts to develop a systems engineering view.
For example, you will have to think about _other systems_ that introduce risk for your selected open-source software in its operational environment. You will also have to identify _enabling systems_ that are critical to your chosen software package but not part of the system-of-interest. This analysis will help you effectively scope your project.

---
class: center, middle
# Security Engineering Perspective

???
From a systems engineering view, we can now define the goals and objectives of a security engineering perspective.

---
# Security Engineering Perspective

## .red[Security]
Freedom from conditions that can cause _loss of assets_ with _unacceptable consequences_

## .red[Engineering challenge]
Engineer .green[_protection capabilities_] for:
1. .red[assets] to which security applies and
1. .red[consequences] against which security is assessed

???

We now define security .red[Security] as freedom from conditions that can cause _loss of assets_ with _unacceptable consequences_

> Conditions are “What bad things that can happen” that are of interest to the engineering effort. These include disruptions, hazards and threats.

> Consequence are effects (i.e. change or no-change) associated with the conditions. The conditions are determined to exist in the operational environment of the system-of-interest. Conditions can be predicted based on historical data or attacks observed on similar systems.

Our primary goal is to engineer protection capabilities for the system-of-interest. All engineering efforts need metrics to define success. In this case the success of the protection capabilities is determined by their ability to prevent the consequences (i.e. effects associated with conditions in the operational environment) against which security is assessed.

---
# Security Engineering Perspective

## Goal: _have .red[protection capabilities] built-in..._

### .red[Active Protections]
* .red[Mechanisms] that exhibit security behavior with functional and performance properties to satisfy security requirements

### .red[Passive Protections]
* Provides the environment for the .red[execution] and .red[construction] of all mechanisms (general purpose and security)

???

Engineering takes a lifecycle perspective. So our goal is to have the protection capabilities built-in! Not bolted on later.

Protection capabilities resulting from security engineering efforts are of two types:

> Active Protection:
These are mechanisms or system features that explicitly satisfy security requirements. They have functional security properties i.e. we add code to the system-of-interest that is directly relevant to security.

> Passive Protections: Provides the environment for the .red[execution] and .red[construction] of all mechanisms (general purpose and security)
For example, developer training in secure coding provides for the construction of security mechanisms with a higher level of assurance. Similarly, a fully patched and hardened java runtime environment provides a protection capability to the hosted java applications. A visual studio complier with the appropriate compiler flags is also a passive protection. These are security properties don't typically add any code to the system of interest. Instead, they provide the assurance that the security relevant code added to the system of interest is actually effective against attacks.

---
# Protection Examples

## Active Protections

- Access control
- Single sign-on
- Identification
- Authentication
- Encryption at rest and in transit
- Configurations
- Backup
- Two-phase commit
- Filters/Wrappers
- Validators
- ...

???
With these definitions let's look at some examples of active and passive protections.
Again, active protection, include mechanisms that add code to the system-of-interest that provide capabilities such as access control, single-sign-on, input validators, etc. So the next question we ask from an engineering perspective is: How strong is the protection mechanism? How good is the code? How good is the architecture that organizes the code? How much effort was put in to identifying the right security requirements? How well do we understand the conditions in the operational environment that led to the identification of the security requirements?

These questions are typically addressed by passive protections that address the strength and assurance questions about active protections.

---
# Protection Examples

## Passive Protections

- Security Requirements
- Architecture
- Design
- Coding guidelines
- Code review
- Developer and user training
- Verified and configured compilers
- Acquisition policies
- Red-teaming
- Project management
- Runtime environments
- ...

???
Engineering effort is time and resource intensive. So depending on the criticality and available resources, we have to decide how much assurance is enough assurance? Of course, there is no excuse for not doing engineering activities that are industry best practices. Today customers and courts have come to expect security engineering activities that are supported effectively with easily available tools and trained personnel. The question then becomes, how much do you go beyond established best practices? The answer to this question is determined by the risk-reward consideration that is specific to the organization and the supported business processes.

So we now introduce the notion of adequate security.

---
# Adequate Security

## A well-reasoned sum of both active and passive protections

### For all .red[system execution modes]
e.g., initialization, operation, maintenance, training, shutdown

### For all .red[system states]   
e.g., secure, nonsecure, normal, degraded, recovery

### For all .red[transitions]
Between system states and between system execution modes.

???

Engineering involves making informed trade-offs. So adequate security is a "well-reasoned" sum of both active and passive protections. These protections should apply in all system states to prevent the consequences against which security is assessed.

For Rugged Software, **gradation** is important and hence reflected in our definition of _adequate security_.

---
class: middle, center
# Security Engineering Framework

???
With the security engineering effort now becoming clear, we organize related activities in a security engineering framework.

---
# Framework

### .red[Problem] Context
A sufficiently complete understanding of the problem
--

### .red[Solution] Context
Transforms the security requirements into design requirements for the system
--

### .red[Trustworthiness] Context
Evidence-based demonstration, through reasoning, that the system-of-interest is deemed trustworthy

???
Security engineering activities that are commonly understood are within the problem context and the solution context. We know that a sufficiently complete understanding of the conditions in the operational environment is needed to understand the required protection capabilities.

We also know that the security requirements need to be transformed into a design that can stop known attacks, tolerate unknown attacks and recover quickly from attacks that it cannot tolerate.

What is often not known or practiced are engineering activities in the trustworthiness context. These activities result in an evidence-based demonstration, through reasoning that the that the system-of-interest is deemed trustworthy. Which means that we have an adequate combination of active and passive protections built-in.


---
class: center, middle
![NIST SP 800-160 Chapter 2](images/framework.png)  
???

???
Figure source: [NIST SP 800-160 Systems Security Engineering](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-160v1.pdf)

The figure establishes the problem, solution, and trustworthiness contexts as key components of a systems security engineering framework. This setup ensures that the security of a system is based on achieving a sufficiently complete understanding of the problem, which translates into effective security solutions that are sufficiently trustworthy.

These contexts employ systems security analyses that includes concepts, principles, means, methods, processes, practices, tools, and techniques necessary to provide relevant data and technical interpretations of issues from the security perspective.

These contexts also support gradation, i.e. They can be differentiated to align with the scope and objectives of where they are applied. The are performed with a level of fidelity, rigor, and formality to produce data with a level of confidence that matches the assurance required by the stakeholders and engineering team.

You can also see that the framework is independent of system type. It is independent of the acquisition or process model. It is also not to be interpreted as a sequence of flows or process steps but rather as a set of interacting contexts, (problem, solution and trustworthiness), each with its own checks and balances.

---
# Problem Context (1/2)
.top-right[
    ![Problem Context](images/problemcontext.png)
]
## .red[Define Security objectives]
What it means to be _adequately_ secure for the assets and the consequences of asset loss against which security will be assessed

## .red[Define Measures of success]
Strength of protection and level of assurance in the engineered protection capability

???
Let's look at some of the activities within each context
The problem context defines several things:

> First it defines the Security Objectives
This is where you start to think of your mission/business processes. What assets are important and the consequences against which security will be assessed.

> Second it defines the measures of Success
The security objectives need measures of success. The two combine to drive the development of specific security-related claims that need support through evidence collected from engineering activities.

---
# Problem Context (2/2)
.top-right[
    ![Problem Context](images/problemcontext.png)
]
## .red[Define Life cycle security concepts]
> Distinct contexts for interpretation of security and the associated processes, methods, and procedures

???
Next, the problem context also defines the lifecycle security concepts. Which means that the problem context not only informs the interpretation of security in the early stages of concept development but also in the rest of the lifecycle stages. This can range from development to   production, maintenance as well as retirement.

--

## .red[Define Security requirements]
> Specifies the functional, assurance, and strength characteristics for a protection mechanism

## .red[Evidence for security aspects of the problem]
> How well do we understand stakeholder protection needs?


???
Finally, the problem context defines the security requirements in terms of the active and passive protections. Let's take an example of an access control protection mechanism to understand its functional, assurance, and strength characteristics

> Access Control itself is as a functional requirement as it requires developing code for the system of interest
> Secure coding standards followed in the development of that code is an assurance requirement  
> Rigor in enforcement and granularity of access control is a strength characteristic  
> Rigor in the coding standard and its security relevance is also a strength characteristic  

In the problem context we also collect evidence that the problem context itself reflects a good understanding of the stakeholder protection needs and concerns.

---
# Solution Context
.top-right[
    ![Solution Context](images/solutioncontext.png)
]

### .red[Define security aspects of the solution]:
- The security architecture views and viewpoints
- The security design
- Security performance verification measures

### .red[Realize security aspects of the solution]:
- Implementation of the system security design

### .red[Evidence for security aspects of the solution]:
- Analysis, demonstration, inspection, and test

???
The solution context as expected, defines security aspects necessary for the architecture and design followed by the implementation of the design. In this context we collect evidence that assures that the developed solution meets the security objectives and requirements from the problem context.


---
# Trustworthiness Context
.top-right[
    ![Trustworthiness Context](images/trustworthinesscontext.png)
]
### .red[Developing and maintaining the assurance case]
- Assurance cases are developed for claims based on the security objectives and associated measures of success

### .red[Demonstrating that the assurance case is satisfied]
- An assurance case is a well-defined and structured set of arguments and a body of evidence showing that a system satisfies specific claims with respect to a given quality attribute

???
Activities in the trustworthiness context focus on developing a "well-reasoned" argument for the trustworthiness of the problem and solution contexts.

Specifically we develop assurance cases or claims based on the security objectives and associated measures of success. This assurance case is a a well-defined and structured set of arguments and a body of evidence showing that a system satisfies specific claims with respect to a given quality attribute

Assurance cases also provide reasoned, auditable artifacts that support the contention that a claim or set of claims is satisfied, including systematic argumentation and its underlying evidence and explicit assumptions that support the claims [ISO/IEC 15026-2]

---

class: center, middle
![NIST SP 800-160](images/framework-course-topics.png)  
???
Figure source: [NIST SP 800-160 Systems Security Engineering](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-160v1.pdf)

The topics we will discuss in the rest of the class will align with this security engineering framework. We will learn to apply methods from the practice of security requirements engineering in the problem context. We will learn about design patterns, architectural principles, threat modeling and secure coding methods in the solution context. We will also learn how to develop good assurance cases as part of the trustworthiness context.

---
![lifecycle processes](images/systems-engineering-lifecycle-processes.png)
???
Figure source: [NIST SP 800-160](https://doi.org/10.6028/NIST.SP.800-160v1r1)

While the NIST SP 800-160 document is very comprehensive, this rest of the class will focus on the technical processes and the related security engineering enhancements.

---
class: center, top
# Questions

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">The future of cybersecurity can be summarized in three words--architecture, architecture, architecture. It&#39;s time to check under the hood instead of admiring the exterior of the car. <a href="https://twitter.com/hashtag/NIST800160?src=hash&amp;ref_src=twsrc%5Etfw">#NIST800160</a> <a href="https://twitter.com/hashtag/NIST800207?src=hash&amp;ref_src=twsrc%5Etfw">#NIST800207</a> <a href="https://twitter.com/hashtag/DevSecOps?src=hash&amp;ref_src=twsrc%5Etfw">#DevSecOps</a> <a href="https://twitter.com/hashtag/SystemsSecurityEngineering?src=hash&amp;ref_src=twsrc%5Etfw">#SystemsSecurityEngineering</a> <a href="https://twitter.com/hashtag/CyberResiliency?src=hash&amp;ref_src=twsrc%5Etfw">#CyberResiliency</a> <a href="https://twitter.com/hashtag/BuildSecurityIn?src=hash&amp;ref_src=twsrc%5Etfw">#BuildSecurityIn</a> <a href="https://t.co/tDPRxjIWJK">pic.twitter.com/tDPRxjIWJK</a></p>&mdash; Ron Ross (@ronrossecure) <a href="https://twitter.com/ronrossecure/status/1295168085763272705?ref_src=twsrc%5Etfw">August 17, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

???
In closing, I leave you with this tweet from Dr. Ron Ross, the head of the NIST FISMA project and the lead author of the 800-160 document. 
I look forward to comments and questions regarding this discussion.
