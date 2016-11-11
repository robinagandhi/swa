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

---

class: middle
# Building Abstractions
## .red[Vulnerabilities] in code are language, product or environment specific
- Dictionary is appropriate

## .orange[Weaknesses] span a range of languages, products and environments
- Taxonomy is appropriate

.footnote[
Difference between a [vulnerability](https://cwe.mitre.org/documents/glossary/#Vulnerability) and [weakness](https://cwe.mitre.org/documents/glossary/#Weakness)
]

---
class: middle
# Building Abstractions

## Commonalities and differences in "Errors"
- Which class of weaknesses to address first?
- What are the related weaknesses in an attack vector?
- What are the known/reusable mitigations?

---

class: middle
# Learning from .red[Errors]

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
- Unified, measurable set of software weaknesses

## Communication
- Effective sharing, description, selection, and use of software security tools and services

## Prioritization
- Ranking of software weaknesses related to design and code

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
## Guidance
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
# Some CWEs to Remember
- [CWE-120](https://cwe.mitre.org/data/definitions/120.html): Classic buffer overflow
- [CWE-798](https://cwe.mitre.org/data/definitions/798.html): Use of hardcoded credentials
- [CWE-311](https://cwe.mitre.org/data/definitions/311.html): Missing encryption
- [CWE-434](https://cwe.mitre.org/data/definitions/434.html): Unrestricted upload of file with dangerous type
- [CWE-250](https://cwe.mitre.org/data/definitions/250.html): Execution with unnecessary privileges
- [CWE-494](https://cwe.mitre.org/data/definitions/494.html): Download of code without integrity check
- [CWE-22](https://cwe.mitre.org/data/definitions/22.html):  Path traversal
- [CWE-759](https://cwe.mitre.org/data/definitions/759.html): Use of one-way hash without a salt

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
Total of 504 attack patterns in version 2.8

## Examples:  
[CAPEC-63](https://capec.mitre.org/data/definitions/63.html), [CAPEC-245](https://capec.mitre.org/data/definitions/245.html)  

## Views:   
[CAPEC 1000](https://capec.mitre.org/data/definitions/1000.html), [CAPEC-3000](https://capec.mitre.org/data/definitions/3000.html)

---
