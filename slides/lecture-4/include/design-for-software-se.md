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
# Security Analysis during Design

## Start with a Data-flow perspective
- Most attacks come through .red[data]
- Control flow is less relevant during the design stage

---

# Data Flow Diagrams (DFD)

## DFDs are visual representations of data flows through components of a software program
- .green[Data Source] &#8594; .orange[Data Transformations] &#8594; .red[Data Sink]
- All control flows are abstracted into _processes_

--

## DFD Elements
1. External interactors
1. Processes
1. Data storage
1. Boundaries
1. Data flows

---

# DFD Elements

.left-column[
## External Interactor/Entity
- .red[_Uncontrollable_] by the codebase of interest but is within the [environment of operation](https://robinagandhi.github.io/swa/slides/lecture-1/systems-security-engineering.html#15)
- Generate data (Source)
- Receive data (Sink)

## Examples    
People, External systems, External APIs
]

--

.right-column[
## Representation
![example](images/externalentity.svg)
## Naming
Noun phrase that describes the entity
]

???
## NOT the focus of threat modeling
---
# DFD Elements

.left-column[
## Process
- A collection of .red[code]
- Codebase of interest that is being threat modeled
- Transforms input data into output data

## Examples     
- Code, Native code, Executables, Libraries
]

--

.right-column[
## Representation
![example](images/process.svg)
## Naming
- Verb phrase that describes the data transformation
- Include process number
]

---

# DFD Elements

.left-column[
## Data Store
- Place to hold data  
- Storage for a single process or transfer between processes  
- Examples:  
Files, Registry keys, Databases, Shared memory, Message Queue
]

--

.right-column[
## Representation
![example](images/datastore.svg)
## Naming
- Noun phrase but plural
]

---

# DFD Elements

.left-column[
## Data Flow
- Flow of data between External Interactors, Processes and Data Stores  
- Contracts between DFD elements
- Examples:  
Cookie, Form data, Response page, Credentials, etc.
]

--

.right-column[
## Representation
![example](images/dataflow.svg)
## Naming
- Noun phrase that describes the application data being transferred
]

---

# DFD Elements

.left-column[
## Trust Boundary
- Intersects data flows
- Component on one side doesn't trust the one on the other side

## Examples  
- Data flows from one privilege level to another  
- External entities and processes with different trust levels
]

--

.right-column[
## Representation
![example](images/boundary.svg)
## Naming
- Describes the boundary placement
]
---
## DFD Example

![example](images/dfd.png)

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
class: middle

# DFD Construction

## Step 1
### Start with a Level 0 diagram for a use case
- Single process
- Identify a few External Interactors
- Draw data flows to connect them
---
class: middle
# DFD Construction
## Step 2
### Transition to a Level 1 diagram
- Breakdown the single Level 0 process into major processes and related data stores
- Check your work
- Can you tell a story without edits?
- Does it match reality?

---
class: middle
# DFD Construction
## Step 3
### Add trust boundaries that intersect data flows
### Trust boundary placement
- Threads in a OS process are often inside a trust boundary, because they share the same privileges, rights, identifiers and access    
- Processes talking across a network always have a trust boundary. They make may create a secure channel, but they’re still distinct entities
- Encrypting network traffic is an ‘instinctive’ mitigation, but may not address tampering or spoofing


---
class: middle
# DFD Construction
## Step 4
### Iterate over processes and data stores
- Break them down if more detail needed to explain .red[_security impact of the design_]
- Break them down if an object crosses a trust boundary
- Break them down if you use words like “sometimes” and “also” in your story

---
class: middle
# DFD Construction
## Step 5
### Check the diagram for sanity
### Data stores
- Two data stores should not be connected with data flows directly. They are static entities.
- External interactors should not directly interact with data stores. Their data representation formats are different.
- Try to locate data sinks, whenever possible


---
# DFD Construction
## Step 5
### Check the diagram for sanity
### External Interactors
- Avoid data flows between External Interactors. They cannot be observed by the system.
- Data always comes from External Interactors.

### Processes
- Avoid direct dataflows between two separate processes. Use intermediate data stores such as message queues or domain sockets.

---
class: middle
# Threat Elicitation

---
