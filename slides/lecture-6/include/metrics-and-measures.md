class: center, middle
# .red[Metrics] and .green[Measures] for Software Security Engineering

???

In this video we will discuss how to approach the development of metrics to assess and control security engineering activites within a software project. 

Resources:
The structure of this discussion is inspired and adapted from Chapter 6 from Mead, N. R., & Woody, C. (2017). Cyber security engineering: A practical approach for systems and software assurance. Addison-Wesley and related references in this chapter.

Chapter 6: Metrics https://learning.oreilly.com/library/view/cyber-security-engineering/9780134189857/ch06.html#ch06lev2sec1

---
class: middle
# Metrics and Measures

![xkcd-metrics](https://imgs.xkcd.com/comics/health_stats_2x.png)

???
We now live in a world where wearable sensors provide many measurements, but is it not often clear what I am supposed to do with those measurements. How to interpret these numbers in terms of my overall health? In software projects, a simillar situation exists. Aligning the project context with the right metrics that support decision making and change detection is important.

---
class: middle
# Why define .red[Metrics]?
Context: The engineered artifacts are too complex to be fully understood, but there is a desire to reduce risk
- Understand performance or diagnose issues
- Quantify an attribute
- Support inquiry or simulation
- Focus on claims/goals/outcomes

???
To start our discussion, let's establish the context. Typically we need to think about metrics when the engineered artifacts are so complex that their behaviors cannot be fully understood or enumerated. Yet, there is a desire to reduce the risk of a security compromise that could lead to various tangible and intangible asset losses. 

In this context, metrics assess the performance of our engineering activities in reducing security flaws. They can also help diagnose issues by testing a hypothesis about engineering activities, collecting related measures and generalize findings.

Well-defined Metrics also quantify an attribute of the problem, solution or the trustworthiness context of the software being developed. Easily undersood metrics can be benchmarked to understand deviations from expected norms. 

Finally, defining metrics early in the software lifecycle allows a manager to focus on on desired outcomes agnostic of the technologies that support those outcomes. More often than not, technologies often dominate the conversation about security contraints necessary for a software project, instead metrics re focus the conversation around outcomes relevant for the threat enviornment in which the software project will operate.

---
class: middle
# Characteristics of a good .red[Metric]?
- Easy to explain 

???
In the book, Security metrics, Jaquith discusses several characteristics of a good metric. First, the metric should be simple to explain. It should be straightforward to determine so that its meaning can be widely understood. 

--
- Consistently measured

???
Next, we should strive to minimize subjectivity in measurement, i.e. the metrics should be consistently measured, regardless of who or what tool is used to collect measurements. 

--
- Cheap to gather

???
Frequently collected metrics should also be cheap to gather, ideally using automation. If a metric is not cheap to gather, then it will likely not be collected frequently to inform decisions. 
--
- Expressible (time, money, counts, etc.)

???
Good metrics should be based on at least one countable unit of measure. For example, consider the metric “number of application security defects.” It is clear that it counts defects. So by using a countable unit of measure, any measurement process, manual or tool-supported, can consistently express the results in terms of the number of defects found. 

Multiple units of measure can also be combined in one metric, for example "number of application security defects per 1,000 lines of code,” provides two units of measure. By incorporating a second dimension, i.e. dividing by 1,000 lines of code, we have constructed a metric that can be used for benchmarking. This allows us to compare code quality within and across projects.

Finally, the metric must be contextually specific, which means it use for supporting decisions or taking meaningful actions is not a mystery. As, Jaquith puts it, a good metric ought to pass the “smell test.” You do not want managers wrinkling their noses and asking questions like “And this helps me how?”

--
- Can be benchmarked

--
- Contextually-specific

---
class: middle

# Security .green[measures] come from...
- Software 
- Engineering steps
- Engineers or vendor capabilities
- Software trust relationships
- Operational environment

???

While good metrics can be developed for many things, measures relevant to security at the very least should be collected these five things. First measures should be collected from the software itself. Next, the engineering steps used to create and maintain software also produce several insights. The capabilities of the software engineers developing the software or vendors from whom we acquire the software is important to understand personnel competency and readiness for security engineering. While most often ignored the trust relationships from the software to other systems and the controls on those connections should also be monitored. Finally, the threats in the operational environment in which the software executes should be monitored for changes. This will assure that the orginal design intent continues to align with the operational intent.

--

# Software Measurement
- Organization-wide program
- Active and Passive protection capabilites

???
Organizations should establish a broad software measurement program in place and add software security considerations to it rather than just consider security measures in a vacuum. At the level of a single project, Software Security measurement assesses two related but distinctly different types of protection capabilities. Active and Passive.

---
class: middle
# Built-in .blue[protection capabilities]

### .blue[Active Protections]
* .blue[Mechanisms] that exhibit security behavior with functional and performance properties to satisfy security requirements

???
A protection capability represents the “many things that come together” in a planned manner to produce an emergent security property. The protections must come together properly so as to do what the protections are supposed to do and to do nothing else, even when made to do something else. 

Active Protection capabilties are the security functions of the system that exhibit security protection behavior, and therefore, have functional and performance attributes. They have functional security properties i.e. we add code to the system-of-interest that is directly relevant to security. 

--

### .blue[Passive Protections]
* Provides the environment for the .blue[execution] and .blue[construction] of all mechanisms (general purpose and security)

???

Passive Protection capabilities offer the environment for the execution and construction of all security functions, including both active protection and general system functionality. 
For example, developer training in secure coding provides for the construction of security mechanisms with a higher level of assurance. Similarly, a fully patched and hardened java runtime environment provides a protection capability to the hosted java applications. A visual studio complier with the appropriate compiler flags is also a passive protection. These are security properties that don't typically add any code. Instead, they provide the assurance that the security relevant code is actually effective against attacks.

--

### .red[Metrics] for .blue[Protection Capabilities]
- Adequacy for threats
- Ability to avoid, resist, tolerate or recover from attacks

???
Now the development of metrics for active and passive protection capabilities should focus on two aspects. 
First, we need metrics for the adequacy of the protection capabilities to address expected threats in the operational environment.

Second, we need metrics that assess the ability of the protection capabilities to avoid certain attacks, resist attacks that we cannot avoid, and tolerate or recover from attacks that we cannot resist in the operational enviornment.

This second aspect prevents us from making general statements about "secure software". The developed metrics and resulting measures help enumerate and plan for known attacks, develop plans to resist unknown attacks, and finally understand how to tolerate and recover from attacks that we cannot resist. This is "resiliency".

---
class: middle

.left-column[ ## Measuring
- Emperical Data
- Cross-sectional/time-series
- Correlation
- Before and after
]

.right-column[ ## Modeling
- Risk Equations
- Annualized Loss Expectancy (ALE)
- Linear Algebra
- Why things happen?
]

???
Before starting to examine metrics proposed in various standards and frameworks, it is important to understand the difference between Measuring and Modeling.

Much of the measurement in security might actually refer to modeling, but they are different. It is quite natural to think about  “security metrics” from the point of view of modeling future threats, residual risk and potential losses. In contrast, empirical measurements show the current state of the world, but don't provide any explations as to why some projects are better than the other. While modeling is necessary to operationalize theories and validate them through measurements, it is a much more involved and difficult process. Good models supply us with rationales for measurement.

A good example of emperical measurements is the Build Security In Maturity Model or BSIMM. 
As a descriptive model, the only goal of the BSIMM is to observe and report real-world software security initiatives. They simply report observations, which in turn can be used as benchmarks to compare similar initiaties in an industy vertical.

On the other hand, NIST 800-53 Control Catalog and related baselines are a model.  They provide recommendations regarding what minimum security controls should be implemented based on the perceived criticality level of an information system, to minimize the possibility of damage from a security policy violation.


---
class:middle
# Case-Studies


.left-column[ ### [BSIMM](https://www.bsimm.com) 
> ![BSIMM](https://community.blackduck.com/servlet/rtaImage?eid=ka12H000000TP61&feoid=00N2H000004orQs&refid=0EM340000002Gmq)
]

.right-column[ ### [SMI](https://github.com/ossf/scorecard) 
![SMI](images/openssf_security_compressed.png)
]

???

In the rest of this module, using case-studies we will examine BSIMM and the Security Metric Initiave from the Open Source Security Foundation.

BSIMM is a way to measure software security initiatives in an entire organization or a project. Through emperical observations, the BSIMM scorecard also allows benchmarking software security initiatives across differenct sectors or for industry verticals such as finance, healthcare and technology. 

The Security Metrics Initiative case study will demonstrate how automation can be used to support valuable decisions about threats and risks associated with open source projects. 