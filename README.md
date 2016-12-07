# Software Assurance

This repository includes things related to the Software Assurance course at UNO

## Table of Contents  
[Syllabus](#syllabus)  
[Supplies](#supplies)  
[Class Topics](#class-topics)  
[Semester Project](#team-semester-project)  
[Project Hall of Fame](#project-hall-of-fame)  
[Project Inspiration](#project-inspiration)  
[Projects to Avoid](#projects-to-avoid)  
[Project Deadlines](#project-deadlines)  
[Final Exam](#final-exam)  
[License](#license)  

## Syllabus
[Course syllabus on Github.io](https://robinagandhi.github.io/swa/)

## Supplies
* Bringing a laptop to class is highly encouraged for in-class activities.
* A notebook and pencil.
* [Online Lab Computer](http://view.unomaha.edu)

## Class Topics
1. Introduction to [Software Assurance](https://robinagandhi.github.io/swa/slides/lecture-0/software-assurance.html)
1. Collaborating when working on Software
  * Get familiar with version control
    * [Github Primer](./module-1/github-primer.md)
1. [Corporate Engagement with Open Source Software (OSS) and Licensing](https://robinagandhi.github.io/swa/slides/matt-g-guest-lecture/corporate-participation-with-oss-communities.pdf)
  * Guest Talk by [Matt Germonprez](http://www.unomaha.edu/college-of-information-science-and-technology/about/faculty-staff/matt-germonprez.php)
1. Engineering For Assurance
  * [Systems Security Engineering](https://robinagandhi.github.io/swa/slides/lecture-1/systems-security-engineering.html). Based on Chapter 2 from [NIST SP 800-160 Public Draft 2](http://csrc.nist.gov/publications/drafts/800-160/sp800_160_second-draft.pdf).
1. [Assurance Cases ](https://robinagandhi.github.io/swa/slides/lecture-2/assurance-case.html) for Software Security Engineering
  * [ISO Standard](https://unomaha.on.worldcat.org/oclc/772089071?databaseList=638) for Assurance cases.
  * Diagramming in [Lucidchart](https://www.lucidchart.com/). You can sign up for a [free student account.](https://www.lucidchart.com/users/education/registerLevel?tP=1&t4=A&t10=A) You may start a new assurance case using this [template](https://www.lucidchart.com/invitations/accept/e8d3aac4-e62b-4fa0-9fd1-c2cf6a6d318d).
  * Formal diagramming in [Adelard ASCE](http://www.adelard.com/asce/v4.2/download.html)  
  * [Assurance Case Exercise (Team Deliverable)](https://robinagandhi.github.io/swa/slides/lecture-2/assurance-case-exercise.html)
1. [Requirements for Software Security Engineering](https://robinagandhi.github.io/swa/slides/lecture-3/requirements-for-software-se.html)
  * Problem Frames (Abuse and Security Frames)  
  * The Meaning of Requirements for Software Security Engineering  
  * [Misuse cases](http://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=1159030)  
  * Using Misuse cases to Elaborate Assurance Cases: [Misuse Case Exercise (Team Deliverable)](https://robinagandhi.github.io/swa/slides/lecture-3/requirements-for-software-se.html#68)
  * Translating compliance constraints to requirements ([NIST 800-160 public draft 2, Appendix J](http://csrc.nist.gov/publications/drafts/800-160/sp800_160_second-draft.pdf))
1. Maturity Models for Software Security Engineering
  * Build Security In Maturity Model ([BSIMM](https://www.bsimm.com))
1. Midterm Exam on Wednesday, October 19. [Performance](./img/misc/fall2016midtermperformance.pdf)
1. Design for Software Security Engineering
  * Design Principles for Security (NIST 800-160 Appendix F)
  * [Threat Modeling](https://robinagandhi.github.io/swa/slides/lecture-4/design-for-software-se.html). Data flow based threat identification and mitigation techniques.  
  Diagramming using [Microsoft Threat Modeling Tool.](https://www.microsoft.com/en-us/download/details.aspx?id=49168)
  * Design patterns (See Blackboard for Slides):
    1. Expressing design principles as patterns
    1. Architectural patterns for security
    1. Object-oriented code patterns for security
1. [Coding for Software Security Engineering](https://robinagandhi.github.io/swa/slides/lecture-5/code-for-software-se.html)
  * Knowledge base: [Common Weakness Enumeration](http://cwe.mitre.org/), [CAPEC](https://capec.mitre.org/), [CERT Secure Coding Guidelines](https://www.securecoding.cert.org/confluence/display/seccode/SEI+CERT+Coding+Standards)
  * [DHS SWAMP](https://www.mir-swamp.org/)
  * Code review tools and techniques
1. Testing for Software Security Engineering
  * Guest Talk by [Matt Hale](http://faculty.ist.unomaha.edu/mhale/) Testing processes, Test Driven Development, and Faculty Research topic overview [(slides)](./guest-lectures/test-driven-development-and-research-guestlecture.pdf)
  * QUnit Slides from [Ben Alman](https://github.com/cowboy) available [here](http://benalman.com/talks/unit-testing-qunit.html) 
1. Other topics
  * Guest talks from other faculty or practitioners.

\* These topics will get refined and updated as the semester progresses

## Teams Project for Fall 2016
[Team projects](https://robinagandhi.github.io/swa/slides/teams-2016/teams.html)

## Team Semester Project
This class strives to encourage learning by doing and making a real difference to the practice of building software. To turn this spirit into reality, a semester long project will require you to work with a open source software project. A group of three students will select a unique open source software project and contribute security related improvements.

The project will have the following deliverables:

1. **Project Proposal**: 2-3 page report that describes the following:
  * Open source project description (What is it?, Contributors, Activity, Use, Popularity, Languages used, platform, documentation sources, etc.)
  * Functional security requirements for the software
  * [License, procedures for making contributions, and contributor agreements](https://guides.github.com/activities/contributing-to-open-source/)
  * Security related history (E.g. known vulnerabilities)
  * Your motivation for selecting this project

1. **Requirements and Design for Secure Software**: 2-3 page report that describes the following:
  * Links to your version control repository that shows your internal collaboration and project related activity.
  * Security requirements for the project captured using mis-use case diagrams. Include links to Lucidchart diagrams with brief descriptions in the document.
  * Threat models for critical dataflows through the software. Include diagrams and a link to download these files.
  * Links to suggested updates for project documentation for security related configuration and installation.

1. **Code analysis and testing for Secure Software**: 2-3 page report that describes the following:
  * Code review strategy
  * Automated code scanning results summary. Include links to full reports.
  * Summary of key findings
  * Links to pull requests to the original project and any follow-up interactions.

1. **Class Presentation**: 10-minute class presentation that highlights the following:
  * Project description
  * Gaps in security requirements and design of the original project
  * Findings from code review and automated software scanning
  * Contributions to the original project (documentation, design changes, code changes, communications)


## Project Hall of Fame
* [List of successful contributions to OSS projects from student teams](https://github.com/robinagandhi/swa/blob/master/HALLOFFAME.md)  

## Project Inspiration
* [Github guide for contributing to Open Source Projects](https://guides.github.com/activities/contributing-to-open-source/)
* [Openhub](https://www.openhub.net) by Black Duck Software
* Github [search](https://github.com/search) and [trends](https://github.com/trending).
* DHS SWAMP listing for [public software packages](https://www.mir-swamp.org/#packages/public).
* [Code Triage](https://www.codetriage.com)
* Some blogs to consider. [1](http://blog.teamtreehouse.com/getting-involved-open-source-projects), [2](https://help.github.com/articles/where-can-i-find-open-source-projects-to-work-on/), [3](http://www.firsttimersonly.com)

## Projects to Avoid
* In-active projects (no recent contributions, no activity on forums, lack of wiki or documentation)
* Old vulnerable project versions
* Android Apps
* Projects with languages that do not have a lot of tool support
* Project with little or no functional security requirements. As surprising as it may sound, not all software have security needs!
* Projects not accepting contributions

## Project Deadlines

1. Project Proposal &ndash; **September 14th, 2016**
1. Requirements and Design for Secure Software &ndash; ~~October 19th, 2016~~ **November 9th, 2016**
1. Code analysis and testing for Secure Software &ndash; **November 30th, 2016**
1. Class presentations &ndash; **December 7th, 2016**

\* All dates are subject to change as the course progresses

## Final Exam

* In-class exam on **December 14th, 5:30pm**

## How to Clone and Navigate this Repo

Use these instructions if you do not intend to contribute any upstream changes. In a CLI navigate to the directory where you want to clone the repository. Then run the following clone command:

```bash
# Clone the Repository to the current directory
# Notice the `.` at the end of the command
git clone https://www.github.com/robinagandhi/swa .
```
Now examine the directory structure. It should have the same directory structure as this repository on Github.com.

The repository has two branches that serve different purposes.
* `master`: This branch includes files for course planning, project description and any self-paced tutorials.
* `gh-pages`: This branch includes website files that are hosted on Github.io. The website hosts the course syllabus and markdown based slides for all the class lectures.

To switch between the two branches use the following git commands:
```bash
# Switch to the `gh-pages` branch
git checkout gh-pages

# Switch to the `master` branch
git checkout master
```

To keep your local repository updated with upstream changes use the git pull command.
```bash
# update the repository
git pull
```

## How to Contribute?

First fork this repo on Github.com while logged into your account. Then clone the forked repo on your computer.

Now you will need two capabilities: 1) Keep your fork (downstream) synced with this repo (upstream) and 2) Make upstream pull requests for changes made in the forked repo. Both these can be accomplished by following these steps:  

1. [Fork a Repo](https://help.github.com/articles/fork-a-repo/)  
1. [Syncing a Fork](https://help.github.com/articles/syncing-a-fork/)  
1. Push changes to your remote fork: `git push origin master`  
1. [Create a pull request from a fork](https://help.github.com/articles/creating-a-pull-request-from-a-fork/)  

More advanced collaboration features can be found here: https://help.github.com/categories/collaborating-on-projects-using-issues-and-pull-requests/

Don't have contributor agreements ready just yet. TBD.   
In general, if you are making it a pull request you agree to abide by this CLA: https://cla.github.com


## License  
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

[tl;drLegal summary](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)
