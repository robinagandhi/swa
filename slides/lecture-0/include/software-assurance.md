class: center, middle
# Software Assurance

???

What is Software Assurance? Perhaps the word Assurance is not familiar to you. It is certainly different than Insurance. While one might think that Assurance is similar to Trust, they are related but different. Assurance is the basis for making trust decisions. In this course, we are interested in making trust decisions about software. Which is a bit of a challenge. You see, trust decisions are often made at the system level. Which prompts discussions like this --> next slide

---
exclude:true
class: center, middle
![Dilbert](http://assets.amuniversal.com/ea1384e06cbb01301d46001dd8b71c47)
???
Fixing software bugs presents a high-cost when software is already in production. Imagine fixing/replacing a lego block that is embedded deep within your structure!
---
exclude:true
class: center, middle
![Dilbert](http://assets.amuniversal.com/73bbbf606d5c01301d80001dd8b71c47)
???
We have now come to tolerate bugs in software. The "business as usual" culture at its best.
---
exclude:true
class: center, middle
![Dilbert](http://assets.amuniversal.com/26c55a909fd8012f2fe600163e41dd5b)
???
As organizations struggle with the quality/cost of in-house software development, outsourcing does not rid of the responsibilities. In fact, expressing expectations and assessing becomes even more important!
---
exclude:true
class: center, middle
[![sandworm](https://regmedia.co.uk/2014/10/14/sandworm_vuln_logo.jpg)](http://www.theregister.co.uk/2014/10/14/isight_microsoft_announce_windows_and_windows_server_0day/)
???
As we explore this course topic, it helps to know about recent day software failures. Each one of these send organizations scrambling for testing and applying patches in their environments.

2014 Sandworm used a zero day exploit in all version of Microsoft Windows. The vulnerability exists in PACKAGER.DLL, which is a part of Windows Object Linking and Embedding (OLE) property. By using a crafted PowerPoint document, an .INF file in embedded OLE object can be copied from a remote SMB share folder and installed on the system. Attackers can exploit this logic defect to execute another malware, downloaded via the same means. [Source: http://blog.trendmicro.com/trendlabs-security-intelligence/an-analysis-of-windows-zero-day-vulnerability-cve-2014-4114-aka-sandworm/]

CVE: https://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2014-4114
CWE: Improper Input Validation (CWE-20)
---
exclude:true
class: center, middle
[![Heartbleed](http://heartbleed.com/heartbleed.png)](http://heartbleed.com)
???
2014 Heartbleed in the OpenSSL library was really a wake-up call for organizations using poor management practices for software acquisition and inventory. Many organizations started paying attention to open source software risk management after this incident. This bug involved a buffer length check issue that allowed an attacker to read all memory contents including SSL\TLS keys used for encryption. At the time, none of the open source or proprietary static or dynamic analysis tools
could discover this vulnerability.
CWE-130: Improper Handling of Length Parameter Inconsistency

---
exclude:true
class: center, middle
[![shellshock](https://upload.wikimedia.org/wikipedia/commons/thumb/4/44/Shellshock-bug.png/440px-Shellshock-bug.png)](https://en.wikipedia.org/wiki/Shellshock_%28software_bug%29)

???
# Shellshock or Bashdoor
A issue in the bash shell that allowed arbitrary commands to be executed when the commands are concatenated to the end of function definitions stored in the values of environment variables. Within days of the publication of this, intense scrutiny of the underlying design flaws discovered a variety of related vulnerabilities, (CVE-2014-6277, CVE-2014-6278, CVE-2014-7169, CVE-2014-7186, and CVE-2014-7187).
---
exclude:true
class: center, middle
[![ghost](http://www.upstream.be/wp-content/uploads/2015/01/red-gost.jpg)](https://blog.qualys.com/laws-of-vulnerabilities/2015/01/27/the-ghost-vulnerability)
???
The GHOST vulnerability is a serious weakness in the Linux glibc library. It allows attackers to remotely take complete control of the victim system without having any prior knowledge of system credentials. CVE-2015-0235 has been assigned to this issue. The flaw existed in a DNS client-side resolver in glibc, and was exploitable through the use of a particular function called getaddrinfo(). It allowed attackers to use DNS servers or domains in their control to essentially takeover systems and applications running the flawed software. All major Linux distributions and the glibc project have issued patches for the problem.

---
exclude:true
class: center, middle
# [Marshalling Pickles](https://frohoff.github.io/appseccali-marshalling-pickles/)
???
# Java Deserialization Bug
Object serialization technologies allow programs to easily convert in-memory objects to and from various binary and textual data formats for storage or transfer – but with great power comes great responsibility, because deserializing objects from untrusted data can ruin your day.

---
exclude:true
class: center, middle
# [#gotofail](https://www.imperialviolet.org/2014/02/22/applebug.html)
???
# Apple SSL/TLS bug
Two goto fail lines in a row. The first one is correctly bound to the if statement but the second, despite the indentation, isn't conditional at all. The code will always jump to the end from that second goto, err will contain a successful value because the SHA1 update operation was successful and so the signature verification will never fail.

---
exclude:true
class: center, middle
.left-column[
![meltdown](https://meltdownattack.com/images/meltdown.min.svg)
]
.right-column[
![specter](https://meltdownattack.com/images/spectre.min.svg)
]

???
* 2017
Meltdown and Spectre exploit critical vulnerabilities in modern processors. These hardware vulnerabilities allow programs to steal data which is currently processed on the computer. While programs are typically not permitted to read data from other programs, a malicious program can exploit Meltdown and Spectre to get hold of secrets stored in the memory of other running programs. This might include your passwords stored in a password manager or browser, your personal photos, emails, instant messages and even business-critical documents.
https://meltdownattack.com

---
exclude:true
class: center, middle
## What % is FUD and Marketing?
[![issues](http://techrights.org/wp-content/uploads/2015/04/ven2-1024x774.png)](http://techrights.org/2015/07/01/sonatype-marketing/)

---
exclude:true
.left-column[
## [2016](http://www.csoonline.com/article/3013107/security/forecast-2016-security-takes-center-stage.html)
![2016](http://core0.staticworld.net/images/article/2015/11/cw_techforecast2016_03_budget_booms_and_busts-100629394-large.idge.png)
]
.right-column[
## 2018
![2018](https://zdnet1.cbsistatic.com/hub/i/2017/09/27/c65515b4-a564-44a0-9ee6-158df503f167/c138729965d13c1fd6b89d3e216911b9/itbudgetsinfographic09272017.jpg)
]
???
# 2016 Predictions

---
exclude:true
class: middle
# [Top Security Concerns in 2017](http://www.csoonline.com/article/3199937/security/top-5-infosec-concerns-for-2017.html)

## Based on Searches on CSOonline
- Network Security
- Networking
- Windows OS (ransomware related)
- OS security
- Active Directory
???
# 2017 Predictions. What are CSO's most worried about, perhaps it is reflected in their search patterns.
---

class: left, middle
## .blue[Most discussions of IT security focus on IT infrastructure and process, stopping short of security considerations related to the design and implementation of the application itself...]

.footnote[
Brian Morgan, CTO, Skyline Technologies
]
???
This is an interesting observation. The security community is too busy dealing with fixing things at the perimeter and largely ignoring the software assurance problem.
So while the tools for security are the most mature in the infrastructure security space, security considerations related to the design and implementation of the application itself remains a hard problem.

---
class: center, middle
# Right questions to ask?
[![goal](http://4.bp.blogspot.com/-ZveWaoZMrvg/T74y7Qu2PXI/AAAAAAAACxc/keSwGPQLXkU/s400/soccer_security_blog.png)](http://cacm.acm.org/magazines/2009/6/28488-answering-the-wrong-questions-is-no-answer/fulltext)

???
So if things are to change then what are the right questions to ask?

Let me tell you a story.  
[Source: http://cacm.acm.org/magazines/2009/6/28488-answering-the-wrong-questions-is-no-answer/fulltext]  
Two buddies leaving a bar find a man on his hands and knees in the parking lot. It looked like he was searching for something. Upon asking they find out that he had dropped his keys. He describes the keys, and says if the two men find them they will receive a reward. They begin to help search. Other people come by and they too are drawn into the search. Soon, there is a crowd combing the parking lot, with an air of competition to see who will be the first to find the keys.

Periodically someone informs the crowd of the discovery of a coin or a particularly interesting piece of rock. After a while, someone in the crowd stands up and asks, “Say, are you sure you lost your keys out here in the parking lot?” To which the man replies, “No. I lost them in the alley.”  Everyone stops to stare at the man. “Well, why the heck are you searching for them here in the parking lot!?” someone exclaimed. To which the man replied, “Well, the light is so much better here. And besides, now I have such good company!”

What's the take away message here?
If we don’t properly define the problem, ask the right questions, and search in the proper places, we may have good company and funding, but we shouldn’t expect to find what is really needed.

Here are a few examples questions that get asked often about software:  

How do I secure my general purpose software against all threats?  

How do I protect my software with an intrusion-detection system, data
loss and prevention tools, firewalls, and other techniques?  

How do I find coding flaws in the system I am using so I can patch them?  

Each of these questions implies it can be answered in a positive, meaningful way.
That is not necessarily the case.

---
class: center, middle
[![Tradition](images/tradition.png)](http://security.gloriad.org/blog/2007/10/21/traditional-thinking/)

???
To ask meaningful questions, we have to understand that the practice of security is to construct sufficient defenses against the likely threats, not all threats, using demonstrably effective engineering practices. Security solutions are the perimeter often have to deal with the problem of filtering the incoming and outgoing traffic. With very little tolerance for mistakes, these filters can only do so much. Finally, without consideration for security engineering during in software design, and complexity of software behaviors coding flaws are always going to be hard to find.

What does this all mean in the context of software assurance? In the next video we will look at the some of the ways in which organizations have attempted to answer questions about software assurance.

---
class: center, middle
# Software Assurance Definitions
???
Let's look at some of the ways in which organizations have attempted to answer questions about software assurance.
---
# [NASA Definition](https://sma.nasa.gov/sma-disciplines/software-assurance)
## The planned and systematic set of activities that ensures that .red[software processes and products] conform to requirements, standards, and procedures.
.red[Processes]: include all of the activities involved in designing, developing, enhancing, and maintaining software    

.red[Products]: include the software, associated data, its documentation, and all supporting and reporting paperwork

.top-right[
![umbrella](https://sma.nasa.gov/images/default-source/discipline-pages/Software_Assurance/software-assurance-umbrella.png)
]  
???
NASA has a long history of software engineering research and focus on software safety. It's definition of software assurance includes ...

The theme is focused on organizational processes. The definition emphasizes a well set of defined activities to achieve compliance with standards and procedures.  

The activities integrate throughout the software lifecycle and relate to products, i.e. the software artifacts.  

NASA stays away from the word security because both security and safety are covered under the umbrella of their software assurance effort and goal is correctness!

Most recently they have updated their webpage and added a bit more to this definition. Perhaps they are starting to see the need to differentiate security from other system qualities.
https://sma.nasa.gov/sma-disciplines/software-assurance However, the first part comes from the Committee on National Security Systems (CNSS)



---
# Committee on National Security Systems (CNSS)
## The level of confidence that .red[software] is free from .red[_vulnerabilities_], regardless of whether they are .red[intentionally] designed into the software or accidentally inserted later in its life cycle, and that the software functions in the intended manner.
???
CNSS provides guidance to DoD organizations that operate National Security Systems.
They define software assurance as the level of confidence that software is free from vulnerabilities, regardless of whether they are intentionally designed into the software or accidentally inserted later in its life cycle, and that the software functions in the intended manner.

This definition introduces some new things. First we see the primary focus on software vulnerabilities. We also see a consideration for the intention of the attacker, and the time of introduction.  While the outcomes are understood, it is not clear what engineering activities will get us there.

---
![NSA definition](images/nsa-def.png)
.footnote[
.red[NSA Center for Assured Software]
]
???
NSA Center for Assured Software was stood up in 2005. Their definition is similar to CNSS, but refine it to focus on **exploitable** vulnerabilities only.

NSA does not develop software, they only test it. So no emphasis on engineering here as well.
---
# DHS
## A planned and systematic set of multidisciplinary activities must be applied to ensure the conformance of both .green[software and processes] to requirements, standards, and procedures
.red[Trustworthiness]: the absence of .green[exploitable vulnerabilities] whether maliciously or unintentionally inserted  

.red[Predictable execution]: provides .red[justifiable confidence] that the software, when executed, will function as intended
???
Coming much later on the scene, the DHS definition includes elements from prior definitions, but adds a focus on engineering, vulnerabilities and justifiable confidence for a complex software property.

DHS wants to help its clients in the federal and public/private sector build better software. So their focus on engineering makes sense for their mission.

---
# Academic Circles
## Secure software cannot be intentionally .red[subverted or forced to fail]
The software that remains .red[correct] and predictable in spite of intentional efforts to compromise .red[dependability]
???
Here is another definition from a publication by software engineering practitioners in academia. Secure software...

This definition sets up a pretty high bar for software assurance, which would be very difficult to attain in practical settings.

---
# Software Engineering Institute

Application of .green[technologies and processes] to achieve a required level of .blue[confidence\*] that software systems and .red[services] function in the intended manner, are free from accidental or intentional vulnerabilities, provide .red[security capabilities appropriate to the threat environment], and .red[recover from intrusions and failures].

.footnote[
\*The use of the word .blue[confidence] implies that there is a .red[basis for the belief] that software systems and services function in the intended manner
]

???
The software engineering institute at Carnegie Mellon University is a Federally funded research and development center for the US Department of Defense (DoD). They have developed software assurance job competencies and curricula for software assurance for undergraduate and graduate programs.

In my review of this definition, I suggested to the authors to further clarify the word confidence in their definition using assurance. While the authors did not change the definition, they did add a footnote.  

In this definition, we see an additional dimensions. One related to security capabilities balanced with respect to the threat environment. The other related to recovery from intrusions and failures.

I really liked this definition, but again like the others it did not provide guidance for security engineering activities.

---
# A Definition focused on Software Security Engineering
## .red[Basis for the belief] that software will operate as expected in its .red[threat environment]
.red[Resist] most attacks  

.red[Tolerate] as many as possible of those attacks it cannot resist  

.red[Contain] the damage and recover to a normal level of operation as soon as possible for attacks that cannot be tolerated  

???

So, I decided to outline a definition that focuses on a practical security engineering challenge. The challenge is to develop basis for the belief...

The definition starts with a claim. "Sofware will operate as expected" is a desired outcome that is complex enough that we cannot possibly examine every circumstance related to it. So this claim is made reasonable by adding a qualifier of "within its threat environment". Which means that during software design, we have to carefully understand the threat environment. It also prevents us from making general statements about secure software. This understanding provides the challenges that need to be solved by security engineering activities. The first challenge is to enumerate and plan for known attacks. The second challenge is to expect and address unknown attacks, i.e. attacks that we don't even know about yet. Finally, acknowledge the fact that software will fail in the presence of a threat that it was not designed for. When such failures occur, the challenge is to engineer mechanisms that allow software to recover. This is "resiliency".

This definition sets up the context for software security engineering activities to take place.

We know that engineering activities focus on processes and products of software. So what should such activities focus on to stop attacks? What makes  attacks on software successful, i.e. turn into a vulnerability?
To answer this question meaningfully, we have to introduce the term software weakness
---

# [Software Weakness](https://cwe.mitre.org/documents/glossary/index.html#Weakness)

## A type of .red[mistake] in software that, in proper conditions, could contribute to the introduction of vulnerabilities within that software.
Weakness are any mistakes in implementation, design, or other phases of the software development lifecycle.
???
The focus on weaknesses is important to manage risk. That is what engineering does. It manages the risk of unexpected outcomes in the future by implementing effective controls in product design.

Managing Risk related to weaknesses is proactive, and is different than just discovering and patching known vulnerabilities, which is reactive.
--

## .red[Basis for the belief] that software will operate as expected in its threat environment increases if evidence from engineering activities is available for _reducing_ weaknesses in software processes and products.

???
In terms of software assurance, basis for the belief...

If instead you focus on only on vulnerability discovery, you run into the "n+1" vulnerability problem. You will never be able to hire enough blackhat hackers, if the foundational design and engineering effort is missing.

---
class: center, middle
# Software Security Engineering*
The .red[Engineering Challenge] is now established.   
Next &mdash; How do we go about it?   

.footnote[
\*it is not the same as Security Software Engineering
]

???
We will use the phrase "Software Security Engineering" interchangeably with Software Assurance. This phrase is better than just saying _secure software_. The phrase software security engineering reflects the intent that software has been designed, developed, and tested to operate as intended in its threat environment.
---
class: left, middle
## Probably the most serious risk in .red[system software] is incomplete design, in the sense that .red[inadvertent loopholes] exist in the protective barriers and have not been .red[foreseen by the designers].
.footnote[
The Ware Report, __1969__
]
???
Are these concerns fresh? think again!
---
class: left, middle
## The technical problem to be solved is that of determining .red[what constitutes an appropriate defense against malicious attack], and then developing hardware and software with the defensive mechanisms .red[built-in].
.footnote[
The Anderson Report, __1972__
]
???
Are these concerns fresh? think again!
---
class: center
# Course Goals
## .red[Internalize]
security engineering during the software development lifecycle
## .green[Assure]
through arguments that are supported by evidence from engineering activities
## .blue[Experience]
software security engineering by engaging in hand-on activities with Open Source Software
???
[Internalize](https://www.google.com/#q=define+internalize) means a behavior becomes second nature. For it to happen for an entire organization, it has to be be rooted in structured practices, methods and tools. We learn about several practices, methods and tools in this course that are also practical enough to internalize.

A desirable outcome of such engineering activities early is the resulting evidence that backs up the claims about security. This is the essence of structured argumentation for assurance that supports informed trust decisions. [Assure](https://www.google.com/#q=assure)

We will get to [Experience](https://www.google.com/#q=experience) these engineering activities in a team by applying them to Open Source Software projects.
---
class: center
# Course Methods
## Process Agnostic
Analysis applicable in any [lifecycle](https://en.wikipedia.org/wiki/Software_development_process) [.blue[strategy]](https://en.wikipedia.org/wiki/Rational_Unified_Process)  
## Lightweight
Share and [institutionalize](https://www.google.com/search?q=intitutaionalize) knowledge  
## Practical
Methods currently effective in professional [software engineering practice](https://www.bsimm.com/framework/)

???
To internalize security engineering activities, the methods that we choose have to be process agnostic, lightweight and practical. These will be our assessment criteria for all the methods that I introduce in the course.
## Process Agnostic
Analysis applicable in any [lifecycle strategy](https://en.wikipedia.org/wiki/Software_development_process)  
_Waterfall, Spiral, UML, Agile, etc._
## Lightweight
Share and [institutionalize](https://www.google.com/search?q=institutionalize) knowledge  
_Relevant and logically analyzable documentation_
## Practical
Methods currently used in software engineering practice  
_e.g., [Microsoft SDL](https://www.microsoft.com/en-us/sdl/), [BSIMM](https://www.bsimm.com/framework/), [SEI Curricula](http://www.cert.org/curricula/software-assurance-curriculum.cfm?)_
---

# Security .red[vs.] Safety, Reliability and Quality

## Common
Software works as expected despite the presence of certain internal and external stimuli, influences, and circumstances
--

## Different for Security
* The nature of external stimuli, influences, and circumstances:   
.red[An Intelligent, persistent attacker]

???
One question you might have or get asked is how is security engineering for software different than safety, reliability or quality engineering? After all they all want software to work as expected despite the presence of certain anomalies.

What is different for security is the nature of the anomaly. The anomaly in the context of security is not just due to accidents, user errors or component failures. But these anomalies are introduced by an intelligent and persistent attacker.

---
class: center, middle
# A Winning Strategy
???
To address this threat, we have to do a number of things from an engineering perspective. It is best explained by the next set of illustrations which I borrowed from Dr. Ron Ross, head of the FISMA program at the National Institute of Standards and Technology (NIST).

---
class: center, middle
![Security Engineering](images/1-engineering-ross.png)


---
class: center, middle
![Security Engineering](images/2-engineering-ross.png)

???
First we have to identify the critical mission and business functions supported by the software.

---
class: center, middle
![Security Engineering](images/3-engineering-ross.png)

???
This helps us to discover and reason about the relevant threats in the operational environment
---
class: center, middle
![Security Engineering](images/4-engineering-ross.png)
???
Since the threats are ever changing and increasing, we need a two pronged attack on the threat space.
---
class: center, middle
![Security Engineering](images/5-engineering-ross.png)
???
First, we have to make sure that the software design is sufficient to address the threat. i.e. the software design meets operational intent.
---
class: center, middle
![Security Engineering](images/6-engineering-ross.png)
???
Before, we deploy the design, we verify that the implementation meets the design intent.

At this point we have built-security-in.

This entire left half is the focus of software assurance and this course.
---
class: center, middle
![Security Engineering](images/7-engineering-ross.png)
???
Once deployed, we also have to monitor the software for its ability to resist the threats over time. i.e. software can preserve its operational intent over time.

For example, conduct regular vulnerability assessments and patching as well as monitor the interactions at the perimeter.

---
class: center, middle
![Security Engineering](images/8-engineering-ross.png)
???
If the threats exceed the design intent or evolve, then we have to provide appropriate feedback for software maintenance.

This entire right half is the focus of information assurance. We won't focus on this aspect in this course.
---
class: center, middle
# Are you ready for it?
.footnote[
[Rugged manifesto](https://ruggedsoftware.org)
]
???
While technology is necessary, it alone cannot solve the problem. We have to acknowledge that it is also a people problem. The rugged manifesto is another perspective that challenges software engineers and developers to pledge a resilient approach to software construction.
---
class: center, middle
## “_This whole economic boom in cybersecurity seems largely to be a consequence of .red[poor engineering]._”  
.footnote[
Carl Landwehr, CACM, February **2015**
]
???
The people problem is also captured well in this quote from Carl Landwehr.

My hope is that this course will prepare you with the right knowledge and tools to address this very important issue using an engineering mindset.

---
class: center, middle
# Discussion?
![that-dont-make-no-sense](https://media.giphy.com/media/DO5JobrylWL7i/giphy.gif)

???
Please do not hesitate to reach out if you have questions regarding this discussion. Go Mavs!
