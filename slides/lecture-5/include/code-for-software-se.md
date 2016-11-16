class: center, middle
# .red[Coding] for Software Security Engineering

---
# Good Code
.right-column[
![xkcd-good-code](http://imgs.xkcd.com/comics/good_code.png)
]
---
class: middle
# What to .red[avoid]?
## Enumerations and Dictionaries
- Common Weakness Enumeration
- Common Attack Pattern Enumeration and Classification
- Common Vulnerabilities and Exposures
- Coding Guidelines

---

class: middle
# Building Abstractions
## .red[Vulnerabilities]\* in code are language, product or environment specific
- Dictionary is appropriate

## .orange[Weaknesses]\* span a range of languages, products and environments
- Taxonomy is appropriate

.footnote[
\* Relationships between a [vulnerability](https://cwe.mitre.org/documents/glossary/#Vulnerability) and [weakness](https://cwe.mitre.org/documents/glossary/#Weakness)
]

---
class: middle
# Building Abstractions

## Commonalities and differences in .red[mistakes]
- Which class of weaknesses to address first?
- What are the related weaknesses in an attack vector?
- What are the known/reusable mitigations?

---

class: middle
# Learning from .red[mistakes]

## The Landwehr Software Flaw Taxonomy (1993)
- Genesis, Location, Time of introduction


## Several recent efforts have followed
- Seven Pernicious Kingdoms, PLOVER, 19 Deadly Sins, OWASP top ten…

## The Common Weaknesses Enumeration [(CWE)](http://cwe.mitre.org)
- Assimilates and advances categorization efforts

---

![CWE](http://cwe.mitre.org/about/images/lg_consensus.jpg)

---

class: middle
# CWE purpose
## Measurement
- Unified, .red[measurable] set of software weaknesses

## Communication
- Effective .red[sharing], description, selection, and use of software security tools and services

## Prioritization
- .red[Ranking] of software weaknesses related to design and code

---

class: middle
# CWE organization
![cwe](images/cwe-organization.png)

---
# CWE Types
### Weakness Class: e.g. [CWE-20](https://cwe.mitre.org/data/definitions/20.html)
- Abstract, independent of any specific language or technology

### Weakness Base: e.g. [CWE-79](https://cwe.mitre.org/data/definitions/79.html)
- Abstract, sufficient details to infer specific methods for detection and prevention

### Weakness Variant: e.g. [CWE-85](https://cwe.mitre.org/data/definitions/85.html)
- Detailed, limited to a specific language or technology.

### Weakness Category: e.g. [CWE-990](https://cwe.mitre.org/data/definitions/990.html)
- A set of other entries that share a common characteristic

---

# Finding the best CWE

## Mapping Guidance
- Map to a Weakness only
- .red[DO NOT] map to Categories or Views
- Map at the lowest abstraction level possible

## Search resources
- [Full text search](https://cwe.mitre.org/find/index.html)
- [Full listing](https://cwe.mitre.org/data/lists/2000.html)
- Navigating views: [CWE-1000](https://cwe.mitre.org/data/graphs/1000.html), [CWE-699](https://cwe.mitre.org/data/graphs/699.html), [CWE-888](https://cwe.mitre.org/data/graphs/888.html)  
Turn on .blue[_Mapping-Friendly_] option
- Navigate parent, child, peer relationships

---

class: middle

# Exercise
## Map [CVE-2004-0492](https://access.redhat.com/security/cve/cve-2004-0492) to CWEs
- Description:   
Heap-based buffer overflow in proxy_util.c for mod_proxy in Apache 1.3.25 to 1.3.31 allows remote attackers to cause a denial of service (process crash) and possibly execute arbitrary code via a negative Content-Length HTTP header field, which causes a large amount of data to be copied.  
- Build a list of most relevant CWEs. E.g. 79 35 34

--

## Submit Response
- [Poll](http://PollEv.com/robingandhi)

???
# http://PollEv.com/robingandhi

---
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
## Negative Technical Impacts of Weaknesses
- Read data  
- Modify data  
- Denial-of-Service: unreliable execution  
- Denial-of-Service: resource consumption  
- Execute unauthorized code or commands  
- Gain privileges / assume identity  
- Bypass protection mechanism  
- Hide activities  

## Top CWE lists
- [CWE/SANS Top 25](https://cwe.mitre.org/top25/index.html)
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
- Total of 504 attack patterns in version 2.8
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
![nvd](https://nvd.nist.gov/NVDLegacy/media/NVDLegacyMedia/images/nvdbannerDHSNIST.jpg)
# [National Vulnerability Database](http://nvd.nist.gov)
- Maintains a dictionary of CVEs
- CVEs use Common Platform Enumeration (CPE) to identify affected products and packages. [Search Engine](https://web.nvd.nist.gov/view/vuln/search)
- Total CVEs: 80000+, ~15-20 added every day

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
- [C, C++, Java, and Perl, and the Android platform](https://www.securecoding.cert.org)
- Software development and software security communities
- Violation does not mean vulnerability but a weakness


## Rules
- [DCL30-C](https://www.securecoding.cert.org/confluence/display/c/DCL30-C.+Declare+objects+with+appropriate+storage+durations), [MEM30-C](https://www.securecoding.cert.org/confluence/display/c/MEM30-C.+Do+not+access+freed+memory)

## Other resources
- [Secure Programs HowTo](http://www.dwheeler.com/secure-programs/Secure-Programs-HOWTO.html#LANGUAGE-SPECIFIC)

---
# Rejoicing Project Managers!
## Johnny, avoid these weaknesses!
- CWE

## Johnny...these are the ways of the bad guys
- CAPEC

## Johnny...learn from your mistakes
- CVE

## Johnny...these are ways to develop secure code
- Secure coding guidelines
.top-right[
![dr.evil](https://upload.wikimedia.org/wikipedia/en/1/16/Drevil_million_dollars.jpg)
]
---
class: middle
# Why Johnny Can't Write Secure Code?
---
class: middle
## Poor Johnny!
![poorjohnny](images/poorjohnny.png)

---
class: middle
## Training Surgeons
![GA](https://pbs.twimg.com/media/CtPPfC3XEAA_sdq.jpg)

---
class: middle
## Paradox we Face!
![paradox](images/paradox.png)

---
class: middle
# Reducing the Cognitive Overload

## When the Devil is in the Details...
- The details to consider for avoiding weaknesses are enormous during the coding phases

## ...simple, intuitive guides are need
---
class: middle
# Key Questions a Weakness
### What are the .blue[Software flaws] (omission, commission, operational) that lead to the weakness?
### What are the defining characteristics of the .orange[Weakness]?
### What are the .green[Resources/Location] where the weakness is typically manifest?
### What are the .red[Consequences] that the weakness precedes?

---
# Do CWEs answer them?
### CWE-119: Failure to Constrain Operations within the Bounds of a Memory Buffer
- The software performs operations on a memory buffer, but it can read from or write to a memory location that is outside of the intended boundary of the buffer.
- Certain languages allow direct addressing of memory locations and do not automatically ensure that these locations are valid for the memory buffer that is being referenced. This can cause read or write operations to be performed on memory locations that may be associated with other variables, data structures, or internal program data. As a result, an attacker may be able to execute arbitrary code, alter the intended control flow, read sensitive information, or cause the system to crash.

---
# Do CWEs answer them?
### CWE-119: .orange[Failure to Constrain Operations within the Bounds of a] .green[Memory Buffer]
- .orange[The software performs operations on a] .green[memory buffer].orange[, but it can read from or write to a memory location that is outside of the intended boundary of the] .green[buffer].
- Certain languages allow direct addressing of memory locations and .blue[do not automatically ensure that these locations are valid for the memory buffer that is being referenced.] .orange[This can cause read or write operations to be performed on memory locations that may be associated with other variables, data structures, or internal program data.] .red[As a result, an attacker may be able to execute arbitrary code, alter the intended control flow, read sensitive information, or cause the system to crash.]

---
# Untangling

![untangle](images/untangle.png)

---
# Full Extraction

![extraction](images/extraction.png)

---
# Buffer Overflow Template
![bo](images/botemplate.png)

---
class: middle
# Putting the pieces together
![crash](https://qph.ec.quoracdn.net/main-qimg-08cc5472e55ff2becf09468b9ae6c650-c?convert_to_webp=true)

---
class: middle
# CVE-2004-0492
- NVD Description:   
.green[Heap-based] .orange[buffer overflow] in proxy_util.c for mod_proxy in Apache 1.3.25 to 1.3.31 .red[allows remote attackers to cause a denial of service (process crash) and possibly execute arbitrary code] via a .blue[negative Content-Length HTTP header field], which .red[causes a large amount of data to be copied.]  

---

![source](images/sourcechanges.png)

---
#### **Buffer Overflow Semantic Template CVE-2004-0492**

![filledbo1](images/filledbo.png)

---
![filledbo2](images/filledbo2.png)

---
# Buffer Overflow Secure Coding Assessment

![checklist](images/checklist.png)
---

#### Injection template

![injection](images/injectiontemplate.png)

---
![filledinjection1](images/filledinjection1.png)

---

# Some take aways...
## Ask Johnny (or your software vendor):
### What CWEs do the vulnerabilities in your project typically map to? Have you taken any hands-on training for them?

--
### Have you looked at the [semantic templates](http://faculty.ist.unomaha.edu/rgandhi/st) by being developed at UNO?
### Here are some [example vulnerabilities](http://faculty.ist.unomaha.edu/rgandhi/st/CVEsamples.zip), why don’t you fill-up the semantic templates to study them?

---

class: middle
# Use/mentions of Semantic Templates

## NIST Bug Framework (BF)
https://samate.nist.gov/BF/

## CWE Acknowledgement
http://cwe.mitre.org/about/process.html#follow_on_opportunities

---
class: middle
# Acknowledgements
## This research is partially funded by
### DoD/AFOSR, NSF FA9550-07-1-0499, .blue[High Assurance Software] and
### NIST 70NANB12H013, .blue[Developing Precise and Accurate Descriptions of Common Software Weaknesses]
