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
![recap](https://robinagandhi.github.io/swa/slides/lecture-1/images/framework-course-topics.png)
???
# Quick recap
---
class: middle
# Security Analysis during Design

## Start with a Data-flow perspective
- **Most attacks come through .red[data]**
- Control flow is less relevant during the design stage
- A structured, concrete artifact to _discuss_ design:  
Conceptualization, Changes or Re-design

---
class: middle
## Practical Applications
_"Applying a structured approach to threat scenarios during design helps a team more effectively and less expensively identify security vulnerabilities, determine risks from those threats, and establish appropriate mitigations"_   
[Microsoft SDL](https://www.microsoft.com/en-us/SDL/process/design.aspx)

---
class: middle
# Data Flow Diagrams (DFD)

## DFDs are visual representations of .red[**data flows**] through components of a software program
- Components of a software program:  
.green[Data Source] &#8594; .orange[Data Transformations] &#8594; .red[Data Sink]
- All control flows are abstracted into _processes_  
that perform data transformations

---

class: middle
# DFD Elements
1. External Interactors
1. Processes
1. Data Stores
1. Trust Boundaries
1. Data Flows

---

# DFD Elements

.left-column[
## External Interactor/Entity
- .red[_Uncontrollable_] by the codebase of interest but is within the [environment of operation](https://robinagandhi.github.io/swa/slides/lecture-1/systems-security-engineering.html#14)
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
.red[Noun phrase] that describes the entity
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
- Code, Native code, Executables, Libraries, Process execution scope
]

--

.right-column[
## Representation
![example](images/process.svg)
## Naming
- .red[Verb phrase] that describes the data transformation
- .red[Include process number]
]

---

# DFD Elements

.left-column[
## Data Store
- Place to hold data  
- Storage for a single process or transfer between processes  

## Examples
Files, Registry keys, Databases, Shared memory, Message Queue
]

--

.right-column[
## Representation
![example](images/datastore.svg)
## Naming
- .red[Noun phrase], but plural
]

---

# DFD Elements

.left-column[
## Data Flow
- Flow of data between External Interactors, Processes and Data Stores  
- Contracts between DFD elements

## Examples
Cookie, Form data, Response page, Credentials, etc.
]

--

.right-column[
## Representation
![example](images/dataflow.svg)
## Naming
- .red[Noun phrase] that describes the application data being transferred
]

---

# DFD Elements

.left-column[
## Trust Boundary
- Intersects .red[data flows]
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
Very high-level; entire component / product / system.  
Show how the system interacts with the outside world.
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
- Identify all External Interactors
- Draw data flows to connect them
---

class: middle
# Playsound API

"_The PlaySound API takes as input a string which represents either a WAV filename or an alias.  If the input is an alias, the PlaySound API retrieves data from the registry under HKCU to convert the alias into a filename.  Once the filename is determined, the PlaySound API opens the WAV file specified and reads the two relevant pieces from the file: the WAVEFORMATEX that defines the type of data in the file and the actual audio data.  It then hands that data to the audio rendering APIs._"

## Build a Threat Model based on this description

???

![solution](images/playsoundthreatmodel.png)  
http://blogs.msdn.com/b/larryosterman/archive/2007/09/13/threat-modeling-again-analyzing-the-threats-to-playsound.aspx

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
- Threads are often inside a trust boundary.   
They share the same privileges, rights, identifiers and access    


- Processes talking across a network may create a secure channel, but .red[they’re still distinct entities.]   
Encrypting network traffic is an ‘instinctive’ mitigation, but may not address tampering or spoofing


---
class: middle
# DFD Construction
## Step 4
### Iterate over processes and data stores
- Break them down if more detail needed to explain .red[_security impact of the design_]


- Break them down if an object crosses a trust boundary. For example, a remote procedural call (RPC)


- Break them down if you use words like “sometimes” and “also” in your story

---
class: middle
# DFD Construction
## Step 5: Check the diagram for sanity (1)
### Data stores
- Two data stores should not be connected with data flows directly. They are static entities.
- External interactors should not directly interact with data stores. Their data representation formats are different.
- Data stores should have an input flow
- Try to locate data sinks, whenever possible

### Data Flows
- Attached to at least one process


---
# DFD Construction
## Step 5: Check the diagram for sanity (2)
### External Interactors
- Avoid data flows between External Interactors. They cannot be observed by the system.
- Data always comes from External Interactors.

### Processes
- Avoid direct dataflows between two separate processes. Use intermediate data stores such as message queues or domain sockets.
---
# DFD Construction
## Step 6
### Simplify
- Consolidate data flows that always flow together


- All processes need appropriate _inputs_ to generate _outputs_. No outputs without inputs!


- Avoid partitioning processes based on control logic.  
Partition processes that perform multiple functions.


- DFDs do not typically show time dependencies.   
If processes can communicate directly they are assumed to be synchronous!
---
class: middle
# DFD Modeling Summary
- DFDs depict data flows from sources to sinks with transformations along the way.   
Trust boundaries intersecting these data flows.


- Hierarchical structuring (Levels) allows system analysis at different levels of abstraction

---
class: middle, center
# Threat Identification
DFDs allows potential threats to be .red[automatically generated]!

---

class: middle
# Microsoft STRIDE Threats

.left-column[
## Threat
- .red[S]poofing
- .red[T]ampering
- .red[R]epudiation
- .red[I]nformation Disclosure
- .red[D]enial of Service
- .red[E]levation of Privilege
]

---

class: middle
# Microsoft STRIDE Threats

## Spoofing
* A process or entity is something other than the claimed identity

## Tampering
* Act of altering bits

## Repudiation
* Deny that something happened or an action was taken

---
class: middle
# Microsoft STRIDE Threats

## Information Disclosure
* Information can be read by an unauthorized party

## Denial of Service
* Process or data store not able to process incoming requests

## Elevation of Privilege
* A user can increase capability or privilege by taking advantage of an implementation bug
---

# STRIDE with DFDs (Per Element)

Threats that a DFD element can cause to its connected elements or is subject to itself.

.left-column[
## External Interactor
- SR

## Process
- STRIDE
]

--

.right-column[
## Data Store
- TID, R (logs only)

## Data Flow
- TID
]
---
class: middle
# Practice
![OWASP](https://www.owasp.org/images/0/00/Data_flow1.jpg)
---
class: middle
# Practice (2)
![OWASP](https://www.owasp.org/images/1/16/Data_flow2.jpg)
---
class: middle
exclude: true
# Observations and Reflections

## Expensive (Time)
- Too many threats to analyze! (even for small diagrams)

## Redundancy
- Redundant threats when analyzed individually

## How can we make this more efficient?
---
class: middle
exclude: true
# STRIDE with DFDs (Per .red[Interaction])
## Focus on Interactions
- Interaction:   
A source and target element connected by a data flow
---
class: middle
exclude: true
# STRIDE with DFDs (Per .red[Interaction])
## Efficiencies and Savings
- For each interactions apply STRIDE
- For each STRIDE threat identify the attacker controlled element and the attacked element
- For data flows inside a .red[single] process space,   
don’t worry about T, I, or D
- Prioritize interactions that cross trust boundaries
???
## Significant reduction in number of threats to be analyzed
---
class: middle
exclude: true
# Trust boundaries
## Trusted/high code reading from untrusted/low
- Look for Tampering threats

## High code writing to low
- Errors may result in Information Disclosure
---
class: middle
exclude: true
# Avoid Distractions
## Applications can't do much here:
- The computer is infected with malware
- Someone removed the hard drive and tampers
- Admin is attacking user
- A user is attacking himself

## Applications can’t address any of these   
(unless you’re the OS)

---
class: middle
exclude: true
# Practice

![OWASP](https://www.owasp.org/images/1/16/Data_flow2.jpg)

#### How many interactions? How many are high priority?

---

class: middle
exclude: true
# Practice
![example](images/dfd.png)

#### How many interactions? How many are high priority?
---
class: middle
# Tool Support

--

## Automation
- Much of this analysis can be automated using simple rules based on the diagram structure
- Tool support

## Traceability
- Would be nice to link all analysis along with the diagram
- A bit more than a PPT, Visio or Lucidchart!

---
class: middle
# [Microsoft TMT 2016](https://www.microsoft.com/en-us/download/details.aspx?id=49168)
![toolsupport](images/toolsupport.png)
---
class: middle
# .center[Threat Mitigation]

.footnote[Why bother if you create a great model, identify lots of threats, and .red[stop!]]

---
class: middle
# Threat Mitigations
## Four ways to address each threat
1. Redesign to eliminate
1. Apply standard mitigations  
What have similar software packages done and how has that worked out for them?
1. Invent new mitigations (.red[risky!])
1. Accept vulnerability in design  
Risk acceptable, but must be verified and approved

---
class: middle
# STRIDE Controls

.left-column[
## Threat
- .red[S]poofing
- .red[T]ampering
- .red[R]epudiation
- .red[I]nformation Disclosure
- .red[D]enial of Service
- .red[E]levation of Privilege
]

.right-column[
## Control
- Authentication
- Integrity
- Nonrepudiation
- Confidentiality
- Availability
- Authorization
]
---

class: middle
# Standard Mitigations

## Spoofing
### Require authentication
- Data source
- Code integrity

### Validation of input read from the data source
- Normalization before neutralization
- Avoid recursion bombs

---
class: middle
# Standard Mitigations

## Tampering

### Integrity Checking
- Digital signatures and message authentication codes
- ACLs for data at rest

### Validation of input read from the data source
- Normalization before neutralization
- Avoid recursion bombs

---
class: middle
# Standard Mitigations

## Repudiation
- One-way log and audit generation mechanism
- Strong authentication for logging

## Information Disclosure
- ACLs
- Encryption with good key management and protocols
---
class: middle
# Standard Mitigations

## Denial or service
- ACLs to protect the contents of files from being removed or modified
- Firewall rules to protect against some network based attacks
- Use disk and processor quotas to prevent excess disk or CPU consumption

---
class: middle
# Standard Mitigations

## Elevation of Privilege
- Input validation
- Input validation
- Input validation
- ACLs, Roles, Groups
- Privilege dropping
- Least privilege

---
# How to ignore threats?
## No requirement
- There are no requirements that the &lt;&lt;element&gt;&gt; protect against &lt;&lt;STRIDE&gt;&gt; threat

## Irrelevant
- This threat does not exist, so we don't care about &lt;&lt;STRIDE&gt;&gt; threat to the &lt;&lt;element&gt;&gt;

## Not applicable
- &lt;&lt;STRIDE&gt;&gt; threat does not apply to this &lt;&lt;element&gt;&gt;
---
class: middle
# Validate the Threat Model

1. Do the threats consider misuse cases?
1. Does the diagram match final code?
1. Are threats enumerated? At minimum:
STRIDE per element that touches a trust boundary
1. Has Test / QA reviewed the model?
Testers often finds issues with threat model or details
1. Is each threat mitigated?
1. Are mitigations done right?  (Assurance case?)
---

# Making this Fun

## Elevation of Privilege Card Game
- Ease developers into doing threat modeling
- [Card Game Introduction](https://www.microsoft.com/en-us/sdl/adopt/eop.aspx)
- [How to play](http://social.technet.microsoft.com/wiki/contents/articles/285.elevation-of-privilege-the-game.aspx)
- [Card Images](https://robinagandhi.github.io/swa/slides/lecture-4/images/eopcardcameimages.pdf)

![EOP](https://c.s-microsoft.com/en-us/CMSImages/EoP_game_screen_shot.jpg?version=4a082487-9fb4-7dd9-ed9f-e79c888c2df4)

---
class: middle
# More about threat modeling

## Blogs
- Microsoft Tutorial on [TMT 2014](http://blogs.microsoft.com/cybertrust/2014/04/15/introducing-microsoft-threat-modeling-tool-2014/  )
- Bruce Schneier on [threat modeling](http://www.schneier.com/blog/archives/2007/10/threat_modeling.html)

## Practice Diagrams
- Microsoft [Readings](https://msdn.microsoft.com/en-us/library/aa562036.aspx)

---
# Sources

- This presentation is borrows a lot from Microsoft training materials on threat modeling
- Many sources for Data flow diagrams
---

class: center, middle
# Threat Modeling Exercise

---
class: middle

# Step 1
- Download and install [TMT 2016](https://www.microsoft.com/en-us/download/details.aspx?id=49168)
- You may also directly access it on your machine at view.unomaha.edu

---

class: middle
# Step 2
## Build a DFD for the Playsound API in TMT 2016
- Examine the threats identified

???
class: middle
exclude: true
# Step 2
## Recall the misuse case assignment
- You identified several use cases to include misuse cases.

---
class: middle
exclude: true
# Step 3
## Elaborate the Misuse cases using Threat models
- Develop Level 1 DFDs that supports each of your use cases.
- Perform analysis on your code base to align the diagram with reality
- Draw the DFDs in TMT 2016
- Identify appropriate trust boundaries on the diagram
- Validate the diagram for any obvious structural deficiencies

---
class: middle
exclude: true
# Step 4
## Analyze the Level 1 diagram to identify the applicable STRIDE threats
- Examine each threat automatically identified
- Document mitigation strategies for the identified threats
- Pay special attention for elements that interact across threat boundaries
- Generate a full HTML report using TMT 2016
- Host the reports on your project github repo.
- Review OSS project actual software design for security related issues based on your threat models. Summarize your observations.

---
class: middle
exclude: true

# Grading criteria

### Use of proper notations
- DFD notation

### Threat Model Quality
- Threat model focuses on critical components of interest
- Proper wording of the model elements
- Clean, coherent and valid DFD diagram

### Threat Mitigation Quality
- Quality of analysis to mitigate threats

---
class: middle
exclude: true
# Due Date
Wednesday November 8th, 2017
