class: center, middle
# Assurance Case*
.footnote[
\* See notes for sources
]
???
This slide deck is based several sources as follows:

1. Goal Structuring Notation
2. [IEEE Standard— Adoption of ISO/IEC 15026-2:2011](https://www.iso.org/standard/52926.html)
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
## Source:   
The cat example is adapted from the example provided in System Assurance: Beyond Detecting Vulnerabilities (The MK/OMG Press) 1st Edition, by Nikolai Mansourov  and Djenana Campara https://amzn.com/0123814146
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

## .blue[Kitty-Kitty-Kitty] Search Process*
1. Search team puts a bowl of milk in the room and says _kitty-kitty-kitty_ three times
1. Four corners and center of room covered
1. Stop when a cat is discovered

.footnote[\* Patent Pending]

---
# Structured Argument
### .red[Claim]
.red[C1:] The room has at least one black cat
--

### .red[Sub-Claims]
.red[C1.1:] Kitty-kitty-kitty search process discovers cats in the room

--

### .red[Evidence]

.red[E1.1.1:] Pictures of cats found

---
class: middle
# .red[Claim 2]
The room has .red[no] black cats

--

### .red[Sub-Claims]
.red[C1.1:] Kitty-kitty-kitty search process discovers no cats

--
### .red[Evidence]

.red[E1.1.1:] Empty findings report


---
class: middle
# Is this argument enough?
Can you ever be 100% sure for a large and complex room?  


---
class: middle
# .red[Assurance]
Basis for the belief in a claim

--

## .green[Belief] increases when .red[doubts] are removed!   

--

A good argument eliminates identified doubts

---

class: middle
# [Eliminative Induction](https://www.google.com/search?q=define+eliminative+induction)
A series of doubts are introduced for some state of affairs,  
and then progressively eliminated by new evidence

---
# Eliminative Induction

## Step 1: Introducing doubts
Challenge the identified claims by introducing doubts
--

## Step 2: Eliminate doubts
For each doubt, identify sub-claims that eliminate the doubt
--

## Step 3: Repeat
Go to Step 1, repeat process for sub-claims
---
class: middle
# Step 1: Introducing doubts

.red[C1.1:] Kitty-kitty-kitty search process discovers no cats
--

* .red[R1.1.1] _Unless_ the cats were not hungry  
* .red[R1.1.2] _Unless_ milk is not put in enough places
* .red[R1.1.3] _Unless_ the people searching are not competent
* .red[R1.1.4] _Unless_ the baby panthers found are indeed cats

---
class: middle
# Step 2: Eliminate doubts

.red[R1.1.1] Unless the cats were not hungry   
* .green[C1.1.1] The room was locked for 5 days  

--

.red[R1.1.2] Unless milk is not put in enough places  
* .green[C1.1.2] The room is simultaneously searched in 10 equal non-overlapping squares  

---
class: middle
# Step 3: Repeat --> Step 1: Identify doubts

.green[C1.1.1] The room was locked for 5 days  
* .red[R1.1.1.1] Unless the room vents allow cats to go in and out  

--

.green[C1.1.2] The room is simultaneously searched in 10 equal non-overlapping squares  
* .red[R1.1.1.2] Unless the cats have an alternate food supply (mice in the room)

---
class: middle
# Step 2: Eliminate doubts

.red[R1.1.1.1] Unless the room vents allow cats to go in and out  
* .green[C1.1.1.1.1] All room vents have nets installed

--

.red[R1.1.1.2] Unless the cats have an alternate food supply (mice in the room)
* .green[C1.1.1.1.2] There are no mice in the room

---
class: middle
# Stopping condition?

## Evidence
When the argument is convincing enough to the reader, it should end in the presentation of .blue[_facts_] that support the .green[_claims_]

---
class: middle
# Evidence

.red[R1.1.1.1] Unless the room vents allow cats to go in and out  
* .green[C1.1.1.1.1] All room vents have nets installed
* .blue[E1.1.1.1.1 Vent inspection report]

.red[Unless] the cats have an alternate food supply (mice in the room)
* .green[C1.1.1.1.2] There are no mice in the room
* .blue[E1.1.1.1.2 Month old exterminator report for rodents]

---
class: middle
# Argument and Evidence
* Without argument, evidence is irrelevant.
* Without evidence the argument is not substantiated.

---

class: middle
# Basis for the Belief

As more reasons for doubt are eliminated, assurance in the top-level claim increases  

If many doubts remain, assurance is diminished

--

A rigorous argumentation structure assists .red[*trust decisions*] for the presented claims
---

class: middle
# .red[Claim 3]
The room will have .red[no] black cats for the .red[next 12 months]

--

Does it make sense to justify this claim by a single search at a moment in time?

---
class: middle
# Risk: A future adverse event

We can introduce even more doubts!
* .red[R1.1.5] Unless the cats hibernate when search is conducted  
* .red[R1.1.6] Unless cat zapper vents are working intermittently
* .red[R1.1.7] Unless the vents are not being inspected periodically
* .red[R1.1.8] Unless the exterminator skips visits

--

To eliminate these doubts, .green[continuous] efforts are required.

---
# A very catty summary

## Equate Cats to .red[Weaknesses]

### Claim 1 (Point Solution)  
* Produces knowledge about what you found  

.top-right[
![catfunny](http://vignette2.wikia.nocookie.net/animal-jam-clans-1/images/6/6b/Funny-Cat-Meme-Work-16.jpg/revision/latest?cb=20160716231247)
]

--

### Claim 2 (Snapshot)  
* Produces knowledge about the whole system

.top-right[
![catfunny](http://i0.kym-cdn.com/entries/icons/original/000/002/232/bullet_cat.jpg)
]

--

### Claim 3 (Continuous Assurance)  
* Produces knowledge about minimizing  
a future undesirable event

.top-right[
![catfunny](http://i0.kym-cdn.com/photos/images/newsfeed/000/115/642/non-stop-nyan-cat.jpg?1303327212)
]

---
class: center, middle
# Developing Assurance Cases

---
# Assurance Case Logical Structure
![structure](images/structure.png)
.footnote[
[Arguing Security - Creating Security Assurance Cases](https://www.us-cert.gov/bsi/articles/knowledge/assurance-cases/evidence-assurance-laying-foundation-credible-security-case)
]

---
# Assurance Case Contents

## A Top-level Claim
The claim is regarding .red[a critical property] of a system or product
## Argumentation
Arguing through .red[multiple levels of subordinate claims] connects the top-level claim to the evidence and assumptions
## Evidence and Assumptions
.red[Explicit information] that underlies the argumentation
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
# Claims Matter!
### Claims concern critical properties

--

### A claim is always worded as a predicate
- i.e. it can only be true or false

--

### Claim should avoid just details about the supporting method/techniques
- .red[Bad claim:] The system uses AES encryption
- Uninteresting

--

### The claim should be a reasonable goal
- .green[Good claim:] “The system is acceptably secure against communication lines related threats”

---
# Claims Matter!

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
- .blue[The system] .green[has no unacceptable] .orange[consequences to assets from security threats]

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
- Just describes an entity: ~~.red[XSS results for Canvas]~~
- Describes an action on entity: ~~.red[Perform XSS on Canvas]~~
- A question: ~~.red[How many XSS weaknesses does Canvas have?]~~
- Fact, no argument needed: .red[~~Canvas uses AES encryption~~]

---
class: middle
# .red[Actual] bad examples

## .red[C5: Security Professionals test code for XSS vulnerabilities]

--

## .red[C18: The System uses a Static Analysis tool]
.footnote[
See notes (hit `p`) for class exercise
]
???
# Class exercise:
# Work with your team to rephrase these appropriately.
When you are done enter your answers in this [Google Doc](https://docs.google.com/a/unomaha.edu/document/d/11Xr8GHBHfWJGLotiLoe-us1EZ4Qjn2msjfxHAKjs64Q/edit?usp=sharing)

---

class: middle
# Good Examples

## .blue[Canvas] .green[has no] .orange[exploitable XSS weaknesses]

--

## .green[All] .blue[Canvas XSS weaknesses] .green[have been sufficiently] .orange[mitigated]

--

## .blue[Canvas] .orange[attack surface] .green[is minimized]

---
class: middle
# Scenario

## OPPD NE has received intelligence.
- Rouge nation states are targeting their software supply chains.
- There is a credible threat. Software bought by OPPD for business functions is being targeted for sabotage with malicious code.

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

## .green[Additional information] that is excluded from the claim or evidence
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
- .green[Argument by appeal to] software acquisition practices

## A strategy is elaborated by providing a series of sub-claims
---
class: middle
# Strategy Visual Notation

![strategy](images/strategy.svg)

---
class: middle
# Argument

- Conveys why we believe a claim has been met
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
class: middle
# Evidence

- Every branch must be terminated in evidence
- Something tangible and measureable

## Grammatical Guidance
- Must be a .blue[noun phrase] only (NO verb phrase)
- Should .red[not] be stated as a claim

---
class: middle
# Evidence

## Examples
- .red[E1:] Test results from penetration tools
- .red[E2:] Warnings from static analysis tool
- .red[E3:] Hardware design review results
- .red[E4:] Parameter validation assurance case
- .red[E5:] Reports for assessing compiler settings with security implications

---
class: middle
![Evidence](images/evidence.svg)

---
![arrow](images/arrows.svg)
.topnote[
What do the arrows mean?
]

---
class: center, middle
# Coming up with a good Argument is .large[Hard!]

---

# Eliminative Induction
## Support/assurance increases as reasons for doubt are eliminated

--

## Claim: .blue[The bulb] .green[will] .orange[glow when switched on]
- .red[Unless] switch not connected to light
- .red[Unless] no power
- .red[Unless] dead light bulb  
![light](images/lightexample.png)

???
Image and example provided in slides by John B. Goodenough

---
# Introducing Doubts*

## Making doubts explicit
### Attack claim (rebutting defeater) — why claim could be false
--

### Attack evidence (undermining defeater) — why evidence could be irrelevant
--

### .green[Attack inference] (undercutting defeater) — premise good; conclusion uncertain

.footnote[
\*See notes for sources [hit: `p`]
]

???
The content in next few slides is based on:
1. SEI Report: Toward a Theory of Assurance Case Confidence http://www.sei.cmu.edu/reports/12tr002.pdf
2. Charles B. Weinstock, John B. Goodenough, and Ari Z. Klein. 2013. Measuring assurance case confidence using Baconian probabilities. In Proceedings of the 1st International Workshop on Assurance Cases for Software-Intensive Systems (ASSURE '13). IEEE Press, Piscataway, NJ, USA, 7-11.
3. Explicit permission to use slides provided by John B. Goodenough

---
# Assurance Case Logical Structure
## Notice .green[inference rules]?
![structure](images/structure.png)
.footnote[
[Arguing Security - Creating Security Assurance Cases](https://buildsecurityin.us-cert.gov/daisy/bsi/articles/knowledge/assurance/643-BSI.html)
]

---
class: middle
# Inference Rule

## A generalization that in most circumstances is considered to be true

## Example
- (premise) If X is a bird then (conclusion) X can fly

--
- (Generalization) All birds can fly

--

.red[An argument is an instantiation of one or more inference rules with a specific premises and conclusions]

---

# Example Claim
![claim](images/tweetyclaim.svg)

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
# Few more notations
## Claim to be further developed
![developclaim](images/developclaim.svg)

---
# Few more notations
## No further argumentation
![stop](images/stopargument-1.svg)
![stop](images/stopargument-2.svg)

---
![preview](images/preview.svg)

???
Source: This example is partially based on the presentation of this paper given at ICSE conference: J. B. Goodenough, C. B. Weinstock and A. Z. Klein, "Eliminative induction: A basis for arguing system confidence," 2013 35th International Conference on Software Engineering (ICSE), San Francisco, CA, 2013, pp. 1161-1164.
---

class: middle
# Assurance Cases in Practice

## CC Evaluations and Software Assurance
- Argue how protection profile needs are satisfied by a Security Target
- Assurance cases are recommended for the highest levels of Evaluation Assurance Levels (EAL)

---

class: middle
_In pursuit of Trusted Computer System Evaluation Criteria (TCSEC) or CC evaluations or Federal Information Processing Standard (FIPS) 140-1 or 140-2 certifications for their security-enforcing IT products, vendors are required not only to submit assurance claims for those products to the independent evaluation or certification facility but to .red[provide complete assurance cases] that provide a sufficient basis for the facility to verify those assurance claims.*_

.footnote[
\* [Software Security Assurance State-of-the-Art Report (SOAR)](https://cwe.mitre.org/documents/iatac_swa_soar.pdf), 2007, DoD Information Assurance Technology Analysis Center (IATAC) Data and Analysis Center for Software (DACS)
]
---
class: middle
# Security Controls
[NIST SP 800-53 Rev. 5](https://csrc.nist.gov/csrc/media/publications/sp/800-53/rev-5/draft/documents/sp800-53r5-draft.pdf)

### Makes the security and privacy controls outcome-based
- Focuses on the security and privacy capabilities
- Controls are now .orange[critical properties] of interest.

???
(i.e., what needs to be done to protect the system or information and not which entity carries out the action or where it is carried out);

---
class: middle
# Security Controls
[NIST SP 800-53 Rev. 5](https://csrc.nist.gov/csrc/media/publications/sp/800-53/rev-5/draft/documents/sp800-53r5-draft.pdf)

IA-2 IDENTIFICATION AND AUTHENTICATION
### Current (Rev 4):
- Control: The information system uniquely identifies and authenticates organizational users.

### Proposed (Rev 5):
- Control: Uniquely identify and authenticate organizational users.

---
class: middle
# Software Security Controls
First to develop and apply assurance case based method for control refinement
- Software related controls derived from the NIST SP 800-53 control catalog
- These software assurance controls are enumerated in [NIST SP 800-160 Appendix-J](https://csrc.nist.gov/csrc/media/publications/sp/800-160/archive/2016-05-04/documents/sp800_160_second-draft.pdf)

#### Gandhi, R., Siy, H., Crosby, K., Mandal, S. (Graduate), (2014). Gauging the Impact of FISMA on Software Security, IEEE Computer, vol. 47 (9)
#### Gandhi, R. A., Crosby, K., Siy, H., Mandal, S. (2016) Driving Secure Software Initiatives Using FISMA: Issues and Opportunities. CrossTalk, Journal of Defense Software Engineering, Jan/Feb 2016 Issue.

---
class: middle
# Other Applications

### Forensics
- Jones, C. (2014). __Evaluating the use of assurance cases for digital forensics.__ Dissertations & Theses @ University of Nebraska - Omaha; ProQuest https://search.proquest.com/docview/1528534691?accountid=14692

---
class: middle
# Other Applications

### Research Study Design
- Gandhi R.A. and Lee, S.W., “Assurance Case driven Case Study Design in Requirements Engineering Research,” In: 15th International Working Conference on Requirements Engineering: Foundations for Software Quality, REFSQ 2009.

### Interview Protocol Design
- Gandhi R.A., Germonprez M., Link G., "Open Data Standards for Open Source Software Risk Management Routine: An Examination of SPDX", ACM GROUP 2018 https://github.com/SPDX-CaseStudy/files/blob/master/AssuranceCase.png

---
class: center, middle
# .large[Got Assurance?]
.bottom-left[
![meme](http://s2.quickmeme.com/img/31/315640bead03adc498079b11707081fbfcfc0d4d97b1e1d69ba1d930dfa286d6.jpg)
]
