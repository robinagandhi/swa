# Software Assurance

This repository includes things related to the Software Assurance course at UNO

### Table of Contents    
[Supplies](#supplies)  
[Class Topics](#class-topics)  
[Semester Project](#team-semester-project)  
[Project Inspiration](#project-inspiration)  
[Projects to Avoid](#projects-to-avoid)  
[License](#license)  

## Supplies
* Bringing a laptop to class is highly encouraged for in-class activities.
* A notebook and pencil.
* [Online Lab Computer](http://view.unomaha.edu)

## Class Topics
1. Introduction to [Software Assurance](https://robinagandhi.github.io/swa/slides/lecture-0/software-assurance.html)
1. Collaborating when working on Software
  * Get familiar with version control
    * [Github Primer](./module-1/github-primer.md)
1. Open Source Software (OSS) Licensing
  * Guest Talk by [Matt Germonprez](http://www.unomaha.edu/college-of-information-science-and-technology/about/faculty-staff/matt-germonprez.php)
1. Engineering For Assurance
  * [Systems Security Engineering](https://robinagandhi.github.io/swa/slides/lecture-1/systems-security-engineering.html). Based on Chapter 2 from [NIST SP 800-160 Public Draft 2](http://csrc.nist.gov/publications/drafts/800-160/sp800_160_second-draft.pdf).
  * Industry practices. [BSIMM](https://www.bsimm.com/framework/)
1. Constructing Assurance Cases  
  * [ISO Standard](https://unomaha.on.worldcat.org/oclc/772089071?databaseList=638) for Assurance cases.
  * Diagramming in [Lucidchart](https://www.lucidchart.com/). You can sign up for a [free student account.](https://www.lucidchart.com/users/education/registerLevel?tP=1&t4=A&t10=A) You may start a new assurance case using this [template](https://www.lucidchart.com/invitations/accept/e8d3aac4-e62b-4fa0-9fd1-c2cf6a6d318d).
  * Formal diagramming in [Adelard ASCE](http://www.adelard.com/asce/v4.2/download.html)  
1. Requirements for Secure Software
  * Theory of secure requirements. Problem Frames.
  * Lucidchart based Mis-use case diagrams. Use this [template](https://www.lucidchart.com/invitations/accept/59a6e092-49bd-4af3-80be-a1f0862923e5) to start a mis-use case.
1. Design for Secure Software
  * Threat Modeling. Data flow based threat identification and mitigation techniques. Diagramming using [Microsoft Threat Modeling Tool.](https://www.microsoft.com/en-us/download/details.aspx?id=49168)
  * Design patterns:
    1. Expressing design principles as patterns
    1. Architectural patterns for security
    1. Object-oriented code patterns for security
1. Coding for Secure Software
  * Knowledge base: [Common Weakness Enumeration](http://cwe.mitre.org/), [CERT Secure Coding Guidelines](https://www.securecoding.cert.org/confluence/display/seccode/SEI+CERT+Coding+Standards)
  * [DHS SWAMP](https://www.mir-swamp.org/)
  * Code review tools and techniques
1. Testing for Secure Software
  * Knowledge base: [CAPEC](https://capec.mitre.org/)
  * Testing strategies
1. Other topics
  * Guest talks from other faculty or practitioners.

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
1. Requirements and Design for Secure Software &ndash; **October 19th, 2016**
1. Code analysis and testing for Secure Software &ndash; **November 30th, 2016**
1. Class presentations &ndash; **December 7th, 2016**

All dates are subject to change as the course progresses

## Final Exam

* In-class exam on **December 14th, 6:30pm**

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
