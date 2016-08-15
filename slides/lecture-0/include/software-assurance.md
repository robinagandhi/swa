class: center, middle
template: inverse
# .large[Software Assurance]
---

class: center, middle
![Dilbert](http://assets.amuniversal.com/ea1384e06cbb01301d46001dd8b71c47)
---
class: center, middle
![Dilbert](http://assets.amuniversal.com/73bbbf606d5c01301d80001dd8b71c47)
---
class: center, middle
![Dilbert](http://assets.amuniversal.com/26c55a909fd8012f2fe600163e41dd5b)
---
class: center, middle
[![sandworm](https://www.isightpartners.com/wp-content/uploads/2014/10/sand_worm_logotype-e1413241743641.jpg)](https://www.isightpartners.com/2014/10/cve-2014-4114/)
---
class: center, middle
[![Heartbleed](https://upload.wikimedia.org/wikipedia/commons/thumb/d/dc/Heartbleed.svg/2000px-Heartbleed.svg.png)](http://heartbleed.com/)
---
class: center, middle
[![shellshock](https://blog.digicert.com/wp-content/uploads/2014/09/Shellshock.png)](https://en.wikipedia.org/wiki/Shellshock_(software_bug))
---
class: center, middle
[![ghost](http://www.upstream.be/wp-content/uploads/2015/01/red-gost.jpg)](https://blog.qualys.com/laws-of-vulnerabilities/2015/01/27/the-ghost-vulnerability)
---
class: center, middle
[![badlock](http://badlock.org/badlock.png)](http://badlock.org/)
---
class: center, middle
# [#gotofail](https://www.imperialviolet.org/2014/02/22/applebug.html)
---
class: center, middle
# [Quadrooter](https://www.defcon.org/html/defcon-24/dc-24-speakers.html#Donenfeld)
---
class: center, middle
# What % is FUD and Marketing?
[![issues](http://techrights.org/wp-content/uploads/2015/04/ven2-1024x774.png)](http://techrights.org/2015/07/01/sonatype-marketing/)
---

# 2014 Predictions
[![2014 predications](http://zdnet3.cbsistatic.com/hub/i/2014/10/04/aba00dfe-4c0a-11e4-b6a0-d4ae52e95e57/429c9df7a412d8ce2a0b8aceaa4b4276/security-2014-graph-620.jpg)](http://www.zdnet.com/article/cybersecurity-in-2014-a-roundup-of-predictions/)
---

# 2015 Predictions
## [Top 15 in 2015](http://www.itproportal.com/2015/01/07/security-trends-2015-predictions-round/#ixzz4H98O0kdp)
Internet of Things  
A growth in the cyber crime economy  
Supply Chain attacks  
Point of Sale attacks  
Renewed risk management  
New tools and solutions emerging  
Cyber insurance  
C-level and board influence  
**Major software flaws**  
Identity-as-a-Service  
Compliance and regulation  
Encryption  
Ransomware  
Major breaches  
Malvertising

---
# 2016 Predictions
[![2016](http://core0.staticworld.net/images/article/2015/11/cw_techforecast2016_03_budget_booms_and_busts-100629394-large.idge.png)](http://www.csoonline.com/article/3013107/security/forecast-2016-security-takes-center-stage.html)

---

class: left, middle
## .blue[Most discussions of IT security focus on IT infrastructure and process, stopping short of security considerations related to the design and implementation of the application itself...]

.footnote[Brian Morgan, CTO, Skyline Technologies]
???
This is an interesting observation. The security community is too busy dealing with fixing things from outside and dealing with the problem after it already is a serious problem. The predictions are almost about the things that the vendors can solve and can currently address. The latter part is the hard problem.

The software engineering community is too busy inventing solutions to build more and more complex pieces of software faster and cheaper.

---
class: center, middle
[![Tradition](images/tradition.png)](http://security.gloriad.org/blog/2007/10/21/traditional-thinking/)

---
class: center, middle
# Right questions to ask?
[![goal](http://4.bp.blogspot.com/-ZveWaoZMrvg/T74y7Qu2PXI/AAAAAAAACxc/keSwGPQLXkU/s400/soccer_security_blog.png)](http://cacm.acm.org/magazines/2009/6/28488-answering-the-wrong-questions-is-no-answer/fulltext)

???
Story time:  
[Source: http://cacm.acm.org/magazines/2009/6/28488-answering-the-wrong-questions-is-no-answer/fulltext]  
Two buddies leaving a tavern find a distressed and somewhat inebriated man on his hands and knees in the parking  lot, apparently searching for something.
They ask him what he has lost, and he replies that he has dropped his keys. He describes the keys, and says if the two men find them they will receive a
reward. They begin to help search. Other people come by and they too are drawn into the search. Soon, there is a crowd combing the lot, with an air of competition
to see who will be the first to find the keys. Periodically someone informs the crowd of the discovery of a coin or a particularly interesting piece of rock.
After a while, one in the crowd stands up and inquires of the fellow who lost his keys, “Say, are you sure you lost your keys out here in the lot?” To which the
man replies, “No. I lost them in the alley.”  Everyone stops to stare at the man. “Well, why the heck are you searching
for them here in the parking lot!?” someone exclaimed. To which the man replied, “Well, the light is so much better
here. And besides, now I have such good company!”

if we don’t properly define the problem, ask the right questions, and search in the proper places, they may have
good company and funding, but they shouldn’t expect to find what they are really seeking.

So it is in research—especially in cyber security and privacy. We have people seeking answers to the wrong
questions, often because that is where “the light is better” and there seems to be a bigger crowd around them. Until
we start asking questions that better address the problems that really need to be solved, we shouldn’t expect to
see progress. Here are a few examples of misleading questions:

* How do I secure my general purpose software against all threats?

* How do I protect my system with an intrusion-detection system, data
loss and prevention tools, firewalls, and other techniques?

* How do I find coding flaws in the system I am using so I can patch them?

Each of these questions implies it can be answered in a positive, meaningful way.
That is not necessarily the case.
We have generally failed to understand that when we build and deploy
systems they are used in a variety of environments, facing different threats.
There is no perfect security in any real system—hardware fails, people make
mistakes, and attacks outside our expectations may defeat our protection
mechanisms. If an attacker is sufficiently motivated and has enough resources
(including time), every system can be defeated in some manner.
If the attacker doesn’t care if the defeat is noticed, it may reduce the work factor
involved; as an obvious example, an assured denial-of-service attack can
be accomplished with enough nuclear weapons.

The goal in the practice of security is to construct sufficient defenses against the likely threats
---
class: center, middle
# .large[What is Software Assurance?]
---
# NASA Definition
## The planned and systematic set of activities that ensures that .red[software processes and products] conform to requirements, standards, and procedures.
### .red[Processes]: include all of the activities involved in designing, developing, enhancing, and maintaining software  

### .red[Products]: include the software, associated data, its documentation, and all supporting and reporting paperwork  
???
* The theme is organizational in nature and emphasizes a well thought-out set of activities to achieve compliance with organizational best practices, requirements standards and procedures.
* Process (a complete cradle to grave  approach for the software lifecycle)
* Products (this amounts to all the software artifacts produced
* NASA stays away from the word security because both security and safety are covered under the umbrella of their software assurance effort and goal is correctness !

---
# Committee on National Security Systems (CNSS)
## The level of confidence that .red[software] is free from .red[_vulnerabilities_], regardless of whether they are .red[intentionally] designed into the software or accidentally inserted later in its life cycle, and that the software functions in the intended manner.
???
- This understanding of software assurance is consistent with the use of the term in connection with information, i.e., information assurance (IA).
- A more technical definition which focuses on software flaws, intention, and time of introduction.  
- __lost the focus on engineering!__
---
# NSA Center for Assured Software
![NSA definition](images/nsa-def.png)
???
This center was stood up in 2005
* They focus on **exploitable** vulnerabilities only. Much more refined scope.
* NSA does not develop software, they only test it. So no emphasis on engineering here as well.

* Design analysis, however, is done before any code analysis.
* The "n+1" vulnerability problem. You will never be able to hire enough blackhat hackers, if the foundational design and engineering effort is missing.
---
# DHS
## A planned and systematic set of multidisciplinary activities must be applied to ensure the conformance of both .green[software and processes] to requirements, standards, and procedures
### .red[Trustworthiness]: the absence of .green[exploitable vulnerabilities] whether maliciously or unintentionally inserted
### .red[Predictable execution]: provides .red[justifiable confidence] that the software, when executed, will function as intended
???
DHS definition is a medely of all prior definitions with a focus on engineering, vulnerabilities and justifiable confidence for a complex system property
---
# Academics
## Secure software cannot be intentionally .red[subverted or forced to fail]
### The software that remains .red[correct] and predictable in spite of intentional efforts to compromise .red[dependability]
???
Leave it to academics to use big words!
---
# Software Engineering Institute
## Application of .green[technologies and processes] to achieve a required level of .blue[confidence\*] that software systems and .red[services] function in the intended manner, are free from accidental or intentional vulnerabilities, provide .red[security capabilities appropriate to the threat environment], and .red[recover from intrusions and failures].
.footnote[
\*The use of the word .blue[confidence] implies that there is a .red[basis for the belief] that software systems and services function in the intended manner
]
---
# Dr. Gandhi's Version
## .red[Basis for the belief] that software will operate as expected in its threat environment
### .red[Resist] most attacks
### .red[Tolerate] as many as possible of those attacks it cannot resist
### .red[Contain] the damage and recover to a normal level of operation as soon as possible
???
Highlights:
* The focus of the definition is on Assurance: Providing the _Basis for the Belief_
* Software behavior is tied to it threat environment (avoid making general statements about secure software)
* Account for known attacks
* Acknowledge unknown attacks and plan for them.
* Recover from failures --> This is "resiliency"
# This is outcome of Software Security Engineering
---
class: center, middle
# Software Security Engineering*
The .red[Engineering Challenge] is now established.   
Next &mdash; How do we go about it?   
.footnote[\*it is not the same as Security Software Engineering]
---
class: left, middle
## Probably the most serious risk in system software is incomplete design, in the sense that .red[inadvertent loopholes] exist in the protective barriers and have not been .red[foreseen by the designers].
.footnote[The Ware Report, __1969__]
???
Are these concerns fresh? think again!
---
class: left, middle
## The technical problem to be solved is that of determining .red[what constitutes an appropriate defense against malicious attack], and then developing hardware and software with the defensive mechanisms .red[built-in].
.footnote[The Anderson Report, __1972__]
???
Are these concerns fresh? think again!
---
class: center
# Course Goals
.left[## .large[[Internalize](https://www.google.com/#q=define+internalize)]
security engineering activities during the software development lifecycle]
.right[## .large[[Assure](https://www.google.com/#q=assure)]
through evidence-based security]
.left[## .large[[Experience](https://www.google.com/#q=experience)]
security engineering by engaging in hand-on activities with Open Source Software]
---

# Course Methods
## Process Agnostic
Analysis applicable in any [lifecycle strategy](https://en.wikipedia.org/wiki/Software_development_process)
- Waterfall, Spiral, UML, Agile, etc.

## Lightweight
Share and [institutionalize](https://www.google.com/search?q=intitutaionalize) knowledge
- Relevant and logically analyzable documentation

## Practical
Methods currently used in software engineering practice
- e.g., [Microsoft SDL](https://www.microsoft.com/en-us/sdl/), [BSIMM](https://www.bsimm.com/framework/), [SEI Curricula](http://www.cert.org/curricula/software-assurance-curriculum.cfm?)
---

# Security vs. {Safety, Reliability, Quality} Engineering

## Common
Software works as expected despite the presence of certain internal and external stimuli, influences, and circumstances
--

## Different
The nature of external stimuli, influences, and circumstances
A intelligent, persistent adversary
---
class: center, middle
# What does it take?

---
class: center, middle
![Security Engineering](images/1-engineering-ross.png)
---
class: center, middle
![Security Engineering](images/2-engineering-ross.png)
---
class: center, middle
![Security Engineering](images/3-engineering-ross.png)
---
class: center, middle
![Security Engineering](images/4-engineering-ross.png)
---
class: center, middle
![Security Engineering](images/5-engineering-ross.png)
---
class: center, middle
![Security Engineering](images/6-engineering-ross.png)
---
class: center, middle
![Security Engineering](images/7-engineering-ross.png)
---
class: center, middle
![Security Engineering](images/8-engineering-ross.png)
---
class: center, middle
# Are you ready for it?
.footnote[[Rugged manifesto](https://www.ruggedsoftware.org/)]
