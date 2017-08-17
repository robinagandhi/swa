---
layout: default
title: 8420 Modules
description: CYBR 8420 Software Assurance Modules
---

# Class Topics*

1. Introduction to Software Assurance
2. Collaborating when working on Software
  - Get familiar with version control. [Github Primer](./module-1/github-primer.md)
3. Corporate Engagement with Open Source Software (OSS) and Licensing
  * Guest Talk by [Matt Germonprez](http://www.unomaha.edu/college-of-information-science-and-technology/about/faculty-staff/matt-germonprez.php)
4. Engineering For Assurance
  * Systems Security Engineering. Based on Chapter 2 from [NIST SP 800-160 Public Draft 2](http://csrc.nist.gov/publications/drafts/800-160/sp800_160_second-draft.pdf).
5. Assurance Cases for Software Security Engineering
  * [ISO Standard](https://unomaha.on.worldcat.org/oclc/772089071?databaseList=638) for Assurance cases.
  * Diagramming in [Lucidchart](https://www.lucidchart.com/). You can sign up for a [free student account.](https://www.lucidchart.com/users/education/registerLevel?tP=1&t4=A&t10=A) You may start a new assurance case using this [template](https://www.lucidchart.com/invitations/accept/e8d3aac4-e62b-4fa0-9fd1-c2cf6a6d318d).
  * Formal diagramming in [Adelard ASCE](http://www.adelard.com/asce/v4.2/download.html)  
  * Assurance Case Exercise (Team Deliverable)
6. Requirements for Software Security Engineering
  * Problem Frames (Abuse and Security Frames)  
  * The Meaning of Requirements for Software Security Engineering  
  * [Misuse cases](http://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=1159030)  
  * Using Misuse cases to Elaborate Assurance Cases: Misuse Case Exercise (Team Deliverable)
  * [Translating compliance constraints to requirements]([NIST 800-160 public draft 2, Appendix-J](http://csrc.nist.gov/publications/drafts/800-160/sp800_160_second-draft.pdf))
7. Maturity Models for Software Security Engineering
  * Build Security In Maturity Model ([BSIMM](https://www.bsimm.com))
8. Midterm Exam. Sometime in October.
9. Design for Software Security Engineering
  * Design Principles for Security (NIST 800-160 Appendix F)
  * Threat Modeling. Data flow based threat identification and mitigation techniques.  
  * Diagramming using [Microsoft Threat Modeling Tool.](https://www.microsoft.com/en-us/download/details.aspx?id=49168)
  * Design patterns (See Blackboard for Slides):
    1. Expressing design principles as patterns
    2. Architectural patterns for security
    3. Object-oriented code patterns for security
10. Coding for Software Security Engineering
  * Knowledge base: [Common Weakness Enumeration](http://cwe.mitre.org/), [CAPEC](https://capec.mitre.org/), [CERT Secure Coding Guidelines](https://www.securecoding.cert.org/confluence/display/seccode/SEI+CERT+Coding+Standards)
  * [DHS SWAMP](https://www.mir-swamp.org/)
  * Code review tools and techniques
11. Testing for Software Security Engineering
  * Guest Talk by [Matt Hale](http://faculty.ist.unomaha.edu/mhale/)  
12. Other topics
  * Guest talks from other faculty or practitioners.

\* These topics will get refined and updated as the semester progresses

# Supplies
* Bringing a laptop to class is highly encouraged for in-class activities.
* A notebook and pencil.
* [Online Lab Computer](http://view.unomaha.edu)

# Final Exam

* In-class exam on **Wednesday, December 13, 2017, 5:30pm**

# How to Clone and Navigate this Repo

Use these instructions if you do not intend to contribute any upstream changes. In a CLI navigate to the directory where you want to clone the repository. Then run the following clone command:

```bash
# Make a empty directory and switch to it
mkdir swa
cd swa
# Clone the Repository to the current directory
# Notice the `.` at the end of the command
git clone https://www.github.com/robinagandhi/swa .
```
Now examine the ```swa``` directory structure. It should have the same directory structure as this repository on Github.com.

The master branch includes the following content:
* `master`: This branch includes files for course planning, project description, course syllabus, markdown based slides and any self-paced tutorials for class lectures.

To keep your local repository updated with upstream changes use the git pull command.
```bash
# update the repository
git pull
```

# How to Contribute?

First fork this repo on Github.com while logged into your account. Then clone the forked repo on your computer.

Now you will need two capabilities: 1) Keep your fork (downstream) synced with this repo (upstream) and 2) Make upstream pull requests for changes made in the forked repo. Both these can be accomplished by following these steps:  

1. [Fork a Repo](https://help.github.com/articles/fork-a-repo/)  
1. [Syncing a Fork](https://help.github.com/articles/syncing-a-fork/)  
1. Push changes to your remote fork: `git push origin master`  
1. [Create a pull request from a fork](https://help.github.com/articles/creating-a-pull-request-from-a-fork/)  

More advanced collaboration features can be found here: https://help.github.com/categories/collaborating-on-projects-using-issues-and-pull-requests/

Don't have contributor agreements ready just yet. TBD.   
In general, if you are making it a pull request you agree to abide by this CLA: https://cla.github.com


# License  
Software Assurance.  
Copyright (C) 2016  Dr. Robin A. Gandhi

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

## What does GPLv3 mean?

[tl;dr Legal summary](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)
