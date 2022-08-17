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
# Why define Metrics?
Context: The engineered artifacts are too complex to be fully understood, but there is a desire to reduce risk
- Understand the performance of an engineering activity or diagnose issues
- Quantify a problem/solution/trustworthiness attribute
- Support discussion making, simulation and inquiry
- Put the focus on claims/goals/outcomes, 

???


---
class: middle
# Characteristics of a good Metric?
- Easy to explain 
- Consistently measured
- Cheap to gather
- Expressible (time, money, counts, etc.)
- Can be benchmarked
- Contextually-specific


???
Jaquith posits that a good metric has three characteristics [Jaquith 2007]:

• Simple to explain and straightforward to determine so the meaning can be widely understood

• Expressible in time, money, or something that can be converted into these readily accepted parameters

• Readily structured for benchmarking so that change can be quickly identified and evaluated

Further, a good metric must be consistently measurable, able to be gathered at a low cost (preferably automated), preferably quantitative (expressed as a number or percentage), and contextually specific to be relevant for decision makers to take action.

Frequently Computed Metrics Should Be Cheap to Gather

Good metrics should evaluate to a number. They should also contain at least one associated unit of measure that characterizes the things being counted. For example, the metric “number of application security defects” expresses one unit of measure—namely, defects. By using a unit of measure, the analyst knows how to consistently express results of a measurement process that looks for defects.

Expressible as a cardinal number or percentage with at least one unit of measure (time, money, counts, etc.)

But if one unit of measure is good, two are better. For example, a better metric might be “number of application security defects per 1,000 lines of code,” which provides two units of measure. By incorporating a second dimension (dividing by 1,000 lines of code), we have constructed a metric that can be used for benchmarking.

“Contextually specific” is a shorthand way of saying that a good metric ought to pass the “smell test.” You do not want managers wrinkling their noses and asking belligerent questions like “And this helps me how?”

---


