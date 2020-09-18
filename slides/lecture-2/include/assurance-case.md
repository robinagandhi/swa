class: center, middle
# Assurance Case*
.footnote[
\* See notes for sources, hit `p`
]
???

This discussion is about a new topic that many in cybersecurity may not have thought about or have experience with. I will introduce a new analytical and modeling technique to plan the evidence that needs to be collected throughout the software lifecycle to support claims about security. The goal is build an argument, akin to a legal case, but instead of defending a person or an organization, our job is to defend the claims we seek to make about security properties of the system-of-interest.


This slide deck is based several sources as follows:

> Goal Structuring Notation  
> [IEEE Standard— Adoption of ISO/IEC 15026-2:2011](https://www.iso.org/standard/52926.html)
Systems and Software Engineering— Systems and Software Assurance— Part 2: Assurance Case
> Research papers on Eliminative Induction use in Assurance Cases
> [SEI publications on Assurance case use in Safety Cases](https://insights.sei.cmu.edu/sei_blog/2013/08/assurance-cases-and-confidence.html)
> [System Assurance: beyond Detecting Vulnerabilities, By Mansourov, Nikolai, and Djenana Campara](https://www.safaribooksonline.com/library/view/system-assurance/9780123814142) (Chapter 2)

---
class: middle

![Dilbert Trust and stupidity](https://assets.amuniversal.com/c8253cc0db9a012e2fae00163e41dd5b)

???
As usual, a bit of humor to kick-off the discussion. Trustworthiness, if evaluated properly, is asserted based on an investigative process. For example, clearing an individual for access to national security related projects involves collecting lot of background information and interviewing close relative and business associates. The investigation produces lots of evidence, which is then used by an authority to make a trust decision.

---
class: middle

## The first principle is that you must not fool yourself and you are the easiest person to fool... After you've not fooled yourself, it's easy not to fool other scientists.

.footnote[
Richard P. Feynman
]
.top-right[
![RF](https://upload.wikimedia.org/wikipedia/commons/1/1a/RichardFeynman-PaineMansionWoods1984_copyrightTamikoThiel_bw.jpg)
]

???
Trust decisions should not be taken lightly. This is particularly, important for scientific inquiries. Richard Feynman, a renowned physicist, had a knack for questioning claims based on research findings. This approach also helped him explore complex concepts using simple questions. So when making scientific inquires, he says the first principle is that you must not fool yourself and you are the easiest person to fool... After you've not fooled yourself, it's easy not to fool other scientists.

Which means that we should question our own security design work before making claims about its effectiveness.

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
???
This sentiment about checking our own design work seems to be popular in the security community too. This is Bruce Schneier, the author of many popular novels and textbooks in Cybersecurity. Here he warns us about the pitfalls of getting too attached to our own clever security solutions, that we fail to see reasons for not trusting it.
---
class: middle

## False assurance is a danger that is avoidable by only trusting technology that is demonstrably trustworthy.

.footnote[
Roger Schell
]
.top-right[
![Roger](http://www.ieee-security.org/TC/SP2010/photos/.xvpics/0054_IMG-thumb.jpg)
]
???
Rightfully so, Roger Schell, the founding director of National Computer Security Center, part of NSA's and responsible for all DoD security in the late 1980s and early 1990, said in one of his publications that false assurance is a danger that is avoidable by only trusting technology that is demonstrably trustworthy.

So how do we get started on "demonstrably trustworthy technology"?

---
# Systems Security Engineering

### .orange[Problem] Context
A sufficiently complete understanding of the problem
--

### .green[Solution] Context
Transforms the security requirements into design requirements for the system
--

### .red[Trustworthiness] Context
Evidence-based demonstration, through reasoning, that the system-of-interest is deemed trustworthy

???
We have some guidance in the systems security engineering framework to develop demonstrably trustworthy technology. If you recall, the Trustworthiness Context our engineering framework is setup to develop an evidence-based demonstration, through reasoning, that the system-of-interest is deemed trustworthy.

We looked at the problem context using requirements engineering techniques. Now we switch gears and talk about **assurance cases** as part of the trustworthiness context.

---

background-image: url(https://live.staticflickr.com/2834/8818803884_1306f9c8aa_b.jpg)
???
To understand concepts in the trustworthiness context, we will start with a simple intellectual exercise.

Our goal in the next five minutes is to find a black cat...
---
background-image: url(images/black.png)

???
in a dark room!

## Source:   
The cat example is adapted from the example provided in System Assurance: Beyond Detecting Vulnerabilities (The MK/OMG Press) 1st Edition, by Nikolai Mansourov  and Djenana Campara https://amzn.com/0123814146

---
class:middle
# Task at hand
Find a **black cat** in a **dark room**


--

Also, we are not sure that the cat is really there!

???
So the task seems simple...  
...but you see we are not sure that the cat is really there!

--

### .blue[
What are the Goals/Claims to be proven?
]
- Operational tasks may not focus on outcomes.
- Assurance is in context of a claim.

???
To approach any complex situation, it makes sense to first write down the outcomes that we are interested in demonstrating. This is the first assurance concept that I want you to become familiar with. To focus on outcomes, you may ask the question: What are the claims that need to proven given a complex situation? Once you know the claims, then you can think of ways to demonstrate the belief associate with the claim by collecting evidence from the complex situation, i.e. we plan how to argue about the claims.

---
class:middle
# Possible claims

### .red[Claim 1:] The room has at least one black cat
--

### .red[Claim 2:] The room has no black cats

???
So given the cat situation, here are potential claims of interest. First, The room has at least one black cat. Another claim could be, the room has no black cats. The first claim is about a tangible property of the room, i.e. something you can see, the second claim is about an intangible property of the room, i.e. something you cannot see but only experience, which in this case is lack of cats. People with varying levels of paranoia about cats may experience this property differently.

--
### .blue[
What is the basis for the belief in these claims?
]

???
Grammatically stated, the claims are proposition, i.e. they can be either true or false. But the degree to which we believe that the claim is true or the claim is false depends on the strength of the argument and available evidence to support the argument. So from an assurance perspective we are interested in knowing what is basis for the belief in these claims. Belief in a claim depends on how convincing and easy to understand is the presented argument and its supporting evidence.

Let's start to argue the first claim.

---
class: middle
# .red[Claim 1]
The room has at least one black cat

---
class: middle
# Basis for the Belief

## .blue[Kitty-Kitty-Kitty] Search Process*
1. Search team puts a bowl of milk in the room and says  
.green[_kitty-kitty-kitty_] three times
1. Four corners and center of room covered
1. Stop when a cat is discovered

.footnote[\* Patent Pending]

???
In order to demonstrate our belief in the claim, we figure out that we need a search process. The more structured the search process, more reliable are the results. Let's assume we have the ability to execute this very structured Kitty-Kitty-Kitty search process shown here. The search team puts a bowl of milk in the room and says .green[_kitty-kitty-kitty_] three times. You have to say it three times. The search covers the four corners and center of room. The search stops when a cat is discovered.


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

???

We think the Kitty-Kitty-Kitty search process is effective to demonstrate claim 1. So logically, we can state a new claim that if true can support claim 1. Continuing this reasoning, the search process can also lead us to evidence that can increase our belief in claim 1. In this case, the evidence is pictures of cats found by executing the search process. Take note that the evidence is stated as a noun phrase, i.e. it refers to tangible things which can be examined or measured about the situation.

Given claim C1, this argument is pretty convincing. But would it be convincing if we used this same argument for claim C2?

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

???
Claim C2 is the room has no black cats. A sub-claim could be the kitty-kitty-kitty search process discovers no cats and the evidence could be an empty findings report!

Now depending on the paranoia level of the reader of this argument, it is natural to start doubting the effectiveness of the search process.

---
class: middle
# Is this argument enough?
Can you ever be 100% sure for a large and complex room?  

???
In particular, if you are dealing with a large and complex room, the search process cannot provide 100% guarantee that there are no cats in the room.

---
class: middle
# .red[Assurance]
Basis for the belief in a claim


--

.green[Belief] increases when .red[doubts] are removed!   

???
So when complexity is involved, which is often the case, the basis for the belief in a claim increases when doubts are removed.

--

A good argument eliminates identified doubts

???
In other words, a good argument eliminates identified doubts!

Now this is a different way of argumentation than what we are used to. By default we are biased to using enumerative induction, i.e. we start to believe things that we see over and over or over a long period of time. But when it comes to demonstrably trustworthiness in claims about a complex situation that no one can fully comprehend, we have to rely on eliminative induction.

---

class: middle
# [Eliminative Induction](https://www.google.com/search?q=define+eliminative+induction)
A series of doubts are introduced for some state of affairs,  
and then progressively eliminated by new evidence

???
With eliminative induction, a series of doubts are introduced for some state of affairs and then progressively eliminated by new evidence.

---
# Eliminative Induction

## Step 1: Introduce doubts
Challenge the identified claims by introducing doubts
???
Here is a structured process to perform eliminative induction. Step 1: Introduce doubts. Here we challenge the claims about the complex situation by introducing doubts.

--

## Step 2: Eliminate doubts
For each doubt, identify sub-claims that eliminate the doubt
???
Next for each doubt identified in step 1, we identify sub-claims that eliminate or address the doubt.

--

## Step 3: Evaluate Argument
Can sub-claims be directly supported by evidence?  
Yes: Reasoning stops. Associate evidence with the sub-claim.  
No: Go to Step 1, repeat process for the sub-claim

???
With sub-claims developed, we ask ourselves: Can sub-claims be directly supported by observable and tangible evidence collected from the complex situation? If the yes, then describe that evidence and associate it with the sub-claim. The reasoning stops here. If the answer is no, then you go back to step 1 and identify more doubts for the sub-claim.

Let's examine with process with claim 2 in our cat related situation.  

---

class: middle
# Step 1: Introduce doubts
The room has .red[no] black cats
--

* .red[R1.1.1] _Unless_ the room is not locked  
* .red[R1.1.2] _Unless_ search process does not cover the entire room
* .red[R1.1.3] _Unless_ the people searching are not competent
* .red[R1.1.4] _Unless_ the baby panthers found are indeed cats

???
In step 1 we introduce a series of doubts for the claim that the room has no black cats. The doubts are expressed in a manner that the provokes the introduction of a doubt. They start with the word .red[**unless.**]. Here are some doubts that I came up with. Unless the room is not locked, unless the search process does not cover the entire room, unless the people searching are not competent, unless the paper panthers found are indeed cats. This last doubt captures a false negative situation.



---

class: middle
# Step 2: Eliminate doubts

.red[R1.1.1] _Unless_ the room is not locked   
* .green[C1.1.1] All room entrances are guarded  

???
Now in step 2, we eliminate the doubts by introducing new claims about the situation that will need to be true. For example, all room entrances are guarded claim eliminates the first doubt.
--

.red[R1.1.2] _Unless_ search process does not cover the entire room  
* .green[C1.1.2] Kitty-Kitty-Kitty search process covers the entire room

???
This next claim if true address the second doubt, so on and so forth.

---
class: middle
# Step 3: Evaluate --> STOP or Step 1: Introduce doubts

.green[C1.1.1] All room entrances are guarded  
* .red[R1.1.1.1] Unless the room vents allow cats to go in and out  

???
Now in step 3, we evaluate if the sub-claims be directly supported by observable and tangible evidence collected from the complex situation? In this case, rather than stop the argument with evidence, I decided to go back to step 1 and identify additional doubts for the sub-claims. For example, while the entrances are guarded, the room vents could allow cats to go in and out.  

--

.green[C1.1.2] Kitty-Kitty-Kitty search process covers the entire room  
* .red[R1.1.1.2] Unless there is an alternate food supply (mice)
???
For the second sub-claim, I also introduce a doubt that the cats could have an alternate food supply and hence not care about the milk placed by the kitty-kitty-kitty search process.

---
class: middle
# Step 2: Eliminate doubts

.red[R1.1.1.1] Unless the room vents allow cats to go in and out  
* .green[C1.1.1.1.1] All room vents have nets installed

--

.red[R1.1.1.2] Unless there is an alternate food supply (mice)
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
* .blue[E1.1.1.1.2 Search coverage report]
* .blue[E1.1.1.1.3 Entrance log]

.red[Unless] the cats have an alternate food supply (mice in the room)
* .green[C1.1.1.1.2] There are no mice in the room
* .blue[E1.1.1.1.4 Month old exterminator report for rodents]
* .blue[E1.1.1.1.5 Search process Activity Log]
* .blue[E1.1.1.1.6 Milk placement map]

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

## Equate Cats to .red[System Weaknesses]

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
Figure source: [Arguing Security - Creating Security Assurance Cases](https://www.us-cert.gov/bsi/articles/knowledge/assurance-cases/evidence-assurance-laying-foundation-credible-security-case)
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

### Avoid claims about the supporting method/techniques
- .red[Bad claim:] The system uses AES encryption
- Why? Because it is not interesting; Means to an end

--

### Claim should be a reasonable goal (outcome)
- .green[Good claim:] “The system is acceptably secure against communication lines related threats”

???

## Good claims
- These say something about expected **outcomes** we really wish for by using security technologies or by performing security-related activities
- Claims about expected outcomes can be argued extensively

- E.g. "AES encryption" (security technology) --> "secure against communication line related threats" (outcome we try wish for)
---
# Claims Matter!

## Claim properties are risk-related
- High confidence is needed in their realization

--

## Good Claim Checklist
- .blue[An entity] relevant to the argument
- .orange[A critical property of the entity]
- .green[A value for the property and related uncertainty]

--

## Example
- .blue[The system] .green[is acceptably] .orange[secure]
- .blue[The system] .green[has no] .orange[unacceptable consequences to assets from security threats]

---
class: middle
# [Grammatical Guidance](http://www.sei.cmu.edu/dependability/tools/assurancecase/)

## .blue[&lt;NOUN-PHRASE&gt;]
- .blue[Noun-Phrase] identifies the subject (“entity”) of the claim

## .orange[&lt;VERB-PHRASE&gt;]  
- .orange[Verb-Phrase] defines a predicate using the critical property of the subject along with its expected value and related uncertainty

## Consider [diagramming sentences](http://grammar.ccc.commnet.edu/grammar/diagrams2/one_pager1.htm)
- Avoid compound predicates

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
exclude: true
class: middle
# Scenario

## OPPD NE has received intelligence.
- Rouge nation states are targeting their software supply chains.
- There is a credible threat. Software bought by OPPD for business functions is being targeted for sabotage with malicious code.

--
exclude: true
## Top Level Claim
- .blue[OPPD NE supply chain processes] .green[minimize ] .orange[the possibility of sabotage by malicious code in software applications]

---
exclude: true
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
# Justification

## Provides .red[rationale] for the use/selection of a claim or strategy

## Example
- Intelligence reports of malicious code in nuclear energy software

---
exclude: true
class: middle
# Assumption

## A statement whose validity has to be relied upon in order to make an argument
- .red[Restricted context]
- .red[Exceptions] or situations the claim does not cover

## Example
- Nuclear energy safety mechanisms do not include software


---
class: middle
# Context Visual Notation

![context](images/context.svg)

.footnote[.red[Arrow head indicates the direction in which the assurance case must be read]]
---
class: middle
# Justification Visual Notation

![justification](images/justification.svg)

---
exclude: true
class: middle
# Strategy

## Provides direction for an argument

## Phrased with respect to the argument
- .green[Argument by appeal to] software acquisition practices

## A strategy is elaborated by providing a series of sub-claims
---
exclude: true
class: middle
# Strategy Visual Notation

![strategy](images/strategy.svg)

---

class: middle
# Argument

- Conveys why we believe the top-level claim has been met
- Develop and refine sub claims, until the sub-claims can be directly supported by evidence
- .red[Avoid drift in the entity of the sub-claim.] It should be related to the entity in the top-level claim or a related entity.
- Bridge the gap between top-level claim and evidence

--

## Stopping condition?
- The rigor is acceptable
- Resources are unavailable
- Further expenditure is not justified

---

## Sub-claim

Develop a sub-claim
#### .blue[Aquisition processeses] are a part .blue[Supply chain processes]
![argument](images/sub-claim1.svg)
.top-right[.red[
Note:] Different arrows mean different things!
]

---
class: middle
# Evidence

- Every branch must be terminated in evidence
- Something tangible and measurable

## Grammatical Guidance
- Must be a .blue[noun phrase] only (NO verb phrase)
- Should .red[not] be stated as a claim
- Describes an entity to be used as evidence

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
![Evidence](images/evidence-1.svg)

---
exclude: true
![arrow](images/arrows.svg)
.topnote[
What do the arrows mean?
]

---
class: center, middle
# Coming up with a good Argument is .large[Hard!]

--
### Do we have all relevant sub-claims?
### Is the evidence sufficient/robust?
### Is the argument strong?

---

# Eliminative Induction
## Support/assurance increases as reasons for doubt are eliminated

--

## Claim: .blue[The bulb] .green[will] .orange[glow when switched on]

--
- .red[Unless] switch not connected to light
- .red[Unless] no power
- .red[Unless] dead light bulb  

--
![light](images/lightexample.png)

.top-right[
\*Example source: [hit: `p`]
]

???
The content in next few slides is based on:
1. SEI Report: Toward a Theory of Assurance Case Confidence http://www.sei.cmu.edu/reports/12tr002.pdf
2. Charles B. Weinstock, John B. Goodenough, and Ari Z. Klein. 2013. Measuring assurance case confidence using Baconian probabilities. In Proceedings of the 1st International Workshop on Assurance Cases for Software-Intensive Systems (ASSURE '13). IEEE Press, Piscataway, NJ, USA, 7-11.
3. Explicit permission to use slides provided by John B. Goodenough

---
# Introducing Doubts*

## Making doubts explicit
### Attack claim (rebutting defeater) — why claim could be false
--

### Attack evidence (undermining defeater) — why evidence could be irrelevant
--

### .green[Attack inference] (undercutting defeater) — premise good; conclusion uncertain

---

# Example Claim

![claim](images/tweetyclaim.svg)

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

# Assurance Case Logical Structure
## Notice .green[inference rules]?
![structure](images/structure.png)

--

.footnote[.red[Inference rule have premises and conclusions. Premises are at the bottom in an assurance case.]]


---
# Undercutting defeater
Premise good; conclusion uncertain
![claim](images/undercut.svg)
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
# Software Security Controls
First to develop and apply assurance case based method for control refinement
- Software related controls derived from the NIST SP 800-53 control catalog
- These software assurance controls are enumerated in [NIST SP 800-160 Appendix-J](https://csrc.nist.gov/csrc/media/publications/sp/800-160/archive/2016-05-04/documents/sp800_160_second-draft.pdf)

#### Gandhi, R., Siy, H., Crosby, K., Mandal, S. (Graduate), (2014). Gauging the Impact of FISMA on Software Security, IEEE Computer, vol. 47 (9)
#### Gandhi, R. A., Crosby, K., Siy, H., Mandal, S. (2016) Driving Secure Software Initiatives Using FISMA: Issues and Opportunities. CrossTalk, Journal of Defense Software Engineering, Jan/Feb 2016 Issue.

---
class: middle
# Security Controls
[NIST SP 800-53 Rev. 5](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/draft)

### Makes the security and privacy controls outcome-based
- Focuses on the security and privacy capabilities
- Controls are now .orange[critical properties] of interest
- Control statements are Verb phrases which can be associated with any system entity

???
(i.e., what needs to be done to protect the system or information and not which entity carries out the action or where it is carried out);

---
class: middle
# Security Controls
[Changes from Rev.4 to Rev. 5](https://csrc.nist.gov/CSRC/media/Publications/sp/800-53/rev-5/draft/documents/sp800-53r5-draft-fpd-summary-of-significant-changes.pdf)

IA-2 IDENTIFICATION AND AUTHENTICATION
### Current (Rev 4):
- Control: The information system uniquely identifies and authenticates organizational users.

### Proposed (Rev 5):
- Control: Uniquely identify and authenticate organizational users and associate that unique identification with processes acting on behalf of those users.

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
class: middle
# Other Applications

### Medical Device Software
- [Safety Assurance Cases Can Improve Your FDA Submissions](https://www.meddeviceonline.com/doc/how-safety-assurance-cases-can-improve-your-fda-submissions-0001)

---
class: center, middle
# .large[Got Assurance?]
.bottom-left[
![meme](http://s2.quickmeme.com/img/31/315640bead03adc498079b11707081fbfcfc0d4d97b1e1d69ba1d930dfa286d6.jpg)
]

???

# Good Examples

## .blue[Canvas] .green[has no] .orange[exploitable XSS weaknesses]

## .green[All] .blue[Canvas XSS weaknesses] .green[have been sufficiently] .orange[mitigated]

## .blue[Canvas] .orange[attack surface] .green[is minimized]
