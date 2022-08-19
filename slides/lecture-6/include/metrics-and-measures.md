class: center, middle
# .red[Metrics] and .green[Measures] for Software Security Engineering

???

In this video we will discuss how to approach the development of performance metrics to assess and control security constraints within a software project. 

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

Finally, defining metrics early in the software lifecycle allows a manager to focus on on desired outcomes agnostic of the technologies that support those outcomes. More often than not, technologies often dominate the conversation about security contraints necessary for a software project, instead of the outcomes necessary for the threat enviornment in which the software project will operate.

---
class: middle
# Characteristics of a good .red[Metric]?
- Easy to explain 

???
In her book, Security metrics, Jaquith suggests that a good metric has the following characteristics. First, the metric should be simple to explain and straightforward to determine so that its meaning can be widely understood. Next, we should strive to minimize subjectivity in its measurement, i.e. it should be consistently measured, regardless of who or what tool is used to collect measurements. 
--
- Consistently measured

--
- Cheap to gather

???
Frequently collected metrics should also be cheap to gather, ideally using automation. If a metric is not cheap to gather, then it will likely not be collected frequently to inform decisions. 
--
- Expressible (time, money, counts, etc.)

???
Good metrics should be based on at least one countable unit of measure. For example, the metric “number of application security defects” counts defects. By using a countable unit of measure, any measurement process, manual or tool-supported, can consistently express the results in terms of the number of defects found. Multiple units of measure can also be combined in one metric, for example "number of application security defects per 1,000 lines of code,” which provides two units of measure. By incorporating a second dimension (dividing by 1,000 lines of code), we have constructed a metric that can be used for benchmarking. This allows us to compare code quality to within and accross projects.

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

While many metrics can be developed, measures relevant to security can be collected from the software itself, the engineering steps used to create and maintain that software, the capabilities of the software engineers developing the software or vendors from whom we acquire the software, the trust relationships from the software to other systems and the controls on those connections, and finally, the threats in the operational environment in which the software executes.

--

# Software Measurement
- Organization-wide program
- Active and Passive protection capabilites

???
Organizations should establish a broad software measurement program in place and add software security considerations to it rather than just consider security measures in a vacuum. Software Security measurement assesses two related but distinctly different types of protection capabilities. Active and Passive.

---
class: middle
# Built-in .blue[protection capabilities]

### .blue[Active Protections]
* .blue[Mechanisms] that exhibit security behavior with functional and performance properties to satisfy security requirements

???
A protection capability represents the “many things that come together” in a planned manner to produce the emergent system security property. The protections must come together properly so as to do what the protections are supposed to do and to do nothing else (to include being made to do something else). 

Active Protection capabilties are the security functions of the system that exhibit security protection behavior and therefore, have functional and performance attributes. These functions explicitly satisfy security requirements that address the behavior, utilization, and interaction of and among technology/machine, environment, human, and physical system elements. These are mechanisms or system features that explicitly satisfy security requirements. They have functional security properties i.e. we add code to the system-of-interest that is directly relevant to security. 

--

### .blue[Passive Protections]
* Provides the environment for the .blue[execution] and .blue[construction] of all mechanisms (general purpose and security)

???

Passive Protection capabilities offer the environment for the execution and construction of all security functions (both active protection and general system functionality). These capabilities includes architecture, design, and the rules that govern behavior, interaction, and utilization. For example, developer training in secure coding provides for the construction of security mechanisms with a higher level of assurance. Similarly, a fully patched and hardened java runtime environment provides a protection capability to the hosted java applications. A visual studio complier with the appropriate compiler flags is also a passive protection. These are security properties don't typically add any code to the system of interest. Instead, they provide the assurance that the security relevant code added to the system of interest is actually effective against attacks.

--

### .red[Metrics] for .blue[Protection Capabilities]
- Adequacy for threats
- Ability to avoid, resist, tolerate or recover from attacks

???
The development of metrics for protection capabilities should focus on two aspects. 
First, we develop metrics for the adequacy of the protection capabilities to address expected threats in the operational environment.

Second, we develop metrics that help to assess the ability of the protection capabilities to avoid, resist, tolerate or recover from attacks in the operational enviornment.

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
Before you starting to examine metrics proposed in various standards and frameworks, it is important to understand the difference between Measuring and Modeling.

Much of the measurement in security might actually refer to modeling, but they are different. It is quite natural to think about  “security metrics” from the point of view of modeling threats, residual risk and potential losses. On the other hand, empirical measurements show the state of the world, but don't provide any explations as to why some projects are better than the other. While modeling is necessary to operationalize theories and validate through measurements, it is a much more involved and difficult process. Good models supply us with rationales for measurement.

A good example of emperical measurements is the Build Security In Maturity Model or BSIMM. As a descriptive model, the only goal of the BSIMM is to observe and report real-world software security initiatives. We simply report observations, which in turn can be used as benchmarks to compare similar initiaties in an industy vertical.

On the other hand, NIST 800-53 Control Catalog and related baselines are a model to provide recommendations regarding what minimum security controls should be implemented based on the perceived criticality level of an information system. 


---
class:middle
# Case-Studies


.left-column[ ### [BSIMM](https://www.bsimm.com) 
> ![BSIMM](https://www.bsimm.com/content/dam/bsimm/bsimm-assessment.jpg.imgw.850.x.jpg)
]

.right-column[ ### [SMI](https://openssf.org/blog/2021/05/03/introducing-the-security-metrics-project/) 
![SMI](https://openssf.org/wp-content/uploads/sites/132/2021/04/unnamed.png)
]


???

In the rest of this module, using case-studies we will examine BSIMM and the Security Metric Initiave from the Open Source Security Foundation.

BSIMM is a way to measure software security initiatives in an entire organization or a project. Through emperical observations, the BSIMM scorecard also allows benchmarking software security initiatives across differenct sectors or for industry verticals such as finance, healthcare and technology. 

The Security Metrics Initiative case study will demonstrate how automation can be used to support valuable decisive information about threats and risks associated with open source projects. Security Metrics comes with a cognitive dashboard for stakeholders to make reliable informed decisions regarding using/accommodating open source projects in their software supply chain.