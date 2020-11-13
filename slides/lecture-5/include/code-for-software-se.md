class: center, middle
# .red[Coding] for Software Security Engineering

???
Security engineering activities learned previously in the class clearly establish what security means for a solution that satisfies stakeholder security requirements. This analysis will help you identify code that implements active protection mechanisms and perform rigorous code reviews, tests, or even formal verification to assure that it is correct.


---
# Good Code
.right-column[
![xkcd-good-code](http://imgs.xkcd.com/comics/good_code.png)
]

???
Ultimately, we all want good code! To tell whether code is good or not, we need ways to measure the ability of code to resist attacks, tolerate attacks that it cannot resist, and contain damage and recover to a normal level of operation as soon as possible for attacks that is cannot tolerate.

Attacks are made possible by weaknesses in code. A way to identify and measure weaknesses in code can help minimize the possibility of attacks being successful.

---
class: middle
# What to .red[avoid]?
- Common Weakness Enumeration (CWE)
- Common Attack Pattern Enumeration and Classification (CAPEC)
- Common Vulnerabilities and Exposures (CVE)

???
Good code in particular minimizes the occurrence of weaknesses in code that leads to security issues. To make this assessment, we first need an enumeration of known weaknesses in software that lead to security issues.

An enumeration is typically defined as a complete, ordered listing of all the items in a collection. In this spirit, the common weakness enumeration knowledge base has been developed to help developers and security tools to describe and report weaknesses.

Similarly, testing for security requires launching attacks. Much like crash testing for safety testing. To assist in security testing efforts, the Common Attack Pattern Enumeration and Classification or CAPEC has been developed.

There is also much to learn from the countless vulnerabilities that are reported everyday. To facilitate efforts related to reporting and patching vulnerabilities, the common vulnerabilities and exposures database exists.

--

# What to .green[do]?
- Secure Coding Guidelines

???

Good code can also be defined in terms of defensive coding guidelines. Identifying and measuring such coding practices is facilitated by secure coding guideline knowledge bases.

We will look at all these knowledge bases in enough details that you can readily use them.

---

class: middle
# Building Abstractions

## .orange[Weaknesses]\* span a range of languages, products and environments
- Enumeration is appropriate

## .red[Vulnerabilities]\* in code are language, product or environment specific
- Dictionary is appropriate

.footnote[
\* Relationships between a [vulnerability](https://cwe.mitre.org/documents/glossary/#Vulnerability) and [weakness](https://cwe.mitre.org/documents/glossary/#Weakness)
]

???
Some knowledge bases are called enumerations while some are dictionaries. Computer scientists don't use these terms loosely.

Software weaknesses are abstract and hence finite. A single weakness definition can span a range of languages, products and environments. For a relatively finite list of weaknesses, an enumeration is appropriate. Hence the name Common Weakness Enumeration.

Vulnerabilities on the other hand are language, product and environment specific. There is no end to the number of vulnerabilities in software, but each instance is unique. So a dictionary is appropriate to organize vulnerabilities. The common vulnerabilities and exposures knowledge is a dictionary.

In one of the earliest modules, we also discussed the relationship between a vulnerability and a weakness. Vulnerabilities are a set of weaknesses that can be discovered by an attacker and exploited. Weaknesses are mistakes that make vulnerabilities possible. These mistakes can happen in any phase of the software development lifecycle.

---
class: middle

## Building Abstractions for .orange[Weaknesses]
Examine commonalities and differences in mistakes
???
Building a weakness enumeration requires examining the commonalities and differences in mistakes. This exercise results in a taxonomy, that can classify mistakes based on their characteristics.

--

### Leads to useful analysis
- Which class of mistakes to address first?
- What are the related mistakes in an attack vector?
- What are the known/reusable mitigations?


???
Such a taxonomy can lead to useful analysis such as which class of mistakes to address first? What are the related mistakes in an attack vector? What are the known/reusable mitigations?

---

class: middle
# Learning from .red[mistakes]

## Landwehr Software Flaw Taxonomy (1993)
- Genesis, Location, Time of introduction

???
One of the earliest successful efforts to build an enumeration, was the Landwher flaw taxonomy. It classified flaws along dimensions of genesis, location and time of introduction. This is one of the foundational papers in the field of cybersecurity.

--

## Other [efforts since](https://cwe.mitre.org/about/sources.html)...
- Seven Pernicious Kingdoms, PLOVER, 19 (Now 24) Deadly Sins, OWASP top ten etc,.

???
Several other notable efforts followed since. But no shared standard emerged that was build using community consensus mechanisms. Lack of a shared understanding of software weaknesses hampered progress in communicating, identifying and reporting them.

--

## Common Weaknesses Enumeration [(CWE)](http://cwe.mitre.org)
- Assimilates and advances categorization efforts

???
The department of homeland security recognized this issue and tasked MITRE to develop and maintain the common weakness enumeration that is built using community-input and consensus-based mechanisms.

---

![CWE](http://cwe.mitre.org/about/images/lg_consensus.jpg)

???
So as is to be expected from a consensus-derived solution, the CWE assimilates a lot of prior work in classifying and categorizing software weaknesses. In turn, it is now adopted and used by number of other efforts as shown in this diagram.

Starting in 2020, the CWE also include hardware weaknesses. The growing areas of IoT applications in industrial control systems, wearables, healthcare equipments, and automobiles makes this an important area to focus on.

---

class: middle
# CWE purpose
## Measurement
- Unified, .red[measurable] set of weaknesses

## Communication
- Effective .red[sharing], description, selection, and use of security tools and services

## Prioritization
- .red[Ranking] of weaknesses (e.g. [CWE Top 25](https://cwe.mitre.org/top25/archive/2020/2020_cwe_top25.html))

???
By providing a unique, short identifier to a weakness description, the purpose of the CWE is to make weaknesses measureable. This also aids in effective sharing of knowledge and consistent reporting of issues by different security tools. Measurability is desirable, so that weaknesses can be prioritized based on criteria such as frequency of occurrence and observed severity of their impact. For example, data from publicly reported vulnerabilities is now used to identify the mistakes that lead to them. This produces the CWE top 25 list (Visit website and observe).

---
class: middle
# CWE Descriptions
- Describe software .blue[behaviors] that operate on .green[resources] in ways that violate desired .orange[properties] that, under the right circumstances, can be exploited by .red[attackers] to cross a security boundary

???
CWE weaknesses are specified at different levels of abstraction. In general, they describe issues related to software behaviors, i.e. things a software does or doesn't do.

Through the behaviors, the software interacts with certain resources. This interaction that may violate certain security-relevant characteristics, i.e. properties, of the behavior or an individual resource.

This violation can be exploited by an attacker to cross a security boundary.

This will make more sense as we examine different weakness abstractions in the CWE.  

---
class: middle
# CWE organization
- .red[Pillar Weakness:] Most abstract, top-level.

> e.g. [CWE-682: Incorrect Calculation](https://cwe.mitre.org/data/definitions/682.html)

???
The most abstract weakness type is called a Pillar. It is the highest-level weakness that cannot be made any more abstract.

For example, Incorrect Calculation (CWE-682) is an example of a pillar, as it describes a mistake (incorrect calculation) but does not imply anything specific about where such a mistake is made or the type of resource that is affected.

---
class: middle
# CWE organization

- .red[Class Weakness:] Abstract, independent of any specific language or technology.

> e.g. [CWE-922: Insecure Storage of Sensitive Information](https://cwe.mitre.org/data/definitions/922.html) describes an issue (Insecure) with a behavior (Store) taken against a general type of resource (Sensitive Information).

???
Class weaknesses are more specific than a Pillar Weakness, but still abstract. They are typically independent of any specific language or technology. Fore example CWE 922 "Insecure Storage of Sensitive Information" describes an issue (Insecure) with a behavior (Store) taken against a general type of resource (Sensitive Information).

---
class: middle
# CWE organization
- .red[Base Weakness:] Abstract, sufficient details to infer specific methods for detection and prevention.

>  e.g. [CWE-134: Use of Externally-Controlled Format String](https://cwe.mitre.org/data/definitions/134.html) describes an issue (Inappropriate action) with a behavior (Use) taken against a specific resource (Format String) with a given property (Externally Controlled).

???
A Base weakness is more specific than a Class Weakness, so while being abstract, it has sufficient details to infer specific methods for detection and prevention. For example the base weakness (CWE-134) "Use of Externally-Controlled Format String" describes an issue (inappropriate action) with a behavior (Use of) taken against a specific resource (Format String) with a given property (Externally Controlled)

---
class: middle
# CWE organization

- .red[Variant Weakness:] Detailed, linked to a certain type of product, typically involving a specific language or technology.

> e.g. [CWE-467: Use of sizeof() on a Pointer Type](https://cwe.mitre.org/data/definitions/467.html) describes an issue (Use of) with a behavior (application of a function) against a resource (Pointer) within an implied language (those that support Pointer Types).

???
A Variant weakness is the most specific type of weakness description. It is linked to a certain type of product, typically involving a specific language or technology. For example CWE-467 "Use of sizeof() on a Pointer Type" describes an issue (Use of) with a behavior (application of a sizeof() function) against a resource (Pointer) within an implied language (those that support Pointer Types).

---
class: middle
# CWE organization
- .blue[Views:] A subset of CWE entries that provides a way of examining CWE content.   
e.g. [CWE-1000: Research Concepts](https://cwe.mitre.org/data/definitions/1000.html)

???
Views help to organize into convenient subsets. CWE-1000, the research concepts view is a rich hierarchy of weaknesses. Another useful view from a development lifecycle perspective is CWE-699, Software Development View, but the hierarchy is not as deep as CWE-1000.

--


- .orange[Category:] A set of CWEs with a common characteristic. A category is not a weakness!   
e.g. [CWE-320 Key Management Errors](https://cwe.mitre.org/data/definitions/320.html)

???
Another organizing unit in the CWE is a Category. It groups a set of CWEs with a common characteristic. Note that a category is not a weakness! You should not be mapping a CWE category to a mistake in software or hardware.  

---
# CWE Organization Example
### Pillar: [CWE-707: Improper Neutralization](https://cwe.mitre.org/data/definitions/20.html)

### Class: [CWE-20: Improper Input Validation](https://cwe.mitre.org/data/definitions/20.html)

### Base: [CWE-79: Improper Neutralization of Input During Web Page Generation ('Cross-site Scripting')](https://cwe.mitre.org/data/definitions/79.html)

### Variant: [CWE-85: Doubled Character XSS](https://cwe.mitre.org/data/definitions/85.html)

### View: [CWE-1000: Research Concepts](https://cwe.mitre.org/data/definitions/85.html)

### Category:[CWE-990: Tainted Input to Command](https://cwe.mitre.org/data/definitions/990.html)

???
Here is a collection of CWEs related to Cross-site scripting, which is a common mistake found in web applications. With cross-site scripting, an attacker can inject malicious scripts into the website's page structure, which is then delivered to other unsuspecting users. This weakness is clearly described in CWE-79. According to the CWE, its level of abstraction is a Base Weakness. We see that there are Class and Pillar weaknessess that are more abstract ways to describe this issue. CWE-20 Improper Input validation is a class weakness and CWE-707–Improper Neutralization is a Pillar weakness. We can also examine a more specific version of cross-site scripting with is CWE 85, Doubled Character XSS. Here the attacker inject two sets of malicious characters. Input validation if done incorrectly, may filter the first character but leave the second one in.

Finally, we see that all these weaknesses are part of the CWE 1000 Research Concepts view. Many of these weaknesses are also share a common characteristic of Tainted input to Command. So you will also find them as members of CWE 990 category.

---

# Finding the best CWE

## [Mapping Guidance](https://cwe.mitre.org/documents/cwe_usage/mapping_navigation.html)
- Map to a Weakness only
- .red[DO NOT] map to Categories or Views
- Map at the lowest abstraction level possible

## Search resources
- [Full text search](https://cwe.mitre.org/find/index.html)
- [Full listing](https://cwe.mitre.org/data/definitions/2000.html)
- Navigating views: [CWE-1000](https://cwe.mitre.org/data/definitions/1000.html), [CWE-699](https://cwe.mitre.org/data/definitions/699.html), [CWE-888](https://cwe.mitre.org/data/definitions/888.html)  
Expand all, Turn on .blue[_Show Details_] option
- For a CWE page, turn on .blue[_Mapping-Friendly_] option.  
Then navigate to parent, child, peer relationships

???
From a large CWE collection, it is important that we find the right CWE to describe a mistake in software. Let's look at the mapping guidance from the CWE maintainers. 


---

class: middle

# Exercise
## Map [CVE-2019-10097](https://nvd.nist.gov/vuln/detail/CVE-2019-10097) to a CWE

- Use this Vulnerability Description:  
In Apache HTTP Server 2.4.32-2.4.39, when mod_remoteip was configured to use a trusted intermediary proxy server using the "PROXY" protocol, a specially crafted PROXY header could trigger a stack buffer overflow or NULL pointer deference. This vulnerability could only be triggered by a trusted proxy and not by untrusted HTTP clients.  

--


- The [NVD Database](https://nvd.nist.gov/vuln/detail/CVE-2019-10097) maps this Vulnerability to   
[CWE 476](https://cwe.mitre.org/data/definitions/476.html) and [CWE 787](https://cwe.mitre.org/data/definitions/787.html)

---
exclude: true

<iframe src="https://embed.polleverywhere.com/free_text_polls/pKUP1ssJBP39qFC?controls=none&short_poll=true" width="100%" height="100%" frameBorder="0"></iframe>

---
class: middle
# Some CWEs to Remember
- [CWE-120](https://cwe.mitre.org/data/definitions/120.html): Classic buffer overflow
- [CWE-798](https://cwe.mitre.org/data/definitions/798.html): Use of hardcoded credentials
- [CWE-311](https://cwe.mitre.org/data/definitions/311.html): Missing encryption
- [CWE-434](https://cwe.mitre.org/data/definitions/434.html): Unrestricted upload of file with dangerous type
- [CWE-250](https://cwe.mitre.org/data/definitions/250.html): Execution with unnecessary privileges
- [CWE-494](https://cwe.mitre.org/data/definitions/494.html): Download of code without integrity check
- [CWE-22](https://cwe.mitre.org/data/definitions/22.html):  Path traversal
- [CWE-759](https://cwe.mitre.org/data/definitions/759.html): Use of one-way hash without a salt

## CWE Compatibility
- [CWE Compatibility and Effectiveness Program](http://cwe.mitre.org/compatible/index.html)

---

class: middle
# CWE Prioritization
## [Technical Impacts](https://cwe.mitre.org/cwss/cwss_v1.0.1.html#2.3.1) of [Weaknesses](https://cwe.mitre.org/cwraf/ti_scorecard.html)
1. Read data  
1. Modify data  
1. Denial-of-Service: unreliable execution  
1. Denial-of-Service: resource consumption  
1. Execute unauthorized code or commands  
1. Gain privileges / assume identity  
1. Bypass protection mechanism  
1. Hide activities  

## Top CWE lists
- [CWE Top 25](https://cwe.mitre.org/top25/index.html)
- Scoring mechanisms: [CWSS](https://cwe.mitre.org/cwss/index.html), [CWRAF](https://cwe.mitre.org/cwraf/index.html)

???
The technical impacts help focus on the set of weaknesses that contribute to the negative technical impact of relevance in a given context. This helps to filter and prioritize a set of weaknesses.

---

class: middle

# Attack Patterns

---

class: middle
# Common Attack Pattern Enumeration and Classification

## Enumerates .red[attack patterns] used in exploits
- Total of 500+ attack patterns
- Abstractions:   
Meta, Standard, Detailed Patterns and Categories

## CAPEC:  
- Patterns:  
[CAPEC-242](https://capec.mitre.org/data/definitions/242.html), [CAPEC-63](https://capec.mitre.org/data/definitions/63.html), [CAPEC-86](https://capec.mitre.org/data/definitions/86.html), [CAPEC-245](https://capec.mitre.org/data/definitions/245.html)    
- Views:    
[CAPEC 1000](https://capec.mitre.org/data/definitions/1000.html), [CAPEC-3000](https://capec.mitre.org/data/definitions/3000.html)

---
class: middle

# Vulnerabilities

---

class: middle
# Common Vulnerabilities and Exposures (CVE)

## One name for a vulnerability
- Akin to a .red[\#hashtag] to track all discussions and reports related to a [vulnerability in different databases](http://cve.mitre.org/about/)

![cve](http://cve.mitre.org/about/images/cve_example.gif)

---
class: middle

# [National Vulnerability Database](http://nvd.nist.gov)
- Maintains a dictionary of CVEs
- CVEs use Common Platform Enumeration (CPE) to identify affected products and packages. [Search Engine](https://nvd.nist.gov/vuln/search)
- Total CVEs: [NVD Dashboard](https://nvd.nist.gov/general/nvd-dashboard)

---

# Visual Recap
![relationships](images/CVE-CWE-CAPEC.png)

---
class: middle
# Secure Coding Guidelines

---
class: middle
# CERT Secure Coding Guidelines
- Normative requirements (aka. coding standards) for programming languages
- [C, C++, Java, Perl, and the Android platform](https://www.securecoding.cert.org)
- Software development and software security communities
- Violation does not mean vulnerability but a weakness


## Rules
- [DCL30-C](https://www.securecoding.cert.org/confluence/display/c/DCL30-C.+Declare+objects+with+appropriate+storage+durations), [MEM30-C](https://www.securecoding.cert.org/confluence/display/c/MEM30-C.+Do+not+access+freed+memory)

## Other resources
- [Secure Programs HowTo](http://www.dwheeler.com/secure-programs/Secure-Programs-HOWTO.html#LANGUAGE-SPECIFIC)

---
exclude: true
# Rejoicing Project Managers!
### Johnny, avoid these weaknesses!
- CWE

### Johnny...these are the ways of the bad guys
- CAPEC

### Johnny...learn from your mistakes
- CVE

### Johnny...follow secure coding guidelines
- Secure coding guidelines
.top-right[
![dr.evil](https://upload.wikimedia.org/wikipedia/en/1/16/Drevil_million_dollars.jpg)
]
---
exclude: true

class: middle
# Why Johnny Can't Write Secure Code?
---
exclude: true
class: middle
## Poor Johnny!
![poorjohnny](images/poorjohnny.png)

---
exclude: true
class: middle
## Training Surgeons
![GA](https://www.closerweekly.com/wp-content/uploads/2017/10/greys-anatomy.jpg?crop=0px%2C0px%2C594px%2C334px&resize=800%2C450)

---
exclude: true
class: middle
## Paradox we Face!
![paradox](images/paradox.png)

---
exclude: true
class: middle
# Reducing the Cognitive Overload

## When the Devil is in the Details...
- The details to consider for avoiding weaknesses are enormous during the coding phases

## ...simple, intuitive guides are need
---
exclude: true
class: middle
# Key Questions for a Weakness
### What are the .blue[Software flaws] (omission, commission, operational) that lead to the weakness?
### What are the defining characteristics of the .orange[Weakness]?
### What are the .green[Resources/Location] where the weakness is typically manifest?
### What are the .red[Consequences] that the weakness precedes?

---
exclude: true
# Do CWEs answer them?
### CWE-119: Failure to Constrain Operations within the Bounds of a Memory Buffer
- The software performs operations on a memory buffer, but it can read from or write to a memory location that is outside of the intended boundary of the buffer.
- Certain languages allow direct addressing of memory locations and do not automatically ensure that these locations are valid for the memory buffer that is being referenced. This can cause read or write operations to be performed on memory locations that may be associated with other variables, data structures, or internal program data. As a result, an attacker may be able to execute arbitrary code, alter the intended control flow, read sensitive information, or cause the system to crash.

---
exclude: true
# Do CWEs answer them?
### CWE-119: .orange[Failure to Constrain Operations within the Bounds of a] .green[Memory Buffer]
- .orange[The software performs operations on a] .green[memory buffer].orange[, but it can read from or write to a memory location that is outside of the intended boundary of the] .green[buffer].
- Certain languages allow direct addressing of memory locations and .blue[do not automatically ensure that these locations are valid for the memory buffer that is being referenced.] .orange[This can cause read or write operations to be performed on memory locations that may be associated with other variables, data structures, or internal program data.] .red[As a result, an attacker may be able to execute arbitrary code, alter the intended control flow, read sensitive information, or cause the system to crash.]

---
exclude: true
# Untangling

![untangle](images/untangle.png)

---
exclude: true
# Full Extraction

![extraction](images/extraction.png)

---
exclude: true
# Buffer Overflow Template
![bo](images/botemplate.png)

---
exclude: true
class: middle
# Putting the pieces together
![crash](https://www.nydailynews.com/resizer/m96o09B1y-FdXEQIQB1mmglMCRs=/1400x0/arc-anglerfish-arc2-prod-tronc.s3.amazonaws.com/public/KSU66ZVVHLMTWRVTJQS7IHJ46A.jpg)

---
exclude: true
class: middle
# CVE-2004-0492
- NVD Description:   
.green[Heap-based] .orange[buffer overflow] in proxy_util.c for mod_proxy in Apache 1.3.25 to 1.3.31 .red[allows remote attackers to cause a denial of service (process crash) and possibly execute arbitrary code] via a .blue[negative Content-Length HTTP header field], which .red[causes a large amount of data to be copied.]  

---
exclude: true
![source](images/sourcechanges.png)

---
exclude: true
#### **Buffer Overflow Semantic Template CVE-2004-0492**

![filledbo1](images/filledbo.png)

---
exclude: true
![filledbo2](images/filledbo2.png)

---
exclude: true
# Buffer Overflow Secure Coding Assessment

![checklist](images/checklist.png)
---
exclude: true
#### Injection template

![injection](images/injectiontemplate.png)

---
exclude: true
![filledinjection1](images/filledinjection1.png)

---
exclude: true
# Some take aways...
## Ask Johnny (or your software vendor):
### What CWEs do the vulnerabilities in your project typically map to? Have you taken any hands-on training for them?

--
exclude: true
### Have you looked at the [semantic templates](https://robinagandhi.github.io/st) by being developed at UNO?
### Here are some [example vulnerabilities](https://robinagandhi.github.io/st/CVEsamples.zip), why don’t you fill-up the semantic templates to study them?

---
exclude: true
class: middle
# Use/mentions of Semantic Templates

## NIST Bug Framework (BF)
https://samate.nist.gov/BF/
https://samate.nist.gov/BF/Enlightenment/ST.html

## CWE Acknowledgement
http://cwe.mitre.org/about/process.html#follow_on_opportunities

---
exclude: true
class: middle
# Acknowledgements
## This research is partially funded by
### DoD/AFOSR, NSF FA9550-07-1-0499, .blue[High Assurance Software] and
### NIST 70NANB12H013, .blue[Developing Precise and Accurate Descriptions of Common Software Weaknesses]
