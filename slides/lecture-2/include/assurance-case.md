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
