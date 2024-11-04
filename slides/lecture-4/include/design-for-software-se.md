class: center, middle
# .red[Design] for Software Security Engineering

???
Design for software security engineering is a set of activities to examine a given software design for incompleteness from a security perspective. In other words, inadvertent loopholes exist in your software's protective barriers that have not been foreseen by the designers, and your job is to discover them using structured activities.

---
class: center, middle
# Threat and Design\*

![bad threat model](http://imgs.xkcd.com/comics/authorization.png)

.footnote[
\* Recommended by a Prior Student and [Bruce S.](https://www.schneier.com/blog/archives/2013/04/xkcd_on_a_bad_t.html)
]

???
This comic illustrates the point of inadvertent loopholes. Our goal with design analysis is to reveal such loopholes that happen due to misplaced trust assumptions or actual user behaviors that might be contradictory to established policies.
---

# Systems Security Engineering

### .orange[Problem] Context
A sufficiently complete understanding of the problem

### .green[Solution] Context
<u>Transforms the security requirements into design requirements for the system</u>

### .red[Trustworthiness] Context
Evidence-based demonstration, through reasoning, that the system-of-interest is deemed trustworthy

???
Now, remember that Software security engineering activities exist within three interacting contexts.

We looked at the problem context using requirements engineering activities and techniques. Then we developed assurance claims, and then argued them using **assurance cases** as part of the trustworthiness context. Now we will see how the solution context transforms the security requirements derived using misuse cases into the system's design requirements.

---
class: middle
# Security Analysis during Design

## Start with a Data-flow perspective
- **Most attacks come through .red[data]**
- **Attacks gravitate towards .red[data]**
???
Here is a master tip for design analysis for security engineering. Always remember this. Most attacks come through data, and these attacks are interested in going after data in the system. So any design analysis for security is most effective when done from a data-flow perspective.

--

- .blue[**Control flow**] is less relevant for analyzing  
security in design and architecture

???
It turns out control-flow is less relevant when performing design analysis for security. In our techniques, we will abstract it away so it does not get in the way. When starting to do data-flow analysis, it is easy to get confused with the control flow. Control flow is the algorithm that transforms data. For example, bubble sort is an algorithm that sorts a list of unordered numbers. We are not interested in the algorithm, but data goes in as string input to an executing process on the machine, and then a string is written to the file system.  

---
class: middle
# Data Flow Diagrams (DFD)
- A structured, concrete artifact to _discuss_ design:  
Conceptualization, _Changes_ or **Re-design**
- Goal: Keep the designer focused on .red[design] issues

???
Staying focused on data flow during our design analysis is essential. So we will use a modeling technique designed to do just that. Data Flow Diagrams, or DFD for short, conceptualizes a system model for security design analysis. Once the model is available, we can systematically reason about the security impact of any initial design decisions, changes to the design, or the need for re-design.

---
class: middle

# Practical Relevance

>_"Applying a structured approach to threat scenarios during design helps a team .red[more effectively and less expensively] identify security vulnerabilities, determine risks from those threats, and establish appropriate mitigations"_  

> [Microsoft SDL](https://www.microsoft.com/en-us/SDL/process/design.aspx), [SDL practice #3. Perform secure​ design review and ​threat modeling](https://www.microsoft.com/en-us/securityengineering/sdl/practices/secure-by-design)

???
Things we learn in this course are firmly grounded in industry best practices for software security engineering. Using DFDs to conduct a structured analysis of threat scenarios is part of the Microsoft Secure Development Lifecycle which is adopted throughout the organization and is also observed in many other organizations through BSIMM assessments. This approach is also recommended by OWASP for web applications, with its own ecosystem of guidelines and tools (https://owasp.org/www-project-threat-dragon/).




---
class: middle
# Data Flow Diagrams (DFD)

## DFDs are visual representations of .red[**data flows**] through .green[components of a software program.]
- A programs execution can be abstracted as:  
Data Source &#8594; .red[Data Transformations] &#8594; Data Sink  

???

One reason for the popularity of DFDs for security design analysis is that they provide a simple view of the system. They are visual representation of data flows through a software program, including where data comes from, and where it ends up.

So a program's execution on a machine can be abstracted by simply identifying the data source, data transformations and data sink. A data flow is a trace of how data moves from the source to the sink through various transformations.

--
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#8595;

> All .blue[control flows] that perform data transformations  
are abstracted into .red[_processes_]  

???

In this view, all control flows that perform data transformations are abstracted to processes executing on a machine.

---

class: middle
# DFD Elements
1. External Interactors
1. Processes
1. Data Stores
1. Data Flows
1. .red[Trust Boundaries]

???
This concise list of elements further reflects the simplicity of a DFD diagram.

The names of the elements also suggest what role they might play in a data flow. For example Data Stores, like a file, would primarily serve as Data sink.

Let's look at teach one of these and their visual notations next.

---

# DFD Elements

.left-column[
## External Interactor/Entity
- .red[_Uncontrollable_] by the codebase of interest but can interact with it
- Generates data (Source)
- Receives data (Sink)

## Examples    
People, External systems, External APIs
]

???
The external interactor is typically a human or other system in your environment of operation. This external interactor is uncontrollable by the system of interest but can interact with it. Good examples of it are people, external systems, external APIs. These entities typically initiate a dataflow using a request that includes some input data or at the end of a dataflow receive the result of a computation, i.e. output. So they can act as a data source or sink.

From a security perspective, it is best to treat any data received from an external interactors as untrustworthy. Also, any data shared with an external interactor should be checked for appropriate authorization.

--

.right-column[
## Representation
![example](images/externalentity.svg)
## Naming
.red[Noun phrase] that describes the entity
]

???
An External Interactor is visually represented as a rectangle. As a general grammatical guideline, phrase all elements in a DFD, including the external interactor as a noun phrase. In this case the noun phrase describes the external entity.

When naming an external interactor, remember that anything that is an external interactor is not a part of your system of interest.

---
# DFD Elements

.left-column[
## Process (Code)
- A collection of .red[code]
- Codebase of interest that is being threat modeled
- Transforms input data into output data

## Examples     
- Code, Native code, Executables, Libraries, Process execution scope
]

???
In contrast, any code that is in our system of interest, should be modeled as a process. A process represents the codebase of interest that is being threat modeled. Its purpose is to transform any input data into output data. A process abstraction in a DFD maps to a program executing on a computer. For example, the Chrome browser spawns a new program for each one of its tabs. Each such program running in its own process space, should be modeled as a process in a DFD diagram.

Examples of processes include code, executables, libraries, or collection of thread that run within the same process execution scope.

--

.right-column[
## Representation
![example](images/process.svg)  
## Naming
- .red[Noun phrase] used to refer to the codebase
- .red[Include process number]
]

???

A process is visually depicted as a circle. It is also described using a noun phrase that typically refers to the codebase that is being threat modeled. It is best to add a process number, as it will help with traceability and ease of reference as we will see later in this discussion.

---

# DFD Elements

.left-column[
## Data Store
- Place to hold data  
- Storage for a single process or transfer between processes  

## Examples
Files, Registry keys, Databases, Shared memory, Message Queue
]

???
A data store is simply any location used to hold data. This data holding area can serve a single process, or in the case of domain sockets could act as a temporary storage area to transfer data back and forth between processes executing in two different memory regions of the computer. Common example of data stores are files, registry keys, Databases, Shared memory when dealing with two processes or Message Queues often used in service-oriented architectures.

--

.right-column[
## Representation
![example](images/datastore.svg)
## Naming
- .red[Noun phrase], but plural
]

???
Its visual notation is just two parallel lines with the name in the middle. Its description is also a noun phrase, that is usually plural as in Data vs. datum which is singular.

---

# DFD Elements

.left-column[
## Data Flow
- Flow of data between External Interactors, Processes and Data Stores  
- Contracts between DFD elements

## Examples
Cookie, Form data, Response page, Credentials, etc.
]

???
Now that we have DFD elements to show data sources, transformations and sinks, we need a way to show the traces between them to visually depict data flow. A data flow between two DFD elements signifies a contract. That is the input provided the DFD element on one end of the data flow is understood by the DFD element on the other end.

--

.right-column[
## Representation
![example](images/dataflow.svg)
## Naming
- .red[Noun phrase] that describes the application data being transferred
]

???
Data flows are represented as arrows that connect two DFD elements. The data flow is named after the application data that is being transferred. So examples of Data flows include cookies, form data, a result set from a database or credentials for a login page. Notice that in all these examples, the data is abstracted so that we understand its criticality during threat modeling. We are generally not too concerned about the details of this data.

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

???
Finally, this last DFD element is only relevant for security design analysis. Trust boundaries are drawn such they cut across data flows. This depicts that a component on one side of the trust boundary should not trust the one on the other side.

In a system where different programs are different privilege levels, trust boundaries direct the analysts attention to be extra careful while accepting or transferring any data from the other side of the trust boundary.

--

.right-column[
## Representation
![example](images/boundary.svg)
## Naming
- Describes the boundary placement
]

???
Since the trust boundary is imaginary, it is visually represented as a dotted line. It is also typically colored in red to serve as a warning. The name of the boundary usually describes its relative placement in the system.

---
class: middle
# DFD Levels

## Levels are hierarchically related
- Based on the granularity of the processes
- Levels 0, 1, 2...

???
Now, software engineering activities often express the design of a system or software at different abstraction levels. Similarly, based on the abstraction level of the codebase that is being threat modeled, we can create different DFDs. The most abstract DFD is level 0. Levels beyond 0 successively add more details to the diagram.  

---
class: middle
## DFD Level 0
- .red[_Single process_] represents the whole system

> Very high-level; entire component / product / system

- **Purpose:** Show system interactions in the   
environment of operation

???
A level 0 DFD uses a single process to represent the whole system. As I said before, this is the most abstract DFD. It gives a very high level view of the entire system of interest. But what do we get from doing so? If we abstract away the system, we can focus on its interactions in the environment of operation, i.e. identify the external interactors.

Let's look at an example with a system a learning management system, Canvas.

---
class: middle
## DFD Level 0 Example
![Example of DFD Level 0](images/dfd0.svg)

???
Here Canvas is my system of interest that is being threat modeled. Now to focus on its interactions in the environment of operation, the entire system is modeled as a single process, and nothing else. No data stores are included in a level 0 diagram. Since the focus is on external interactions, we have now identify the major external interactors for this system and the primary data flows. This diagram gives a quick snapshot of potential attack surfaces for the system of interest. Remember, most threats comes through data!

---
class: middle
## DFD Level 1
- Major .red[processes and data stores] identified

> High level; .orange[**single** feature / scenario]

- **Purpose:** Analyze critical data flows for a   
single scenario of interest

???
In a level 1 DFD, we start to add more details to the entire system's single process from level 0, in the context of a single scenario. While this diagram is still high-level, it aims to identify and analyze the critical data flows for a single scenario of interest.

---
class: middle
## DFD Level 1 Example

![Example of DFD Level 1](images/dfd1.svg)

???
For example, we want to analyze a student use case to check grades using Canvas. In this use case, the model identifies relevant DFD elements, including data stores and threat boundaries. Note that a DFD does not need to show all details of this use case but only highlight its major components and what data flows between the components. We also see that the model places a trust boundary between the external interactor and the process. This boundary serves as a warning that the process should not trust anything received from the other side and ensure that any data shared is authorized for that external interactor.

---
class: middle
## DFD Level 2
- Detailed .red[subcomponents of processes]  
(if they exist during system run-time execution)  

> Low level; detailed features of a .orange[**single** feature / scenario]

- **Purpose:** Analyze critical data flows deep in the system design for a single scenario of interest

???
While there is no upper limit on the levels, the details in a level 1 or level 2 DFD should be sufficient in most practical cases. A Level 2 diagram adds more information to a Level 1 diagram to surface security issues embedded deep within the system. In some cases, the Level 2 diagram might be a more faithful representation of the system runtime environment.

---
class: middle
## DFD Level 2 Example

![Example of DFD Level 2](images/dfd2.svg)

???
Here we see that a Level 2 DFD adds more information to the Canvas web app process. This diagram makes it clear that there is a front-end HTTP server process that communicates using HTTP with a backend application server. While these processes may exist on the same machine, they are in separate memory spaces at runtime during system execution, justifying their separation in the DFD.

---
class: middle

# How to start DFD Construction?

## Step 1
### Start with a Level 0 diagram for a .red[use/misuse case]
- Draw a .red[single process] that represents the system;  
NO data stores
- Identify and draw all External Interactors (EI);  
Human or Other Systems
- Draw data flows to connect External Interactors & the Process

???
DFD levels, starting with Level 0, offer a natural progression to start building a DFD diagram for a given scenario. To get started, the first step is to develop a level 0 diagram. This includes drawing a single process that represents the entire system. Remember that there are no data stores in a level 0 diagram. Next identify External interactors and then connect them to the process using dataflows. Name all elements appropriately.  

---

class: middle
# Playsound API

"_The PlaySound API takes as input a string which represents either a WAV filename or an alias.  If the input is an alias, the PlaySound API retrieves data from the registry under HKCU to convert the alias into a filename.  Once the filename is determined, the PlaySound API opens the WAV file specified and reads the two relevant pieces from the file: the WAVEFORMATEX that defines the type of data in the file and the actual audio data.  It then hands that data to the audio rendering APIs._"

???
Here is design narrative for you to practice building a DFD. Pause the video here and create a Level 0 diagram. Here the Playsound API is our codebase of interest.

---

## Level 0
![example](images/Playsound-level0.svg)


???
Compare your work with my solution. In this Level 0 diagram, you will notice right away that it abstracts away a lot of details in the narrative and focuses only on the major external interactors in the given scenario. In this view, it is easy to see where data enters and exits the system.

---

class: middle
# DFD Construction
## Step 2
### Transition to a Level 1 diagram
- Breakdown the single Level 0 process into major processes and related data stores .red[for a single feature / scenario]
- Check your work
- Can you tell a story without edits?
- Does it match reality?

???
To proceed further in DFD construction, we try to develop a level 1 DFD for the given Playsound API narrative. Such narratives may also come from a use case diagram. Using the details of the scenario, we add more information to the single level 0 process, such that you can tell a story without making changes to the DFD.

Now pause the video here and try to come up with a level 1 diagram based on the Playsound API narrative.

---

## Level 1
![example](images/Playsound-level1-nb.svg)


???

In my solution, I added two data stores to faithfully capture the given narrative and the associated data flows. I can describe the narrative using this diagram, i.e. I can tell a story without any edits.

---
class: middle
# DFD Construction
## Step 3
### Add trust boundaries that intersect data flows
### Trust boundary placement
- Threads are often inside a trust boundary.   
They share the same privileges, rights, identifiers and access    


- Processes talking across a network may create a secure channel, but .red[they’re still distinct entities.]   

???
Now it is time to add trust boundaries to the level 1 diagram. While it may be tempting to add trust boundaries in many places, it also places a greater burden for the analyst.

For example, different threads within a single process space would share the same rights and privileges. So there is little value in adding a trust boundary between them. However, in certain cases trust boundaries must be added. For example, you may have two processes talking across a network. Now they may have an encrypted channel for communication, but they are still different. If the network is exposed to malicious actors, adding a trust boundary is justified.

---

## Level 1 Trust Boundaries
![example](images/Playsound-level1.svg)


???
In our example, I placed three trust boundaries. While the App boundary is easy to justify, I also added the registry boundary and filesystem boundary. The latter two boundaries reflect a design decision to not trust data that is received from the registry or the filesystem.

The example is based on this blog by Larry Osterman at Microsoft.

![Example](images/playsoundthreatmodel.png)  
http://blogs.msdn.com/b/larryosterman/archive/2007/09/13/threat-modeling-again-analyzing-the-threats-to-playsound.aspx
---
class: middle
# DFD Construction
## Step 4
### Iterate over processes and data stores
- Break them down if more detail needed to explain .red[_security impact of the design_]
- Break them down if an object crosses a trust boundary. For example, a remote procedural call (RPC)
- Break them down if you use words like “sometimes” and “also” in your story

???
At this point, you have a decision to make. Does the DFD need more details to surface additional security issues? Is the DFD missing important aspects of the runtime environment? If the answer to both these questions is no then you stop here. If the answer is yes, then you proceed to develop a level 2 diagram. In the case of the Playsound API narrative, I did not think a level 2 diagram is necessary.

---
class: middle
# DFD Construction
## Step 5: Sanity Check (1)
### Data stores
- Two data stores should not be connected directly
- EIs should not directly interact with data stores
- Data stores should have an input flow
- Try to locate data sinks, whenever possible

### External Interactors
- Avoid data flows between External Interactors
- Data always comes from External Interactors

???
Now before we finalize a DFD, it is prudent do a sanity check.
Here is a list of things to avoid. I have it organized by DFD elements, starting with Data Stores.

First, two data stores should not be connected with data flows directly. They are static entities they cannot actively transfer data over dataflows.
Second, external interactors should not directly interact with data stores. As a general convention, data stores are encapsulated or mediated by processes.
Third, data stores should have an input flow to respond with some output. They are passive entities so cannot initiate data transfer on their own.
Finally, while telling your story using a DFD, make sure that the data eventually finds a sink. These are typically data stores.

We will look at example of these shortly. Meanwhile let's look at sanity checks for external interactors.

First sanity check, avoid data flows between External Interactors. They cannot be observed by the system so why include them in our diagram.
Second, your story should begin with data starting from External Interactors. This sanity check will keep you focused on high priority threat scenarios.

---

## Things to Avoid in a DFD
![example](images/avoid.svg)


???
Let's look at how some of these issues can appear in a DFD diagram.
In the top left diagram, we don't ever want an external interactor to interact directly with a data store. We need a process element to mediate this interaction.
The top right diagram, depicts dataflows between two external interactors. You don't want this as the system cannot see or control these, so why include them in the diagram and waste our time analyzing them.
The leftmost diagram in the bottom row shows that two data stores are connected directly. We need a process element between them as data stores are static entites. They cannot actively initiate dataflows. They only react to external stimilus.
The rightmost diagram in the bottom row illustrates a diagraming issue where the input to the data store is missing, which generates the ouput. Again, data stores are not active entities.

---
# DFD Construction
## Step 5: Sanity Check (2)

### Data Flows
- Attached to at least one Process or External Interactor

.top-right[![example](images/avoid-dangling.svg)]

### Processes
- All processes need appropriate _inputs_ to generate _outputs_
- Carefully think about direct dataflows between two separate processes on a single machine  
Use intermediate data stores such as message queues or domain sockets in a level 2 diagram


???
Checks for dataflows and processes are a bit simpler. First both ends of a dataflow should be attached to another DFD element. No dangling dataflows. This check is so easy, tools could automatically check for it and report issues. This condition is illustrated in the figure on the top right side.

For processes, the first sanity check is to make sure that all processes have appropriate input to generate outputs. Remember, no output without inputs!

The last sanity check pertains to two processes communicating with each other. Processes that exist in different memory areas cannot exchange messages with each other. Memory isolation at the CPU level would prevent this. So, in a level 2 diagram it would be more accurate to depict intermediate data stores such as message queues, temporary files, or domain sockets for two processes to exchange messages.

---
# DFD Construction
## Step 6
### Simplify (1)
- Consolidate data flows that always flow together
![example](images/avoid-flows.svg)


???
The final step in DFD construction is to look for opportunities to simplify! Here are some pointers to do so.

First, consolidate data flows that always flow together. In a given direction, two DFD elements should only be connected with a single dataflow. If you have multiple flows identified, consolidate them into a single data flow and label  it with the most critical data exchanged between the DFD elements in a given scenario. This simplification will result in better automated threat generation using a DFD. We will look at threat generation shortly.

In the example, I illustrate how two separate dataflows are consolidate into a single dataflow, with a label that is abstract enough to include both data items.

---
# DFD Construction
## Step 6
### Simplify (2)
- Avoid partitioning processes based on control logic.  
Only partition processes that exist in different memory spaces. Different functions of a single program are still in the same memory region.
![example](images/avoid-split.svg)

???

Second, there is a natural tendency to want to partition processes based on functions or classes. Avoid the urge to do this. From a threat analysis perspective, if different program modules reside within the same shared memory area at execution time, splitting them into separate processes is useless. Processes in your DFD diagram should correspond to the runtime processes that would appear in your task manager, when software is executing.

In the example, I illustrate two processes that are two functions that are part of the same program. They both run in the same virtual memory space at runtime. In this case it is better to simplify the diagram by consolidating them into a single sorter process. For security analysis this is more efficient.


---
# DFD Construction
## Step 6
### Simplify (3)

- DFDs do not typically show time dependencies.   
If processes can communicate, they are assumed to be synchronous.  

![example](images/avoid-time.svg)

???

Finally, DFDs are not appropriate to show time dependencies or sequence of messages. UML sequence diagrams or swimlane diagrams would be more appropriate in that case. So avoid creating a sequence of messages using dataflows. Remember that Dataflows are labeled with just the data that is transferred.


---
class: middle
# DFD Modeling Summary
- DFDs depict dataflows from sources to sinks with transformations along the way.   
Trust boundaries intersect data flows.
- Hierarchical structuring (Levels) allows system analysis at different levels of abstraction   
It also helps in DFD construction through successive refinement.

???
In summary, we discussed why we want to construct DFDs, how to construct DFDs and how to refine and simplify DFDs.   

Here is the big takeaway, and I said it before: Most attacks come through data, and these attacks are interested in going after data in the system. So design analysis for security is most effective when done from a data-flow perspective.

In the next video we will look at how we can use DFDs to automatically identify threats.

---
class: middle, center
# Threat Identification
DFDs allows potential threats to be .red[automatically generated]!

???
Constructing Data Flow Diagrams is a necessary first step in applying a structured approach to threat scenarios during design. Once a DFD is available, a developer can automatically enumerate potential threats using a simple checklist. To do this, a developer needs no special security training or background. As a result, many companies have found it valuable to perform threat modeling without burdening the security team.


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
???

To analyze potential issues at design time, Microsoft has identified six threat categories. Fortunately, these six categories are easy to remember based on an acronym. The acronym is STRIDE, which helps us remember Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service and Elevation of Privilege threat categories.

---

class: middle
# Microsoft STRIDE Threats

## Spoofing
* A DFD element claims a fake identity

## Tampering
* Act of altering bits

## Repudiation
* Deny that something happened or an action was taken

???
Here are some simple definitions to make sure we have a shared understanding of STRIDE threats.   
> Spoofing means the DFD element, such as a process or an external interactor, claims to be someone they are not.

> Tampering means violating the integrity of data or code.

> Repudiation means a DFD element can deny that something happened, i.e., challenge the result of an action. For example, in an e-commerce scenario, a customer can deny placing an order.

---
class: middle
# Microsoft STRIDE Threats

## Information Disclosure
* Information can be read by an unauthorized party

## Denial of Service
* Process or data store not able to process incoming requests

## Elevation of Privilege
* A user can increase capability or privilege by taking advantage of an implementation bug

???

Continuing the list...

> Information disclosure means that an unauthorized user can read data, violating confidentiality

> Denial of service is like what it sounds. In the context of a DFD, the elements that provide services are processes and data stores. So when these elements cannot process incoming requests due to an overload of requests or component failure, availability is impacted.

> Elevation of Privilege is often a pre-cursor to other threats. Here a malicious user can exploit an implementation bug to increase their capability or privilege. So it essential to contain and limit the damage that can be caused by exploiting user-facing components.

---
class: middle

# STRIDE Per .red[Interaction]
## Focus on Interactions
- Interaction:   
A source and target element connected by a data flow
![Example of DFD Level 1 Interaction](images/interactiondfd1.svg)

???
A basic strategy is to instantiate STRIDE threats for each DFD element. This strategy is called STRIDE per element. However, as you can imagine, this would generate many threats for any non-trivial DFD diagram. Instead, we can do something better.  

In a DFD diagram, an interaction refers to a data flow with a source and target. In the example on the slide, we see that the Form Request Data dataflow has a source: the Student external interactor and a target called the Canvas Web App. STRIDE threats make a lot more sense in the context of this interaction. For example, what if the Student spoofs their identify as a Teaching Assistant when interacting with the Canvas Web App? Similarly we can instantiate the rest of STRIDE threats in the context of this interaction. This strategy is very effective and saves time. It is called STRIDE per Interaction.

---
class: middle

# STRIDE Per .red[Interaction]
## For each interaction apply STRIDE
- For each STRIDE threat identify the attacker controlled element and the attacked element

## Optimizations
- For data flows inside a single process space,   
don’t worry about T, I, or D
- Prioritize interactions that _cross trust boundaries_
???
As the name suggests, with STRIDE per interaction strategy, we identify the attacker-controlled element and the attacked element connected by a dataflow for each instantiated STRIDE threat.

There are a couple more optimizations that can save us time by reducing the number of threats generated.

First, if you are analyzing data flows within a single process space, i.e., the source and target processes are within the same virtual memory region, don't worry about Tampering,  Information Disclosure, or Denial of Service threats. Why? Well... if the source and target processes are in the same virtual memory space, they cannot address concerns related to confidentiality, integrity, and availability from each other.

But, spoofing and elevation of privilege are both threats that can have cascading effects that can carry over beyond the limited context. So we cannot ignore them even for processes within a single process space.

The second optimization suggests that we prioritize interactions that cross trust boundaries, which means that we should spend more time analyzing the threats related to interactions that cross a trust boundary.

So on the previous slide, we would spend more time studying the interactions that cross the Internet Boundary.


## Significant reduction in number of threats to be analyzed
---
class: middle

# Another Optimization
- **STRIDE per Interaction** is only applied for interactions that cross a trust boundary

> .red[Trusted/high code reading from untrusted/low]  

> .red[High code writing to low]  


???
As an additional optimization, you can apply STRIDE per Interaction strategy only to interactions that cross a trust boundary.

In particular, the following scenarios are critical. When a more trusted code reads from untrusted sources across a trust boundary, the data can be tampered with or come from a spoofed identity.

In contrast, when a trusted code outputs data to untrusted targets across a trust boundary, it is critical to assure that the data being shared is authorized for the recipient. For example, an error message may result in unauthorized Information Disclosure through inference.

In short, interactions crossing a trust boundary deserve intense scrutiny.

---
class: top
# Tool Support

## Automation
- Tool support for threat generation

## Traceability
- Would be nice to link all analysis along with the diagram
- A bit more than a PPT, Visio or Lucidchart!

???

Turns out, much threat generation can be automated using simple rules based on the diagram structure. Also, it would be nice to associate the analysis for each generated threat with the diagram itself. While the DFD is simple enough to be drawn anywhere, the automation and traceability of analysis would require something more than PowerPoint, Visio or Lucid-chart.

So Microsoft has developed a special tool for threat modeling. OWASP is also following in the steps of Microsoft and developing additional cross-platform tool options. But the Microsoft tool is more mature at this point and hence we will use that for our class.

---
class: middle
## [Microsoft Threat Modeling Tool (TMT)](https://www.microsoft.com/en-us/download/details.aspx?id=49168)
![toolsupport](images/toolsupport.png)

???
The tool that we will use for this class is simply called Microsoft threat modeling tool (TMT). This tool only installs on a Windows Operating system. If you are using a MacOS then I recommend you install windows in a virtual machine and then install the tool.

For practice, I recommend that you build a DFD for the Playsound API on Slide [34](http://localhost:8000/slides/lecture-4/design-for-software-se.html#p34) in TMT and then examine the threats identified

---
class: middle
# .center[Threat Mitigation]

???
Now why bother to create a DFD model, identify lots of threats, and then stop!
So it is important to think about mitigating the identified threats.

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

???
For each threat, we need to make a decision. The first instinct should be to redesign — redesign such that it eliminates the threat. If that is not possible, then apply standard mitigations. In most cases, a standard mitigation library should be maintained, informed by past performance. For example, what have similar software packages done for mitigating the threat? How has that worked out for them and their users? It is better to use a standard library for security services such as cryptography and access control.

If standard mitigations don't exist, then you may have to invent or implement new mitigations. Be very careful in selecting this option, as it may have loopholes that are yet to be discovered. The final option is to do nothing and accept the vulnerability in the design. This option means that the risk from the threat is acceptable, but the designated risk authority should approve such a decision.

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

???
In many cases, the option to implement a mitigation is the most straightforward. Each STRIDE Threat category also has a corresponding control category that addresses it. For example, an authentication control addresses a threat in the Spoofing category.

With these mappings, the next few slides identifies a few standard mitigations that can be applied in each threat category.

---

class: middle
# Standard Mitigations

## Spoofing
### Authentication
- Data or Code

### Validation
- Normalization before neutralization

???
Addressing spoofing threats requires a validated identity of the source from which data or code is received. Identify checks are crucial for code downloaded from a remote location.

Authentication controls are often the target of injection attacks. Therefore, when performing authentication checks, normalize the authentication data to a standard representation before any filtering procedures are applied to neutralize special characters used in an attack.

---
class: middle
# Standard Mitigations

## Tampering

### Integrity Checking
- Digital signatures and message authentication codes
- Access Control Lists (ACLs) for data at rest

### Validation
- Normalization before neutralization

???
Tampering threats require integrity checks to be implemented. Stronger integrity checks are based on digital signatures and cryptographic message authentication codes. Tampering can also be prevented using appropriate permissions for data at rest.

Again, as with spoofing, ensure that the integrity data such as digital signatures and message auth codes are validated before checking.

---
class: middle
# Standard Mitigations

## Repudiation
- One-way log and audit generation mechanism

## Information Disclosure
- ACLs
- Encryption with good key management and protocols

???

Addressing Repudiation requires strong logging and audit controls. It is essential to make sure that logs are forensically sound using appropriate authentication and access control mechanisms.

Information disclosure threats can be addressed appropriate authentication and access control mechanisms. While encryption is likely mitigation, care must be taken to use strong algorithms and have good key management protocols.

---
class: middle
# Standard Mitigations

## Denial or service
- ACLs to protect the contents of files from being removed or modified
- Firewall rules to protect against some network based attacks
- Use disk and processor quotas to prevent excess disk or CPU consumption

???
Denial of service threats are addressed by either throttling or rejecting unauthenticated requests. Here are some examples, but other mitigations are undoubtedly possible. In some cases, the mitigations may be implemented outside the system of interest, for example, in a load balancer or firewall.

---
class: middle
# Standard Mitigations

## Elevation of Privilege
- Input validation
- ACLs, Roles, Groups
- Privilege dropping
- Least privilege
- Compartmentalization

???
Finally, elevation of privilege threats are addressed by containing the damage that can be done. As with spoofing and tampering threats, input validation is a must. In addition, authorization controls can be implemented using permissions or role-based access controls. When using permissions, it is prudent to drop the permissions as soon as the high privilege task is done. Also a process must run with the least privilege necessary to do its task. Finally, the memory region a process can access should be limited. This can help contain the damage from a previously unknown implementation error.

---
class: middle

# Avoid Distractions
## Applications can't address these threats:  

> The computer is infected with malware  

> Someone removed the hard drive and tampers  

> Admin is attacking user  

???
When thinking about threats and mitigations, it is best to avoid some distractions. If you are threat modeling an application, which will often be the case, ignore threats that cannot be addressed at the application layer. For example,
> The computer is infected with malware  

> Someone removed the hard drive and tampers, or

> Admin is attacking user

---
# How to ignore threats?
## No requirement
- There are no requirements that the &lt;&lt;element&gt;&gt; protect against &lt;&lt;STRIDE&gt;&gt; threat

## Irrelevant
- This threat does not exist, so we don't care about &lt;&lt;STRIDE&gt;&gt; threat to the &lt;&lt;element&gt;&gt;

## Not applicable
- &lt;&lt;STRIDE&gt;&gt; generated threat does not apply to this &lt;&lt;element&gt;&gt;

???
Now it may happen that some of the automatically generated threats are not appropriate. In that case, use standard terminology to document the reason for ignoring a generated threat.

The phrase "No requirement" is used to indicate that there is no user requirement that the DFD &lt;&lt;element&gt;&gt; protect against &lt;&lt;STRIDE&gt;&gt; threat

The phrase "Irrelevant" is used to express that the threat does not exist, so we don't care about &lt;&lt;STRIDE&gt;&gt; threat to the DFD &lt;&lt;element&gt;&gt;

Finally, use the "Not applicable" phrase to indicate that the &lt;&lt;STRIDE&gt;&gt; generated threat does not apply to the DFD &lt;&lt;element&gt;&gt;


---
class: middle
# Validate the Threat Model

1. Do the threats consider misuse cases?
1. Does the diagram match final code?
1. Are enough threats enumerated?
1. Has Test / QA reviewed the model?
Testers often finds issues with threat model or missing details
1. Is each threat mitigated?
1. Are mitigations done right?  (Assurance case, possibly)

???
When all threats are addressed, it is time to step back and think about validating the threat model.
during Validation, we ask questions like:

> Do the threats consider misuse cases?  
> Does the diagram match code/implementation?   
> Are enough threats enumerated?  
> Has Test / QA reviewed the model?  
Testers often finds issues with threat model or missing details  
> Is each threat mitigated?  
> Are mitigations done right?  (Assurance case, possibly)  


---

# Making this Fun

## Elevation of Privilege Card Game
- Ease developers into doing threat modeling
- [How to play](http://social.technet.microsoft.com/wiki/contents/articles/285.elevation-of-privilege-the-game.aspx)
- [Card Images](https://github.com/adamshostack/eop)
- [Other SDL developer resources](https://www.microsoft.com/en-us/download/details.aspx?id=20303)
- [More information](https://shostack.org/games/elevation-of-privilege)

![EOP](https://c.s-microsoft.com/en-us/CMSImages/EoP_game_screen_shot.jpg?version=4a082487-9fb4-7dd9-ed9f-e79c888c2df4)

???
To encourage threat modeling in development teams, Microsoft has come up with a card game. The objective of the game is to come of threats for a given DFD to earn points. The player with the most points at the end of the game wins.

---
class: middle
# Sources and Additional Readings
- This presentation is borrows a lot from Microsoft training materials on threat modeling and many sources for DFDs  

## Threat Modeling in Practice
- Threat Modeling Security Fundamentals [User Guide](https://learn.microsoft.com/en-us/training/paths/tm-threat-modeling-fundamentals/)  
- Bruce Schneier on [threat modeling](http://www.schneier.com/blog/archives/2007/10/threat_modeling.html)  
- [SAFECode Tactical Threat Modeling](https://safecode.org/safecodepublications/tactical-threat-modeling/)  
- Microsoft [Docs](https://www.microsoft.com/en-us/securityengineering/sdl/practices/secure-by-design)
- [Integrating threat modeling with DevOps](https://learn.microsoft.com/en-us/security/engineering/threat-modeling-with-dev-ops)
- [Threat modeling AIML](https://learn.microsoft.com/en-us/security/engineering/threat-modeling-aiml)

???
This presentation borrows and adapts a lot from Microsoft training materials for threat modeling and many other sources for DFD diagraming techniques.

There are some additional readings on the topic which I link here. These include blogs and white papers that talk about the use of threat modeling in practice at some of the leading companies in software development such as Google, Adobe and Microsoft.

---
exclude: true
class: center, middle
# Threat Modeling In-Class Demonstration

---
exclude: true
class: middle

# Step 1
- Download and install [Microsoft TMT](https://www.microsoft.com/en-us/download/details.aspx?id=49168)

---
exclude: true

class: middle
# Step 2
- Build a DFD for the Playsound API in TMT
- Examine the threats identified

---
class: center, middle
# Discussion?
![that-dont-make-no-sense](https://media.giphy.com/media/DO5JobrylWL7i/giphy.gif)
???
In the next video we will talk about structural-design patterns that help to redesign for for security.
