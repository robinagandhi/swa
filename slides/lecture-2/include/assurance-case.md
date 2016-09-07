class: center, middle
# Assurance Case
???
This slide deck is based several sources as follows:

1. Goal Structuring Notation
2. IEEE Standard— Adoption of ISO/IEC 15026-2:2011
Systems and Software Engineering— Systems and Software Assurance— Part 2: Assurance Case
3. Research papers on Eliminative Induction use in Assurance Cases
4. SEI publications on Assurance case use in Safety Cases

---
class: middle

## The first principle is that you must not fool yourself and you are the easiest person to fool... After you've not fooled yourself, it's easy not to fool other scientists.

.footnote[
Richard P. Feynman
]
.top-right[
![RF](http://www.hwscience.com/physics/apphysicsc/Feynman-2.gif)
]
---
class: middle

## .blue[Schneier's Law]  
## Any person can invent a security system so clever that he or she can’t imagine a way of breaking it.

.footnote[
Bruce Schneier
]
.top-right[
![Bruce](https://upload.wikimedia.org/wikipedia/commons/thumb/f/fc/Bruce_Schneier_at_CoPS2013-IMG_9174.jpg/220px-Bruce_Schneier_at_CoPS2013-IMG_9174.jpg)
]
---
class: middle

## False assurance is a danger that is avoidable by only trusting technology that is demonstrably trustworthy.

.footnote[
Roger Schell
]
.top-right[
![Roger](http://www.ieee-security.org/TC/SP2010/photos/.xvpics/0054_IMG-thumb.jpg)
]
---
background-image: url(http://wallpapercraze.com/images/wallpapers/uwp6%20%282%29-110045.jpeg)
???
Scenario: Our goal is to find a black cat in a dark room.
---
background-image: url(images/black.png)

???
We also not sure if there is a cat there to begin with!
## Source: The cat example is adapted from the example provided in System Assurance: Beyond Detecting Vulnerabilities (The MK/OMG Press) 1st Edition, by Nikolai Mansourov  and Djenana Campara https://amzn.com/0123814146
---
class:middle
# Task at hand
Find a **black cat** in a **dark room**  
--

Also, we are not sure that the cat is really there!

--

## .blue[
What are the Goals/Claims to be proven?
]

---
class:middle
# Possible claims

## .red[Claim 1:] The room has at least one black cat
--

## .red[Claim 2:] The room has no black cats

--
## .blue[
What is the basis for the belief in these claims?
]
---
class: middle
# .red[Claim 1]
The room has at least one black cat

---
class: middle
# Basis for the Belief

## .blue[Kitty-Kitty] Search Process*
1. Search team puts a bowl of milk in the room and says _kitty-kitty-kitty_ three times
1. Four corners and center of room covered
1. Stop when a cat is discovered

.footnote[\* Patent Pending]

---
# Structured Argument
### .red[Claim]
The room has at least one black cat
--

### .red[Sub-Claim]
Search team followed the “kitty-kitty” search process
--

### .red[Inference Rule] (Connects Claim to Sub-claims)
By following a good search process we can find black cats
--

### .red[Evidence]
Report of cat findings from the search process
---

# Assurance Case
![claim1-case](images/claim1-case.svg)

---
class: middle
# .red[Claim 2]
The room has .red[no] black cats
---
class: middle
# Basis for the Belief

### The search process now needs to be exhaustive!
--

### The problem needs decomposition
--

> To do this we introduce .red[doubts]

---

class: middle, center
# [Eliminative Induction](https://www.google.com/search?q=define+eliminative+induction)
A series of doubts are introduced for some state of affairs,  
and then progressively eliminated by new evidence

---
# Eliminative Induction

## Step 1
Challenge claims by introducing doubts
--

## Step 2
For each doubt, identify sub-claims that eliminate the doubt
--

## Step 3
Go to Step 1, repeat process for sub-claims
---
class: middle
# Step 1: Introducing doubts

.green[Kitty-Kitty Search process, finds all cats]
--

* .red[Unless] the cats were not hungry  
* .red[Unless] the milk is not put in enough places
* .red[Unless] the people are not competent
* .red[Unless] the baby panthers found are indeed cats

---
class: middle
# Step 2: Eliminate doubts

.red[Unless] the cats were not hungry  
* .green[The room was locked for 5 days]  

--

.red[Unless] the milk is not put in enough places  
* .green[The room is simultaneously searched in 10 equal non-overlapping squares]  

---
class: middle
# Step 3: Repeat

.green[The room was locked for 5 days]  
* .red[Unless] the room vents allow cats to go in and out  

--

.green[The room is simultaneously searched in 10 equal non-overlapping squares]  
* .red[Unless] the cats have an alternate food supply (mice in the room)

---
class: middle
# Stopping condition?

## Evidence
When the argument is convincing enough to the reader, it should end in the presentation of facts that support the claims

---
class: middle
# Evidence

.red[Unless] the room vents allow cats to go in and out  
* .green[All room vents have nets installed]
* .blue[Evidence:] Vent inspection report

.red[Unless] the cats have an alternate food supply (mice in the room)
* .green[There are no mice in the room]
* .blue[Evidence:] Month old exterminator report for rodents

---

class: middle
# Basis for the Belief

As more reasons for doubt are eliminated, assurance in the top-level claim increases  

If many doubts remain, assurance is diminished

--

In any situation, a rigorous argumentation structure assists trust decisions for the presented claims
---

class: middle
# .red[Claim 3]
The room will have no black cats for the next 12 months

--

Does it make sense to justify this claim by a single search at a moment in time?

---
# Risk: A future adverse event

We can introduce even more doubts!
* .red[Unless] the cats hibernate when search is conducted  
* .red[Unless] cat zapper gates are working intermittently
* .red[Unless] the vents are not being periodically inspected
* .red[Unless] the exterminator skips visits

--

To eliminate these doubts, continuous efforts are required.

---
# A very catty summary

## Equate Cats to Software Weaknesses

### Claim 1 (Point Solution)  
* Produces knowledge about what you found  

.bottom-left[
![catfunny](http://memesvault.com/wp-content/uploads/Funny-Cat-Meme-Work-1.jpg)
]

---
# A very catty summary

## Equate Cats to Software Weaknesses

### Claim 2 (Snapshot)  
* Produces knowledge about the whole system

.bottom-left[
![catfunny](http://i0.kym-cdn.com/entries/icons/original/000/002/232/bullet_cat.jpg)
]

---
# A very catty summary

## Equate Cats to Software Weaknesses

### Claim 3 (Continuous Assurance)  
* Produces knowledge about minimizing  
a future undesirable event

.bottom-left[
![catfunny](http://i0.kym-cdn.com/photos/images/newsfeed/000/115/642/non-stop-nyan-cat.jpg?1303327212)
]
---
class: center, middle
# Developing Assurance Cases

---
# Assurance Case Logical Structure
![structure](images/structure.png)
.footnote[
[Arguing Security - Creating Security Assurance Cases](https://buildsecurityin.us-cert.gov/daisy/bsi/articles/knowledge/assurance/643-BSI.html)
]

---
# Assurance Case Contents

## A Top-level Claim
The claim is regarding a property of a system or product
## Argumentation
Arguing through multiple levels of subordinate claims connects the top-level claim to the evidence and assumptions
## Evidence and Assumptions
Explicit information that underlies the argumentation
---

class: middle
# Convince a bystander

### _While an assurance case is useful for decision-making by knowledgeable stakeholders (e.g., developers and service providers), often the primary motivation for an assurance case is to support crucial decisions by stakeholders without this background, such as those involved in certification, regulation, acquisition, or audit of the system._

.footnote[
[ISO/IEC 15026-2:2011](http://www.iso.org/iso/catalogue_detail.htm?csnumber=52926)
]
---

# [ISO/IEC 15026-2:2011](http://www.iso.org/iso/catalogue_detail.htm?csnumber=52926)
![iso](images/iso-standard.png)

---
# Claims
### Claims concern critical properties

--

### A claim is always worded as a predicate
- i.e. it can only be true or false

--

### Claim should avoid just details about the supporting method/techniques
- .red[Bad claim:] The software uses AES encryption
- Uninteresting

--

### The claim should be a reasonable goal
- .green[Good claim:] “The system is acceptably secure”

---
# Claims

## Claim properties are risk-related
- High confidence is needed in their realization

--

## Good Claim Checklist
- .blue[An entity]
- .orange[A critical property of the entity]
- .green[A value for the property and related uncertainty]

--

## Example
- .blue[The system] .green[is acceptably] .orange[secure]
- .blue[The System] .green[has no] .orange[unacceptable consequences to assets from security threats]

---
class: middle
# [Grammatical Guidance](http://www.sei.cmu.edu/dependability/tools/assurancecase/)

## .blue[&lt;NOUN-PHRASE&gt;]
- .blue[Noun-Phrase] identifies the subject (“entity”) of the claim

## .orange[&lt;VERB-PHRASE&gt;]  
- .orange[Verb-Phrase] defines a predicate using the critical property of the subject along with its expected value and related uncertainty

---
class: middle
# [Grammatical Guidance](http://www.sei.cmu.edu/dependability/tools/assurancecase/)

## Bad Examples
- Describes an entity: ~~.red[XSS results for Blackboard]~~
- Describes an action: ~~.red[Perform XSS on Blackboard]~~
- A question: ~~.red[How many XSS weaknesses does Blackboard have?]~~

---
class: middle
# .red[Actual] bad examples

## .red[C5: Security Professionals test code for XSS vulnerabilities]

--

## .red[C18: The System uses a Static Analysis tool]
.footnote[
See notes for class exercise
]
???
# Class exercise:
Work in your team to rephrase these appropriately.
When you are done enter your answers [here.](https://docs.google.com/a/unomaha.edu/document/d/1ApR8Mdh4Ks4bB10ame4oXb6hs3AcxriOH0L-mjKOS1I/edit?usp=sharing)

---

class: middle
# Good Examples

## .blue[Blackboard] .green[has no] .orange[exploitable XSS weaknesses]

--

## .blue[All Blackboard XSS weaknesses] .green[have been sufficiently] .orange[mitigated]

--

## .blue[Blackboard] .orange[Attack surface] .green[is minimized]

---
class: middle
# Scenario

## OPPD NE has received intelligence.
- Rouge nation states are targeting their software supply chains.
- There is a credible threat. OPPD NE bought software for business functions is being targeted for sabotage with malicious code.

--

## Top Level Claim
- .blue[OPPD NE supply chain processes] .green[minimize ] .orange[the possibility of sabotage by malicious code in software applications]

---
class: middle
# Claim Visual Notation
## Based on Goal Structuring Notation (GSN)

![claim](images/claim.svg)

---
class: middle
# Elaborating the Claim

## Additional information not part of the claim or evidence
- Context (understanding)
- Justification (rationale)
- Assumptions (validity)

---
class: middle
# Context

## Information necessary for a claim to be understood or amplified
- Includes a statement that defines the .red[scope] of the claim
- Provides means to check .red[satisfaction] of the claim

## Examples
- External references, Definitions, Clarification of myths
- Security considerations for supply chain processes per NIST SP 800-160

---
class: middle
# Assumption

## A statement whose validity has to be relied upon in order to make an argument
- .red[Restricted context]
- .red[Exceptions] or situations the claim does not cover

## Example
- Nuclear energy safety mechanisms do not include software

---
class: middle
# Justification

## Provides .red[rationale] for the use/selection of a claim or strategy

## Example
- Intelligence reports of malicious code in nuclear energy software

---
class: middle
# Context Visual Notation

![context](images/context.svg)

---
class: middle
# Justification Visual Notation

![justification](images/justification.svg)

---
class: middle
# Strategy

## Provides direction for an argument

## Phrased with respect to the argument
- .green[Argument by appeal to software acquisition practices]

## A strategy is elaborated by providing a series of sub-claims
---
class: middle
# Strategy Visual Notation

![strategy](images/strategy.svg)

---
class: middle
# Argument

## Conveys why to believe a claim has been met
- Refine claims into sub claims, until the sub-claim can be directly supported by the actual evidence
- Bridges the gap between claims and evidence

--

## Stopping condition?
- The rigor is acceptable
- Resources are unavailable
- Further expenditure is not justified

---

## Sub-claim

Develop a sub-claim
![argument](images/strategy.svg)

---
## Sub-claim
![sub-claim](images/sub-claim.svg)
---
# Evidence

## Every branch must be terminated in a reference to a item of evidence
## Prove/substantiate the claims with something tangible and measure-able
## Must be a noun phrase only (NO verb phrase)
## Should not be stated as a claim

---
class: middle
# Evidence

## Examples
- Test results from penetration tools
- Warnings from static analysis tool
- Hardware design review results
- Parameter validation assurance case
- Reports for assessing compiler settings with security implications

---
class: middle
![Evidence](images/evidence.svg)

---
class: center, middle
# Coming up with a good Argument is .large[Hard!]

---
# Introducing Doubts*

## Making doubts explicit
### Attack claim (rebutting defeater) — why claim could be false
### Attack evidence (undermining defeater) — why evidence could be irrelevant
### Attack inference (undercutting defeater) — premise good; conclusion uncertain

.footnote[
\*See notes for sources [hit: p]
]

???
The content in next few slides is based on:
1. SEI Report: Toward a Theory of Assurance Case Confidence http://www.sei.cmu.edu/reports/12tr002.pdf
2. Charles B. Weinstock, John B. Goodenough, and Ari Z. Klein. 2013. Measuring assurance case confidence using Baconian probabilities. In Proceedings of the 1st International Workshop on Assurance Cases for Software-Intensive Systems (ASSURE '13). IEEE Press, Piscataway, NJ, USA, 7-11.
3. Explicit permission to use slides provided by John B. Goodenough

---

# Eliminative Induction
## Support/assurance increases as reasons for doubt are eliminated

--

## Claim: The bulb will always turn on
- Unless switch not connected to light
- Unless no power
- Unless dead light bulb  
![light](images/lightexample.png)

???
Image and example provided in slides by John B. Goodenough

---
class: middle
# Measuring Confidence

## Baconinan Probability
- 0|n (no confidence) — no doubts eliminated
- 2|3 (partial confidence) — residual doubt
- n|n (complete confidence) — no doubts remain

--

## Use for relative improvements, not comparison

???
Source: Slides by John B. Goodenough
Source: Charles B. Weinstock, John B. Goodenough, and Ari Z. Klein. 2013. Measuring assurance case confidence using Baconian probabilities. In Proceedings of the 1st International Workshop on Assurance Cases for Software-Intensive Systems (ASSURE '13). IEEE Press, Piscataway, NJ, USA, 7-11.

---

# Example Claim
![claim](images/tweetyclaim.svg)
---
class: middle
# Inference Rule

## A generalization that in most circumstances is considered to be true

## Example
- (Generalization) All birds can fly
- (premise) If X is a bird then (conclusion) X can fly

--

.red[An argument is an instantiation of one or more inference rules with a specific premises and conclusions]

---
# Inference Rule
![inference](images/inference.svg)

---

# Undercutting defeater
## Premise good; conclusion uncertain
![claim](images/inference.svg)
---

![claim](images/undercut.svg)

---

# Rebutting defeater
## Why claim could be false
![claim](images/inference.svg)
---

# Rebutting defeater
## Why claim could be false
![claim](images/rebutting.svg)

---
# Address Rebutting defeater
![claim](images/rebuttclaim.svg)

---
# Undermining defeater
## Why evidence could be irrelevant
![claim](images/undermine.svg)

---
# Undermining defeater
![claim](images/undermine-done.svg)

---
![preview](images/preview.svg)

???
Source: This example is partially based on the presentation of this paper given at ICSE conference: J. B. Goodenough, C. B. Weinstock and A. Z. Klein, "Eliminative induction: A basis for arguing system confidence," 2013 35th International Conference on Software Engineering (ICSE), San Francisco, CA, 2013, pp. 1161-1164.
---
class: center, middle
# .large[Got Assurance?]
.bottom-left[
![meme](http://s2.quickmeme.com/img/31/315640bead03adc498079b11707081fbfcfc0d4d97b1e1d69ba1d930dfa286d6.jpg)
]
