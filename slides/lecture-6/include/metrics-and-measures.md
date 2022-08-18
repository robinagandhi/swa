class: center, middle
# .red[Metrics] and .green[Measures] for Software Security Engineering

???

In this video we will discuss how to approach the development of performance metrics to assess and control security constraints within a software project. 

Resources:
The structure of this video is inspired from Chapter 6 from Mead, N. R., & Woody, C. (2017). Cyber security engineering: A practical approach for systems and software assurance. Addison-Wesley.

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
To start our discussion, let's establish the context. Typically we need to think about metrics when the artifacts that we are building or engineering are so complex that their behaviors cannot be fully understood or enumerated. Yet, there is a desire to reduce risk of a security compromise that could lead to various tangible and intangible asset losses. 

In this context, we seek to define metrics to understand the performance of our engineering activities in reducing security flaws or diagnosing issues using metrics to test a hypothesis and collecting measures to generalize findings.

Metrics can also help quantify some attribute of the problem, solution or the trustworthiness context of the software being developed. Easily undersood metrics can be benchmarked to understand deviations from expected norms. 

Finally, defining metrics early in the software lifecycle allows a manager to focus on on desired outcomes agnostic of the technologies that support those outcomes. More often than not, technologies often dominate the conversation about security contraints necessary for a software project, instead of the outcomes necessary for the threat enviornment in which the software project will operate.

---
class: middle
# Characteristics of a good .red[Metric]?
- Easy to explain 
- Consistently measured
- Cheap to gather
- Expressible (time, money, counts, etc.)
- Can be benchmarked
- Contextually-specific


???
In her book, Security metrics, Jaquith suggests that a good metric has the following characteristics. First, the metric should be simple to explain and straightforward to determine so that its meaning can be widely understood. Next, we should strive to minimize subjectivity in its measurement, i.e. it should be consistently measured, regardless of who or what tool is used to collect measurements. Frequently collected metrics should also be cheap to gather, ideally using automation. If a metric is not cheap to gather, then it will likely not be collected frequently to inform decisions. 

Good metrics should be based on at least one countable unit of measure. For example, the metric “number of application security defects” counts defects. By using a countable unit of measure, any measurement process, manual or tool-supported, can consistently express the results in terms of the number of defects found. Multiple units of measure can also be combined in one metric, for example "number of application security defects per 1,000 lines of code,” which provides two units of measure. By incorporating a second dimension (dividing by 1,000 lines of code), we have constructed a metric that can be used for benchmarking. This allows us to compare code quality to within and accross projects.

Finally, the metric must be contextually specific, which means it use for supporting decisions or taking meaningful actions is not a mystery. As, Jaquith puts it, a good metric ought to pass the “smell test.” You do not want managers wrinkling their noses and asking questions like “And this helps me how?”

---
class: middle

# Security .green[measures] come from...
* Software 
* Engineering steps
* Engineers or vendor capabilities
* Software trust relationships
* Operational environment

???

While many metrics can be developed, measures relevant to security can be collected from the software itself, the engineering steps used to create and maintain that software, the capabilities of the software engineers developing the software or vendors from whom we acquire the software, the trust relationships from the software to other systems and the controls on those connections, and finally, the threats in the operational environment in which the software executes.

Organizations should establish a broad software measurement program in place and add assurance considerations to it rather than just consider security measures in a vacuum. Software measurement assesses two related but distinctly different attributes: functional correctness and structural correctness. Functional correctness measures how the software performs in its environment. Structural correctness assesses the actual product and process implementation.

---

APPLICATION SECURITY

Applications are the electronic engines that drive most businesses. Microsoft Office, web servers, order-management software, supply chain management, and ERP systems are all applications that businesses rely on every day. Applications automate firms’ workforce

https://learning.oreilly.com/api/v2/epubs/urn:orm:book:9780321349989/files/graphics/f74tab01.jpg