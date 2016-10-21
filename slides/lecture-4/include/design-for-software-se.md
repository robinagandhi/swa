class: center, middle
# .red[Design] for Software Security Engineering

---
class: center, middle
# Threat and Design\*

![bad threat model](http://imgs.xkcd.com/comics/authorization.png)

.footnote[
\* Recommended by a Prior Student and [Bruce S.](https://www.schneier.com/blog/archives/2013/04/xkcd_on_a_bad_t.html)
]

---
class: middle
# Focus on Data Movement/Flows

## For security analysis of design we tend to focus on Data-flow through software components
- Most threats come through “Data”
- Control flow is less relevant to during the design stage

## Source &#8594; Transformations &#8594; Sink

---

# Data Flow Diagrams (DFD)

## DFD: Diagrams of data-flow that include:
1. External interactors
1. Processes
1. Data storage
1. Boundaries
1. Data flows

--

## All control flows are abstracted into _processes_ that transform input data into output results

---

# DFD Elements

.left-column[
## External Interactors/Entity
- Any entity .red[_uncontrollable_] by the application
- Within the environment of operation
- Examples: People, External systems, External APIs
]

--

.right-column[
## Representation
![example](images/externalentity.svg)
]

---

# DFD Levels

## Levels are hierarchically related
### Based on the granularity of the processes
- .red[**Level 0:**] Single process represents the whole system  
Very high-level; entire component / product / system
- .red[**Level 1:**] Major processes and data stores identified   
High level; single feature / scenario
- .red[**Level 2:**] Detailed subcomponents of processes  
Low level; detailed features of a single feature / scenario
- ...

---
