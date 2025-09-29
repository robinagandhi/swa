class: center, middle
# Assurance Case*
.footnote[
\* See notes for sources, hit `p`
]
???

This discussion is about a new topic that many in cybersecurity may not have experience with or even thought about. I will introduce a new analytical and modeling technique to plan the evidence that needs to be collected throughout the software lifecycle to support security claims. The goal is to build an argument, similar to a legal case. Instead of defending a person or an organization, our job is to defend the claims we seek to make about the system-of-interest security properties.


This slide deck is based several sources as follows:

- Goal Structuring Notation  
- [ISO/IEC/IEEE 15026-2:2022 ](https://www.iso.org/standard/80625.html) Systems and software engineering — Systems and software assurance — Part 2: Assurance case
- Research papers on Eliminative Induction use in Assurance Cases
- [SEI publications on Assurance case use in Safety Cases](https://insights.sei.cmu.edu/sei_blog/2013/08/assurance-cases-and-confidence.html)  
- [System Assurance: beyond Detecting Vulnerabilities, By Mansourov, Nikolai, and Djenana Campara](https://www.safaribooksonline.com/library/view/system-assurance/9780123814142) (Chapter 2)

---
class: middle

![Dilbert Trust and stupidity](https://assets.amuniversal.com/c8253cc0db9a012e2fae00163e41dd5b)

???
As usual, a bit of humor to kick-off the discussion. Trustworthiness, if evaluated properly, is asserted based on an investigative process. For example, clearing an individual for access to national security-related projects involves collecting a lot of background information and interviewing close relative and business associates. The investigation produces lots of evidence, which is then used by an authority to make a trust decision.

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
Roger Schell, is the founding director of National Computer Security Center, which later became part of NSA and responsible for all DoD security in the late 1980s and early 1990. He rightfully said in one of his publications that false assurance is a danger that is avoidable by only trusting technology that is demonstrably trustworthy.

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
The cat example is adapted from the example provided in [System Assurance: beyond Detecting Vulnerabilities, By Mansourov, Nikolai, and Djenana Campara](https://www.safaribooksonline.com/library/view/system-assurance/9780123814142) (Chapter 2)

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
To approach any complex situation, it makes sense to first write down the outcomes that we are interested in demonstrating. This is the first assurance concept that I want you to become familiar with. To focus on outcomes, you may ask the question: What are the claims that need to proven given a complex situation? Once you know the claims, then you can think of ways to demonstrate the belief associated with the claim by collecting evidence from the complex situation, i.e. we plan how to argue about the claims.

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
In step 1 we introduce a series of doubts for the claim that the room has no black cats. The doubts are expressed in a manner that the provokes the introduction of a doubt. They start with the word unless. Here are some doubts that I came up with. Unless the room is not locked, unless the search process does not cover the entire room, unless the people searching are not competent, unless the baby panthers found are indeed cats. This last doubt captures a false negative situation.



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

???
Following a similar process as before, we eliminate the doubts by introducing new claims about the situation that will need to be true.  

--

.red[R1.1.1.2] Unless there is an alternate food supply (mice)
* .green[C1.1.1.1.2] There are no mice in the room

???
At this point, I am pretty convinced that I can collect directly observable and tangible evidence to support these sub-claims without any further argumentation.

---
class: middle
# Stopping condition?

## Evidence
When the argument is convincing enough to the reader, it should end in the presentation of .blue[_facts_] that support the .green[_claims_]

???
So when you think the argument will be convincing enough to the reader, it should end in the presentation of .blue[_facts_] that support the .green[_claims_]. So depending on your audience and the level of assurance needed, you will have to decide where you stop the argument and present the facts or evidence.

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

???
So what does evidence look like in the cat situation? It a collection of facts available at the end of a branch of argumentation, should be relevant and sufficient to address all claims in that branch. Fact is a piece of information generally known to be true, an objective measurement or a measurement or observation made by a qualified expert.

So here we see that the last sub-claim in an argumentation branch is associated with several pieces of evidence. The Vent inspect report, search coverage report and the entrance log. Collectively these facts support the argument made earlier.

Similarly, for the other branch we can see that evidence strengthens the argument about cat food supply. Note that without the argument, the evidence of rodent extermination report may be seen as very irrelevant.


---
class: middle
# Argument and Evidence
* Without argument, evidence is irrelevant.
* Without evidence the argument is not substantiated.

???
So we realize now that Argument and Evidence both are necessary to increase our belief in claims about a complex situation that no one person or entity fully understands.

So without argument, evidence is irrelevant and without evidence the argument is not substantiated.

---

class: middle
# Basis for the Belief

As more reasons for doubt are eliminated, assurance in the top-level claim increases  

If many doubts remain, assurance is diminished

???
With claim 2 example, we see how eliminative induction works quantitatively. As more reasons for doubt are eliminated, assurance in the top-level claim increases. If many doubts remain, assurance is diminished

--

A rigorous argumentation structure assists .red[*trust decisions*] for the presented claims

???
With a structured and rigorous argumentation, we can make informed trust decisions about the dark room having no black cats.

---

class: middle
# .red[Claim 3]
The room will have .red[no] black cats for the .red[next 12 months]

???
But wait! what about forward looking claims? What about a claim about risk? i.e. A claim not about the current state of affairs but about avoiding a future undesired event?

In the cat situation we could be interested in the following claim. The room will have .red[no] black cats for the .red[next 12 months]

--

Does it make sense to justify this claim by a single search at a moment in time?

???
Does it make sense to justify this claim by a single search at a moment in time?

---
class: middle
# Risk: A future, adverse event

We can introduce even more doubts!
* .red[R1.1.5] Unless the cats hibernate when search is conducted  
* .red[R1.1.6] Unless cat zapper vents are working intermittently
* .red[R1.1.7] Unless the vents are not being inspected periodically
* .red[R1.1.8] Unless the exterminator skips visits

???
Now we can introduce even more doubts compared to claim 2.

--

To eliminate these doubts, .green[continuous] efforts are required.

???
You will also notice that in order to eliminate these doubts, continuous efforts are required to be demonstrated.

---
# A very catty summary

## Equate Cats to .red[System Weaknesses]

### Claim 1 (Point Solution)  
* Produces knowledge about what you found  

.top-right[
![catfunny](http://vignette2.wikia.nocookie.net/animal-jam-clans-1/images/6/6b/Funny-Cat-Meme-Work-16.jpg/revision/latest?cb=20160716231247)
]

???
Now what is the point of this example? The room and the cat are just placeholders. Let's replace "room" with "software", and "cats" with "weaknesses" in Claim 1. Most software is complex enough to be a dark room. So the claim becomes: The software has at least one weakness. This claim seems quite trivial and most bug discovery processes should be effective at proving it correct. But this is just a point solution. It produces knowledge about the weakness you just found. It says nothing about the rest of the software. Unfortunately, most efforts of finding bugs in software are doing just this!

--

### Claim 2 (Snapshot)  
* Produces knowledge about the whole system

.top-right[
![catfunny](http://i0.kym-cdn.com/entries/icons/original/000/002/232/bullet_cat.jpg)
]

???
Claim 2 becomes: The software has no weaknesses. Now this claim produces useful knowledge about software, at a certain point in time. This is often called a snapshot. Engineering know-how is required to provide assurance in the design work. This claim takes a lot of effort during the software development lifecycle to make a convincing argument and collect supporting evidence.

--

### Claim 3 (Continuous Assurance)  
* Produces knowledge about minimizing  
a future undesirable event

.top-right[
![catfunny](http://i0.kym-cdn.com/photos/images/newsfeed/000/115/642/non-stop-nyan-cat.jpg?1303327212)
]

???
Finally claim 3 becomes: The software will have no weaknesses for the next 12 months. Now this claim is what most customers, businesses and organizations are interested in, but they don't know how to asking for such assurance. A corresponding argument and supporting evidence produces knowledge about minimizing a future undesirable event, i.e. Risk. Of course, this will require continuous security engineering efforts.

In the next video we will talk about a standard notation to represent and reason about assurance cases for systems security engineering.

---
class: center, middle
# Developing Assurance Cases

???
In the last video we motivated the need for structured argumentation. Now we will jump right into a standard notation to develop assurance cases.

---
# Assurance Case Logical Structure
![structure](images/structure.png)
.footnote[
Figure source: [Arguing Security - Creating Security Assurance Cases](https://www.us-cert.gov/bsi/articles/knowledge/assurance-cases/evidence-assurance-laying-foundation-credible-security-case)
]

???
Here is what an assurance case can look like. Let's look at some of the major components. First we have a top-level claim. The claim is regarding a critical property of a system or product. Next, multiple levels of subordinate claims connect the top-level claim to the evidence. This evidence is the explicit information that underlies the argumentation.

Interpretation of the tree structure is based on a series of if-then statements. These are called inference rules. Inference rules have a premise and a conclusion. If the premise is true then the conclusion must be true. Since assurance cases are based on induction, the rules are read bottom up rather than top-down, i.e. the premise is below the conclusion is the tree structure. For example, if the premise is "Evidence A" then the conclusion is "Sub-Claim 1". Similarly, if the premise is "Evidence B" then conclusion is "Sub-claim 2". As we continue this reasoning, if "Sub-claim 1" and "Sub-claim 2", then "Top-level claim". Ultimately, the logical argument connects the evidence to the top-level claim.

---

# [ISO/IEC/IEEE 15026-2:2022 ](https://www.iso.org/standard/80625.html)
![iso](images/iso-standard.png)

???
Assurance Cases are not just an intellectual exercise. Actually, they are specified in a companion international standard to the software and systems engineering, upon which the NIST SP 800-160 Systems Security Engineering publication is built. So this is all very relevant to the systems security engineering perspective that we have been considering from the very beginning of the class.

This standard is available from the UNO library and is made available in Canvas as an additional reference.

---

class: middle
# Convince a bystander

### _While an assurance case is useful for decision-making by knowledgeable stakeholders (e.g., developers and service providers), often the primary motivation for an assurance case is to support crucial decisions by stakeholders without this background, such as those involved in certification, regulation, acquisition, or audit of the system._

.footnote[
[ISO/IEC/IEEE 15026-2:2022 ](https://www.iso.org/standard/80625.html)
]

???
Per this standard, while an assurance case is useful for decision-making by knowledgeable stakeholders (e.g., developers and service providers),   

often the primary motivation for an assurance case is to support crucial decisions by stakeholders without this background, such as those involved in certification, regulation, acquisition, or audit of the system.

So here we see that an assurance case is positioned as an aid to make trust decisions. Consequently, the way we author claims in an assurance case matters a lot to the stakeholders that are going to base their crucial decisions on it! In fact, 90% or more of an assurance case is just claims! So, let's learn how to author claims.

---
# Claims Matter!
### Claims concern critical properties

???
Always remember that assurance is only needed when we don't fully understand the entity that we are analyzing. So coming up with top-level claims about trivial things is just plain useless. Top-level claims have to be about critical properties about non-trivial system artifacts. In the context of this course, they also have to be relevant to security.

--

### A claim is always worded with a predicate
- It can be labeled as a true or false statement

???
Next, grammatically, a claim should be worded with a predicate, i.e. there is a clear subject or noun phrase followed by a particular descriptive property about the subject. With this sentence structure, we can label the sentence as true of false upon investigation.

--

### Avoid claims about the supporting method/techniques
- .red[Bad claim:] The system uses AES encryption
- Why? Because it is not interesting; Means to an end

???
We know that claims have be about critical and important system properties. So these properties cannot be trivial things that can  be determined to be true or false based on just a simple examination of the system. For example, The system uses AES encryption. This is a well-formed claim. It has a subject, "the system" and a predicate "uses AES encryption". However, the predicate can be determined to be true or false based on a simple examination of the system. As a result, such claims are not worth arguing. So how can we make it something worth arguing?

--

### Claim should be a reasonable goal (outcome)
- .green[Good claim:] “The system minimizes information disclosure during communication”

???

Claims that are worth arguing, are about the expected outcomes that we really wish for by using security technologies or by performing security-related activities.
These claims can be argued extensively. For example, "AES encryption" security technology is only relevant because we want to "minimizes information disclosure during communication". So the claim "The system minimizes information disclosure during communication" now can lead to a much richer argument beyond just an encryption feature, such as sub-claims related to the encryption feature being implemented correctly, or the keys being managed properly, or the selection of algorithms that matches perceived threat capabilities.

---
# Claims Matter!

## Claim properties are risk-related
- High confidence is needed in their realization

???
Another aspect about good claims is that they need to be risk related. Depending on how important it is to address the risk, appropriate strength is needed in the corresponding argument. With risk comes also comes uncertainty. We can never reduce risk to zero. There is always residual risk. Residual risk leads to uncertainty. A good claim acknowledges this uncertainty. For example on the previous slide we used the word "minimize" instead of "eliminate". We know that communication threats can never be totally eliminated. But we can certainly take steps to minimize them to an acceptable level.

--

## Good Claim Checklist
- .blue[An entity] relevant to the argument
- .orange[A critical property of the entity]
- .green[A value for the property and related uncertainty]

???
So here is a full good claim checklist. First, we need a subject in the claim. This is an entity-of-interest which we want to be demonstrably trustworthy. Second, we need a critical property of the entity-of-interest that is non-trivial and worth arguing. Typically this is related to the important outcomes that system stakeholders are interested in. The last part provides a value expected for the property and related uncertainty. For example, in the claim the room has no black cats. Black cats is the property of the room. The room is the entity-of-interest. The value of the black cat property that we are interested in demonstrating is zero, with no uncertainty. When we use the word minimize, then we suggest that the value needs to be as low as acceptable to the stakeholders. Minimize is appropriate for qualitative risk assessments, whereas concrete values are appropriate when we are dealing with situations where quantitative risk measures are being used.

--

## Examples
- .blue[The system] .green[is acceptably] .orange[secure]
- .blue[The login page] .green[has no] .orange[exploitable SQL injection weakness]

???
Here are examples of claims with qualitative and quantitative values and related uncertainty, associated with a critical property.

---
class: middle
# [Grammatical Guidance](http://www.sei.cmu.edu/dependability/tools/assurancecase/)

## .blue[&lt;NOUN-PHRASE&gt;]
- .blue[Noun-Phrase] identifies the subject (“entity”) of the claim

## .orange[&lt;VERB-PHRASE&gt;]  
- .orange[Verb-Phrase] defines a predicate using the critical property of the subject along with its expected value and related uncertainty

## Consider [diagramming sentences](https://www.grammarly.com/blog/sentence-diagramming/)
- Avoid compound predicates

???
It is best for a claim to start with a noun phrase followed by a verb-phrase. The noun phrase identifies the subject, and the verb phrase associates a value with a critical property about the subject.

In the verb phrase, avoid compound statements. For example writing claims such as the room has no black cats and brown cats is not recommended. This claim conceals logical structure within the its specification rather than making it explicit in the argument.

---
class: middle
# [Grammatical Guidance](http://www.sei.cmu.edu/dependability/tools/assurancecase/)

## Bad Examples
- Just describes an entity: ~~.red[XSS results for Canvas]~~
- Describes an action on entity: ~~.red[Perform XSS on Canvas]~~
- A question: ~~.red[How many XSS weaknesses does Canvas have?]~~
- Fact, no argument needed: .red[~~Canvas uses AES encryption~~]

???
Now that we know how to write good claims, we can also look at some poor claim constructions that should be avoided. The first bad example is "XSS results for Canvas". This claim has a noun-phrase but no verb phrase. It is just describing an entity. The second claim is a bad example as it is describing an action to be taken, and not a system property. The third claim is a question. Finally, the last claim can be examined by direct observation and no argument is needed. So it is not appropriate as a top-level claim. Although, it may be OK if it appears towards the end of an argument, and is directly supported with evidence.

---
class: middle
# .red[Actual] bad examples

## .red[C5: Security Professionals test code for XSS vulnerabilities]

--

## .red[C18: The System uses a Static Analysis tool]

???
Here are some actual bad examples of claims that students in this class authored, when they were just starting to learn about assurance cases. Please pause the video here and try to re-phrase them such that they can meet all the necessary qualities of a good claim.


Optional exercise:  
> Work with your team or individually to rephrase these appropriately.
When you are done enter your answers in this [Online Word Doc](https://uofnebraska-my.sharepoint.com/:w:/g/personal/20882301_nebraska_edu/EaHTB-WXStJKph9m1n-6o9gBibyQV9tERHHvve2A3uUcbA?e=vkOhq6).

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

## .green[Additional information] that is excluded from the claim
- Context (understanding)
- Justification (rationale)

???
Now that we know how to draw and write a claim, let's see some ways in which we can add more information to it. The first is a context element and then we look at the justification element.

---
class: middle
# Context

## Information necessary for a claim to be understood or amplified
- Includes a statement that defines the .red[scope] of the claim
- Provides means to check .red[satisfaction] of the claim
- External references or Definitions

???
The context element is used to provide information necessary for a claim to be understood. There are no restriction on its wording, but generally it includes statements that help to understand the scope of a claim, or its satisfaction using external references and definitions.

---
class: middle
# Context Visual Notation

![context](images/context.svg)

.footnote[.red[Arrow head indicates the direction in which the assurance case must be read]]

???

In this example, the claim that OPPD Nebraska supply chain processes minimize the possibility of sabotage by malicious code in software applications. is elaborated using the Context that the supply chain process referred to in the claim is enhanced with security considerations per the NIST SP 800-160 document.

Note the arrow starts from the claim, which is to read first, and then points towards the context, which is to be read after the claim.

---
class: middle
# Justification

## Provide .red[rationale] for a claim

???
A justification element is used to express rationale as to why a claim was developed. So in the previous claim it was not clear why we wanted to look at supply clain processes. So let's fix that by adding a justification element.

---
class: middle
# Justification Visual Notation

![justification](images/justification.svg)

???
Now we realize that the claim is necessary due to _Intelligence reports of malicious code in nuclear energy software_

---

class: middle
# Argument

- Conveys why we believe the top-level claim has been met
- Develop and refine sub claims, until the sub-claims can be directly supported by evidence
- .red[Avoid drift in the entity of the sub-claim.] It should be related to the entity in the top-level claim or a related entity.
- Bridge the gap between top-level claim and evidence

???
Now that we understand the top-level claim, the next comes the argument. These are refinements of the top-level claim using sub-claims.

To maintain the flow of the argument, care should be taken to avoid drift in the entity used by the sub-claim and that of the top-level claim.

Remember that the purpose of the argument is to bridge the gap between the claim and the evidence.

---

## Sub-claim

Develop a sub-claim
#### .blue[Aquisition processeses] are a part .blue[Supply chain processes]
![argument](images/sub-claim1.svg)
.top-right[.red[
Note:] Different arrows mean different things!
]

???
In our previous example, you can see that I have a specific sub-claim related to acquisition practices that are generally part of a supply chain process. Note that the shape used to represent a sub-claim is the same as a claim. However, the sub-claim is connected to the top-level claim with an arrow. Note that the arrows coming out of the top-claim mean different things, based on what they are connected to.

---
class: middle
# Evidence

- Every branch must be terminated in evidence
- Something tangible and measurable

## Grammatical Guidance
- Must be a .blue[noun phrase] only (NO verb phrase)
- Should .red[not] be stated as a claim
- Describes an entity to be used as evidence

???
Now, every branch of an argument must end in evidence. Evidence is something directly observable. So it has to be tangible and measure-able.

Evidence is different from claims and sub-claims. So care must be taken not to phrase Evidence as a claim. To avoid this issue, the evidence must always be a noun phrase that describes an entity.


---
class: middle
# Evidence

## Examples
- .red[E1:] Test results from penetration tools
- .red[E2:] Warnings from static analysis tool
- .red[E3:] Hardware design review results
- .red[E4:] Parameter validation assurance case
- .red[E5:] Reports for assessing compiler settings with security implications

???
Here are several examples of Evidence.

.red[E1:] Test results from penetration tools  
.red[E2:] Warnings from static analysis tool  
.red[E3:] Hardware design review results  
.red[E4:] Parameter validation assurance case  
.red[E5:] Reports for assessing compiler settings with security implications  

In each case we are describing an entity using a noun-phrase.

---

class: middle
![Evidence](images/evidence-1.svg)

???
For our running example, let's make the argument really simple and terminate the it with Evidence. The evidence is a Report on software weakness trends in acquired software.

Now on thing you will notice right away using this visual notation is that the argument is not very convincing. It lacks breadth and depth. For example, a multi-legged argument would be more convincing than a single-legged one.

You are also probably thinking that coming up with an argument is hard. And it is. In the next video we will see how to systematically come up with a good argument.

---
class: center, middle
# Coming up with a good Argument is .large[Hard!]

???
Now that we understand all the elements of an assurance case, the task that remains is to actually come up with a good argument! We also want to avoid subjectivity and at the same time improve repeatability in the argumentation process. In short, to do this well, we need some guidance for the following questions:

> Do we have all relevant sub-claims identified?  (Missing Claims?)
> Is the evidence sufficient/robust?  (holes in the evidence?)
> Is the argument strong/logical?  (conclusion follows from the premise? Do the sub-claims mean the higher level claim?)

--
### Do we have all relevant sub-claims identified?
### Is the evidence sufficient/robust?
### Is the argument strong/logical?

???
While there is no closed answer to these questions, what we do know is that we want to increase  assurance in the claims being made...

---

# Eliminative Induction
## Support/assurance increases as reasons for doubt are eliminated

???
... and we know, from the cat example, that assurance increases as reasons for doubt are eliminated.

--

## Claim: .blue[The bulb] .green[will] .orange[glow when switched on]

???
Let's take and example to discuss this. If I want to increase assurance in the following claim The bulb will glow when switched on, then I have two options. First, I could just turn the switch on and see if the bulb turn on. I could also repeat this operation several times. This is external observation and the process is called enumerative induction.

Note that process tells us nothing about the quality of the setup.

The second option, is eliminative induction, which works by introducing doubts. So we now have to think what can go wrong that would prevent the bulb from glowing when switched on. So I start to identify doubts. We start statements which identify doubts using _unless_.

--
- .red[Unless] switch not connected to light
- .red[Unless] no power
- .red[Unless] dead light bulb  

???
Here are some doubts for this claim.

--
![light](images/lightexample.png)

.top-right[
\*Example source: [hit: `p`]
]

???
Now if we go ahead remove these doubts by proper investigation and produce evidence, my assurance in the claim increases. In fact this argument is much stronger than making a few external observations.

The content in next few slides is based on:
> SEI Report: Toward a Theory of Assurance Case Confidence https://www.sei.cmu.edu/library/toward-a-theory-of-assurance-case-confidence/     
> Charles B. Weinstock, John B. Goodenough, and Ari Z. Klein. 2013. Measuring assurance case confidence using Baconian probabilities. In Proceedings of the 1st International Workshop on Assurance Cases for Software-Intensive Systems (ASSURE '13). IEEE Press, Piscataway, NJ, USA, 7-11.  
> Explicit permission to use slides provided by John B. Goodenough

---
# Introducing Doubts*

## Making doubts explicit
### Attack claim (rebutting defeater) — why claim could be false

???
Turns out by making doubts explicit we can come up a pretty good argument. First, to make sure that we don't have any missing sub-claims, we attack a claim by introducing defeaters. We call them defeaters as their purpose is to defeat a claim. Specifically, we called them rebutting defeaters, as in a rebuttal to a claim. These defeaters identify why a claim could be false.


--

### Attack evidence (undermining defeater) — why evidence could be irrelevant
???
Similarly, we can attack the evidence, by introducing an undermining defeater. These introduce doubt in the evidence. They identify why the evidence could be irrelevant or in some cases insufficient for the argument that it terminates.

--

### .green[Attack inference] (undercutting defeater) — premise good; conclusion uncertain
???
Finally, we can also attack the logic of the argument using an undercutting defeater. At every level of refinement in the assurance case, the assumption is that if all sub-claims then the higher claim. This is an implicit inference rule, that can be made explicit and then attacked using the undermining defeater.

Let's examine all of these defeaters and see how they lead to a strong argument.

---

# Example Claim

![claim](images/tweetyclaim.svg)

???
So we have a top level claim C1 that Tweety can fly. Tweety is the subject, fly is the property and the value is it "can" fly without any uncertainty. From the context CT1 we also know that tweety is an animal.

---

# Rebutting defeater
## Why claim could be false
![claim](images/rebutting.svg)

???
Now using rebutting defeaters, we can introduce doubts in this claim. Here we have R1 which introduces a doubt: Unless Tweety is not a bird.

---
# Address Rebutting defeater
![claim](images/rebuttclaim.svg)

???
To address defeater R1, we introduce the sub-claim C2 which says that Tweety is a winged bird. Continuing the argument, we can also attack sub-claim C2 with two additional defeaters R2 and R3. R2 says Unless Tweety is handicaped and R3 says Unless Tweety is a Penguin. Both are good defeaters for the argument at this point. We address R2 with sub-claim C3: Tweety is physically able, and R3 is addressed by sub-Claim C4, which is Tweety is a member of the flying bird species. So it is not a penguin.  

---
# Undermining defeater
## Why could evidence be irrelevant or insufficient?
![claim](images/undermine.svg)

???
Now, C3 and C4 sub-claims are specific enough to support them with directly observable evidence.  Here we have three pieces of evidence. E1 and E2 are relevant for sub-claim C3, and E3 is appropriate for C4. E1 is a physical test report, E2 documents sightings of Tweety flying, and E3 is Tweety's DNA test results.

At this point in the argument, you can explicitly choose to introduce doubts in your evidence. Why could it be irrelevant or insufficient?
---
# Undermining defeater
![claim](images/undermine-done.svg)

???
For example, we can undermine evidence E3 with a defeater: Unless the DNA test was contaminated. The contamination can happen if the lab does not handle the samples properly. So we address this with a sub-claim C5: The DNA sample has no cross-contamination. Eventually, we support this claim using the evidence E4, which is Lab Procedures document.

Notice that in this diagram we explicitly show that argumentation in each branch is using a grey filled circle.


---

# Assurance Case Logical Structure
## Notice .green[inference rules]?
![structure](images/structure.png)

???
Let's move on to the final type of defeaters, the undercutting defeater. To deploy an undercutting defeater, we first need to locate an inference rule. But they are left implicit in the assurance case logical structure. So the first step is to make them explicit.

--

.footnote[.red[Inference rule have premises and conclusions. Premises are at the bottom in an assurance case.]]

???
Now, remember that inference rules have premises and conclusions. Premises are at the bottom in an assurance case. If the premise is sub-claims 1 and 2, then the conclusion is the top-level claim. Similarly, if the premise is Evidence C, then the conclusion is Sub-claim 4. So on and so forth. So let's make this inference rule explicit. I will illustrate that using our Tweety example.

---
# Undercutting defeater
Premise good; conclusion uncertain
![claim](images/undercut.svg)

???
In this diagram the inference rule IR1 is made explicit. The premise of the inference rule is Sub-claim C2, which is tweety is a winged bird, and the conclusion is the top claim C1 which is tweety can fly. So IR1 states that If tweety is a bird then it can fly. By making it explicit, we can now attack it using the Undercutting defeater UC1. The doubt we introduce is that Unless Tweety is a juvenile bird. It is a baby bird that cannot fly. To address this defeater, we introduce a sub-claim C6, which states that Tweety is an adult.

---
# Few more notations
## Claim to be further developed
![developclaim](images/developclaim.svg)

???
In the last diagram you saw a diamond shape underneath claim c6. This shape indicates that the argument is incomplete and needs to be further developed.

---
# Few more notations
## No further argumentation
![stop](images/stopargument-1.svg)

???
Note that the filled diamond is different than the filled grey circle. The grey circle indicates that no further argumentation is needed.

---
![preview](images/preview.svg)

???
Here is the entire assurance case for the top level-claim tweety can fly. I think you would agree if I said that it is pretty convincing given supporting evidence is available.


Source: This example is partially based on the presentation of this paper given at ICSE conference: J. B. Goodenough, C. B. Weinstock and A. Z. Klein, "Eliminative induction: A basis for arguing system confidence," 2013 35th International Conference on Software Engineering (ICSE), San Francisco, CA, 2013, pp. 1161-1164.

---
# Compare and Contrast
![preview](images/preview-cat.svg)

???
Now compare and contrast this structure to the very first claim in the cat example, which is The room has at least one black cat. This structure is not as deep or broad as the tweety example. So even visually, a richer argument is immediately apparent from the overall structure of an assurance case.



---

class: middle
# Measuring Confidence

## Baconinan Probability
- 0|n (no confidence) — no doubts eliminated
- 2|3 (partial confidence) — residual doubt
- n|n (complete confidence) — no doubts remain

???
Assurance cases can also produce certain quantitative metrics about the amount of assurance available. Let's see how.  Assurance cases use defeasible logic, which means that the truth value of the statements made in this logic can be revised with the introduction of new information.

So as more evidence becomes available, we can retract the conclusions made. So, it makes sense to use the number of doubts removed, as a metric to provide a quantitative measure of the level of assurance in a claim.

Assurance cases built using defeaters, use a Baconian probability computed as the ratio of the number of doubts removed and the total number of doubts. This ratio gives stakeholders a spectrum to choose from. It ranges from no doubts removed to all doubts removed, depending on the availability of resources and the possibility of collecting evidence.  

--

## Use for relative improvements, not comparison

???
Since the Baconian probability is based counts, it does not account for the doubt's quality or importance. So this metric should only be used for relative improvement in the assurance of a claim, rather than comparing two different claims.


---

class: middle
# Assurance Cases in Practice

## CC Evaluations and Software Assurance
- Argue how protection profile needs are satisfied by a Security Target
- Assurance cases are recommended for the highest levels of Evaluation Assurance Levels (EAL)

???
You are probably wondering why have you not seen many assurance cases? Turns out, Assurance cases have found many uses in high assurance software projects. For example, Common Critiera (CC) recommends using them to argue how requirements in a protection profile are satisfied by the security target. Common Criteria (CC) requires them for Evaluation Assurance Levels (EAL) 6 and above. So, unfortunately they have not been put in to wide use at lower levels of assurance.

---

class: middle
_In pursuit of Trusted Computer System Evaluation Criteria (TCSEC) or CC evaluations or Federal Information Processing Standard (FIPS) 140-1 or 140-2 certifications for their security-enforcing IT products, vendors are required not only to submit assurance claims for those products to the independent evaluation or certification facility but to .red[provide complete assurance cases] that provide a sufficient basis for the facility to verify those assurance claims.*_

.footnote[
\* [Software Security Assurance State-of-the-Art Report (SOAR)](https://cwe.mitre.org/documents/iatac_swa_soar.pdf), 2007, DoD Information Assurance Technology Analysis Center (IATAC) Data and Analysis Center for Software (DACS)
]
???
They are also selectively used in certain certification processes. Vendors of security products undergoing Federal Information Processing Standards FIPS 140-1 and 140-2 certification for cryptography need to submit assurance claims and even complete assurance cases in some projects to independent evaluators.

---
class: middle
# Software Security Controls
First to develop and apply assurance case based method for control refinement
- Software related controls derived from the NIST SP 800-53 control catalog
- These software assurance controls are enumerated in [NIST SP 800-160 Appendix-J](https://csrc.nist.gov/csrc/media/publications/sp/800-160/archive/2016-05-04/documents/sp800_160_second-draft.pdf)

#### Gandhi, R., Siy, H., Crosby, K., Mandal, S. (Graduate), (2014). Gauging the Impact of FISMA on Software Security, IEEE Computer, vol. 47 (9)
#### Gandhi, R. A., Crosby, K., Siy, H., Mandal, S. (2016) Driving Secure Software Initiatives Using FISMA: Issues and Opportunities. CrossTalk, Journal of Defense Software Engineering, Jan/Feb 2016 Issue.

???
In my research, we applied assurance cases to derive software security-related requirements from system level regulations. This novel method resulted in the first-ever subset of controls identified specifically for software assurance. Not only that, this work informed the update of the NIST SP 800-53 FISMA control catalog in its fifth version. As a result of this work, NIST acknowledged my team's contributions in both the NIST SP 800-53 rev. 5, and NIST SP 800-160 Systems security engineering documents. You can find our names in the acknowledgment section.

---
class: middle
# Security Controls
[NIST SP 800-53 Rev. 5](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/draft)

### Makes the security and privacy controls outcome-based
- Focuses on the security and privacy capabilities
- Controls are now .orange[critical properties] of interest
- Control statements are Verb phrases which can be associated with any system entity

???
In the NIST control catalog version 5, the controls statements are now outcome based. Which means that they are critical properties of interest which can be associated with entities at the system or software level.

---
class: middle
# Security Controls
[Changes from Rev.4 to Rev. 5](https://csrc.nist.gov/CSRC/media/Publications/sp/800-53/rev-5/draft/documents/sp800-53r5-draft-fpd-summary-of-significant-changes.pdf)

IA-2 IDENTIFICATION AND AUTHENTICATION
### Current (Rev 4):
- Control: The information system uniquely identifies and authenticates organizational users.

### Proposed (Rev 5):
- Control: Uniquely identify and authenticate organizational users and associate that unique identification with processes acting on behalf of those users.

???
In this example you can see how the control specification changed from version 4 to version 5. In version 4, the control was limited to just information systems. In version 5, the control statement is just a verb phrase that can be associated with any appropriate entity including software.

---
class: middle
# Other Applications

### Forensics
- Jones, C. (2014). __Evaluating the use of assurance cases for digital forensics.__ Dissertations & Theses @ University of Nebraska - Omaha; ProQuest https://search.proquest.com/docview/1528534691?accountid=14692

???
I also advised a Masters thesis that looked at the effectiveness of assurance cases in organizing evidence from a digital forensics investigation.

---
class: middle
# Other Applications

### Research Study Design
- Gandhi R.A. and Lee, S.W., “Assurance Case driven Case Study Design in Requirements Engineering Research,” In: 15th International Working Conference on Requirements Engineering: Foundations for Software Quality, REFSQ 2009.

### Interview Protocol Design
- Gandhi R.A., Germonprez M., Link G., "Open Data Standards for Open Source Software Risk Management Routine: An Examination of SPDX", ACM GROUP 2018 https://github.com/SPDX-CaseStudy/files/blob/master/AssuranceCase.png

???
I have also used assurance cases to design research studies and organize evidence collected from research studies.
---
class: middle
# Other Applications

### Medical Device Software
- [Safety Assurance Cases Can Improve Your FDA Submissions](https://www.meddeviceonline.com/doc/how-safety-assurance-cases-can-improve-your-fda-submissions-0001)

???
Assurance cases were first made popular in the safety industry and find a prominent place in safety certifications of medical devices by the FDA.

---
class: center, middle
# .large[Got Assurance?]
.bottom-left[
![meme](images/meme.jpeg)
]

???

In summary, assurance cases provide a much needed structure and logic for activities in the Trustworthiness context of the Systems Security Engineering framework.

> Good Examples of Claims  
> Canvas has no exploitable XSS weaknesses.  
> All Canvas XSS weaknesses have been sufficiently mitigated.  
> Canvas attack surface is minimized.  

More recent analysis of Security Assuance Cases
Mohamad, M., Steghöfer, JP. & Scandariato, R. Security assurance cases—state of the art of an emerging approach. Empir Software Eng 26, 70 (2021). https://doi.org/10.1007/s10664-021-09971-7

