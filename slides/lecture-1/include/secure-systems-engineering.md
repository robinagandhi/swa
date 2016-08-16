class: center, middle
template: inverse
# .large[Systems Security Engineering]
???
This slide deck is largely based on the content from Chapter 2 of NIST 800-160 Public draft 2
---

# Agenda
## Terminology
## Systems Security Engineering Framework
## Topic 3
---

class: center, middle
![Dilbert](http://assets.amuniversal.com/b7797c402f4901348be4005056a9545d)
---

class: center, middle
#Starting with the Right Abstractions
.top-right[
    ![Abstractions](http://www.espen.com/graphics/math-answer-findx.gif)
]
---

# Terminology

## System
Combination of interacting .red[elements] organized to achieve one or more stated purposes
--

## System Element
Recursively defined as a .red[system]  
Member of a set of elements that constitute a system  

_Examples: hardware; .red[software]; firmware; data; facilities; materials; humans; processes; and procedures_
--

## System of Interest
System that is the focus of the .red[engineering] effort
???
# System and System Element
* The recursive definition of a system element allows us to support the notion of a system of systems.  
* The term **system** may apply to a collection of elements or a single element
* One observer’s system may be another observer’s system element.  

# System of Interest
* The term system-of-interest is used to define the set of system elements, system element interconnections, and the environment that it operates in.
---

# Terminology

## Enabling System
System that supports a .red[system‐of‐interest] during its life cycle stages but does not necessarily contribute directly to its function during operation   

_Examples: computer‐aided design tool, prototype, test harness, trainer, code compilers, and code assemblers_
--

## Other Systems
System that interacts with the .red[system‐of‐interest] in its operational environment  

_Examples: a global positioning system space vehicle being an “other system” interacting with a GPS receiver as the “system‐of‐interest.”_
---
class: center, middle
![NIST SP 800-160 Public Draft 2](images/view.png)  
Systems Engineering View
???
Things to note:
* The system of interest: set of system elements, system element interconnections, and the environment that it operates in
* All _other systems_ that interact with the system of interest are included in the operational environment
* Some enabling systems may exist outside the environment of operation, for example, the compiler used at the developer site.
---


---

# Types of Vulnerabilities

The Task Force also described several tiers of vulnerabilities within organizations including
known vulnerabilities, unknown vulnerabilities, and adversary-created vulnerabilities. The
important and sobering message conveyed by the Defense Science Board is that the top two tiers
of vulnerabilities (i.e., the unknown vulnerabilities and adversary-created vulnerabilities) are, for
the most part, totally invisible to most organizations. These vulnerabilities can be effectively
addressed by sound systems security engineering techniques, methodologies, processes, and
practices—in essence, providing the necessary trustworthiness to withstand and survive well-resourced,
sophisticated cyber-attacks on the systems supporting critical missions and business
operations.

---










class: center, middle
![NIST SP 800-160 Public Draft 2](images/framework.png)  
Systems Security Engineering Framework
